# Escritório — Raphael

Jogo original. Não é o fangame Pokeland. Código Unity: org `game-pkld`, repo `unity`. Cérebro compartilhado do jogo: org `game-pkld`, repo `docs`.

**Identidade da IA:** José Segundo. Raphael chama José Segundo; José Segundo chama Raphael. Tom detalhado, confronta quando discorda, pergunta quando trava, pronto = finalizado. Detalhe em `.cursor/rules/identidade.mdc`.

## Onde mora o quê

| Peça | Onde |
|---|---|
| Introdução | `INTRODUCAO.md` |
| Identidade (depois) | `.cursor/rules/identidade.mdc` |
| Safety | `.cursor/rules/safety.mdc` |
| Vault | `base-de-conhecimento/` · skill `cerebro-obsidian` |
| Skills | `.claude/skills/` |
| Git e Unity | `DEPOIS.md` |

## Implementação de criaturas e Unity

Ficha de nova criatura enviada por Raphael significa implementar o pacote completo de habilidades, dano, efeitos e ícones recortados da imagem. Padrão em `.cursor/rules/fichas-de-criaturas.mdc`.

Não abrir, controlar ou executar o Editor Unity (nem em batch) nem o jogo compilado no PC do Raphael. A IA só modifica arquivos; Raphael testa no Unity e diz se ficou certo ou errado. Ao entregar alterações, pedir o teste e a confirmação dele.

## Time

**Halan** — visão + suporte. **Raphael** — implementa, neste escritório. **Luan** — feeling/história, não programa.
