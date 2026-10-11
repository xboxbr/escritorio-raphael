---
tags: [aprendizados, insights]
data: 2026-10-02
status: revisado
---

# 00 — Insights e Padrões

Ainda cedo. Grava quando o padrão aparecer ≥ 2 vezes.

### Feeling antes de sistema

**O que**: Cápsula andando na Unity tirou o medo do Halan mais que conversa sobre engine.
**Por quê**: Play visível > plano abstrato.
**Como aplicar**: Cada fase do [[03 - Plano de execução]] termina num build que o Luan joga. Sem Play, não avança.

### Modelo ≠ casa

**O que**: Hype de GPT-6 Astra misturou modelo (OpenAI) com ferramenta (Codex vs Cursor).
**Por quê**: Redes vendem o modelo; o Raphael precisa do editor + vault + Unity deste repo.
**Como aplicar**: Novo flagship → pergunta “em qual harness, neste Windows, neste Unity?” antes de trocar assinatura.

### Douglas não é “sim, mestre”

**O que**: Na reunião o Halan descreveu a IA como quem concorda e executa.
**Por quê**: Operação pede tradeoff, não bajulação (regra do escritório).
**Como aplicar**: Executa o pedido; aponta o custo. Recorte de IP, teto de poder e daily já nasceram assim — a kickoff moveu o daily pra ~1h; o custo continua válido.

### Kickoff sem o slide 15 ainda tem um Play

**O que**: Duas horas não nomearam o próximo Play no fim. No meio, a sala descreveu o mínimo: quadrado, times que se batem.
**Por quê**: Refs e modos enchem o relógio; o cubo cabe numa frase.
**Como aplicar**: Se a call não fechar o item 15, Douglas nomeia o mínimo que já foi dito e trata o resto como homework.

### Silhueta vence textura e cor

**O que**: Cubo com albedo de pedra ainda lê como bloco. Burst colorido ainda lê como a mesma skill.
**Por quê**: O olho fecha a forma primeiro; tiling e hue vêm depois.
**Como aplicar**: Rocha de previz = esferas amontoadas. Skill = formato diferente (espinho, raio, pilar), não o mesmo flash pintado.

### Serrilhado ≠ cubo

**O que**: A previz lia “Minecraft” por dois motivos juntos: primitivas `Cube` na caverna e anti-aliasing desligado (URP Deferred, MSAA=1, câmera `None`).
**Por quê**: Filtro (SMAA, bloom, grain) suaviza pixel da borda. Não muda silhueta de parede-caixa. Fotoreal de bicho continua Meshy, não post-process.
**Como aplicar**: Jagged → SMAA High na câmera (TAA fantasma nos VFX). Quadrado → cilindro/esfera, não cubo. Não vender filtro como arte final.

### Osso de humanoide, movimento no código

**O que**: Remesh da Meshy estragou o UV da Escama. O rig de quadrúpede da Tripo no Farpa saiu torto; o modo humanoide no mesmo corpo serviu. Respirar, andar e atacar são o `BoneMotion`, não um clipe da Meshy.
**Por quê**: A biblioteca de animação da Meshy não aceitou esses corpos, e o export de esqueleto da Tripo no plano grátis não vinha. O FBX humanoide entrou, e o código escolhe o eixo e deita o ciclo.
**Como aplicar**: Não remeshar modelo que já tem textura boa. Quadrúpede estranho → rig humanoide na Tripo + `BoneMotion`. Ver [[00 - Rig automático]].

### Malha do bicho nasce em 10 mil triângulos

**O que**: A Meshy em qualidade alta, levada à Tripo, volta com pedido de recriar a malha.
**Por quê**: A retopologia da Tripo existe para essa malha densa e mira no máximo 20.000 triângulos. Remesh depois da textura já estragou UV.
**Como aplicar**: Gerar o bicho já em torno de 10.000 triângulos (faixa 8.000–15.000) e mandar essa malha para a Nira. Não subir a malha de qualidade alta.

### Canto do mapa ≠ canto da câmera

**O que**: Colunas de tijolo no canto geométrico da sala (`z ≈ -7.5`, boca da caverna) não apareceram no Play.
**Por quê**: Câmera 3/4 em `(5.1, 5.7, -9)` deixa esses cantos fora do frustum; o olho só vê o que a lente enquadra.
**Como aplicar**: Peça “canto visível” → colocar no frustum (perto das paredes laterais, `z ≈ -1.6`), não no canto do mesh.

## Notas relacionadas

- [[00 - Log de Decisões]] · [[00 - Index]]
