# 🐂 Simulação Git Aplicada: Plano de Manejo de Rebanho de Corte

Este repositório documenta uma simulação prática de como o Git pode ser utilizado para versionar e gerenciar um "Plano de Manejo de Rebanho de Corte". O objetivo é demonstrar a aplicação do controle de versão para documentar de forma transparente e rastreável todos os protocolos, rotinas e dados de desempenho do rebanho, desde a cria até a engorda.

## 💡 Sobre o Projeto

Este projeto é um guia prático que simula o ciclo de vida do manejo de um rebanho de corte. Ele enfatiza a importância da documentação detalhada de planejamento, manejo sanitário, nutricional, reprodutivo, dados de desempenho e observações de campo, utilizando o Git para registrar cada atualização e revisão.

## 🎯 Etapas da Simulação

A simulação é dividida em etapas que cobrem os seguintes conceitos e comandos do Git:

### Preparação do Ambiente: Montando o Plano Digital do Rebanho

- Criação da pasta raiz do projeto e inicialização do repositório Git.
- Configuração do nome e e-mail do usuário.
- Definição da branch principal como `rebanho-atual`.
- **Comandos:** `mkdir`, `cd`, `git init`, `git config`.

### Passo 1: Estrutura Inicial e Planejamento Geral do Rebanho

- Criação da estrutura de pastas para o plano (`01-planejamento-geral/`, `02-manejo-sanitario/`, etc.).
- Registro dos objetivos do rebanho e cronograma anual de manejo.
- **Comandos:** `mkdir`, `git status`, `git add .`, `git commit -m`.

### Passo 2: Desenvolvendo Protocolos Sanitários (Branching e Merge)

- Criação de uma nova branch (`desenvolvimento/sanidade`) para revisar e atualizar protocolos de vacinação e controle de parasitas.
- Adição de arquivos como `protocolo-vacinas.md` e `controle-parasitas.md`.
- **Comandos:** `git switch -c`, `git add`, `git commit -m`.

### Passo 3: Integrando os Protocolos Sanitários (Merge)

- Retorno à branch `rebanho-atual`.
- Mesclagem da branch `desenvolvimento/sanidade` na `rebanho-atual`.
- Exclusão da branch de desenvolvimento.
- **Comandos:** `git switch`, `git merge`, `git branch -d`.

### Passo 4: Corrigindo uma Dose de Medicamento com `amend`

- Correção de um erro em `02-manejo-sanitario/controle-parasitas.md`.
- Alteração do último commit para incluir a correção e atualizar a mensagem.
- **Comandos:** `git add`, `git commit --amend -m`.
- **Alerta:** Discussão sobre `git push --force` em ambientes colaborativos.

### Passo 5: Descartando uma Observação de Campo Não Relevante com `git reset --soft`

- Registro de uma observação diária temporária e posterior decisão de removê-la do histórico principal.
- Desfazendo o commit, mas mantendo as alterações no Staging Area.
- **Comandos:** `git add`, `git commit -m`, `git status`, `git reset --soft HEAD~1`, `git restore`, `git reset --hard HEAD`.

### Passo 6: Atualizando o Plano Nutricional com `git rebase` (Histórico Linear)

- Simulação de uma atualização na `rebanho-atual` (estação de monta) enquanto uma nova branch (`desenvolvimento/nutricao-recria`) está sendo desenvolvida.
- Aplicação de `git rebase` para manter um histórico linear.
- Mesclagem da branch de nutrição na `rebanho-atual` (fast-forward merge).
- **Comandos:** `git switch`, `git add`, `git commit -m`, `git log --oneline --all --graph`, `git rebase`, `git merge`, `git branch -d`.

### Passo 7: Adicionando Últimas Seções e Finalizando o Plano

- Adição de seções como `03-manejo-nutricional/dieta-engorda.md`, `04-manejo-reprodutivo/controle-partos.md`, `05-dados-desempenho/` e `observacoes-campo/incidentes.md`.
- Registro final das últimas seções no plano de manejo.
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

Este projeto é uma ferramenta essencial para profissionais do agronegócio que buscam aplicar princípios de TI na gestão de rebanhos de corte, garantindo um controle preciso e rastreável das operações.
