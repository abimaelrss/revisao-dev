# 🥩 Simulação Git Aplicada: Sistema de Gestão de Confinamento

Este repositório documenta uma simulação prática de como o Git pode ser utilizado para versionar e gerenciar um "Sistema de Gestão de Confinamento". O objetivo é demonstrar a aplicação do controle de versão para documentar protocolos, rotinas e dados de desempenho dos animais confinados, garantindo transparência, rastreabilidade e eficiência na tomada de decisões.

---

## 💡 Sobre o Projeto

Este projeto é um guia prático que simula o ciclo de vida de um lote de animais em confinamento, desde a entrada até o abate. Ele enfatiza a importância da documentação detalhada de manejo nutricional, sanitário, desempenho e custos operacionais, utilizando o Git para registrar cada atualização e revisão.

---

## 🎯 Etapas da Simulação

A simulação é dividida em etapas que cobrem os seguintes conceitos e comandos do Git:

### Preparação do Ambiente: Montando o Sistema de Confinamento Digital

- Criação da pasta raiz do projeto e inicialização do repositório Git.
- Configuração do nome e e-mail do usuário.
- Definição da branch principal como `main` (representando o `lote-atual`).
- **Comandos:** `mkdir`, `cd`, `git init`, `git config`.

### Passo 1: Estrutura Inicial e Registro de Entrada de Animais

- Criação da estrutura de pastas para o sistema (`01-entrada-animais/`, `02-manejo-nutricional/`, etc.).
- Registro dos dados gerais do Lote 001 e protocolo de chegada.
- **Comandos:** `mkdir`, `git status`, `git add .`, `git commit -m`.

### Passo 2: Detalhando o Manejo Nutricional (Branching e Merge)

- Criação de uma nova branch (`desenvolvimento/nutricao`) para detalhar dietas e consumo diário.
- Adição de arquivos como `dieta-inicial.md` e `consumo-diario.md`.
- **Comandos:** `git switch -c`, `git add`, `git commit -m`.

### Passo 3: Integrando os Protocolos Nutricionais (Merge)

- Retorno à branch `main`.
- Mesclagem da branch `desenvolvimento/nutricao` na `main`.
- Exclusão da branch de desenvolvimento.
- **Comandos:** `git switch`, `git merge`, `git branch -d`.

### Passo 4: Corrigindo uma Dose de Medicamento na Chegada com `amend`

- Correção de um erro em `01-entrada-animais/protocolo-chegada.md`.
- Alteração do último commit para incluir a correção e atualizar a mensagem.
- **Comandos:** `git add`, `git commit --amend -m`.
- **Alerta:** Discussão sobre `git push --force` em ambientes colaborativos.

### Passo 5: Descartando um Registro de Pesagem Preliminar com `git reset --soft`

- Registro de uma pesagem temporária e posterior decisão de removê-la do histórico principal.
- Desfazendo o commit, mas mantendo as alterações no Staging Area.
- **Comandos:** `git add`, `git commit -m`, `git status`, `git reset --soft HEAD~1`, `git restore`, `git reset --hard HEAD`.

### Passo 6: Atualizando Protocolos de Sanidade com `git rebase` (Histórico Linear)

- Simulação de uma atualização na `main` (dieta de transição) enquanto uma nova branch (`desenvolvimento/tratamentos-sanidade`) está sendo desenvolvida.
- Aplicação de `git rebase` para manter um histórico linear.
- Mesclagem da branch de sanidade na `main` (fast-forward merge).
- **Comandos:** `git switch`, `git add`, `git commit -m`, `git log --oneline --all --graph`, `git rebase`, `git merge`, `git branch -d`.

### Passo 7: Adicionando Últimas Seções e Finalizando o Sistema

- Adição de seções como `04-desempenho-abate/`, `05-custos-operacionais/` e `observacoes-diarias/`.
- Registro final das últimas seções no sistema.
- **Comandos:** `git add`, `git commit -m`.

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
- `git log --oneline --all --graph`

---

Este projeto é uma ferramenta essencial para profissionais do agronegócio que buscam aplicar princípios de TI na gestão de confinamentos, garantindo um controle preciso e rastreável das operações.
