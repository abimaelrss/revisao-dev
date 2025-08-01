# 🔬 Simulação Git Aplicada: Gestão de Projetos de Pesquisa Agrícola

Este repositório documenta uma simulação prática de como o Git pode ser utilizado para versionar e gerenciar projetos de **pesquisa agrícola**. O objetivo é demonstrar a aplicação do controle de versão na organização de metodologias, coleta de dados, análises e geração de relatórios técnicos, promovendo rastreabilidade, colaboração e integridade científica.

---

## 💡 Sobre o Projeto

Este projeto simula o ciclo completo de experimentos agrícolas conduzidos por uma equipe técnica, utilizando o Git para organizar múltiplos fluxos de trabalho e integrar contribuições de diversos pesquisadores.

---

## 🎯 Etapas da Simulação

### Preparação do Ambiente: Montando o Laboratório Digital

- Criação da pasta raiz e inicialização do repositório Git.
- Configuração do usuário Git e definição da branch principal `master-pesquisa`.
- **Comandos:** `mkdir`, `cd`, `git init`, `git config`

### Passo 1: Início do Projeto de Pesquisa e Documentação Base

- Criação de `README.md`, pastas e arquivos base (`metodologia.md`, `protocolo-coleta-dados.md`).
- **Comandos:** `git status`, `git add .`, `git commit -m`

### Passo 2: Coleta de Dados de Campo (Branching e Merge)

- Criação da branch `dados/experimento-x`.
- Registro dos dados da semana 1 no arquivo `.csv`.
- Integração via `git merge`.
- **Comandos:** `git switch -c`, `git add`, `git commit`, `git merge`, `git branch -d`

### Passo 3: Corrigindo Metodologia com `amend`

- Correção da descrição de tratamentos no `metodologia.md`.
- Uso de `git commit --amend`.
- **Alerta sobre `push --force`**.

### Passo 4: Desfazendo um Rascunho de Análise com `git reset --soft`

- Criação de rascunho de análise preliminar.
- Desfazendo o commit mantendo os arquivos no Staging Area.
- **Comandos:** `git reset --soft`, `git restore`, `git reset --hard`

### Passo 5: Desenvolvendo um Novo Experimento com `git rebase`

- Atualização no protocolo de coleta.
- Criação da branch `desenvolvimento/experimento-y`.
- Uso de `git rebase` para manter histórico linear.
- Merge final (fast-forward).
- **Comandos:** `git rebase`, `git switch`, `git merge`, `git branch -d`

### Passo 6: Gerando Relatório Final e Arquivando com `tag`

- Geração do relatório final v1.0 do Experimento X.
- Criação da tag `v1.0-experimento-x` para marcar a versão.
- **Comandos:** `git tag -a`, `git log --oneline --decorate --tags`

---

## 🛠️ Como Reproduzir a Simulação

Para reproduzir este projeto e praticar os comandos, siga as instruções detalhadas no arquivo `roteiro.md` anexo.

---

## ✨ Comandos Utilizados (Resumo)

- `mkdir`
- `cd`
- `git init`
- `git config`
- `git status`
- `git add`
- `git commit -m`
- `git switch -c`
- `git switch`
- `git merge`
- `git branch -d`
- `git commit --amend -m`
- `git reset --soft`
- `git restore`
- `git reset --hard`
- `git rebase`
- `git tag`
- `git log --oneline --all --graph --decorate`

---

Este projeto demonstra como o Git pode ser uma poderosa ferramenta para a **gestão de projetos científicos e agrícolas**, trazendo transparência, controle de versões e colaboração estruturada para o dia a dia no campo e no laboratório.
