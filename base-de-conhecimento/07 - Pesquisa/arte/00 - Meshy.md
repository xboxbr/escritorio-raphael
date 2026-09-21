---
tags: [pesquisa, arte, meshy, 2026]
data: 2026-09-09
fontes: 8
status: rascunho
---

# 00 — Meshy

Gerador 3D (text/imagem → mesh). Loop 1 é **3D**. Placeholder interno: plano Free — **gerar sim; baixar pro Unity, com ressalva**.

> [!info] Fontes 9 set: [preço](https://www.meshy.ai/pricing), [Free plan](https://help.meshy.ai/en/articles/15696428-what-is-included-on-the-free-plan), [planos](https://help.meshy.ai/en/articles/12062933-which-meshy-plan-is-right-for-you), [créditos](https://help.meshy.ai/en/articles/10000507-how-many-credits-does-each-generation-task-cost), [Unity workflow](https://www.meshy.ai/tutorials/3d-model-for-unity-workflow), [game assets](https://docs.meshy.ai/en/webapp/guides/use-cases/game-assets).

## Free (o que vale pra este escritório)

- 100 créditos/mês, reset dia 1 UTC. Não acumula. Sem cartão.
- Geração completa (mesh + textura) ~30 créditos no Meshy 6; Lite mais barato (~10 mesh + 10 textura). 1 modelo teste cabe.
- Output **CC BY 4.0** — interno ok. Ship comercial: creditar Meshy ou ir pro Pro (licença private).
- Auto-rig (Smart-Rig): 0 créditos na tabela da help. Text to motion: 3. Presets de animação no Free: **20**. Pro: 600+.
- Plugin Unity é grátis; **Bridge (send to Unity) pede Pro**.

> [!warning] Download no Free: a tabela de planos marca “Model Downloads ❌”. A help do Free é mais específica: **10 downloads/mês só de Meshy 6 Lite**. Meshy 6 e 7 no Free batem paywall. Confirmar no botão Download da web antes de contar com o FBX no `client/`.

## Como entra no Unity

FBX na pasta `client/Assets/` (arrasta). Personagem: Rig → **Humanoid**. Animação mora no **Animator** (Idle ↔ Walk por velocidade; Wave = trigger). A cápsula do CharacterController fica — o mesh é só pele. Cubo/chão: FBX estático, MeshCollider.

Não usar GLB sem pacote extra; Unity lê FBX nativo.

## Pro

US$ 20/mês (novo assinante: 50% no 1º mês, segundo a help). Download ilimitado, 1000 créditos, Bridge. **Não assinar sem o Halan pedir.**

## Limite

Protótipo/indie. Auto-rig falha fora de humanoide/quadrupede. Não substitui artista de volume.

> [!warning] Não promptar personagem de terceiro. Cara nossa.

## Notas relacionadas

- [[00 - Overview]] · [[02 - Produção Loop 1]] · [[00 - Higgsfield]] · [[00 - Tech - Overview]]
