# 🚀 Fluxo Git Prático: Simulação de Projeto Colaborativo

Este repositório documenta uma simulação prática de um fluxo de trabalho colaborativo utilizando Git e GitHub. O objetivo é consolidar o aprendizado dos comandos essenciais do Git em um cenário que replica o desenvolvimento de um projeto em equipe, incluindo a gestão de branches, merges e resolução de conflitos.

---

## 💡 Sobre o Projeto

Este projeto foi desenvolvido como parte de um roteiro de estudos para aprofundar o conhecimento em Git. Ele simula as etapas típicas de um desenvolvimento colaborativo, desde a inicialização do repositório até a criação de tags de versão e a resolução de divergências no histórico.

---

## 🎯 Etapas da Simulação

A simulação é dividida em etapas que cobrem os seguintes conceitos e comandos do Git:

### Etapa 1: Preparação do Projeto

- Criação de um novo repositório no GitHub.
- Clonagem do repositório localmente.
- Criação e primeiro commit de um arquivo `index.html`.
- **Comandos:** `git clone`, `git init`, `git add`, `git commit`, `git push`.

### Etapa 2: Criação e Uso de Branches

- Criação de uma nova branch para uma funcionalidade (`feature/header`).
- Adição de um `<header>` ao `index.html` e commit na nova branch.
- **Comandos:** `git checkout -b`, `git add`, `git commit`, `git push`.

### Etapa 3: Merge com a Branch Principal

- Retorno à branch `main`.
- Mesclagem da `feature/header` na `main`.
- **Comandos:** `git checkout`, `git merge`, `git push`.

### Etapa 4: Simulando um Conflito

- Criação de uma nova branch para outra funcionalidade (`feature/footer`).
- Adição de um `<footer>` na `feature/footer` e commit.
- Edição da `main` no mesmo local, criando uma alteração conflitante.
- Tentativa de merge da `feature/footer` na `main`, resultando em conflito.
- Resolução manual do conflito e novo commit.
- **Comandos:** `git checkout -b`, `git add`, `git commit`, `git push`, `git merge`.

### Etapa 5: Criação de uma Tag de Versão

- Criação de uma tag de versão (`v1.0.0`) após a integração das funcionalidades.
- **Comandos:** `git tag -a`, `git push --tags`.

### Etapa 6: Comandos Extras para Revisão

- Exploração de comandos para visualizar o histórico e o estado do repositório.
- **Comandos:** `git log --oneline --graph --all`, `git status`, `git diff`, `git remote -v`.

---

## 🛠️ Como Reproduzir a Simulação

Para reproduzir este projeto e praticar os comandos, siga as instruções detalhadas no arquivo `roteiro.md` anexo.

---

## ✨ Comandos Utilizados (Resumo)

- `git clone`
- `git checkout -b`
- `git merge`
- `git push`
- `git tag`
- `git log`
- `git status`
- `git diff`
- `git remote -v`
- `git add`
- `git commit`

---

Este projeto é uma excelente ferramenta para solidificar conhecimentos em Git, especialmente no que tange ao trabalho colaborativo e à gestão de histórico.

```

```
