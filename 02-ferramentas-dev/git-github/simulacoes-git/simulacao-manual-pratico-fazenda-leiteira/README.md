# 🐄 Simulação Git Aplicada: Manual Prático de Pecuária Leiteira

Este repositório documenta uma simulação prática de como o Git pode ser utilizado para versionar e gerenciar um "Manual Prático de Fazenda" focado em pecuária leiteira. O objetivo é demonstrar a aplicação do controle de versão no contexto de atualizações, revisões e colaboração na documentação técnica da propriedade.

## 💡 Sobre o Projeto

Este projeto é um guia prático que simula a criação e manutenção de um manual de operações para uma fazenda de pecuária leiteira. Ele enfatiza a importância da documentação de seções como introdução, controle de custos, manejo reprodutivo, saúde do rebanho, produtividade e manejo de pastagens, utilizando o Git para registrar cada "edição" do manual.

## 🎯 Etapas da Simulação

A simulação é dividida em etapas que cobrem os seguintes conceitos e comandos do Git:

### Preparação do Ambiente: Criando a Fazenda Digital

- Criação da pasta para o manual da fazenda e inicialização do repositório Git.
- Configuração do nome e e-mail do usuário.
- Definição da branch principal como `producao`.
- **Comandos:** `mkdir`, `cd`, `git init`, `git config`.

### Passo 1: Publicando a Versão Inicial do Manual

- Criação das seções iniciais do manual, como `introducao.md` e `custos.md`.
- Registro da primeira versão do manual no histórico do Git.
- **Comandos:** `git status`, `git add .`, `git commit -m`.

### Passo 2: Desenvolvendo uma Nova Seção: Manejo Reprodutivo (Branching e Merge)

- Criação de uma nova branch (`desenvolvimento/reproducao`) para adicionar uma seção detalhada sobre manejo reprodutivo.
- Adição do arquivo `reproducao.md`.
- **Comandos:** `git switch -c`, `git add`, `git commit -m`.

### Passo 3: Integrando a Nova Seção ao Manual Principal (Merge)

- Retorno à branch `producao`.
- Mesclagem da branch `desenvolvimento/reproducao` na `producao`.
- Exclusão da branch de desenvolvimento.
- **Comandos:** `git switch`, `git merge`, `git branch -d`.

### Passo 4: Corrigindo um Erro de Digitação com `amend`

- Correção de um erro em `custos.md`.
- Alteração do último commit para incluir a correção e ajustar a mensagem.
- **Comandos:** `git add`, `git commit --amend -m`.
- **Alerta:** Discussão sobre `git push --force` em ambientes colaborativos.

### Passo 5: Desfazendo um Registro Temporário com `git reset --soft`

- Adição de uma nota temporária em `introducao.md` e posterior decisão de removê-la do histórico permanente.
- Desfazendo o commit, mas mantendo as alterações no Staging Area.
- **Comandos:** `git add`, `git commit -m`, `git status`, `git reset --soft HEAD~1`, `git restore`, `git reset --hard HEAD`.

### Passo 6: Atualizando uma Seção com `git rebase` (Histórico Linear)

- Simulação de uma atualização na `producao` (nova regulamentação sanitária) enquanto uma nova branch (`desenvolvimento/saude-rebanho`) está sendo desenvolvida.
- Aplicação de `git rebase` para manter um histórico linear.
- Mesclagem da branch de saúde na `producao` (fast-forward merge).
- **Comandos:** `git switch`, `git add`, `git commit -m`, `git log --oneline --all --graph`, `git rebase`, `git merge`, `git branch -d`.

### Passo 7: Simulando Colaboração: `git fetch` e `git pull` (Conceitual)

- Explicação conceitual de como `git fetch` e `git pull` seriam usados em um cenário de múltiplos colaboradores.
- **Comandos:** `git fetch`, `git pull`.

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
- `git fetch`
- `git pull`

Este projeto é uma ferramenta essencial para profissionais do agronegócio que buscam aplicar princípios de TI na gestão de fazendas de pecuária leiteira, garantindo um controle preciso e rastreável da documentação técnica.

**Bons estudos e continue com o excelente trabalho!**