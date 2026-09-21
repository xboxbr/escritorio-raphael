---
name: criar-skill
description: Cria uma nova skill custom seguindo padrão de qualidade. Use quando o Halan pedir explicitamente "crie uma skill X" OU quando você (Douglas) detectar que executou o mesmo processo manual ≥ 3 vezes em sessões diferentes e ele merece virar mecanismo reutilizável. Garante que toda skill nasce com frontmatter correto, gatilhos explícitos (não princípios genéricos), procedimento numerado, anti-padrões, e fica em .claude/skills/<nome>/ (project-level, nunca global).
---

# criar-skill

Meta-skill: como nascer skills novas com qualidade consistente. Usar isso evita que cada skill seja um floco de neve com formato e nível de detalhe diferentes.

---

## Quando invocar

| Gatilho | Ação |
|---|---|
| Halan pediu literalmente "crie uma skill X" | Invocar. Confirmar nome/escopo se ambíguo. |
| Você (Douglas) executou o mesmo processo manual em ≥ 3 turnos/sessões | Propor ao Halan "isso virou padrão, vale criar skill". Se ele aprovar, invocar. |
| Halan corrige a forma como você fez algo repetidamente | Padrão a codificar. Propor skill que automatiza a forma correta. |
| Skill existente está sendo "esticada" para casos que não estão no escopo dela | Considerar criar skill nova específica em vez de inflar a existente. |

**Não invoque** para tarefa one-off ou para "deixar registrado" — isso é o que o vault Obsidian é. Skill = processo executável repetível.

---

## Procedimento

### 1. Defina nome

- **Verbo + objeto** sempre que possível: `revisar`, `cerebro-obsidian`, `criar-skill`, `pesquisa-aprofundada`.
- **kebab-case**.
- **Curto** (≤ 3 palavras). Se precisa de mais, talvez é skill demais junta.
- **PT-BR ok** para projetos do Halan.

### 2. Defina o `description` do frontmatter (o mais importante)

Esta string é o que o sistema usa para decidir se invoca a skill. Regras:

- **Comece com o verbo de ação** (que a skill faz).
- **Liste os gatilhos explicitamente** ("Use quando X", "Use SEMPRE QUE Y").
- **Não use** linguagem vaga ("ajuda com X", "facilita Y") — use sinais concretos.
- **Inclua anti-padrões** se relevante ("não use para Z").
- **2–4 frases** é o sweet spot. Curtinho demais não dispara; longo demais polui.

Exemplo ruim:

```
description: Ajuda com pesquisas online.
```

Exemplo bom (real, da `pesquisa-aprofundada`):

```
description: Realiza pesquisa multi-fonte sobre um tópico, cruzando WebSearch,
WebFetch, Brave Search API e Perplexity API para encontrar conteúdo primário,
contexto relacionado e fontes de alta qualidade. Use quando o usuário pedir
"pesquisa aprofundada", "deep research", "pesquise tudo sobre X", "monte um
dossiê sobre X" ou quando uma pergunta exigir cruzamento de múltiplas fontes
para reduzir alucinação e cobrir conteúdo relacionado relevante.
```

### 3. Defina a estrutura do conteúdo

Toda SKILL.md tem **seções na ordem**:

1. **Título** (`# nome-da-skill`).
2. **1-2 parágrafos** de visão geral: o que faz, por que existe, o que NÃO faz.
3. **Quando invocar** — tabela com `Gatilho | Ação` ou bullets com sinais explícitos.
4. **Procedimento** — passos numerados. Cada passo é uma instrução acionável.
5. **Templates** — se a skill produz artefato (nota, ticket, mensagem), incluir template literal.
6. **Anti-padrões** — lista do que **não** fazer com a skill.
7. **(Opcional) Checklist final** — caixinhas para verificar antes de fechar o turno.

### 4. Escreva gatilhos, não princípios

| Ruim (princípio) | Bom (gatilho) |
|---|---|
| "Documente decisões importantes." | "Após Halan escolher entre opções ≥ 2 que você apresentou, escrever entrada em `05 - Decisões/00 - Log de Decisões.md`." |
| "Pesquise com rigor." | "Se o tópico é posterior ao seu knowledge cutoff OU pede dados quantitativos, fazer ≥ 2 motores de busca em paralelo." |
| "Mantenha o cérebro atualizado." | "Quando Halan define uma preferência de engine, atualizar `02 - Tech/` ANTES de fechar o turno." |

A diferença prática: princípio depende de eu lembrar e aplicar. Gatilho dispara sozinho na presença do sinal.

### 5. Local: project-level, sempre

Skill nova vai em `.claude/skills/<nome>/SKILL.md` **dentro do projeto** atual. Nunca em `~/.claude/skills/` (global).

Para criar (Windows / PowerShell):

```powershell
New-Item -ItemType Directory -Force -Path ".claude\skills\<nome>"
# depois Write em .claude/skills/<nome>/SKILL.md
```

### 6. Após criar — confirme com o Halan

Apresente:

- **Nome** da skill.
- **1 frase** do que ela faz.
- **Gatilhos** principais (3 bullets max).
- **Onde** ficou no filesystem.

Pergunte: "Faz sentido? Algum gatilho que faltou?"

### 7. Registre no log se for mecanismo grande

Se a skill formaliza um processo importante (não é só atalho):

- Atualizar `base-de-conhecimento/05 - Decisões/00 - Log de Decisões.md` com o estado vigente.

---

## Template canônico de SKILL.md

Use isso como ponto de partida ao criar nova skill:

```markdown
---
name: <nome-kebab>
description: <verbo de ação>. Use quando <gatilho 1>, <gatilho 2>, ou <gatilho 3>. <Anti-padrão se aplicável>.
---

# <nome-kebab>

<1-2 parágrafos: o que faz, por que existe, o que NÃO faz>

---

## Quando invocar

| Gatilho | Ação |
|---|---|
| <sinal concreto> | <o que faz> |
| <sinal concreto> | <o que faz> |

**Não invoque** para <contraexemplo>.

---

## Procedimento

### 1. <Passo>

<instrução acionável>

### 2. <Passo>

<instrução acionável>

...

---

## Templates

<se aplicável: blocos de código com formato literal do output>

---

## Anti-padrões

- **Não** <coisa que pode atrapalhar>.
- **Não** <coisa que repete trabalho>.

---

## Checklist antes de fechar o turno

```
[ ] <verificação>
[ ] <verificação>
```
```

---

## Anti-padrões da criação de skills

- **Não** crie skill que faz duas coisas grandes. Divida em duas skills com gatilhos diferentes.
- **Não** crie skill cujo gatilho é "use sempre que precisar" — isso não é gatilho.
- **Não** crie skill genérica ("assistente de produtividade"). Skill = mecanismo específico.
- **Não** crie skill que duplica ferramenta built-in (TodoWrite, WebSearch). Compose; não recrie.
- **Não** crie skill sem testar mentalmente o gatilho: "se isso acontecesse agora, eu invocaria?".
- **Não** popule descrição com sinônimos só para "pegar mais matches". Especificidade > recall.

---

## Checklist antes de fechar o turno

```
[ ] Nome é verbo + objeto, kebab-case, curto
[ ] description tem gatilho explícito (≥ 2 sinais concretos)
[ ] Procedimento tem passos numerados acionáveis
[ ] Templates incluídos se a skill produz artefato
[ ] Anti-padrões listados
[ ] Arquivo está em .claude/skills/<nome>/SKILL.md (project-level)
[ ] Halan foi avisado e confirmou
[ ] Decisão registrada no log se for mecanismo grande
```
