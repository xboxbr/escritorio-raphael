---
name: revisar
description: Faz revisão estruturada em camadas (correctness, completeness, consistency, clarity, risk) de código, arquitetura, decisões, escrita, ou da própria base-de-conhecimento. Use quando o Halan pedir "revise X", "audite Y", "o que você acha disso", "tem algo que dá pra melhorar aqui", ou antes de marcar como concluído algo > trivial que você acabou de produzir. Output sempre priorizado em críticos / sugestões / nice-to-have. NÃO é checklist de superfície — é análise deliberada em passes separados.
---

# revisar

Skill de revisão robusta. Diferente de "dar uma olhada e comentar", aplica **passes em camadas** — cada um faz uma pergunta única — e fecha em **diagnóstico priorizado**. Funciona para código, arquitetura, decisão, texto, ou a própria estrutura do cérebro (vault Obsidian).

Por que em camadas: revisão genérica mistura "tem bug" com "está confuso" com "talvez devesse ter feito diferente" — e tudo vira lista igual de prioridade. Camadas separam **o que está errado** de **o que está pior do que poderia estar**, com prioridade clara.

---

## Quando invocar

| Gatilho | Ação |
|---|---|
| Halan pede "revise X", "audite Y", "o que você vê de errado/melhorar" | Invocar com escopo = X. |
| Você acabou de produzir algo > trivial (skill nova, arquitetura, doc, mudança de código) | Auto-invocar antes de reportar como pronto. |
| Halan vai tomar decisão grande com base num artefato (código, plano, proposta) | Invocar sobre o artefato antes da decisão. |
| Antes de commit/push de mudança não trivial | Invocar sobre o diff. |
| Periodicamente (ex.: mensal) sobre o estado do vault e das skills | Invocar com escopo = "estado da base de conhecimento". |

**Não invoque** para tarefa trivial (mudança de 1 linha, typo, rename simples) — só consome contexto.

---

## Os 5 passes

Cada pass faz **uma pergunta**. Faça os passes **em sequência**, não em paralelo (cada um informa o próximo). Anote achados por pass.

### Pass 1 — Correctness

> **A coisa faz o que diz que faz?**

- Código: roda? Lógica está certa? Edge cases tratados?
- Arquitetura: as conexões existem? Os componentes alegados estão presentes?
- Decisão: o rationale conecta com a escolha? Não tem non sequitur?
- Texto: fatos verificáveis estão certos? Citações reais?
- Skill: gatilhos disparam nos sinais que descrevem? Procedimento é executável?

**Output**: lista de defeitos concretos. Cada item: **local** + **o que está errado** + **evidência**.

### Pass 2 — Completeness

> **Falta alguma coisa essencial?**

- Código: faltam tratamentos de erro, validação de input, casos de borda?
- Arquitetura: tem ponta solta? Componente referenciado mas não definido?
- Decisão: opções importantes não consideradas? Stakeholder esquecido?
- Texto: argumento tem buraco lógico? Falta evidência crítica?
- Skill: cobre o gatilho principal mas esquece o secundário óbvio?

**Output**: lista de buracos. Cada item: **o que falta** + **por que importa**.

### Pass 3 — Consistency

> **Bate com o resto?**

- Código: estilo do projeto? Convenções da codebase?
- Arquitetura: nomeação alinhada? Padrão repetido sem desvio inexplicado?
- Decisão: contradiz decisão anterior? Princípio declarado em outro lugar?
- Texto: tom uniforme? Termos usados consistentemente?
- Skill: segue o template canônico (`criar-skill`)? Gatilho conflita com outra skill?

**Output**: lista de inconsistências. Cada item: **o que diverge** + **com o quê** + **deveria seguir qual?**

### Pass 4 — Clarity

> **Futuro-eu (ou outro humano) vai entender em 3 meses?**

- Código: nomes claros? Comentários onde o "porquê" é não-óbvio?
- Arquitetura: diagrama/texto deixa claro o fluxo? Termos definidos?
- Decisão: rationale fica claro sem contexto da sessão atual?
- Texto: estrutura ajuda leitura? Ideias importantes em destaque?
- Skill: gatilhos não-ambíguos? Procedimento sem "depende"?

**Output**: lista de pontos confusos. Cada item: **trecho** + **o que confunde** + **como esclarecer**.

### Pass 5 — Risk

> **O que pode dar errado depois?**

- Código: caminho irreversível? Race condition? Vulnerabilidade?
- Arquitetura: ponto único de falha? Dependência frágil?
- Decisão: efeito colateral não-óbvio? Custo de reverter?
- Texto: afirmação que pode envelhecer mal? Promessa cara?
- Skill: gatilho falso-positivo frequente? Procedimento destrutivo sem confirmação?

**Output**: lista de riscos. Cada item: **risco** + **probabilidade alta/média/baixa** + **impacto alto/médio/baixo** + **mitigação possível**.

---

## Síntese: priorizar achados

Junte todos os achados dos 5 passes e classifique em **3 buckets**:

### CRÍTICOS (resolver antes de marcar feito)

- Tudo de Pass 1 (correctness).
- Pass 5 com risco alto+alto OU médio+alto.
- Pass 2 com buracos que invalidam o objetivo.

### SUGESTÕES (resolver se tempo permitir)

- Pass 2 com buracos cosméticos.
- Pass 3 inconsistências visíveis.
- Pass 5 risco médio.

### NICE-TO-HAVE (registrar como follow-up)

- Pass 4 melhorias de clareza.
- Pass 3 inconsistências menores.
- Pass 5 risco baixo.

---

## Output ao Halan

Template do relatório de revisão:

```markdown
## Revisão de <escopo>

### Pontos sólidos
- <2-4 bullets curtos do que está bem feito>

### CRÍTICOS (N itens)
1. **<problema>** — <local específico>. <Evidência>. Sugestão: <fix>.
2. ...

### SUGESTÕES (N itens)
- <problema> em <local>. <Por que importa>. Possível fix: <X>.
- ...

### NICE-TO-HAVE (N itens)
- <ponto menor>.
- ...

### Próximo passo recomendado
<Uma ou duas linhas: o que fazer primeiro>
```

**Tamanho**: revisão pequena → relatório curto. Revisão grande → relatório longo mas SEMPRE com os 3 buckets na ordem.

---

## Quando auto-invocar (sem o Halan pedir)

Antes de reportar como concluído:

- Skill nova criada.
- Arquivo de arquitetura/`AGENTS.md` alterado.
- Mais de 3 arquivos editados em sequência.
- Decisão vigente em `05 - Decisões/` com impacto > trivial.

Nesses casos, rode **passes 1, 3 e 5** internamente (correctness + consistency + risk), mais leves, e só reporte ao Halan se encontrar algo crítico. Se tudo limpo, basta dizer "rodei revisão interna, nada crítico".

---

## Calibração: quando NÃO encontrar nada também é resposta

Feedback do Halan: **IA que faz review tende a "encontrar qualquer coisa quando não encontra nada"** — vira nitpicking quando a entrega já está boa suficiente. Combater esse viés é parte central da skill.

Regras pra evitar nitpicking:

- **Aprovação positiva é resposta legítima.** Se rodou os 5 passes e não há crítico real → diga "OK, aprovado, sem achados". Não invente sugestões pra justificar a revisão.
- **Default conservador.** Assuma que o autor tomou decisões deliberadas. Pra contestar, precisa de razão concreta (risco, gap, bug), não estilística ("eu faria diferente").
- **Custo do feedback é real.** Cada achado custa tempo do autor pra resolver. Achado marginal com custo alto e benefício baixo é desperdício — não inclua.
- **Threshold por contexto.** Loop 1 é learning slice: tolerância a "imperfeito mas funcional" é alta. Store / MMO é outra conversa. Pergunte ao Halan se o contexto não estiver claro.
- **"Vai virar dor em < 6 meses?"** Regra prática pra decidir entre SUGESTÃO e NICE-TO-HAVE. Se a resposta é "não", é nice-to-have ou nem entra.
- **Pontos sólidos primeiro.** Sempre liste 2-4 coisas bem feitas antes dos achados. Calibra o feedback e protege contra viés negativo.

Se a revisão volta com 0 críticos + 0 sugestões + 0 nice-to-have, está OK. Reporte "rodei os 5 passes, deliverable atende, nada a ajustar" — não force achado pra parecer útil.

---

## Anti-padrões

- **Não** misturar os passes. Cada um responde **uma** pergunta.
- **Não** classificar tudo como crítico. Se tudo é crítico, nada é crítico.
- **Não** sugerir reescrita total quando 3 ajustes pontuais resolvem.
- **Não** revisar **forma** quando o **conteúdo** tem buraco — sempre pass 1 primeiro.
- **Não** confundir gosto pessoal com defeito. Em pass 3 (consistency), o critério é "alinha com o resto do projeto", não "eu faria diferente".
- **Não** rodar revisão sem escopo claro. Se o Halan disser "revisa tudo", pergunte: tudo de quê? Pasta? Skills? Vault inteiro?
- **Não** inventar achado pra "ser útil" quando o output já está bom. Aprovação positiva é resposta legítima.
- **Não** acumular nice-to-have a ponto da lista virar ruído. Se passa de 5 itens, corte os mais marginais.

---

## Checklist antes de fechar a revisão

```
[ ] Escopo declarado e confirmado
[ ] Passes 1–5 executados em sequência
[ ] Achados separados em CRÍTICOS / SUGESTÕES / NICE-TO-HAVE
[ ] Pontos sólidos também listados (não só problemas)
[ ] Próximo passo recomendado dito em 1-2 linhas
```
