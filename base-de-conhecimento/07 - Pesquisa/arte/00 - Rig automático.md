---
tags: [pesquisa, arte, rig, 2026]
data: 2026-09-26
fontes: 6
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
