---
tags: [tech, ata, linear]
status: em andamento
criado: 2026-10-23
---

# 07 - Leva da viagem

Ata da leva de tarefas que o Halan abriu no Linear em 22 out 2026 à noite, antes de viajar. Ele vai acompanhar o jogo pelo celular, sem PC. Toda tarefa da leva manda seguir a regra do José ([[07 - Leva da viagem#A regra do José]]) e registrar aqui.

## As filas

| Fila | Prioridade | Resumo | Pronto quando |
|---|---|---|---|
| POK-203 | Urgente, primeira | O José guia o Raphael como um time profissional | a regra está na `main` e o José a segue numa conversa nova |
| POK-140 | Urgente | O jogo roda num Android: Firebase App Distribution, build de dev sem servidor (modo vitrine, save local) | o Halan instala pelo Firebase e joga só com o dedo; vídeo do celular do Raphael |
| POK-204 | Alta | O servidor decide: servidor local no PC do Raphael, sem nuvem; primeiro vira projeto de verdade (ASP.NET Core, .NET 10), depois a luta sai da Unity para `Game.Rules` | um APK alterado não ganha ouro, bicho nem recompensa sem o servidor confirmar |
| POK-205 | Alta, depois do APK | Base profissional: CI com APK a cada merge, testes automáticos, áudio e opções, HUD fora do IMGUI, simulador de balanceamento, registro de decisões, varredura de segredo | — |

Princípio da POK-204: o APK é público e pode ser alterado; esconder segredo nele não protege. O cliente manda a **intenção** ("lutei com estas escolhas"), nunca o **resultado** ("ganhei 500 de ouro"). A luta roda inteira no aparelho; o servidor fala só no começo e no fim.

## A regra do José

Arquivo `.cursor/rules/jose-guia.mdc` no repo `game-pkld/unity`, `alwaysApply: true`, citado no `AGENTS.md` e no `CLAUDE.md` do repo e carregado também pelo `CLAUDE.md` deste escritório. Em resumo: explicar em linguagem simples antes de mexer; no máximo dois caminhos com recomendação; uma branch por tarefa; conta de jogo só em `Game.Rules`; o servidor decide; nada de segredo no código; teste antes de dizer que terminou; Done só com prova; três linhas no fim de cada tarefa (feito, aprendido, risco); decisão grande vira nota em `docs/decisoes/`; a última palavra é do Raphael.

## Registro

- **23 out 2026, POK-203:** regra criada e ligada nos três arquivos de instrução. Ata aberta.

## Notas relacionadas

- [[00 - Tech - Overview]] · [[00 - Log de Decisões]] · [[02 - Produção Loop 1]]
