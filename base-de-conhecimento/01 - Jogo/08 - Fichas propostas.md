---
tags: [jogo, bichos, skills, proposta]
status: ativa-no-jogo
criado: 2026-10-24
---

# 08 - Fichas propostas para os oito bichos sem ficha

Pedido do Raphael (24 out 2026): sugestões de ficha para os bichos que ainda têm skills provisórias, no estilo das cinco fichas prontas (Hellflame, Shadowmane, Frostfang, Vaelith, Cinderplate), sem repetir e sem desbalancear. Tudo aqui é **proposta**: o Halan decide, o Raphael manda a ficha final em imagem, e aí a skill entra no jogo pelo pacote completo (`fichas-de-criaturas.mdc`).

## Como as fichas prontas foram lidas

| Bicho | Papel | Mecânica que o define |
| -- | -- | -- |
| Hellflame | canhão de vidro especial, anti-suporte | rouba buffs, bloqueia cura e buff, paga vida pela ultimate, cresce quando inimigos caem a 50% |
| Shadowmane | controle físico | atordoa em área no básico, cegueira, veneno em acúmulos, véu invisível |
| Frostfang | ciclo de poder | Cristal Yuki a cada 4 turnos muda o que cada skill faz; congela; rouba buffs antes do golpe |
| Vaelith | risco e recompensa | voo, paga vida atual, zera recargas ao matar, poder sobe com a vida perdida, chamas que seguram em 1 HP |
| Cinderplate | tanque que se enterra | reduz ataque, enterra, treme a terra em área, ultimate limpa e cura, passiva de defesa |

Padrões que valem para as novas: **golpe** sem recarga ou curta (0 a 2), poder 30 a 60; **rajada** com recarga 1 a 4, poder 0 a 100 ou efeito forte sem dano; **estouro** muitas vezes em área, poder 20 a 60, recarga 0 a 3; **ultimate** exige fúria, poder 90 a 120 em um alvo ou 45 a 60 em grupo; **passiva** permanente ou cíclica. Acerto entre 60% e 100%. Tipo de golpe (físico ou especial) segue o atributo forte do bicho.

## O que o motor já roda

Efeitos: redução e aumento de ataque, defesa, velocidade, crítico, poder; enterrar e desenterrar; limpar; cura e regeneração; proteção contra debuff; corte de dano (oculto); roubo e bloqueio de buff; bloqueio de cura; voo; chamas de 1 HP; cegueira; atordoar, congelar, dormir, petrificar, medo, paralisia, confusão; veneno, queimadura, sangramento, maldição (ticks); camuflagem e oculto; imunidade a debuff; provocar; silêncio; bloqueio de fúria. Cada efeito tem chance, duração, "em si mesmo", condição (com ou sem Cristal Yuki) e "antes do golpe".

Regras únicas: custo de vida, bônus contra alvo com pouca vida, velocidade ao matar, bloqueio de cura que passa adiante, recargas zeradas ao matar, fúria extra, poder que cresce com a vida perdida, passiva com velocidade, passiva cíclica a cada N turnos, acerto e poder condicionais ao Cristal.

Passivas prontas: precisão, chance de crítico, dano geral, defesa, "inimigo a 50%", "qualquer skill de Fogo", instinto predador, ciclo (Zero Absoluto).

Tudo que foge disso está marcado **novo no motor**, com a alternativa pronta ao lado. Regra da casa: no máximo uma regra nova por bicho, e só se ela for a graça do bicho.

## Distribuição de controles (um dono por controle duro)

| Controle | Dono | Já tem |
| -- | -- | -- |
| Atordoar | Shadowmane | sim |
| Congelar | Frostfang | sim |
| Sono | Blossom Queen | proposta |
| Petrificar | Lithon | proposta |
| Paralisia | Thunderhawk (e um toque no Grizzleback) | proposta |
| Medo | Noct | proposta |
| Confusão | Eclipse | proposta |
| Provocar | Grizzleback | proposta |
| Silêncio | Eclipse | proposta |
| Bloqueio de fúria | Noct | proposta |

Ticks: veneno (Shadowmane), sangramento (Lithon), maldição (Eclipse e Noct, um cada). Regeneração: Aurion, Blossom Queen, Grizzleback, cada um de um jeito.

---

## Aurion · Dragão / Luz · o paladino

Atributos: HP 92, velocidade 14, ataque físico 18 (o maior do elenco), defesa física 14. Papel: linha de frente física que se sustenta com a própria luz e limpa o que jogam nele. Compensa o Hellflame (que bloqueia cura) sendo o único que cura de verdade.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Condição |
| -- | -- | -- | -- | -- | -- | -- |
| Presa Luminosa (golpe) | Luz | físico 40 | único | 95% | — | 25% de chance de Cegueira (−30% precisão) por 1 turno |
| Bênção da Aurora (rajada) | Luz | sem dano | si mesmo | — | 3 | Limpar (remove todos os debuffs), Regeneração 10% por 2 turnos, Imunidade a debuff por 1 turno |
| Investida Dracônica (estouro) | Dragão | físico 70 | único | 85% | 2 | Defesa do alvo −20% por 2 turnos |
| Julgamento Solar (ultimate) | Luz | físico 60 | grupo | 80% | fúria | Cegueira (−50% precisão) por 2 turnos em todos os acertados |

**Passiva · Coração de Dragão:** na primeira vez que a vida cai a 50% ou menos na luta, cura 25% da vida máxima e ganha Regeneração 5% por 3 turnos. Uma vez por luta.
**Novo no motor:** a passiva "inimigo a 50%" do Hellflame existe; a versão "eu mesmo a 50%" é uma variação pequena dela. Alternativa pronta: +15% de defesa (como a do Cinderplate, com outro número).

Descrição no estilo da ficha: "Presa Luminosa: crava as presas envoltas em luz no alvo, causando dano de Ataque Físico do tipo Luz de poder 40. 25% de chance de cegar o alvo por 1 turno, reduzindo a precisão em 30%."

## Blossom Queen · Planta / Lutador · a rainha das pétalas

Atributos: HP 78, velocidade 12, ataque especial 17, defesa especial 13. Papel: atacante especial que enfraquece o inimigo com pólen e se recupera pela seiva; o lado Lutador entra num chute que fecha o combo.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Condição |
| -- | -- | -- | -- | -- | -- | -- |
| Pétalas Cortantes (golpe) | Planta | especial 35 | único | 90% | — | 20% de chance de Velocidade −15% por 1 turno |
| Pólen Soporífero (rajada) | Planta | especial 25 | grupo | 85% | 3 | para cada acertado, 40% de chance de Sono por 1 turno (acorda ao ser atingido) |
| Chute Florescente (estouro) | Lutador | especial 70 | único | 80% | 2 | após o golpe, Regeneração 8% por 2 turnos em si mesma |
| Jardim Real (ultimate) | Planta | especial 60 | grupo | 90% | fúria | Redução de Poder 25% por 2 turnos em todos; Regeneração 10% por 3 turnos em si mesma |

**Passiva · Seiva Real:** a cada 3 turnos dela, começando no primeiro (1º, 4º, 7º...), ganha Regeneração 8% por 2 turnos. Mesmo mecanismo cíclico do Zero Absoluto, com outro efeito: **já roda**.

## Eclipse · Luz / Trevas · as duas faces

Atributos: HP 84, velocidade 11, ataque especial 15, defesa especial 16. Papel: controlador especial que confunde e cala; o único com duas faces de elemento, e isso é a graça dele.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Condição |
| -- | -- | -- | -- | -- | -- | -- |
| Lampejo (golpe) | Luz | especial 40 | único | 90% | — | 30% de chance de Cegueira (−30% precisão) por 1 turno |
| Sussurro Noturno (rajada) | Trevas | especial 30 | único | 85% | 2 | 50% de chance de Confusão por 1 turno (50% de bater em si mesmo e perder a vez) |
| Eclipse Total (estouro) | Trevas | especial 35 | grupo | 85% | 3 | para cada acertado, 50% de chance de Silêncio por 2 turnos (não usa skill de suporte) |
| Corona (ultimate) | Luz | especial 95 | único | 80% | fúria | Maldição por 3 ticks (bloqueia cura enquanto dura) e Bloqueio de Fúria por 2 turnos |

**Passiva · Fase:** cada skill de Luz que ele usa dá +30% de poder à próxima skill de Trevas, e cada skill de Trevas dá +30% à próxima de Luz. Não acumula.
**Novo no motor:** alternância entre elementos não existe. Alternativa pronta: +15% de precisão (ele enxerga no escuro), passiva de precisão já existe.

## Grizzleback · Terra / Normal · o tanque que provoca

Atributos: HP 100, velocidade 9, ataque físico 16, defesa física 18 (a maior do elenco). Papel: tanque de verdade: puxa os golpes para si, aguenta e devolve. Diferente do Cinderplate, que some no chão; o Grizzleback fica e apanha.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Condição |
| -- | -- | -- | -- | -- | -- | -- |
| Patada (golpe) | Normal | físico 45 | único | 95% | — | 15% de chance de Paralisia por 1 turno (50% de não agir) |
| Rugido da Toca (rajada) | Terra | sem dano | si mesmo | — | 3 | Provocar por 2 turnos (inimigos só miram nele) e Defesa +30% por 2 turnos |
| Tremor Pesado (estouro) | Terra | físico 30 | grupo | 85% | 2 | para cada acertado, 35% de chance de Paralisia por 1 turno |
| Avalanche de Garras (ultimate) | Terra | físico 110 | único | 85% | fúria | Defesa do alvo −30% por 2 turnos; cura 15% da vida máxima em si mesmo |

**Passiva · Fôlego de Urso:** Regeneração 4% da vida máxima no começo de cada turno dele, a luta inteira. **Já roda** (regeneração permanente).

Nota de balanceamento: Provocar junto com a maior defesa do elenco é forte; por isso a rajada não dá dano e a recarga é 3. Se o Halan achar demais, Provocar por 1 turno.

## Lithon · Pedra · o cristal que sangra

Atributos: HP 96, velocidade 8, ataque físico 14 e especial 14 (equilibrado), defesas 13/12. Papel: dano constante por sangramento e um único controle pesado (petrificar), coerente com o cristal.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Condição |
| -- | -- | -- | -- | -- | -- | -- |
| Lasca de Cristal (golpe) | Pedra | físico 40 | único | 90% | — | 30% de chance de Sangramento por 2 ticks (1% da vida máxima por tick; bloqueia cura enquanto dura) |
| Olhar de Pedra (rajada) | Pedra | especial 20 | único | 80% | 3 | 70% de chance de Petrificar por 1 turno (perde a vez) |
| Chuva de Estilhaços (estouro) | Pedra | físico 35 | grupo | 85% | 2 | para cada acertado, 50% de chance de Sangramento por 2 ticks |
| Prisma Devastador (ultimate) | Pedra | especial 100 | único | 90% | fúria | antes do golpe, Crítico +50 pontos percentuais em si mesmo por 1 turno (quase sempre crítico) |

**Passiva · Facetas:** +15 pontos percentuais de chance de crítico durante a batalha. Passiva de crítico **já roda**.

## Noct · Dragão / Trevas · o colosso do pesadelo

Atributos: HP 120 (o maior), velocidade 6 (a menor), ataque físico 17, defesa física 19. Papel: lento e inevitável: cada golpe pesa, espalha medo e corta a fúria do inimigo. O contrapeso da velocidade baixa é o dano.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Condição |
| -- | -- | -- | -- | -- | -- | -- |
| Mordida Noturna (golpe) | Trevas | físico 50 | único | 90% | — | 25% de chance de Medo por 1 turno (50% de não agir) |
| Pesadelo (rajada) | Trevas | físico 30 | grupo | 80% | 3 | para cada acertado, 40% de chance de Medo por 1 turno |
| Asa Pesada (estouro) | Dragão | físico 85 | único | 75% | 2 | Bloqueio de Fúria por 2 turnos (a fúria do alvo não enche) |
| Noite Sem Fim (ultimate) | Trevas | físico 120 | único | 85% | fúria | Maldição por 3 ticks no alvo; Corte de dano 20% por 2 turnos em si mesmo |

**Passiva · Colosso:** +15% de dano geral em todos os golpes. Passiva de dano geral **já roda** e nenhum bicho pronto a usa.

## Tidepaw · Normal / Lutador · o monge da maré

Atributos: HP 78, velocidade 16, ataque especial 15. Papel: o mais rápido com o Thunderhawk; bate muitas vezes, limpa a si mesmo e desacelera o inimigo. Sem controle duro: a força dele é agir antes.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Condição |
| -- | -- | -- | -- | -- | -- | -- |
| Jato da Maré (golpe) | Normal | especial 45 | único | 95% | — | gera 5% de fúria extra |
| Postura Fluida (rajada) | Lutador | sem dano | si mesmo | — | 3 | Limpar; Velocidade +25% e Crítico +20 pontos por 2 turnos |
| Rasteira da Maré (estouro) | Lutador | especial 60 | único | 85% | 2 | Velocidade do alvo −30% por 2 turnos |
| Tsunami de Punhos (ultimate) | Lutador | especial 45 | grupo | 90% | fúria | Ataque −30% por 2 turnos em todos os acertados |

**Passiva · Ritmo da Maré:** +15% de velocidade durante a batalha. Regra de passiva com velocidade **já roda** (o Shadowmane usa 20%; aqui é só velocidade, sem ataque).

## Thunderhawk · Voador / Elétrico · a tempestade

Atributos: HP 78, velocidade 16, ataques 12/12, defesas 9/10. Papel: atacante aéreo de paralisia; frágil, então vive de agir primeiro e sair do alcance.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Condição |
| -- | -- | -- | -- | -- | -- | -- |
| Bicada Elétrica (golpe) | Elétrico | especial 40 | único | 90% | — | 25% de chance de Paralisia por 1 turno |
| Rasante (rajada) | Voador | físico 55 | único | 85% | 2 | após o golpe, entra em Voo até o próximo turno (evita ataques únicos e de área, como o Vaelith) |
| Tempestade de Penas (estouro) | Elétrico | especial 30 | grupo | 85% | 3 | para cada acertado, 35% de chance de Paralisia por 1 turno |
| Raio Celeste (ultimate) | Elétrico | especial 110 | único | 75% | fúria | Defesa do alvo −25% por 2 turnos |

**Passiva · Olho da Tempestade:** +15% de precisão durante a batalha. Passiva de precisão **já roda**.
Opcional (novo no motor): imune a Paralisia. Pequeno, mas é regra de imunidade seletiva, que não existe.

---

## Conferência de balanceamento

- **Poder total das ultimates:** Noct 120 único (lento, 6 de velocidade), Thunderhawk 110, Grizzleback 110, Lithon 100 (com crítico quase certo), Eclipse 95, Aurion 60 grupo, Blossom 60 grupo, Tidepaw 45 grupo. Entre o Frostfang (100, até 150 com Cristal) e o Vaelith (20 a 200).
- **Controle duro em área:** só Blossom (Sono 40%), Grizzleback (Paralisia 35%), Noct (Medo 40%) e Thunderhawk (Paralisia 35%), todos com recarga 2 a 3 e chance abaixo de 50%. O Shadowmane continua o rei do controle em área (Atordoar 80% no básico).
- **Sustentação:** Aurion (uma cura grande, uma vez), Blossom (regeneração cíclica), Grizzleback (regeneração constante de 4%). O Hellflame bloqueia cura e o Lithon sangra: os dois anulam exatamente esses três. Pedra, papel e tesoura.
- **Nenhum bicho** tem dois controles duros com chance acima de 50%, nem cura e provocação juntos.
- **Tipos de golpe:** físicos (Aurion, Grizzleback, Noct, Lithon no básico), especiais (Blossom, Eclipse, Tidepaw, Thunderhawk). Metade a metade, como nos prontos.

## O que seria novo no motor (resumo)

| Bicho | Regra | Tamanho | Alternativa pronta |
| -- | -- | -- | -- |
| Aurion | passiva "eu mesmo a 50%" (cura + regeneração, uma vez) | pequeno (variação da "inimigo a 50%") | +15% de defesa |
| Eclipse | alternância Luz/Trevas (+30% na próxima do outro elemento) | médio | +15% de precisão |
| Thunderhawk | imunidade só a Paralisia | pequeno | nenhuma (a passiva de precisão já basta) |

Os outros cinco entram inteiros com o que o motor já tem.

## Referências

Summoners War (SW): cada monstro com um papel claro, controle em área com chance e recarga, passiva que define o bicho. Pokeland (fangame anterior): tipos no bicho e no golpe, nomes curtos de skill. Nada foi copiado; os efeitos vêm da lista que o jogo já roda e os papéis preenchem o que as cinco fichas prontas deixaram em aberto.

## Notas relacionadas

- [[00 - Overview]] · [[07 - Kickoff 19 set]] · [[04 - Recortes de inspiração]]

Tarefa no Linear para o Halan analisar: POK-232 (24 out 2026), com o conteúdo desta nota inteiro na descrição.

## Efeitos visuais (24 out 2026)

Os 32 efeitos das skills propostas ja estao no jogo, guardados e sem uso na luta: `Arena3v3/MonsterSpellFx.Proposals.cs` e o shader `ModernVfx`. Toca-se pela Bancada de efeitos (Game > VFX), secao "Propostas". Pra ligar numa skill, o Motion recebe `proposta:<id>`.

## Ativadas no jogo (24 out 2026, noite)

Raphael mandou ativar sem esperar o Halan ("se ele nao gostar, muda depois"). As oito fichas estao nos assets `Bicho NN` como propostas aqui, com as alternativas prontas nas tres regras novas. Cada skill aponta `Motion = proposta:<id>` (efeito + movimento). Sem icones proprios ainda (glifo automatico).
