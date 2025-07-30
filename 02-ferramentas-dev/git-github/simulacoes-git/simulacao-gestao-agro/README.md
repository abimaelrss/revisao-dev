# 🌿 Simulação Git Aplicada: Manual de Gestão Agropecuária por Pastas

Este repositório documenta uma simulação prática de como o Git pode ser utilizado para versionar e gerenciar um "Manual de Gestão Agropecuária", organizando os assuntos em uma estrutura de pastas específica. O objetivo é demonstrar a aplicação do controle de versão para uma gestão mais granular da documentação técnica da fazenda, focando na pecuária leiteira.

## 💡 Sobre o Projeto

Este projeto é um guia prático que simula a criação e manutenção de um manual de gestão agropecuária, com informações organizadas em diretórios temáticos (custos, produtividade, manejo, extras). Ele enfatiza a importância da rastreabilidade e colaboração na documentação, utilizando o Git para registrar cada alteração e a evolução do manual.

## 🎯 Etapas da Simulação

A simulação é dividida em etapas que cobrem os seguintes conceitos e comandos do Git:

### Preparação do Ambiente: Criando a Estrutura da Fazenda Digital

- Criação da pasta raiz do projeto (`gestao-agro`) e inicialização do repositório Git.
- Configuração do nome e e-mail do usuário.
- Definição da branch principal como `main`.
- **Comandos:** `mkdir`, `cd`, `git init`, `git config`.

### Passo 1: Estrutura Inicial e Conteúdo Base

- Criação do `README.md` principal do projeto com a estrutura do manual.
- Criação das subpastas (`01-custos/`, `02-produtividade/`, etc.).
- Criação de arquivos iniciais dentro de `01-custos/` (ex: `alimentacao.md`, `medicamentos.md`).
- Registro da primeira versão do manual no histórico do Git.
- **Comandos:** `mkdir`, `git status`, `git add .`, `git commit -m`.

### Passo 2: Desenvolvendo a Seção de Produtividade (Branching)

- Criação de uma nova branch (`desenvolvimento/produtividade`) para detalhar métricas de produtividade.
- Adição de arquivos como `leite-diario.md`, `taxa-lotacao.md` e `controle-reproducao.md` em `02-produtividade/`.
- **Comandos:** `git switch -c`, `git add`, `git commit -m`.

### Passo 3: Integrando a Seção de Produtividade ao Manual Principal (Merge)

- Retorno à branch `main`.
- Mesclagem da branch `desenvolvimento/produtividade` na `main`.
- Exclusão da branch de desenvolvimento.
- **Comandos:** `git switch`, `git merge`, `git branch -d`.

### Passo 4: Corrigindo um Detalhe na Seção de Custos com `amend`

- Correção de um detalhe em `01-custos/alimentacao.md`.
- Alteração do último commit para incluir a correção e ajustar a mensagem.
- **Comandos:** `git add`, `git commit --amend -m`.
- **Alerta:** Discussão sobre `git push --force` em ambientes colaborativos.

### Passo 5: Desfazendo um Registro Temporário com `git reset --soft`

- Adição de uma nota temporária em `README.md` e posterior decisão de removê-la do histórico permanente.
- Desfazendo o commit, mas mantendo as alterações no Staging Area.
- **Comandos:** `git add`, `git commit -m`, `git status`, `git reset --soft HEAD~1`, `git restore`, `git reset --hard HEAD`.

### Passo 6: Atualizando Seções com `git rebase` (Histórico Linear)

- Simulação de uma atualização na `main` (nova observação técnica) enquanto uma nova branch (`desenvolvimento/calendario-vacinas`) está sendo desenvolvida.
- Aplicação de `git rebase` para manter um histórico linear.
- Mesclagem da branch de manejo na `main` (fast-forward merge).
- **Comandos:** `git switch`, `git add`, `git commit -m`, `git log --oneline --all --graph`, `git rebase`, `git merge`, `git branch -d`.

### Passo 7: Adicionando Últimas Seções e Finalizando o Manual

- Adição de seções como `03-manejo/rotina-trato.md` e `extras/boas-praticas.md`.
- Registro final das últimas seções no manual.
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

Este projeto é uma ferramenta essencial para profissionais do agronegócio que buscam aplicar princípios de TI na gestão de fazendas, garantindo um controle preciso e rastreável da documentação técnica organizada por áreas.