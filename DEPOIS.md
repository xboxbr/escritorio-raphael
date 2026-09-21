# Depois da entrevista — git e Unity

Só quando a IA já tiver nome em `.cursor/rules/identidade.mdc`.

## Git (conta pessoal)

Uma conta GitHub, a sua. **HTTPS**. Sem `gh`, sem chave SSH de outro PC.

1. Instalar [Git for Windows](https://git-scm.com/download/win) (Git Credential Manager marcado).
2. No terminal, **seu** nome e o e-mail da sua conta GitHub:

```
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@do-github.com"
```

3. Criar um repositório **privado** na sua conta (site do GitHub, sem README).
4. Nesta pasta:

```
git init
git add .
git commit -m "Escritório inicial"
git branch -M main
git remote add origin https://github.com/SEU_USER/SEU_REPO.git
git push -u origin main
```

O Cursor já logado no GitHub resolve o HTTPS.

## Unity (org do jogo)

Clonar **ao lado** deste escritório, não dentro:

```
pkld/
  escritorio/     ← esta pasta (seu git)
  unity/          ← git clone https://github.com/game-pkld/unity.git
```

Unity Hub → Open → `unity`. Editor **6.3 LTS** (`6000.3.23f1`). Play: a cápsula anda.

Documentação canônica do jogo (se precisar atualizar o cérebro): [`game-pkld/docs`](https://github.com/game-pkld/docs).

Não fazer `git push --force`. Não commitar `Library/`.
