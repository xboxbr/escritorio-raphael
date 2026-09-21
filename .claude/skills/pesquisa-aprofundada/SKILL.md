---
name: pesquisa-aprofundada
description: Realiza pesquisa multi-fonte sobre um tópico, cruzando WebSearch, WebFetch, Brave Search API e Perplexity API para encontrar conteúdo primário, contexto relacionado e fontes de alta qualidade. Use quando o usuário pedir "pesquisa aprofundada", "deep research", "pesquise tudo sobre X", "monte um dossiê sobre X" ou quando uma pergunta exigir cruzamento de múltiplas fontes para reduzir alucinação e cobrir conteúdo relacionado relevante. Também popula o vault Obsidian com os achados quando solicitado. Neste escritório: engines, mercado, refs de gacha/MMO/collection — não o fangame Pokeland.
---

# pesquisa-aprofundada

Skill de pesquisa multi-fonte. Em vez de uma única consulta a um único motor, executa uma estratégia em camadas:

1. **Decomposição do tópico** em sub-perguntas (núcleo + relacionados).
2. **Busca paralela** em múltiplos motores (WebSearch, Brave, Perplexity).
3. **Aprofundamento** com WebFetch nos links mais ricos.
4. **Triangulação** — só afirma fatos confirmados por ≥2 fontes independentes.
5. **Síntese** estruturada com citações.
6. **Opcional**: gravação dos achados no vault Obsidian.

Casos típicos neste escritório: "Godot vs Unity para mobile + editor no PC", "como indies fazem save local antes de MMO", "o que o mercado chama de pet collection hoje".

**Não** use para copiar dado/mecânica do fangame Pokeland como se fosse nosso. Inspiração vira decisão em `01 - Jogo/`, com as nossas palavras.

---

## Quando usar

Acione esta skill quando o pedido casar com qualquer padrão:

- "pesquise/pesquisa aprofundada sobre X"
- "monte um dossiê / relatório / overview sobre X"
- "encontre tudo o que puder sobre X"
- "preciso entender o estado da arte de X"
- "popule o vault sobre X"
- Qualquer pergunta cuja resposta correta exija cruzar fontes para reduzir chute.

**Não acione** para perguntas factuais simples (uma busca resolve) ou perguntas sobre o próprio código deste repo (use Grep/Read).

---

## Credenciais

As chaves vêm de **variáveis de ambiente** — **fora** do git. Use-as via `curl`. Neste escritório os nomes oficiais são:

- **Brave Search API**: `$env:AI_BRAVE_API_KEY` (Windows) / `$AI_BRAVE_API_KEY`
- **Perplexity API**: `$env:AI_PERPLEXITY_API_KEY` (Windows) / `$AI_PERPLEXITY_API_KEY`

Onde setar: User env do Windows, depois quit total do Cursor.

Se as variáveis não estiverem setadas neste ambiente, caia pra WebSearch + WebFetch (nativos) e avise o Halan que Brave/Perplexity não estão configurados aqui.

> **NUNCA** escreva os valores literais das chaves neste arquivo, em qualquer arquivo do projeto/vault, em commits, ou em respostas. Use **apenas** os nomes `$AI_BRAVE_API_KEY` / `$AI_PERPLEXITY_API_KEY` dentro de `curl`.

---

## Procedimento

### Etapa 1 — Decompor o tópico

Antes de buscar, escreva (mentalmente ou em TodoWrite) 3–6 sub-perguntas:

- **Núcleo**: o que o usuário pediu literalmente.
- **Relacionados óbvios**: termos, versões, nomes próprios mencionados.
- **Contexto**: histórico do tópico, mudanças recentes.
- **Discordâncias**: existem versões conflitantes?

### Etapa 2 — Busca paralela em múltiplos motores

Faça TODAS as buscas iniciais em UMA única mensagem (chamadas paralelas). Para cada sub-pergunta principal, dispare em paralelo:

**a) WebSearch** (nativo):
```
WebSearch query="<sub-pergunta>"
```

**b) Brave Search** (cobertura ampla, resultados crus):
```bash
curl -s -X GET "https://api.search.brave.com/res/v1/web/search?q=<query>&count=10" \
  -H "Accept: application/json" \
  -H "X-Subscription-Token: $AI_BRAVE_API_KEY"
```

**c) Perplexity** (síntese com citações, bom para "qual o estado atual de X"):
```bash
curl -s -X POST "https://api.perplexity.ai/chat/completions" \
  -H "Authorization: Bearer $AI_PERPLEXITY_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"model": "sonar-pro", "messages": [{"role": "user", "content": "<pergunta>"}]}'
```

**Modelos Perplexity disponíveis** (escolha pelo perfil de custo/qualidade):
- `sonar` — leve, rápido, citações básicas
- `sonar-pro` — síntese mais profunda, melhor para overview
- `sonar-reasoning` — quando precisa de raciocínio em cima dos resultados

### Etapa 3 — Aprofundamento

Identifique 3–6 links de **alta qualidade** entre todos os resultados (priorize fontes primárias: docs oficiais > changelog do engine > post do autor > coverage). Faça WebFetch em paralelo para extrair detalhes.

Prompts de WebFetch devem ser específicos — não "resuma a página".

### Etapa 4 — Triangulação

Antes de afirmar qualquer fato no entregável:

- Foi mencionado em **≥ 2 fontes independentes**? Se sim, alta confiança.
- Apareceu em **apenas 1 fonte**? Marque como tal ("segundo X, ..."). Não promova a fato consensual.
- **Fontes divergem**? Apresente as duas versões.
- Uma fonte é claramente primária? Privilegie-a sobre coverage de terceiros.

### Etapa 5 — Síntese

Entregue ao usuário:

- Um **resumo executivo** de 3–5 bullets.
- **Seções por sub-pergunta** com fatos triangulados e citações inline.
- Uma seção **"Relacionado"** com tópicos adjacentes que apareceram repetidas vezes.
- Uma lista de **fontes** no final, agrupadas por tipo (primária / secundária / opinião).

### Etapa 6 — Obsidian (opcional)

Se o Halan pediu para popular o vault, ou se o achado é conhecimento durável, grave via a skill `cerebro-obsidian`:

- **Dossiê de pesquisa** → `07 - Pesquisa/<tema>/00 - <Tema> - Overview.md` (fontes no próprio dossiê).
- **Se o achado vira decisão de produto** → também reflita em `01 - Jogo/` ou `02 - Tech/`.

**Convenções de nota**:

- **Frontmatter** em toda nota:
  ```yaml
  ---
  tags: [pesquisa, <tema>, <ano>]
  data: YYYY-MM-DD
  fontes: <n>
  status: rascunho | revisado
  ---
  ```
- **Wikilinks** `[[Nota]]` para conectar conceitos relacionados.
- **Callouts**: `> [!info]` (≥2 fontes), `> [!warning]` (1 fonte / a confirmar).
- **Não escreva chaves de API** nas notas.
- **Inclua URLs cruas** para o Halan poder clicar.

---

## Boas práticas

- **Paralelize agressivamente**: WebSearch + Brave + Perplexity numa mesma mensagem; depois 3–6 WebFetch numa mesma mensagem.
- **Cite datas e versões** sempre que possível.
- **Distinga** afirmação de fonte primária vs. coverage vs. opinião.
- **Não invente**: se nenhuma fonte cobre algo, diga "não encontrei evidência pública sobre X".
- **Termos em PT-BR e EN**.
- **Refine consultas**: se a primeira rodada veio rasa, mude vocabulário e busque de novo.

---

## Anti-padrões

- **Não** dispare múltiplas perguntas vagas em sequência — decomponha primeiro, depois busque em paralelo.
- **Não** confie em uma única síntese de Perplexity — pode confabular. Sempre cruze com Brave/WebSearch.
- **Não** escreva no vault sem o Halan ter pedido (ou sem que o achado seja claramente durável).
- **Não** repita pesquisa já feita nesta sessão — verifique no histórico antes de relançar a mesma query.
- **Não** trate inspiração do fangame como spec deste jogo.
