# 🌱 Simulação Git Aplicada: Sistema de Gestão de Análise de Solo

Este repositório documenta uma simulação prática de como o Git pode ser utilizado para versionar e gerenciar um "Sistema de Gestão de Análise de Solo". O objetivo é demonstrar a aplicação do controle de versão para documentar de forma transparente e rastreável todos os protocolos de coleta, resultados de laboratório, recomendações agronômicas e o histórico de fertilidade de cada área da fazenda.

## 💡 Sobre o Projeto

Este projeto é um guia prático que simula o ciclo de vida do manejo da fertilidade do solo. Ele enfatiza a importância da documentação de protocolos de coleta, resultados de análises, interpretações e recomendações, utilizando o Git para registrar cada atualização e revisão.

## 🎯 Etapas da Simulação

A simulação é dividida em etapas que cobrem os seguintes conceitos e comandos do Git:

### Preparação do Ambiente: Configurando o Laboratório de Solo Digital

- Criação da pasta raiz do projeto (`analise-solo-git`) e inicialização do repositório Git.
- Configuração do nome e e-mail do usuário.
- Definição da branch principal como `solo-produtivo`, representando a versão consolidada e ativa do sistema.
- **Comandos:** `mkdir`, `cd`, `git init`, `git config`.

### Passo 1: Estrutura Inicial e Protocolos Básicos

- Criação da estrutura de pastas para o sistema (`01-protocolos-coleta/`, `02-resultados-analises/`, etc.).
- Criação de arquivos iniciais como o `README.md`, `visao-geral.md` e `amostragem-pastagem.md`.
- Registro da primeira versão do sistema no histórico do Git.
- **Comandos:** `mkdir`, `git status`, `git add .`, `git commit -m`.

### Passo 2: Detalhando Resultados e Interpretações (Branching e Merge)

- Criação de uma nova branch (`desenvolvimento/resultados-talhao-5`) para registrar os resultados de uma análise específica.
- Adição de arquivos como `talhao-5-analise-2025.md` e `talhao-5-interpretacao-2025.md`.
- **Comandos:** `git switch -c`, `git add`, `git commit -m`.

### Passo 3: Integrando os Resultados da Análise (Merge)

- Retorno à branch `solo-produtivo`.
- Mesclagem da branch `desenvolvimento/resultados-talhao-5` na `solo-produtivo`.
- Exclusão da branch de desenvolvimento.
- **Comandos:** `git switch`, `git merge`, `git branch -d`.

### Passo 4: Corrigindo um Erro de Digitação com `amend`

- Correção de um erro em `amostragem-pastagem.md`.
- Alteração do último commit para incluir a correção e ajustar a mensagem.
- **Comandos:** `git add`, `git commit --amend -m`.
- **Alerta:** Discussão sobre `git push --force` em ambientes colaborativos.

### Passo 5: Desfazendo um Registro Temporário com `git reset --soft`

- Adição de uma nota temporária em `README.md` e posterior decisão de removê-la do histórico permanente.
- Desfazendo o commit, mas mantendo as alterações no Staging Area.
- **Comandos:** `git add`, `git commit -m`, `git status`, `git reset --soft HEAD~1`, `git restore`, `git reset --hard HEAD`.

### Passo 6: Atualizando a Recomendação de Adubação com `git rebase` (Histórico Linear)

- Simulação de uma atualização na `solo-produtivo` (nova análise) enquanto uma nova branch (`desenvolvimento/recomendacao-adubacao`) está sendo desenvolvida.
- Aplicação de `git rebase` para manter um histórico linear.
- Mesclagem da branch de recomendação na `solo-produtivo` (fast-forward merge).
- **Comandos:** `git switch`, `git add`, `git commit -m`, `git log --oneline --all --graph`, `git rebase`, `git merge`, `git branch -d`.

### Passo 7: Adicionando Últimas Seções e Finalizando o Sistema

- Adição de seções como `04-historico-talhoes/`, `historico-talhao-5.md`.
- Registro final das últimas seções no sistema.
- **Comandos:** `git add`, `git commit -m`.

## 🛠️ Como Reproduzir a Simulação

Para reproduzir este projeto e praticar os comandos, siga as instruções detalhadas no arquivo `roteiro.md` anexo.

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
- `git log --oneline --all --graph`

Este projeto é uma ferramenta essencial para profissionais do agronegócio que buscam aplicar princípios de TI na gestão da fertilidade do solo, garantindo um controle preciso e rastreável das informações.