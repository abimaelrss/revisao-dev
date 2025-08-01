# 🌾 Simulação Git Aplicada: Plano de Safra com Versionamento

Este repositório documenta uma simulação prática de como o Git pode ser utilizado para versionar e gerenciar um **Plano de Safra Agrícola**. O objetivo é demonstrar a aplicação do controle de versão para documentar decisões técnicas, protocolos agronômicos e ajustes operacionais, garantindo rastreabilidade e eficiência na gestão da lavoura.

---

## 💡 Sobre o Projeto

Este projeto é um guia prático que simula a criação, organização e atualização de um plano de safra ao longo do ciclo produtivo, desde o planejamento inicial até o armazenamento pós-colheita. Ele demonstra o uso do Git para registrar ajustes no cronograma, manejo fitossanitário, irrigação, nutrição e pesquisa de variedades.

---

## 🎯 Etapas da Simulação

A simulação é dividida em etapas que cobrem os seguintes conceitos e comandos do Git:

### Preparação do Ambiente: Montando o Plano de Safra Digital

- Criação da pasta raiz do projeto e inicialização do repositório Git.
- Configuração do nome e e-mail do usuário.
- Definição da branch principal como `safra-atual`.
- **Comandos:** `mkdir`, `cd`, `git init`, `git config`.

### Passo 1: Estrutura Inicial e Planejamento Geral

- Criação da estrutura de pastas (`01-planejamento-geral/`, `02-manejo-solo-plantio/`, etc.).
- Registro do cronograma da safra e objetivos de produção.
- **Comandos:** `mkdir`, `git status`, `git add .`, `git commit -m`.

### Passo 2: Detalhando o Manejo Fitossanitário (Branching e Merge)

- Criação da branch `desenvolvimento/fitossanitario` para registrar novos protocolos.
- Adição de arquivos como `controle-pragas.md` e `controle-doencas.md`.
- **Comandos:** `git switch -c`, `git add`, `git commit -m`.

### Passo 3: Integração dos Protocolos Fitossanitários (Merge)

- Retorno à branch `safra-atual`.
- Mesclagem da branch de desenvolvimento.
- Exclusão da branch após integração.
- **Comandos:** `git switch`, `git merge`, `git branch -d`.

### Passo 4: Corrigindo a Dose de Adubação com `amend`

- Correção da dose de ureia em `adubacao.md`.
- Alteração da mensagem do último commit com `--amend`.
- **Comandos:** `git add`, `git commit --amend -m`.
- **Alerta:** Discussão sobre `git push --force` em ambientes colaborativos.

### Passo 5: Descartando Nota Temporária com `git reset --soft`

- Registro de uma observação temporária no `README.md`.
- Remoção do commit mantendo o conteúdo para revisão ou descarte.
- **Comandos:** `git commit -m`, `git reset --soft HEAD~1`, `git restore`, `git reset --hard HEAD`.

### Passo 6: Atualizando Pesquisa com `git rebase` (Histórico Linear)

- Atualização do protocolo de plantio na `safra-atual`.
- Desenvolvimento da branch `pesquisa/nova-variedade-x`.
- Aplicação de `rebase` e integração com merge rápido.
- **Comandos:** `git rebase`, `git merge`, `git switch`, `git branch -d`.

### Passo 7: Finalizando o Plano com Últimas Seções

- Adição de arquivos em `analise-solo.md`, `plano-irrigacao.md`, `protocolo-colheita.md`, entre outros.
- Registro final da estrutura completa.
- **Comandos:** `git add`, `git commit -m`.

---

## 🛠️ Como Reproduzir a Simulação

Para reproduzir este projeto e praticar os comandos, siga as instruções detalhadas no arquivo `roteiro.md` (ou use este README como guia).

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

Este projeto é uma ferramenta essencial para profissionais do agro que desejam aplicar princípios de versionamento e organização técnica à gestão da lavoura, otimizando registros e tomadas de decisão com base em dados.
