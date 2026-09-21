---
tags: [pesquisa, tech, cursor, openai, 2026]
data: 2026-09-17
fontes: 8
status: rascunho
---

# 00 — GPT-6 Astra vs Cursor (Raphael)

Pergunta do Halan, 17 set: as redes falam de GPT-6 ASTRA; vale contratar **Codex** no lugar do **Cursor** pro Raphael?

> [!info] GPT-6 Astra é produto oficial da OpenAI (anúncio [openai.com/index/gpt-6-astra](https://openai.com/index/gpt-6-astra/), docs [developers.openai.com](https://developers.openai.com/api/docs/models/gpt-6-astra), system card [deploymentsafety.openai.com/gpt-6-astra](https://deploymentsafety.openai.com/gpt-6-astra)). Não é rumor. Não é o [Project Astra](https://deepmind.google/models/project-astra/) da Google (assistente multimodal).

## Três coisas diferentes

| Peça | O que é |
|---|---|
| **GPT-6 Astra** | Modelo. API `gpt-6-astra`. ChatGPT Plus/Pro/Business/Enterprise + Codex + API. |
| **Codex** | Agente de código da OpenAI (CLI, web, app macOS, extensão de IDE). Roda **em cima** de um modelo (Astra, Sol, etc.). Incluído no ChatGPT pago. |
| **Cursor** | Editor (este escritório). Agente próprio, regras, vault, MCP. Lista Codex como IDE suportada ([docs Codex](https://learn.chatgpt.com/docs/codex/ide)). |

Trocar Cursor por Codex é trocar **casa**, não “pegar o modelo novo”.

## O que a OpenAI afirma

Astra é o flagship pra coding e computer use. Codex atualizado junto. Benchmarks oficiais (Terminal-Bench 4.0, etc.) acima de GPT-5.6 Sol. Demos incluem jogo/Blender/Unreal — **não** Unity 6.3 LTS deste repo.

API (docs): input US$ 10 / output US$ 50 por 1M tokens (standard). Fast = 2×.

## Independente (1 laboratório)

[Endor Labs](https://www.endorlabs.com/learn/gpt-6-astra-on-codex---the-biggest-codex-leap-to-date) (8–9 set, 1 laboratório): Codex+Astra 82.1% FuncPass / 34.6% SecPass vs Sol 67.6% / 20.1%. Ainda atrás de Claude Code + Fable 5.1 (87.2% / 37.4%) no board deles; Astra ~1.8× mais lento (~16.8 min/task vs ~9.5). Salto real no *harness Codex*; **não** prova “melhor que Cursor neste Unity”.

## Cursor nativo, 17 set

Fórum Cursor (13 set, 1 thread): **não** há GPT-6 built-in; workaround VSIX. [OpenAI lista Cursor](https://learn.chatgpt.com/docs/codex/ide) como IDE da extensão Codex. Relato de corte de modelos OpenAI no Cursor em nov/2026 = **1 fonte**, não cravar.

## Pra este escritório

Raphael não é técnico. Loop 1 foi Cursor + Unity + vault/skills neste Windows. App desktop Codex é **macOS**; no PC daqui o caminho oficial é CLI ou extensão de IDE. Codex CLI sozinho perde o cérebro do escritório. Astra no Codex **pode** ser teste paralelo (ChatGPT pago, extensão oficial no Cursor), não substituição. Sem VSIX/BYOK hack.

> [!warning] Não comprar Pro 20x / Ultra no hype. Plus Astra no Codex é cota curta (help OpenAI: ordem de 5–45 msgs/janela 5h no Plus — confirmar na conta). Sem eval Unity daqui.

## Conclusão (17 set)

**Não trocar Cursor por Codex pro Raphael.** Astra é real e provavelmente o melhor modelo OpenAI; o Raphael precisa do editor deste escritório. Se quiser Astra: ChatGPT Plus/Pro + extensão Codex *dentro* do Cursor, depois do kickoff, como experimento — não como casa nova.

## Fontes

- Primária: [anúncio Astra](https://openai.com/index/gpt-6-astra/), [Astra no trabalho/Codex](https://openai.com/index/gpt-6-astra-next-generation-work/), [API](https://developers.openai.com/api/docs/models/gpt-6-astra), [Codex no IDE](https://learn.chatgpt.com/docs/codex/ide), [system card](https://deploymentsafety.openai.com/gpt-6-astra)
- Secundária: Endor Labs; [fórum Cursor](https://forum.cursor.com/t/i-figured-out-how-to-use-gpt-6-astra-in-cursor/171491); help usage (403 no fetch; ranges via coverage)

## Notas relacionadas

- [[00 - Tech - Overview]] · [[05 - Kickoff 19 set]] · [[02 - Produção Loop 1]]
