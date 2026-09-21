---
tags: [pesquisa, engine, godot, unity, gacha, 2026]
data: 2026-09-08
fontes: 14
status: rascunho
---

# 00 — Godot vs Unity (Loop 1)

Dossiê para escolher engine deste slice: celular, teste no PC, personagem anda, first-time game, Halan backend 16 anos + IA. Destino gacha/MMO **não** é o critério deste loop.

> [!warning] Brave Search não está neste Windows. Perplexity env está presente mas a API recusou a chave (401). Pesquisa feita com WebSearch + WebFetch.

> [!info] Confirmado por ≥2 fontes independentes ou fonte primária (entrevista / docs oficiais / Android Developers).

## Resumo

- Gacha comercial de escala (Genshin, FGO, Raid, Summoners War Chronicles) quase sempre **Unity** ou **engine própria**. Godot não aparece nesse clube.
- Isso **não** implica Unity no Loop 1. Esses times customizam o engine; o produto é liveops, não “boneco anda”.
- Para first game, 2D/andar, MIT, editor leve: **Godot 4** é o default mais amigável. Unity se o critério for “mesmo stack do mercado gacha desde o dia 1”.
- Decisão de trabalho (8 set): **Unity**. Custo: [[01 - Unity - Licença e custo]].

## O que os gachas usam

| Jogo | Engine | Confiança | Fonte |
|---|---|---|---|
| Summoners War: Sky Arena | Engine **própria** Com2uS | alta | [Korea Herald](https://www.koreaherald.com/article/2582135) (oficial da empresa) |
| Summoners War: Chronicles | **Unity** + Vulkan | alta | [Android Developers / Com2uS](https://developer.android.com/stories/games/com2us-vulkan) |
| Genshin Impact | **Unity** (fork pesado) | alta | [GamesIndustry.biz](https://www.gamesindustry.biz/making-genshin-impact-shine-on-everything-from-mobile-to-ps5) (tech director miHoYo) |
| Arknights: Endfield | **Unity** + pipeline C++ próprio | alta | [Inven / talk da Hypergryph](https://www.invenglobal.com/articles/24006/the-know-how-behind-arknights-endfield-seamlessly-implementing-fields-and-factories-with-unity) |
| Raid: Shadow Legends | **Unity** | média-alta | [MobyGames](https://www.mobygames.com/game/125493/raid-shadow-legends/releases/) (crédito de engine; não é entrevista) |
| Fate/Grand Order | **Unity** | média-alta | Análise de binário [FlyTrap](https://flytrap.dev/app-catalog/com.aniplex.fategrandorder) (2026-07); Wikipedia/IGDB secundários |
| Epic Seven | Engine **própria** Smilegate | alta | [Korea Herald](https://www.koreaherald.com/article/2582135) |
| Idle Heroes | **Cocos2D + Lua** | 1 fonte | [Portfólio de quem trabalhou na DH Games](https://alessianigretti.wixsite.com/main) — não é post oficial |
| AFK Arena | Cocos2d (coverage) | 1 fonte / a confirmar | coverage; **não** promover a fato |
| Gacha mobile em Godot | Não encontrei título notável | — | ausência de evidência pública |

Padrão: Unity **ou** in-house. Cocos ainda existe no idle chinês. Godot não é o stack desse gênero em produção de liveops.

Unity declara ~70% dos top mobile studios — é marketing da própria Unity ([unity.com/topics/mobile-game-design](https://unity.com/topics/mobile-game-design)). Útil como sinal de mercado, não como prova.

## Godot 4 vs Unity — critério deste escritório

| Critério | Godot 4 | Unity |
|---|---|---|
| First game / editor leve | Editor ~100–160 MB, 2D nativo, GDScript feito pro editor | Hub + vários GB; 2D existe, mas o motor é 3D-first |
| Linguagem | GDScript (docs: comece aqui). C# oficial (.NET editor); Android/iOS C# ainda experimental | C# de ponta a ponta, ecossistema enorme |
| Mobile (Android no Windows) | Export oficial; AAB via Gradle. iOS precisa de Mac + Xcode | Export maduro iOS/Android; IAP/ads/LiveOps de prateleira |
| Licença | MIT. Jogo pode ser proprietário; incluir o texto da licença | Personal até US$ 200k receita+funding; Pro depois. Runtime Fee **cancelada** em 2024 ([Unity Blog](https://unity.com/blog/terms-update-runtime-fee-cancellation), [Reuters](https://www.reuters.com/technology/unity-software-scraps-runtime-fee-pricing-policy-introduces-price-hikes-2024-09-12/)) |
| IA / Cursor | Menos StackOverflow; docs oficiais claras; GDScript curto | Mais tutorial, mais plugin, mais ruído |
| Contratar depois | Mercado menor | Mercado maior |
| Destino gacha/MMO | Dá. Liveops/IAP/ads são mais trabalho nosso | Onde o mercado já está |

Docs Godot: [FAQ / MIT](https://docs.godotengine.org/en/stable/about/faq.html), [licença](https://docs.godotengine.org/en/stable/about/complying_with_licenses.html), [linguagens](https://docs.godotengine.org/en/latest/getting_started/step_by_step/scripting_languages.html), [C#](https://docs.godotengine.org/en/4.6/tutorials/scripting/c_sharp/index.html), [export Android](https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_android.html).

## Recomendação (não é decisão)

**Godot 4** para o Loop 1. Motivo: o slice é andar num cenário, offline, no celular, first-time. Backend 16 anos cobre a curva de GDScript; IA cobre o resto. MIT não cria surpresa de contrato.

Unity é a escolha certa se a pergunta for “quero o mesmo chão que Genshin/FGO/Raid **agora**” — IAP, ads, contratar Unity dev, Asset Store.

Trocar depois dói. Se for Godot, manter lógica de jogo (movimento, save, cena) magra e explícita, não espalhada em plugin.

## Relacionado

- iOS: os dois pedem Mac pra store. Loop 1 pode viver em Android + editor no PC.
- Cocos2d-x: aparece em idle chinês; não é candidato nosso (Halan não perguntou; ecossistema pior pra este escritório).
- Unreal: overkill pro Loop 1; some gacha 3D high-end usa, não é o nosso slice.

## Fontes

**Primária:** Android Developers (Com2uS/Vulkan), Korea Herald (Com2uS, Smilegate), GamesIndustry.biz (miHoYo), docs Godot, Unity Blog + Reuters (Runtime Fee).

**Secundária:** MobyGames (Raid), FlyTrap (FGO binário), Inven (Endfield), Unity marketing (70%).

**1 fonte:** portfólio Idle Heroes / Cocos2D.

## Notas relacionadas

- [[00 - Tech - Overview]] · [[00 - Log de Decisões]] · [[00 - Overview]]
