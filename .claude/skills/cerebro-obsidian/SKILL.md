---
name: cerebro-obsidian
description: Consulta ou alimenta o vault Obsidian em base-de-conhecimento/ (cérebro deste jogo original). Use ANTES de responder qualquer pergunta sobre o jogo, a stack, decisões prévias, ou pesquisa já feita (modo consulta). Use SEMPRE QUE aprender fato novo sobre o nosso jogo, o Halan tomar decisão > trivial, observar padrão, ou registrar pesquisa nova (modo escrita). Tem dois modos com gatilhos distintos — leia o procedimento. Não use para o fangame Pokeland (isso é e:\dev\pokeland).
---

# cerebro-obsidian

Skill para usar o vault Obsidian como cérebro persistente do **jogo original**. Dois modos: **consulta** (leitura) e **escrita** (alimentação). Ambos têm gatilhos explícitos.

O vault vive em `base-de-conhecimento/` (relativo à raiz do projeto). Toda referência a pasta aqui é dentro dele.

## Mapa do vault

| Pasta | O que guarda |
|---|---|
| `01 - Jogo/` | Design do **nosso** jogo: loop, mecânicas, destino de produto, o que entra/não entra neste slice. |
| `02 - Tech/` | Engine, export, save local, infra quando existir. |
| `05 - Decisões/` | O que vale agora (sem histórico de norte morto). |
| `06 - Aprendizados/` | Insights, padrões, anti-padrões. |
| `07 - Pesquisa/` | Dossiês (engines, refs, mercado). Não é dump do fangame Pokeland. |

---

## Modo CONSULTA — gatilhos

Invoque ANTES de responder/agir quando qualquer um dos sinais aparecer:

| Sinal | Onde olhar primeiro |
|---|---|
| Mecânica, loop, o que o jogo é / não é | `01 - Jogo/` |
| Engine, export, save, repo, Linear | `02 - Tech/` |
| "aquela decisão", "o que decidimos sobre" | `05 - Decisões/00 - Log de Decisões.md` |
| "o que a gente aprendeu sobre" | `06 - Aprendizados/00 - Insights e Padrões.md` |
| Tema já pesquisado a fundo | `07 - Pesquisa/` |
| Antes de tarefa grande / mapa geral | `00 - Index.md` |

### Procedimento de consulta

1. **Identifique a pasta provável** pela tabela acima.
2. **Use Glob** para listar arquivos relevantes: `Glob pattern="base-de-conhecimento/**/*.md"`.
3. **Use Grep** para encontrar menções específicas.
4. **Read** a(s) nota(s) mais relevante(s). Comece pelo Overview da pasta (`00 - …`).
5. **Não responda** baseado só na sessão se o vault pode ter informação canônica.
6. **Se o vault não tiver**, dizer explicitamente: "nada registrado sobre isso no cérebro, vou pesquisar/inferir."

### Anti-padrões de consulta

- **Não consultar e chutar** quando o vault claramente teria a resposta.
- **Não varrer todas as pastas** quando o sinal aponta pra uma.
- **Não citar nota como verdade absoluta** se tem `status: rascunho` ou callout `> [!warning]`.
- **Não puxar dado do fangame Pokeland** e tratar como regra deste jogo.

---

## Modo ESCRITA — gatilhos

Invoque APÓS detectar qualquer dos eventos abaixo durante a conversa:

| Evento | Onde gravar |
|---|---|
| Define mecânica / loop / o que o jogo é | `01 - Jogo/` |
| Define engine, export, save, infra | `02 - Tech/` |
| Halan toma decisão > trivial | `05 - Decisões/00 - Log de Decisões.md` com o estado vigente |
| Observa padrão repetido (≥ 2 ocorrências) OU insight útil | append em `06 - Aprendizados/00 - Insights e Padrões.md` |
| Pesquisa aprofundada ou conhecimento de domínio novo | `07 - Pesquisa/<tema>/` |

### Procedimento de escrita

1. **Confirme se já existe nota** (Glob/Grep antes de criar). Se sim, **edite**; nunca crie duplicata.
2. **Use frontmatter padrão**:

```yaml
---
tags: [<pasta>, <tema>]
data: YYYY-MM-DD
status: rascunho | revisado
---
```

3. **Use callouts certos**:
   - `> [!info]` — fato confirmado por ≥ 2 fontes independentes OU declarado direto pelo Halan.
   - `> [!warning]` — inferência / 1 fonte só / a confirmar.
   - `> [!quote]` — citação direta (com atribuição).
   - `> [!todo]` — pendência operacional.

4. **Linke** com `[[wikilinks]]`.
5. **Atualize o `00 - Index.md`** se a nota é de alta visibilidade.
6. **Termine a nota** com `## Notas relacionadas` e (se aplicável) `## Fontes`.

### Decisões

Atualizar `05 - Decisões/00 - Log de Decisões.md` com o **estado vigente**. Não appendar norte antigo. Não guardar “era X, agora é Y” — só o Y.

### Aprendizados: template

```markdown
### <Título do insight>

**O que**: <observação concreta>
**Por quê**: <causa / motivação>
**Como aplicar**: <próxima vez que isso aparecer, faça X>
```

### Anti-padrões de escrita

- **Não criar nota órfã** — sempre conectar via wikilink a ≥ 1 nota existente.
- **Não duplicar** — Glob/Grep antes; se existe, edite.
- **Não escrever segredos** (chaves de API, tokens) em nenhuma nota.
- **Não inflar** — fato cru. Se não vai ser lido daqui a um mês, não grave.
- **Não rebobinar** — atualize a nota vigente; apague o norte morto.
- **Não documentar o fangame Pokeland aqui.** Inspiração vira decisão nossa, com as nossas palavras.

---

## Checklist mínimo antes de responder qualquer pergunta substantiva

```
[ ] Esta pergunta pode ter resposta canônica no vault?
    → SIM: consultar (Glob + Read da nota Overview correspondente)
    → NÃO: responder direto

[ ] Esta resposta vai gerar conhecimento novo sobre o jogo / stack / decisão?
    → SIM: ao fim do turno, gravar (modo escrita)
    → NÃO: seguir
```
