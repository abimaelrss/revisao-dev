# 🚀 Simulação de Fluxo Completo de Git

Este repositório documenta uma simulação completa de um fluxo de trabalho Git, projetada para colocar o usuário no papel de um Desenvolvedor Junior. O objetivo é praticar a criação de novas funcionalidades, a resolução de conflitos e o versionamento de projetos, consolidando o conhecimento em Git e GitHub.

---

## 💡 Sobre o Projeto

Este projeto é um roteiro prático que simula um ciclo de desenvolvimento de software, desde a inicialização de um repositório Git até a conexão com um ambiente remoto (GitHub) e a gestão de versões. Ele enfatiza o uso de boas práticas de commits e o entendimento de cenários comuns no dia a dia de um desenvolvedor.

---

## 🎯 Etapas da Simulação

A simulação é dividida em etapas que cobrem os seguintes conceitos e comandos do Git:

### 1. Inicialização do Projeto

- Criação de um diretório local e inicialização do repositório Git.
- **Comandos:** `git init`.

### 2. Criação de Commits Básicos

- Adição de arquivos e realização de commits com mensagens claras e semânticas.
- **Comandos:** `git add .`, `git commit -m`.

### 3. Criação e Troca de Branches

- Criação de uma nova branch (`feature/login`) para desenvolver uma nova funcionalidade (tela de login).
- Realização de alterações e commit na nova branch.
- **Comandos:** `git branch`, `git checkout`, `git switch -c`.

### 4. Merge da Branch (sem conflitos)

- Retorno à branch `main` e integração da `feature/login` sem ocorrência de conflitos.
- **Comandos:** `git checkout`, `git merge`.

### 5. Simulação de Conflito

- Criação de uma nova branch (`feature/home`).
- Alteração da mesma linha em `index.html` tanto na `feature/home` quanto na `main`.
- Tentativa de merge, resultando em um conflito.
- Resolução manual do conflito, `add` e novo commit.
- **Comandos:** `git checkout -b`, `git add`, `git commit -m`, `git merge`.

### 6. Análise do Histórico

- Visualização do histórico de commits e comparação de diferenças.
- **Comandos:** `git log --oneline --graph --all`, `git diff`.

### 7. Conectar a um Repositório Remoto

- Criação de um repositório vazio no GitHub e conexão do repositório local.
- Envio das branches `main` e das branches de feature para o remoto.
- **Comandos:** `git remote add origin`, `git branch -M main`, `git push -u origin main`, `git push origin <branch>`.

### 8. Criar Tags de Versão

- Simulação de uma nova versão da aplicação (`v1.0`) e criação de uma tag.
- **Comandos:** `git tag -a`, `git push origin <tag>`.

### 9. Limpeza de Branches

- Exclusão de branches locais e remotas após serem mescladas.
- **Comandos:** `git branch -d`, `git push origin --delete`.

---

## 🛠️ Como Reproduzir a Simulação

Para reproduzir este projeto e praticar os comandos, siga as instruções detalhadas no arquivo `roteiro.md` anexo.

---

## ✨ Comandos Utilizados (Resumo)

- `git init`
- `git add`
- `git commit -m`
- `git branch`
- `git checkout`
- `git switch -c`
- `git merge`
- `git log`
- `git diff`
- `git remote add origin`
- `git branch -M`
- `git push`
- `git tag -a`
- `git branch -d`
- `git push origin --delete`

---

Este projeto é uma ferramenta essencial para qualquer Desenvolvedor Junior que busca dominar o Git e entender o fluxo de trabalho em equipes de desenvolvimento.
