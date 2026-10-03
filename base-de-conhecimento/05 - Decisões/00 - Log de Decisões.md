---
tags: [decisões]
data: 2026-10-02
status: revisado
---

# 00 — Decisões vigentes

O que vale **agora**. Sem histórico de norte antigo.

## Escritório

- Pasta: `e:\dev\game` (nome de trabalho, não é marca).
- Casa: **Cursor**, workspace **separado** do Pokeland.
- Skills em `.claude/`.
- GitHub: `git`, nunca `gh`. SSH só via `github-personal` (não mexer no perfil PortX). Conta `halannl`. Repo do escritório: [`halannl/game-pkld-vibes`](https://github.com/halannl/game-pkld-vibes). Org: [`docs`](https://github.com/game-pkld/docs) (cérebro) + [`unity`](https://github.com/game-pkld/unity) (código). Escritório Cursor do Raphael: zip, versiona no git pessoal. O `client/` em `e:\dev\game` não é o remote oficial.
- Linear: workspace [`pokeland-vibes`](https://linear.app/pokeland-vibes), team Pokeland-vibes. MCP `linear-game`, chave `AI_LINEAR_GAME`. Sem Firecrawl/Supabase/Vercel do fangame. Cada push do jogo no GitHub ganha um issue Done no Linear, no mesmo turno (Raphael, 3 out).
- Pesquisa: `AI_BRAVE_API_KEY`, `AI_PERPLEXITY_API_KEY` (skill pesquisa-aprofundada). Nunca valores no git.
- Este vault é o **jogo original**. Fangame (site/canal) = `e:\dev\pokeland`.

## Produto

- Oficial, design próprio. Marca Pokeland (site/canal) **não** lança este jogo.
- Destino: gacha + coleção + luta. Essência Pokeland + [[00 - Summoners War]] + [[00 - Idle Heroes]]. Coluna: **clima** como tema (não buff de sala) — [[06 - Clima como coluna]]. Hub destino: **ilha** com coleção visível. Primeira luta destino: **3v3**, turno por speed, fileira. Título Storm: estacionado. Sem go-live. Recortes: [[04 - Recortes de inspiração]]. Kickoff: [[07 - Kickoff 19 set]].
- Frase de player (19 set): luto e competo (ganhar de quem tem mais poder); coleciono e o comum existe sem pagar; vejo o arsenal no mundo.
- Comum F2P existe; evoluir pede cópia. Whale compra **tempo**, não dump infinito. Teto de poder sobe por update.
- Daily obrigatório das recompensas: **~1h**. Quem quiser ficar o dia tem o que fazer, com ganho pequeno.
- **Loop 1** (já existe): apresentação → personagem → nome → andar. **Próximo Play:** placeholder 3v3 que se bate (quadrado na tela). Sem ilha, sem gacha, sem 6 fichas no primeiro commit.
- Time (19 set): Halan visão + suporte + paga ferramentas; **Raphael** implementa no **Cursor** (R$ 250/semana de partida); **Luan** feeling/história/ficha, **não programa**; Douglas neste escritório. Discordância: a sala pediu **consenso** (Halan recusou martelo “eu pago”). GPT-6 Astra não troca a casa ([[00 - GPT-6 Astra vs Cursor]]).
- “Nunca” absoluto e IP/mod: **não fechados** na kickoff. Não tratar como spec.
- Engine: **Unity 6.3 LTS** (`6000.3.23f1`, 8 set). Projeto `client/` (URP). Personal enquanto Total Finances ≤ US$ 200k / 12 meses. 6.6 não é o editor deste projeto.
- Bootstrap: Halan custeia assinaturas e Raphael. Código: Raphael + Halan suporte + Douglas. **Sem investidor.** Independente.
- Arte do slice: 3D. Meshy Free ok pra placeholder interno (CC BY 4.0). Higgsfield = conceito/imagem/vídeo e GLB de previz — **não** é o motor do jogo.

## Movimento e time (Raphael, 2 out)

- Esqueleto: Tripo, modo humanoide, inclusive nos quadrúpedes. Movimento no jogo: `BoneMotion` (respirar parado, andar na trilha, investida de ataque).
- Eco (Bicho 06) usa o FBX da planta (`a26665b4`): clipe `walk` na trilha, chute `front_kick_02` em todo ataque. A espera é balanço no código. Estatura 1,544, rosto para a frente da luta. Pingo (Bicho 09) é o lagarto de lava (`8e779854`), de quatro, estatura 1,5. Escama soca para a frente em todo ataque. Musgo estatura 1,305. Galho voltou ao mesh antigo. Na vez de atacar, o corpo não cresce.
- Bicho 07 continua com o nome Limo. O mesh é o FBX novo da Tripo. Retrato com fundo transparente e arco verde.
- O time de três grava em `PlayerPrefs` (`team.slots`). A luta 3v3 abre com essa escolha.
- Aventura: sombra oval no chão e zoom da roda do mouse, o mesmo gesto da arena.

## HUD da luta (Halan, 1 out)

A distribuição da luta 3v3 segue o print que o Halan mandou. O desenho é o kit místico, não o print. Velocidade e auto ficam à esquerda. No topo, nome e Power de cada lado. A fila de quem joga fica à direita. A saída fica no canto. As três skills ficam embaixo, no centro; a ultimate acende quando pode ser usada. A vida do bicho fica no pé, com a carga da ultimate numa barra fina embaixo. Ajuda não entra. Suporte, insígnia, campo, fruta e ressonância esperam a mecânica. Escudo não aparece enquanto a luta não tiver esse número. Velocidade continua 1x, 2x e 4x. Nível de conta não entra.

## Tipos, cristal e língua (Halan, 30 set)

- Dezenove tipos. Chave em inglês, rótulo na língua da tela. A grade mora num lugar só. Sem elemento, fator 1. Dois elementos, o produto, sem teto.
- Cristal: cinco marcas, não age, não morre. Velocidade copiada de um dos três, pela seed. Ouro pelos marcos a partir de 10.000. O dia é o relógio do servidor. Semana começa na segunda. O cliente não manda o dia.
- Línguas: `pt-BR`, `en-US`, `es-ES`. Frase por chave em inglês. Fora das três, `pt-BR`. Tradução faltando cai em `en-US`. Schema em inglês (`locale`).

## Notas relacionadas

- [[00 - Overview]] · [[03 - Plano de execução]] · [[04 - Recortes de inspiração]] · [[06 - Clima como coluna]] · [[07 - Kickoff 19 set]]
