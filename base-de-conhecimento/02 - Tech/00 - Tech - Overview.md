---
tags: [tech, overview]
data: 2026-09-08
status: revisado
---

# 00 — Tech - Overview

Pré-kick-off de código. Linear confirmado. GitHub pessoal + org. Premissa de engine: Unity.

> [!info] Confirmado por Halan: escritório `e:\dev\game` (1 set); Linear MCP (2–8 set); org [`game-pkld`](https://github.com/game-pkld) (8 set); Unity como premissa (8 set).

## Linear

- Workspace: [`pokeland-vibes`](https://linear.app/pokeland-vibes). Team: **Pokeland-vibes**.
- MCP: `linear-game` → `https://mcp.linear.app/mcp`. Chave: env `AI_LINEAR_GAME`.
- Escritório Raphael: `.cursor/mcp.json` interpola `${env:AI_LINEAR_GAME}` no header `Authorization`. Valor só no User env do Windows, nunca no arquivo.
- Admins vistos em 8 set: `halannl85@gmail.com`, `gotensousa5@gmail.com` (LOGAN).
- Sem Firecrawl/Supabase/Vercel do Pokeland (fangame).

## GitHub

- **git CLI, nunca `gh`.** `gh` neste Windows é PortX / `halanlima`.
- SSH: alias `github-personal` → `~/.ssh/id_ed25519_github_personal` (conta `halannl`). Trabalho: `github-portx` / `github.com-company` → chave PortX. **Não mexer.**
- Escritório interno: [`halannl/game-pkld-vibes`](https://github.com/halannl/game-pkld-vibes). Remote: `git@github-personal:halannl/game-pkld-vibes.git`.
- Org do jogo: [`game-pkld`](https://github.com/game-pkld). **docs** (cérebro) e **unity** (Unity). Remote: `git@github-personal:game-pkld/<repo>.git`. O `client/` em `e:\dev\game` não é o remote oficial. Escritório Cursor do Raphael: zip, git pessoal dele.
- Config local deste repo: `Halan Lima` / `halannl85@gmail.com`.

## Alvo deste slice

- 3D
- Celular; teste no PC
- Offline, só local
- Save: opcional neste loop (lembrar nome). Se não tiver, recomeça.

## Engine

**Unity 6.3 LTS** (`6000.3.23f1`). Projeto: `client/` neste workspace, template **Universal 3D** (URP). Sem Unity Cloud. Dossiê: [[00 - Godot vs Unity]]. Licença: [[01 - Unity - Licença e custo]]. 6.6 (update release) **não** é o editor deste projeto.

Loop 1: Unity Personal, US$ 0, enquanto a receita/funding ligada ao uso da Unity (pessoa física) ou da empresa do jogo (PJ) não passar de US$ 200k nos últimos 12 meses. Sem royalty sobre o jogo.

Não apontar Vercel/Supabase/Firecrawl do **Pokeland** para cá. Qualquer cloud: ainda não.

## Agente (Raphael)

Casa: **Cursor** neste workspace. GPT-6 Astra (OpenAI, set/2026) é modelo, não substituto do editor. Dossiê: [[00 - GPT-6 Astra vs Cursor]]. Não trocar Raphael pra Codex-only no hype.

## Notas relacionadas

- [[00 - Overview]] · [[00 - Log de Decisões]] · [[01 - Unity - Licença e custo]] · [[02 - Produção Loop 1]] · [[00 - Godot vs Unity]] · [[00 - GPT-6 Astra vs Cursor]]
