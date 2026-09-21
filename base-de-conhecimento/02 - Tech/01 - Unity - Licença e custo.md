---
tags: [tech, unity, licença]
data: 2026-09-08
status: revisado
---

# 01 — Unity: licença e custo

O que “licença” significa neste motor, o que pagamos, quando, e o contraste MIT (Godot). Premissa de trabalho: Unity. Números em USD.

> [!info] Fonte primária: [Unity Plans](https://unity.com/products), [Personal](https://unity.com/products/unity-personal), [pricing 2026](https://unity.com/products/pricing-updates), [Editor Software Terms](https://unity.com/legal/editor-terms-of-service/software) (atualizado 30 jun 2026). Godot: [FAQ](https://docs.godotengine.org/en/stable/about/faq.html) / [MIT](https://docs.godotengine.org/en/stable/about/complying_with_licenses.html).

> [!warning] Não é parecer jurídico. Termos mudam; Unity atualiza preço no renewal.

## Uma frase

Não compramos a Unity. Eles autorizam o **Editor** (onde se trabalha) e o **Runtime** (o player dentro do APK). O jogo é nosso. Sem receita neste loop: **Personal, US$ 0**. Não há royalty da Unity sobre venda do jogo (Runtime Fee cancelada em 2024).

## O que é licença

Permissão de uso, não escritura do motor. Analogia ruim de “comprar Visual Studio”: mais perto de assinar o direito de usar a ferramenta e de **embarcar o player** no binário. Cadeira (seat) = uma pessoa no editor, um uso por vez (pode instalar em dois PCs).

Conteúdo C#, arte, nome: nosso. Unity continua dona da Unity. Se os créditos do jogo listam atribuições, os termos pedem a linha “made with Unity” + copyright da Unity ([sec. 2.12](https://unity.com/legal/editor-terms-of-service/software)).

## Quanto / quando / por quê

| Quando | Paga | Por quê |
|---|---|---|
| Agora (Loop 1, sem loja) | US$ 0 — Personal | Indivíduo fazendo o próprio jogo: “amount generated in connection with your use of the Software” nos últimos 12 meses. |
| Cruzou US$ 200k / 12 meses | Pro: **US$ 2.310/ano** pré-pago por cadeira, ou **US$ 210/mês** | Obrigatório no dia. Inclusive protótipo interno. |
| US$ 25M+ / 12 meses | Enterprise (custom) | Fora deste escritório. |

**Total Finances** (termos 1.1):

- Pessoa física, jogo próprio: o que o **uso da Unity** gera — não o salário PortX.
- **Pessoa jurídica**: receita bruta **+ funding** da entidade. Abrir empresa e capitar conta mesmo com jogo a R$ 0.
- Prestando serviço pra terceiro: conta a receita/funding **do cliente**.

Não misturar Personal e Pro na mesma organização.

Runtime: “distribute the Unity Runtime without royalty, revenue share, or a runtime fee” para Unity 6 e versões anteriores, desde que a cadeira/tier esteja em dia.

## O que o dinheiro compra (Pro)

Não é fatia do jogo. É:

- Direito de **continuar** usando Unity depois do teto Personal.
- Build pra console e Apple Vision Pro (Personal: PC, web, Android, iOS).
- Fila de suporte mais rápida; mais storage cloud Unity.
- Splash “Made with Unity”: no **Unity 6** já é opcional no Personal.

Não compra código-fonte (Enterprise). Asset Store, Ads, IAP plugin “incluído” como ferramenta — compras e receita de ads são outro contrato.

## MIT (Godot) — o que isso teria sido

MIT = pode usar, copiar, modificar, vender o **motor**. Jogo pode ser proprietário. Obrigação típica: incluir o texto da licença nos créditos. Sem cadeira, sem teto, sem plano anual.

Ajuda: previsibilidade e custo zero do engine. Não ajuda: o chão de mercado gacha (IAP/ads/contratar) que levou a premissa Unity.

## Fora da Unity (ship)

- Google Play: taxa de desenvolvedor (historicamente ~US$ 25, uma vez).
- Apple Developer: ~US$ 99/ano. iOS precisa de Mac.
- Comissão da loja: 15–30% da venda, independente da Unity.
- Cloud Unity (Version Control / Build): cota grátis; dá pra ignorar e usar git.

## Neste escritório

Não pagar agora. Um Halan no editor = Personal. Luan só jogando o build: sem cadeira. Luan no editor: Personal ainda grátis; Pro seria +1 cadeira.

## Notas relacionadas

- [[00 - Tech - Overview]] · [[00 - Godot vs Unity]] · [[00 - Log de Decisões]]

## Fontes

- https://unity.com/products
- https://unity.com/products/unity-personal
- https://unity.com/products/pricing-updates
- https://unity.com/legal/editor-terms-of-service/software
- https://docs.godotengine.org/en/stable/about/complying_with_licenses.html
