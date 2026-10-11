---
tags: [pesquisa, arte, rig, 2026]
data: 2026-10-10
fontes: 9
status: rascunho
---

# 00 — Rig automático

Quem gera o mesh e já devolve esqueleto, e quanto custa o plano de entrada. Consulta 26 set. Brave e Perplexity não estavam nesta máquina; a leitura foi das páginas oficiais e de dois textos de terceiros.

> [!info] A conta da Meshy que este escritório já usa (Pro, API) já faz rig. No site o rig e a animação saem a 0 crédito. Pela API são 5 créditos o rig e 3 por animação. Não precisa de outro plano só para ter osso.

## Planos (páginas oficiais, 26 set)

| Ferramenta | Plano de entrada pago | Esqueleto | Serve bicho estranho |
|---|---|---|---|
| Meshy | Pro US$ 20/mês, 1000 créditos. API só no pago. | Sim. Site: 0 crédito. API: 5 o rig, 3 a animação. Biblioteca 600+ no Pro. | Humanoide e quadrúpede. Fora disso o rig falha. |
| Tripo | Pro na página de preço: US$ 20/mês no anual (US$ 240/ano), 3000 créditos, uso comercial. Free: 200 créditos, modelo público, sem comercial. | Sim. API: checagem grátis, rig 25 créditos (US$ 0,25), cada animação 10. Modelo de rig `v2.5-20260210` lista quadrúpede, ave, serpente, aquático. | Documentado para ave. Planta não está na lista. |
| Mixamo | Grátis, com conta Adobe. | Sim, só humanoide. | Não. Planta e pássaro caem fora. |
| AccuRIG | App grátis, limite de uma malha. | Sim, só humanoide. | Não. |

> [!warning] Um texto da própria Tripo fala em Pro a US$ 13,93/mês. A página de preço aberta em 26 set mostra US$ 20/mês no anual. Vale o que estiver na página no dia de assinar. Não assinar sem o Halan.

> [!warning] Rodin (Hyper3D) aparece em páginas da Meshy e da Tripo como mesh sem esqueleto, Creator a US$ 30/mês. A página de preço da Hyper3D não abriu daqui. Não tratar como fato da fonte deles.

## Play, 2 out

> [!info] Raphael rigou na Tripo e o movimento entrou no Unity. Carnivora, Furia, Musgo, Nuvem, Escama, Farpa e o Bicho 07 (nome na ficha: Limo).

- Remesh da Meshy estragou o UV da Escama. O FBX com a textura original ficou.
- Rig de quadrúpede no Farpa saiu com osso solto embaixo da barriga. O mesmo corpo no modo humanoide ficou usável. Os outros quadrúpedes seguiram esse modo.
- No plano grátis a Tripo rigou, e o export do esqueleto pediu plano pago. O que entrou no jogo foi o FBX que o Raphael baixou depois.
- O clipe não veio da Meshy. `BoneMotion` respira, anda e investe, e deita o ciclo do esqueleto humanoide no chão. O eixo de cada osso é escolhido no código: a perna da Escama ia para o lado.

## Malha densa, 10 out

> [!info] A retopologia oficial da Tripo mira 500–20.000 triângulos (quad: 500–10.000). O prerigcheck diz que não há limite estrito. A Nira do esqueleto (`niraanimates.com`) não publica teto de triângulos.

- Raphael, 10 out: malha da Meshy na Tripo volta com qualidade alta e pede para recriar a malha. Isso é a retopologia, não um defeito do bicho.
- Segundo a Scenario (uma fonte, citando a engenharia da Tripo, guia atualizado perto de 10 out): não há teto rígido; acima de ~300.000 polígonos o rig tende a falhar com "Model too complex". O exemplo deles desce de 1.482.050 triângulos para ~12.000 faces.
- `nira.app` é outro produto (visor de scan, fala em centenas de milhões de triângulos). Não é a Nira do esqueleto. Não usar esse número.
- Alvo deste jogo, para a luta 3v3: **10.000 triângulos** por bicho. Faixa 8.000–15.000. 15.000 é o teto do smart topology da Meshy (T2). 20.000 é o teto da retopo da Tripo, só se a silhueta quebrar. Nasce na geração. Remesh depois estragou o UV da Escama.

## O que isso muda aqui

Carnivora e Furia não são humanoide. Mixamo e AccuRIG não resolvem. O caminho barato é rigar na Meshy que já está paga, e só olhar a Tripo se o rig da Meshy quebrar nesses dois corpos. Um teste de terceiro (maio 2026) preferiu o osso da Tripo em bicho não humano; outro levantamento de volume de jogo achou a Meshy um pouco mais pronta para entrar no motor. Não é vitória clara.

## Notas relacionadas

- [[00 - Meshy]] · [[00 - Higgsfield]] · [[02 - Produção Loop 1]]

## Fontes

- https://www.meshy.ai/en/pricing
- https://docs.meshy.ai/en/api/pricing
- https://docs.meshy.ai/en/webapp/pricing
- https://www.tripo3d.ai/pricing
- https://developers.tripo3d.ai/en/pricing
- https://developers.tripo3d.ai/en/docs/animations-rig
- https://www.strayspark.studio/blog/ai-auto-rigging-showdown-2026-tripo-meshy-cascadeur-mixamo
- https://docs.tripo3d.ai/animation/pre-rig-check-v2-0-20250506.html
- https://developers.tripo3d.ai/en/docs/mesh-decimate
- https://niraanimates.com/features/ai-auto-rigging
- https://help.scenario.com/articles/4692888910-tripo-family-the-complete-guide
