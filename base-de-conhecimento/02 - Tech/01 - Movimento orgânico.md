---
tags: [tech, movimento, animação, pesquisa]
data: 2026-10-21
status: rascunho
---

# 01 — Movimento orgânico

Por que o `BoneMotion` ficava duro, e as três técnicas que usamos para dar vida ao esqueleto sem animador: **mola**, **pose-chave** e **ruído**. É a nota que as tarefas [POK-157](https://linear.app/pokeland-vibes/issue/POK-157), [POK-165](https://linear.app/pokeland-vibes/issue/POK-165) e [POK-166](https://linear.app/pokeland-vibes/issue/POK-166) citam. Decisões em [[00 - Log de Decisões]] ("Movimento orgânico dos bichos", 14 out). Escrita em 21 out a partir de fontes públicas e do código em `S:\unity\Assets\Game\Arena3v3\BoneMotion*.cs`.

## O problema

> [!info] Diagnóstico (Raphael e José, 14 out; confirmado no código)
> O `BoneMotion` antigo refazia a pose do zero a cada quadro, com senos, **sem memória entre quadros**. Nada atrasava, nada assentava, nada passava do ponto. Por isso o movimento lia como duro: um esqueleto que obedece na hora e para na hora. O golpe genérico (`Attack()`, `Swipe`, `Slam`, `Lunge`) ainda é assim.

## A referência: Rosen, GDC 2014

David Rosen (Wolfire, *Overgrowth*), "Animation Bootcamp: An Indie Approach to Procedural Animation", GDC 2014, ~30 min. Vídeo grátis no [GDC Vault](http://www.gdcvault.com/play/1020583/Animation-Bootcamp-An-Indie-Approach) e no [YouTube](https://www.youtube.com/watch?v=LNidsMesxSE). Em 2022 a Wolfire abriu o código do *Overgrowth*; a animação fica em `Source/Objects/riggedobject`.

> [!info] A ideia central (≥2 fontes)
> **Poucas poses-chave e o código interpolando.** A locomoção base do *Overgrowth* usa **13 poses** no total. Andar e correr têm **4 poses cada** (passar e alcançar, de cada lado); agachar é 1 pose; o idle é 1 pose. A interpolação entre poses **não é linear**: é "tipo mola" (spring damper). O resto fica para a física e o ragdoll. Fontes: [techarthub](https://techarthub.com/first-do-no-harm-to-the-gameplay/), [Unity Discussions](https://discussions.unity.com/t/an-indie-approach-to-procedural-animation-gdc-video-talk/538228), [projeto da TAMU](https://people.engr.tamu.edu/sueda/courses/CSC474/2016W/demos/ismithgr/index.html), [jMonkeyEngine hub](https://hub.jmonkeyengine.org/t/dynamic-procedural-character-animation-system/29460).

> [!info] Os 10 passos da palestra (techarthub, lista; Little Polygon confirma os passos 2 a 4 e 7)
> 1. Movimento responsivo ("primeiro, não faça mal ao gameplay")
> 2. Pose de idle, girar na direção da velocidade
> 3. Inclinação pela aceleração
> 4. Roda de passada, poses de passar e alcançar
> 5. Várias velocidades (correr e andar)
> 6. Misturar velocidades e poses
> 7. Quique da gravidade (e balanço)
> 8. Mistura por fase
> 9. Pose aditiva de agachar
> 10. Interpolação por mola entre poses aditivas
>
> Daí em diante: pulo, queda e simulação física.

> [!quote] Rosen
> "We really need animation and code to work more closely together, so we can use the code to help offload repetitive tasks from the animators." ([Game Developer](https://www.gamedeveloper.com/design/video-an-indie-approach-to-procedural-animation))

> [!warning] O golpe em quatro tempos (1 fonte: o ticket POK-166, Halan)
> Antecipação (devagar, "vai vir"), golpe (rápido), passar do ponto, volta. O ticket atribui a divisão à palestra do Rosen. Não achei fonte escrita que confirme essa parte da palestra; a divisão em si é a dos princípios clássicos de animação (antecipação, *overshoot*, *follow-through*). Confirmar assistindo ao vídeo.

## As três técnicas, e onde estão no nosso código

### 1. Mola (segunda ordem)

Cada articulação secundária persegue a pose com atraso e assenta. Fórmula do **t3ssel8r** ("Giving Personality to Procedural Animations using Math", [vídeo](https://www.youtube.com/watch?v=KPoeNZZ6H4s)), que é a que `BoneMotion.Organic.cs` implementa.

> [!info] Parâmetros e fórmulas (≥2 fontes: [Hackaday](https://hackaday.com/2022/page/250), [crate `spring_motion`](https://docs.rs/spring_motion/latest/src/spring_motion/lib.rs.html), nosso código)
> Três números por osso, os mesmos da janela **Game → Mola**:
> - **f, frequência**: quão rápido alcança a pose (baixo = preguiçoso, alto = rápido).
> - **ζ, amortecimento**: quanto balança antes de parar. ζ < 1 vibra e morre; ζ ≥ 1 não vibra, só aproxima. Perto de 1 = firme; perto de 0,3 = borracha.
> - **r, resposta**: r > 1 passa do ponto no começo; r = 1 acompanha; r ≈ 0 atrasa; **r < 0 antecipa** (vai um pouco para o lado contrário antes de ir).
>
> Com ω = 2πf: `k1 = ζ / (πf)`, `k2 = 1 / ω²`, `k3 = r·ζ / ω`.
> Por quadro (Euler semi-implícito): `y += dt·v` e depois `v += dt·(x + k3·ẋ − y − k1·v) / k2`, onde `x` é o alvo e `ẋ` a velocidade do alvo.
> Estabilidade com quadro longo: `k2 = max(k2, dt²/2 + dt·k1/2, dt·k1)` (o nosso) ou limitar o `dt` a `√(4k2 + k1²) − k1` (crate).

No nosso `Jiggle`: o alvo é a posição da **próxima articulação** depois da pose procedural; a mola move a ponta e o osso gira para apontar para ela, com um **limite de dobra por osso** (`MaxBend`, 6° a 14°). Se der não-finito ou fugir longe, recomeça da pose.

> [!info] O que aprendemos (Raphael, 14 out; [[00 - Log de Decisões]])
> Amortecimento 0,3 a 0,6 virou "esqueleto de borracha, tecido ao vento". Amortecimento perto de 1 com dobra limitada foi aprovado (Shadowmane e Noct). **Osso que dá o golpe não leva mola**, senão o dano cai fora do golpe. Osso de apoio no chão também não.

Padrão hoje (`BuildOrganic`): pescoço `f 5,5 ζ 0,95 r 1 dobra 8°`; rabo da base à ponta `f 4,5→2,8 ζ 0,9→0,65 r 0,6→0,2 dobra 6°→14°`; membrana de asa `f 5 ζ 0,85 r 0,5 dobra 10°`; bigodes do Aurion `f 2,4 ζ 0,45 r 0,3 dobra 22°`. Ajuste por bicho em `Resources/Mola/<bicho>.asset` ([POK-164](https://linear.app/pokeland-vibes/issue/POK-164), feito); nenhum bicho afinado ainda ([POK-165](https://linear.app/pokeland-vibes/issue/POK-165)).

### 2. Pose-chave

Em vez de seno, o movimento é definido por poucas poses (rotação por osso) e o código interpola com curva. É o método do Rosen e o que faz as skills do Shadowmane, Cinderplate, Hellflame, Vaelith e Frostfang lerem como vivas: poses à mão em C# (`BoneMotion.Shadowmane.cs`, `BoneMotion.Skills.cs`, `BoneMotion.Yuki.cs`), com `Ease`, `Fall` e `Ring` entre elas.

> [!info] Poses como dados ([POK-166](https://linear.app/pokeland-vibes/issue/POK-166), em prova)
> `StrikePoses` (`Resources/Golpe/<bicho>.asset`): três poses (antecipação, golpe, passar do ponto) mais o descanso, tempo e `AnimationCurve` por fase, dano no fim da fase do golpe, janela **Game → Golpe → Ajustar poses no Play**. Grizzleback é a prova. Se o Halan aprovar, o método vai para os outros golpes numa tarefa nova, e aí os oito bichos de golpe genérico (Grizzleback, Lithon, Noct, Tidepaw, Eclipse, Blossom Queen, Aurion, Thunderhawk) ganham movimento sem um arquivo C# cada.

A mola fica **por cima** da pose-chave: a pose manda nos ossos do golpe, a mola carrega pescoço, rabo e pontas.

### 3. Ruído

Nada vivo repete um loop exato. No idle: respiração com ritmo que deriva (`OrganicBreath`, Perlin sobre a fase e a amplitude) e um olhar em volta por ruído suave (`OrganicGlance`). Troca de movimento fundida em 0,22 s (`BlendLength`), em vez de cortar.

> [!warning] Ruído (1 fonte: nosso código e a decisão de 14 out)
> A palestra do Rosen não trata de ruído no idle, pelo que achei por escrito. É acréscimo nosso, aprovado no Shadowmane e no Noct.

## Ordem de trabalho (fila POK-157)

1. Janela de mola no Play (feita, POK-164)
2. Ajuste bicho a bicho, de olho, com vídeo antes/depois (POK-165)
3. Golpe em poses-chave, prova no Grizzleback (POK-166)
4. Pesquisa com teste: Mesh2Motion e referências por família de corpo (POK-167)

## Fontes

- [GDC Vault: Animation Bootcamp: An Indie Approach](http://www.gdcvault.com/play/1020583/Animation-Bootcamp-An-Indie-Approach) · [YouTube](https://www.youtube.com/watch?v=LNidsMesxSE)
- [Wolfire: GDC 2014 Procedural Animation Video](https://www.wolfire.com/blog/2014/05/GDC-2014-Procedural-Animation-Video/)
- [Game Developer: Video: An indie approach to procedural animation](https://www.gamedeveloper.com/design/video-an-indie-approach-to-procedural-animation)
- [techarthub: First, Do No Harm to the Gameplay](https://techarthub.com/first-do-no-harm-to-the-gameplay/) (os 10 passos)
- [Little Polygon: Procedural Animation: Locomotion (Part 1)](https://blog.littlepolygon.com/posts/loco1/)
- [TAMU CSC474: reimplementação do sistema](https://people.engr.tamu.edu/sueda/courses/CSC474/2016W/demos/ismithgr/index.html)
- [Unity Discussions](https://discussions.unity.com/t/an-indie-approach-to-procedural-animation-gdc-video-talk/538228) · [jMonkeyEngine hub](https://hub.jmonkeyengine.org/t/dynamic-procedural-character-animation-system/29460) · [Game Anim](https://www.gameanim.com/2018/03/04/indie-approach-procedural-animation/)
- t3ssel8r: [vídeo](https://www.youtube.com/watch?v=KPoeNZZ6H4s) · [Hackaday](https://hackaday.com/2022/page/250) · [crate `spring_motion`](https://docs.rs/spring_motion)

> [!todo]
> - Assistir ao vídeo do Rosen e confirmar a parte do golpe em quatro tempos (aí os dois `[!warning]` viram `[!info]`).
> - Subir para `revisado` quando o Halan ler.
