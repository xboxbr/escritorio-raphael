---
tags: [decisões]
data: 2026-10-13
status: revisado
---

# 00 — Decisões vigentes

O que vale **agora**. Sem histórico de norte antigo.

## Escritório

- Pasta: `e:\dev\game` (nome de trabalho, não é marca).
- Casa: **Cursor**, workspace **separado** do Pokeland.
- Skills em `.claude/`.
- GitHub: `git`, nunca `gh`. SSH só via `github-personal` (não mexer no perfil PortX). Conta `halannl`. Repo do escritório: [`halannl/game-pkld-vibes`](https://github.com/halannl/game-pkld-vibes). Org: [`docs`](https://github.com/game-pkld/docs) (cérebro) + [`unity`](https://github.com/game-pkld/unity) (código). Escritório Cursor do Raphael: zip, versiona no git pessoal. O `client/` em `e:\dev\game` não é o remote oficial.
- Linear: workspace [`pokeland-vibes`](https://linear.app/pokeland-vibes), team Pokeland-vibes. MCP `linear-game`, chave `AI_LINEAR_GAME`. Sem Firecrawl/Supabase/Vercel do fangame. Cada push do jogo no GitHub ganha um issue Done no Linear, no mesmo turno (Raphael, 3 out).
- Git do jogo (`game-pkld/unity`): cada trabalho nasce numa branch. Não se commita direto na `main`. O merge para a `main` acontece quando o trabalho fecha, ou quando o Raphael manda. Sem force push na `main` (Halan, 6 out).
- Pesquisa: `AI_BRAVE_API_KEY`, `AI_PERPLEXITY_API_KEY` (skill pesquisa-aprofundada). Nunca valores no git.
- Este vault é o **jogo original**. Fangame (site/canal) = `e:\dev\pokeland`.

## Produto

- Oficial, design próprio. Marca Pokeland (site/canal) **não** lança este jogo.
- Destino: gacha + coleção + luta. Essência Pokeland + [[00 - Summoners War]] + [[00 - Idle Heroes]]. Coluna: **clima** como tema (não buff de sala) — [[06 - Clima como coluna]]. Hub destino: **ilha** com coleção visível. Primeira luta destino: **3v3**, turno por speed, fileira. Título Storm: estacionado. Sem go-live. Recortes: [[04 - Recortes de inspiração]]. Kickoff: [[07 - Kickoff 19 set]].
- Frase de player (19 set): luto e competo (ganhar de quem tem mais poder); coleciono e o comum existe sem pagar; vejo o arsenal no mundo.
- Comum F2P existe; evoluir pede cópia. Whale compra **tempo**, não dump infinito. Teto de poder sobe por update.
- Daily obrigatório das recompensas: **~1h**. Quem quiser ficar o dia tem o que fazer, com ganho pequeno.
- **Loop 1** (já existe): apresentação → personagem → nome → andar. **Próximo Play:** placeholder 3v3 que se bate (quadrado na tela). Sem ilha, sem gacha, sem 6 fichas no primeiro commit.
- Time (19 set): Halan visão + suporte + paga ferramentas; **Raphael** implementa no **Cursor** (R$ 250/semana de partida); **Luan** feeling/história/ficha, **não programa**; Douglas neste escritório. Discordância: a sala pediu **consenso** (Halan recusou martelo “eu pago”). GPT-6 Astra não troca a casa ([[00 - GPT-6 Astra vs Cursor]]).
- “Nunca” absoluto e IP/mod: **não fechados** na kickoff. Não tratar como spec.
- Engine: **Unity 6.3 LTS** (`6000.3.23f1`, 8 set). Projeto `client/` (URP). Personal enquanto Total Finances ≤ US$ 200k / 12 meses. 6.6 não é o editor deste projeto.
- Bootstrap: Halan custeia assinaturas e Raphael. Código: Raphael + Halan suporte + Douglas. **Sem investidor.** Independente.
- Arte do slice: 3D. Meshy Free ok pra placeholder interno (CC BY 4.0). Higgsfield = conceito/imagem/vídeo e GLB de previz — **não** é o motor do jogo.

## Movimento e time (Raphael, 2 out)

- Movimento no jogo: `BoneMotion` (respirar parado, andar na trilha, investida de ataque). Quem entra nesse movimento é o elenco de 10 out.
- O time de três grava em `PlayerPrefs` (`team.slots`). A luta 3v3 abre com essa escolha.
- Lutar abre a escolha da área. As seis: Caverna, Clareira, Santuário, Observatório, Costa e Campina. Santuário é o solar suspenso. Observatório é o do crepúsculo. Costa é a de vento, céu aberto, mar e a luz do fim do dia. Campina é a de tempestade, céu carregado, pedras de runa, relâmpago de vez em quando. Esses quatro nasceram com o nome do modelo que os fez (sol 6.1, Astra 6, Opus 5.5, Fable 5.1) para o Raphael comparar a criação 3D. O nome no jogo passou a ser o do lugar. O commit `04b8dcf` guarda o nome antigo.
- A aventura é uma rota 3D contínua: luta, caminhada e paisagem compartilham coordenadas (`AdventureDiorama`). Materiais fotográficos CC0 do ambientCG, com fonte registrada em `Resources/AdventureArt/SOURCES.md`. Texturas ficam em git normal enquanto nenhum arquivo passar de 10 MB; LFS só para arquivos grandes como o `ggml-small.bin`.
- Aventura: sombra oval no chão e zoom da roda do mouse, o mesmo gesto da arena.

## Elenco (Halan, 10 out)

Os 13 de `ativos/bichos/escolhidos` são os únicos bichos do jogo: coleção, ficha, luta e inimigo. Aurion, Blossom Queen, Cinderplate, Eclipse, Frostfang, Grizzleback, Hellflame, Lithon, Noct, Ruffletail, Shadowmane, Tidepaw, Vaelith. O corpo de cada um é a imagem anexada no filho. Não redesenhar. Mesh na Meshy até acabar o crédito; sem crédito, Tripo. Esqueleto na Nira. Movimentos: idle, cheer-up, dying, walking/moving, e um golpe padrão. Cinderplate, Hellflame, Vaelith e Shadowmane têm habilidades implementadas pelas respectivas cartas; os outros nove ainda usam habilidades dummy. Shadowmane integrado em 14/10/2026, aguardando teste de Raphael. Vaelith integrado em 14/10/2026, aguardando teste no Unity pelo Raphael. Hellflame testado no Unity por Raphael e confirmado como funcionando em 13/10/2026. Fila: [POK-111](https://linear.app/pokeland-vibes/issue/POK-111/elenco-os-13-de-escolhidos-substituem-os-bichos-do-jogo), filhos POK-112 a POK-124, assignee Raphael, Todo.

## Retratos (Raphael, 7 out)

Foto de bicho na interface: diagonal, olhando para a frente, cabeça à esquerda. Na fila da luta o arquivo é JPG com o nome do bicho, em `Portraits/` (`Aurion.jpg`, `Blossom Queen.jpg`). A moldura dourada fica por cima, com o miolo transparente. O corpo 3D não sai dessa foto: sai da imagem anexada no filho do POK-111.

## HUD da luta (Halan, 1 out)

A distribuição da luta 3v3 segue o print que o Halan mandou. O desenho é o kit místico, não o print. Velocidade e auto ficam à esquerda. No topo, nome e Power de cada lado. A fila de quem joga fica à direita. A saída fica no canto. As três skills ficam embaixo, no centro; a ultimate acende quando pode ser usada. A vida do bicho fica no pé, com a carga da ultimate numa barra fina embaixo. Ajuda não entra. Suporte, insígnia, campo, fruta e ressonância esperam a mecânica. Escudo não aparece enquanto a luta não tiver esse número. Velocidade continua 1x, 2x e 4x. Nível de conta não entra.

## Tipos, cristal e língua (Halan, 30 set)

- Dezenove tipos. Chave em inglês, rótulo na língua da tela. A grade mora num lugar só. Sem elemento, fator 1. Dois elementos, o produto, sem teto. O golpe multiplica essa vantagem no `StrikeMath`. Ataque 0 continua 0.
- Quem luta é a ficha do bicho. Arena e trilha não resolvem o golpe pelo Azul/Vermelho. Inimigo e jogador saem do elenco de 13. O cristal não é bicho: a defesa 24 está no asset `Cristal`. Cada bicho tem um ou dois elementos; cada skill tem um.
- Cristal: cinco marcas, não age, não morre. Velocidade copiada de um dos três, pela seed. Ouro pelos marcos a partir de 10.000. O dia é o relógio do servidor. Semana começa na segunda. O cliente não manda o dia.
- Línguas: `pt-BR`, `en-US`, `es-ES`. Frase por chave em inglês. Fora das três, `pt-BR`. Tradução faltando cai em `en-US`. Schema em inglês (`locale`).

## Cinderplate (Raphael, 12 out)

- Elementos Ground e Rock.
- Slots na ordem da carta: Jogo Sujo é o básico (CD 2), Poder Terrestre é a skill (CD 2), Terremoto é o estouro, Ira da Terra é a ultimate.
- Escavado: nada o alcança, nem área, até o turno seguinte dele. Só a Ira da Terra de outro bicho o tira.
- Resistência +10% por 10 turnos ([POK-129](https://linear.app/pokeland-vibes/issue/POK-129)) é um corte de dano escondido. Entra na última camada, depois do escudo, antes do único arredondamento. Não aparece na ficha nem no número flutuante. A limpeza da Ira da Terra tira esse corte.
- Chance de acerto ficou 85/70/90/80. A tarefa do Halan sobre isso continua aberta.
- A passiva da carta não tem nome. No jogo o nome é Passiva. Sobe a defesa e entra no Power.
- A defesa enrolada usa a malha `cinderplate-roda`. Girando, 65% fica dentro do solo e 35% fica para fora.
- Na ficha, clicar no nome da skill mostra o golpe no modelo. O boneco fica na frente do bicho, inteiro no quadro. Debaixo do chão o corpo some e só a poeira segue até o impacto.
- Hellflame na luta fica 25% maior. Ficha e hub não mudam.
- Na tela de time, o corpo atual fica assim: Hellflame 10% menor, Blossom Queen 15% menor, Cinderplate 10% maior, Aurion 49,5% maior (15% maior do que o teste de 30%), Noct 20% maior, Shadowmane 10% maior, Ruffletail 20% menor, Vaelith 21,25% menor (5% maior do que o teste de 25% menor), Warphant 30% maior, Eclipse 36,125% maior que o encaixe (10% maior do que o tamanho anterior) e 22 cm para o fundo do disco, com as asas dobradas 32° no idle da tela de time, Grizzleback 5% menor, Frostfang 10% maior, Lithon 15% maior. Luta, ficha e hub não mudam.
- Na ilha, o santuário abre Bichos, a lanterna abre Time, o obelisco abre Evoluir e o portal abre Cristal. Itens continua no ponto antigo da foto.
- No menu principal, os bichos da ilha têm o dobro da altura de antes. Andam só no chão livre, afastados 1,6 m da arquibancada e da escada.
- Na vez do jogador, a skill de um alvo pode ser marcada antes do clique no inimigo, ou o alvo vem primeiro. Skill de área dispara nos três sem um alvo só. Segurar o bicho por mais de 1 segundo mostra os status da luta, com o valor de agora, no painel do log.

## Fichas e Hellflame (Raphael, 13 out)

- Nova imagem de criatura significa implementar passiva, skills, ultimate, dano/poder, efeitos, durações, alvos, recargas e ícones recortados da própria ficha. Preservar atributos não informados. Padrão em `.cursor/rules/fichas-de-criaturas.mdc`.
- Downloads de FX podem ser usados se necessários, sem compra automática; registrar fonte/licença. Hellflame usa VFX originais do projeto.
- Hellflame: Força das sombras (Dark, especial 60, único, abate dá +20% velocidade por 2 turnos, máximo 2); Garra das sombras (Ghost, dano zero, roubo de buffs e bloqueio de aumentos por 2 turnos, CD 3); Onda de calor (Fire, especial 20, grupo, +30 pontos de crítico após golpe por 2 turnos sem acumular; os dois braços sobem e o corpo inclina um pouco para a frente); Investida amaldiçoada (Ghost, especial 70, único, custo de 20% da vida máxima, sem matar — fica com 1 se não houver vida bastante —, anticura 3 turnos com transferência no abate, +50% dano contra vida estritamente abaixo de 50%).
- Passiva: cada inimigo que cruza para 50% de vida ou menos ativa uma vez; +10% Ataque Especial até o fim da batalha, máximo 3 acúmulos.
- Não abrir, operar ou executar o Editor Unity, inclusive batch. Raphael opera o Editor e confirma o resultado. Toda entrega pede teste no Unity e confirmação. C# compilado sem erros. Raphael confirmou em 13/10/2026 que o teste do Hellflame no Unity deu certo; entrega validada por ele.
## Notas relacionadas

- [[00 - Overview]] · [[03 - Plano de execução]] · [[04 - Recortes de inspiração]] · [[06 - Clima como coluna]] · [[07 - Kickoff 19 set]]


## Vaelith (Raphael, 14 out)

- Implementado conforme a ficha Vaelith-Oh; mantém o nome Vaelith, atributos-base, tipo da criatura e chances de acerto do cadastro existente, que a carta não redefine.
- Passiva: qualquer criatura, aliada, inimiga ou o próprio Vaelith, usando skill Fire dá +10% de ataque físico e +5% de velocidade por 5 turnos. Até 5 acúmulos com durações individuais; no limite, renova o mais próximo de expirar. Um lançamento em área ativa uma vez.
- Explosão divina: Fire, físico 30, grupo, +10 fúria adicional, Voo até o próximo turno, CD 1. Voo segue a proteção do Cinderplate, inclusive contra área; Ira da Terra atravessa e remove o estado.
- Ciclone das sombras: Dark, físico 30, único, Chama Infernal até o próximo turno, CD 4.
- Asas da morte: Flying, físico 60, único, custo de 50% da vida atual depois do golpe. Abate zera todas as recargas, sem repor fúria. Sem CD adicional indicado na ficha.
- Punição divina de Oh: Fire, físico 20–200, único, poder proporcional à vida perdida (20 cheio; 110 com metade); CD 1 e fúria cheia. Aplica Chama da Ressurreição até o próximo turno.
- **Chama da Ressurreição:** conforme esclarecimento explícito de Raphael, mantém pelo menos 1 HP até o próximo turno, não importa quantos ataques receba, e pode ser reaplicada a cada ultimate. Não cura nem se consome no primeiro dano letal. Chama Infernal também impede HP abaixo de 1 até o próximo turno. As duas não podem ser roubadas nem dissipadas.
- Cinco ícones extraídos diretamente da ficha, em círculos 124×124 dentro de canvas 128×128, como Cinderplate. VFX originais com penas e asas incandescentes, fogo turbulento, ciclone violeta e penas azul-brancas. Raphael pediu fogo mais elaborado que o anterior.
- Integração na branch `codex/vaelith-skills`, sem commit/push. Compilação externa de C# e testes matemáticos aprovados; não houve execução do Editor. Falta validação visual/combate por Raphael. Fontes e roteiro de teste em `assets/vaelith/SOURCES.md`.


## Shadowmane (Raphael, 14 out)

- Usa a carta que traz o título Dracolizar, mantendo Shadowmane no cadastro. Tipos Dark/Poison, atributos-base existentes preservados.
- Shadow Wave: físico 30, grupo, 80% de atordoar por um turno ao acertar, CD2. Shadow Sting: físico 60, único, cegueira de -70% da precisão atual por dois turnos, CD3.
- Poison Breath: grupo, sem dano imediato, 50% por alvo de aplicar veneno, CD3. Cada acúmulo causa 5% HP máximo no fim do turno por três turnos, máximo três, durações individuais; no limite renova o mais próximo de expirar.
- Shadow Veil é ultimate em si mesmo, sem dano, CD4 e fúria cheia. Imunidade a novos negativos garantida por dois turnos; 30% de chance de Camuflagem por dois turnos. Camuflagem impede ataques únicos e permite área. Raphael escolheu explicitamente essas regras e os poderes/recargas propostos.
- Instinto Predador: bônus inato permanente de +5% ataque físico e +5% velocidade em combate.
- Rig recebe movimentos de costas, cabeça/pescoço, quatro patas e cauda, sincronizados com onda, ferrão, sopro e véu. Ícones recortados da imagem no encaixe circular do Cinderplate, efeitos originais. Textos PT/EN/ES integrados.
- Código na `main` do jogo, commit `98dd98a`. Compilação C# aprovada, sem executar Editor ou jogo; testes de combate e aprovação visual pertencem a Raphael. Ver `assets/shadowmane/SOURCES.md`.


## Revisão de Halan: Shadowmane (Raphael, 14 out)

Estas regras substituem a configuração inicial do Shadowmane. Raphael optou por manter nomes em inglês.

- Shadow Wave: físico Dark, grupo, poder20. Sorteio independente de80% de stun por1 turno para cada inimigo acertado.
- Shadow Sting: físico Dark, único, poder100 e acerto100%. Sorteio separado de70% para Blind, reduzindo precisão50% por2 turnos.
- Poison Breath: físico Poison, grupo, poder20, acerto100%. Cada inimigo acertado rola50% para Veneno; até3 acúmulos, cada um com3 ticks de10% HP máximo, no fim do turno.
- Shadow Veil: Dark, buff em si mesmo, invisibilidade e estado inatingível contra ataques únicos e em área por2 turnos, +20% ataque físico e +20% velocidade por2 turnos, tudo garantido. Substitui camuflagem30% e imunidade a novos negativos da versão anterior. Condições já aplicadas continuam contando.
- Recargas2/3/3/4 e passiva permanente5% preservadas. Commit local `f334a16` na branch `codex/shadowmane-ajustes-halan`; ainda sem push. Compilação externa C# aprovada, sem execução de Editor/jogo. Falta Raphael testar e confirmar. Fontes e backups em `assets/shadowmane/SOURCES.md`.


## Instinto Predador — ordem do bônus em batalha (Raphael, 14 out)

- Substitui a passiva inicial de5%: Dark, +20% de velocidade e +20% de ataque físico durante o combate. Nome traduzido conforme a língua.
- Somar primeiro os bônus normais de atributos; a passiva multiplica o valor final de entrada por1,20. Exemplo explícito de Raphael: 200+200=400; em batalha, 400×1,20=480. Aplicação permanente e não dissipável, restrita ao combate.
- Bônus temporário de20% da ultimate tem multiplicador separado: 1,20×1,20=1,44 enquanto ambos estão ativos. Asset, código e textos atualizados; C# compilado sem erros. Teste de gameplay pertence a Raphael.


## Shadowmane — efeitos visuais refeitos (Raphael, 14 out)

- Raphael pediu efeitos novos e bonitos para as quatro skills, coerentes com a descrição, usando como sugestão a galeria do Cartoon FX Remaster (Jean Moreno). O pacote é pago e não estava na máquina: nada foi comprado nem baixado. A galeria serviu só de referência de estilo; tudo foi recriado no motor procedural do jogo.
- Linguagem visual: fumaça cartunesca de tinta, com contorno e sombreamento em dois tons, que se desfaz por erosão em vez de ficar transparente; clarões fortes no impacto; veneno verde-limão com toque violeta (Dark/Poison).
- Shadow Wave: tinta puxada para as patas, golpe no chão, onda negra que se curva e cobre a linha inimiga inteira; quebra em cada alvo com clarão, estilhaços e um anel fechando sobre a cabeça (atordoamento).
- Shadow Sting: espinho carregando na cauda, rastro de tinta no avanço, espinho atravessando o alvo pelas costas, cruz de luz e tinta espirrando no rosto (cegueira).
- Poison Breath: inspira partículas verdes, sopra um cone contínuo de gás e sobe uma nuvem com caveiras tóxicas, bolhas e poça em cada inimigo.
- Shadow Veil: círculo rúnico no chão, coluna de fumaça e véu se fechando, sumiço no instante do impacto com anéis descendo, olhos de predador piscando e rajadas subindo (+ataque, +velocidade).
- Código: shader novo `ShadowmaneVfx` (formas Ink, Skull, Spike, Eye, Rune) e `MonsterSpellFx.Shadowmane.cs` reescrito, no ramo `codex/shadowmane-ajustes-halan`, sem commit. C# do jogo compilado com Roslyn sem erros; o shader só compila no Unity. Falta Raphael testar e aprovar.


## Movimento orgânico dos bichos (Raphael, 14 out)

- Diagnóstico: o `BoneMotion` refazia a pose do zero a cada quadro, com senos, sem memória entre quadros, e por isso o movimento ficava duro. Solução só em código, em `BoneMotion.Organic.cs`. Pescoço, cauda e membrana das asas seguem a pose com mola de segunda ordem (t3ssel8r). A troca de movimento se funde em 0,22 s. O descanso tem respiração de ritmo variável e um olhar em volta por ruído suave. Os ossos que dão o golpe não levam mola, para o dano continuar caindo junto com o golpe.
- Primeira afinação (amortecimento 0,3 a 0,6) ficou "esqueleto de borracha / tecido ao vento", nas palavras do Raphael. A afinação atual, com amortecimento perto de 1 e limite de dobra por osso de 6° a 14°, ele aprovou como melhor.
- Noct: a morte com asas moles foi aprovada (antes ele flutuava apoiado na asa). A caminhada com IK deixou as pernas girando rápido, porque o pé não era restaurado a cada quadro. Raphael pediu para voltar à caminhada antiga, mantendo só o pé reto. Shadowmane com a camada orgânica foi aprovado; a caminhada de quadrúpede com pés plantados por IK fica.
- Shadow Wave refeito: empina, bate as patas no chão em 0,48 s (quando a onda do efeito nasce) e fica abaixado empurrando até o impacto. Shadow Sting refeito: cauda erguida como a de um escorpião, bote em arco, chicote da base para a ponta no instante do dano. Formas conferidas por simulação offline no `shadowmane.glb`. Falta Raphael testar no Unity.
