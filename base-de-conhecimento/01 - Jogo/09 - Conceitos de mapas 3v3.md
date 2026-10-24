---
tags: [jogo, mapas, 3v3, conceito]
status: em-construcao
criado: 2026-10-24
---

# 09 - Conceitos de mapas 3v3: luz e trevas

Pedido do Raphael (24 out 2026): mais dois conceitos de arena 3v3, um de luz e um de trevas, sem a obrigação de serem ilhas flutuantes. As arenas prontas: Rift (trevas, disco flutuante), Zênite (luz, disco flutuante), Clareira Antiga (floresta, disco com grama). Os dois abaixo saem do disco: um é chão de verdade, o outro é uma plataforma dentro de um lugar fechado.

## Luz · Santuário das Marés (praia sagrada ao amanhecer)

- **Onde:** uma enseada de areia branca na maré baixa. A luta acontece sobre um grande círculo de pedra clara meio enterrado na areia, com sulcos de água do mar correndo entre as lajes. Ao fundo, o mar calmo e um sol nascendo baixo; dos lados, colunas de coral branco e pedras com conchas; na frente da câmera, só areia molhada refletindo o céu.
- **Luz:** sol baixo e quente vindo de trás, reflexos no chão molhado, névoa fina de maresia. Clara como o Zênite, mas mais fresca (azul e dourado em vez de ouro e laranja).
- **O que o torna diferente:** o chão reflete, a água corre pelos sulcos e a maré sobe e desce de leve nas bordas. Não flutua: a borda do mapa é a linha da água.
- **Peças novas (Tripo):** coluna de coral branco quebrada, pedra com conchas e estrela-do-mar, altar de conchas com uma pérola, âncora antiga coberta de musgo.
- **Peças reaproveitadas:** cristal de luz do Zênite nas rochas, braseiro do Zênite como tocheiro de pedra.
- **Aura:** clara (0,1 em repouso, 0,14 na skill), como no Zênite.

### Prompt da imagem (Gemini)

```
Cena de jogo estilo fantasia pintada à mão, vista de cima em ângulo de 35 graus como câmera de batalha de jogo mobile, formato 16:9. Uma enseada de areia branca na maré baixa ao amanhecer. No centro, um grande círculo de pedra clara meio enterrado na areia, com sulcos onde corre água do mar, e espaço vazio no meio para seis criaturas lutarem. Ao fundo, o mar calmo e um sol baixo dourado nascendo; dos lados, colunas quebradas de coral branco, pedras com conchas e estrelas-do-mar, um pequeno altar de conchas com uma pérola brilhando. Areia molhada refletindo o céu azul e dourado, névoa fina de maresia, luz quente vindo de trás. Sem personagens, sem texto, cores limpas e claras, estilo coerente com um jogo de criaturas colecionáveis.
```

## Trevas · Catedral Submersa (ruína afundada, luar pela água)

- **Onde:** o interior de uma catedral antiga afundada, vista de dentro. A luta acontece numa plataforma de pedra escura que sobrou do piso, no meio de um salão alagado: água negra parada em volta, colunas góticas subindo até se perderem na escuridão, vitrais quebrados lá no alto por onde entra o luar azul em feixes. Candelabros apagados pendem tortos; algas e correntes nas colunas.
- **Luz:** quase nenhuma luz própria. Feixes de luar azul descendo dos vitrais, reflexos trêmulos na água, velas verdes fantasmagóricas em alguns nichos. Mais escuro que o Rift, com azul e verde no lugar do roxo.
- **O que o torna diferente:** é um lugar fechado. Não tem céu nem borda flutuante: a câmera vê paredes, colunas e o teto sumindo no escuro. A água em volta reflete os feixes de luz e as criaturas.
- **Peças novas (Tripo):** coluna gótica com algas e corrente, candelabro de ferro caído, vitral quebrado em arco (peça de parede), estátua de anjo sem cabeça coberta de limo.
- **Peças reaproveitadas:** escombro e cristal pequeno do Rift (como entulho), braseiro do Vale do Eclipse com a chama verde.
- **Aura:** fraca (0,02 em repouso, 0,1 na skill), como no Rift.

### Prompt da imagem (Gemini)

```
Cena de jogo estilo fantasia sombria pintada à mão, vista de cima em ângulo de 35 graus como câmera de batalha de jogo mobile, formato 16:9. O interior de uma catedral antiga afundada: um salão alagado com água negra parada, e no centro uma plataforma de pedra escura que sobrou do piso, vazia no meio para seis criaturas lutarem. Colunas góticas cobertas de algas e correntes enferrujadas sobem até se perder no escuro, vitrais quebrados lá no alto deixam entrar feixes de luar azul que refletem trêmulos na água. Candelabros de ferro caídos, uma estátua de anjo sem cabeça coberta de limo, velas verdes fantasmagóricas em nichos. Sem céu, lugar fechado, muito escuro com azul e verde, reflexos na água. Sem personagens, sem texto, estilo coerente com um jogo de criaturas colecionáveis.
```

## Como seguem

1. Raphael gera as duas imagens e escolhe (ou manda refazer).
2. Com a imagem aprovada, eu monto a estrutura no código (chão, luz, câmera, água) com as peças que já temos.
3. Raphael gera as peças novas na Tripo pelos prompts que eu passo depois, como na Clareira.

## Notas relacionadas

- [[00 - Overview]] · [[04 - Recortes de inspiração]]

## Em construcao (24 out 2026, noite)

Raphael aprovou as duas imagens do Gemini. Estrutura no codigo: `MaresArena.cs` e `CatedralArena.cs` (commit 014b7dc na main), texturas do SpriteCook em `Cenario/Resources/Mares` e `Catedral` (anel de runas, areia, vitral, parede). Faltam as pecas da Tripo. Tarefas no Linear: Santuario das Mares e Catedral Submersa.
