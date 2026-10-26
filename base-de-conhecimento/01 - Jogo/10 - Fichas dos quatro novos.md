---
tags: [jogo, bichos, skills, proposta]
status: ativa-no-jogo
criado: 2026-10-25
---

# 10 - Fichas dos quatro bichos do catálogo (Veinyx, Groveback, Pyrantis, Gildelle)

Pedido do Raphael (24 out, noite): os quatro bichos novos do catálogo do Halan entram no jogo com atributos do site, skills no estilo das propostas, efeitos visuais e movimentos. Texto abaixo é o que vai pro Halan revisar. Tudo já está no jogo (Bichos 16 a 19). Esqueletos do Tripo Studio: Veinyx, Groveback e Pyrantis em 25 out, Gildelle em 26 out (rig veio meio nomeado, meio numerado e sem osso de cabeça; o jogo tem um ramo próprio pra ele em `BoneMotion`).

Controles usados sem repetir os dos outros: Veinyx fica com Veneno e Bloqueio de Cura; Groveback com redução de velocidade e corte de dano; Pyrantis com Queimadura (ninguém tinha); Gildelle com redução de defesa, imunidade e corte de dano cíclico.

## Veinyx · Veneno / Pedra · a pantera de cristal (Épico, especial)

HP 133, atq especial 143, atq físico 113, def especial 143, def física 113, velocidade 143.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Efeito |
| -- | -- | -- | -- | -- | -- | -- |
| Espinho Venenoso (golpe) | Veneno | especial 40 | único | 90% | — | 30% de Veneno por 2 turnos (2 ticks de 5%) |
| Cristal Corrosivo (rajada) | Pedra | especial 55 | único | 85% | 2 | Defesa do alvo −25% por 2 turnos |
| Névoa Tóxica (estouro) | Veneno | especial 30 | grupo | 85% | 3 | cada acertado: 50% de Veneno por 2 turnos |
| Erupção de Veias (ultimate) | Pedra | especial 100 | único | 85% | fúria | Veneno por 3 turnos (3 ticks de 8%) e Bloqueio de Cura por 2 turnos |

**Passiva · Casca Cristalina:** com a vida abaixo de 50%, imune a reduções de atributo.
Movimentos: rajada frontal (cospe), arremesso, conjurar, rugido. Cores: ametista, magenta e verde tóxico.

## Groveback · Terra / Planta · o ogro da mata (Épico, físico)

HP 185, atq físico 122, atq especial 92, def física 167, def especial 157, velocidade 104.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Efeito |
| -- | -- | -- | -- | -- | -- | -- |
| Tromba de Raiz (golpe) | Terra | físico 45 | único | 95% | — | 20% de Velocidade −20% por 1 turno |
| Casca de Carvalho (rajada) | Planta | sem dano | si mesmo | — | 3 | Defesa +35% por 2 turnos e Regeneração 6% por 2 turnos |
| Raízes Vorazes (estouro) | Planta | físico 30 | grupo | 85% | 2 | todos acertados: Velocidade −30% por 2 turnos |
| Fúria da Floresta (ultimate) | Terra | físico 105 | único | 85% | fúria | Ataque do alvo −25% por 2 turnos; corta 25% do dano recebido por 2 turnos |

**Passiva · Casca Antiga:** +20% de Defesa durante a luta.
Movimentos: soco, postura de guarda, pisão, investida. Cores: casca e folha.

## Pyrantis · Fogo / Inseto · o louva-a-deus de brasa (Épico, especial)

HP 112, atq especial 165, atq físico 125, def especial 123, def física 113, velocidade 155.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Efeito |
| -- | -- | -- | -- | -- | -- | -- |
| Lâmina Ardente (golpe) | Fogo | especial 40 | único | 90% | — | 25% de Queimadura por 2 ticks |
| Dança das Foices (rajada) | Inseto | especial 65 | único | 85% | 2 | antes do golpe, Crítico +20 pontos por 1 turno |
| Enxame de Brasas (estouro) | Fogo | especial 30 | grupo | 85% | 3 | cada acertado: 40% de Queimadura por 2 ticks |
| Ceifa Incandescente (ultimate) | Fogo | especial 110 | único | 80% | fúria | Queimadura por 3 ticks; Velocidade +20% em si por 2 turnos |

**Passiva · Olho da Mantis:** +10 pontos percentuais de chance de crítico.
Movimentos: garra, golpe de asa (foices cruzadas), mergulho, pancada dupla. Cores: brasa, magma e carapaça vermelha.

## Gildelle · Metal / Fada · a kirin dourada (Épico, físico)

HP 154, atq físico 142, atq especial 122, def física 132, def especial 132, velocidade 151.

| Skill | Tipo | Dano | Alvo | Acerto | Recarga | Efeito |
| -- | -- | -- | -- | -- | -- | -- |
| Chifre Dourado (golpe) | Metal | físico 45 | único | 95% | — | 20% de Defesa −10% por 1 turno |
| Escudo de Ouro (rajada) | Fada | sem dano | si mesmo | — | 3 | corta 30% do dano recebido por 2 turnos; imune a efeitos negativos por 1 turno |
| Chuva de Agulhas (estouro) | Metal | físico 35 | grupo | 85% | 2 | cada acertado: 35% de Defesa −15% por 2 turnos |
| Julgamento Feérico (ultimate) | Fada | físico 110 | único | 85% | fúria | Poder das skills do alvo −30% por 2 turnos; cura 15% da própria vida |

**Passiva · Escamas Reluzentes:** a cada 3 turnos dela, começando no primeiro, corta 30% do dano recebido por 1 turno.
Movimentos: mordida (chifrada), conjurar, rabo (chicote da cauda), mergulho (salto). Cores: ouro, branco e violeta feérico.

## Descrições como estão nas fichas do jogo

As descrições completas, no estilo das outras fichas, estão nos assets `Bicho 16` a `Bicho 19` em `Assets/Game/Collection/Resources/`.

## Notas relacionadas

- [[08 - Fichas propostas]] · [[00 - Overview]]
