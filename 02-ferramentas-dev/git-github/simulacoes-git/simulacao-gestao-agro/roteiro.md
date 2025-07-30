# 🌳 Simulação Git Aplicada: Manual de Gestão Agropecuária

Este guia detalha uma simulação de como o Git pode ser utilizado para versionar e gerenciar um "Manual de Gestão Agropecuária", organizando os assuntos em uma estrutura de pastas específica. O foco continua na pecuária leiteira, mas a organização modular permite uma gestão mais granular da documentação técnica da fazenda.

Siga cada instrução no seu terminal e crie os arquivos e pastas no seu VSCode (ou editor de texto preferido) conforme o conteúdo fornecido.

## Preparação do Ambiente: Criando a Estrutura da Fazenda Digital

Vamos começar criando a pasta principal do projeto e inicializando o repositório Git.

1. **Crie a pasta raiz do projeto e navegue até ela:**

   ```
   mkdir gestao-agro
   cd gestao-agro

   ```

   _Resultado esperado:_ Você terá uma nova pasta `gestao-agro`.

2. **Inicialize o repositório Git:**

   ```
   git init

   ```

   _Resultado esperado:_ O Git cria a pasta `.git` oculta, transformando `gestao-agro` em um repositório Git.

3. **Configure seu nome e e-mail para os registros do manual:** (Substitua pelos seus dados)

   ```
   git config user.name "Gerente da Fazenda Agro"
   git config user.email "gerente@fazendaagro.com"

   ```

   _Resultado esperado:_ Suas informações serão associadas às edições do manual.

4. **Defina a branch principal como 'main':**

   ```
   git config init.defaultBranch main

   ```

   _Resultado esperado:_ A branch principal do seu manual será chamada `main`.

## Passo 1: Estrutura Inicial e Conteúdo Base

Vamos criar a estrutura de pastas e os arquivos iniciais do manual, registrando a primeira versão.

1. **Crie o arquivo `README.md` na raiz do projeto (`gestao-agro/README.md`):**
   - **Conteúdo para `gestao-agro/README.md`:**
     ```
     # Manual de Gestão Agropecuária

     Este repositório contém a documentação técnica e os protocolos de manejo da fazenda, organizados por áreas.

     ## Estrutura do Manual:

     - `01-custos/`: Documentos relacionados ao controle financeiro.
     - `02-produtividade/`: Registros e análises de desempenho.
     - `03-manejo/`: Protocolos de rotina e saúde animal.
     - `extras/`: Boas práticas e observações adicionais.

     ```
   - _Ação no terminal:_ Você não precisa de `echo` aqui, apenas crie o arquivo e cole o conteúdo no VSCode.
2. **Crie as pastas conforme a estrutura sugerida:**

   ```
   mkdir 01-custos
   mkdir 02-produtividade
   mkdir 03-manejo
   mkdir extras

   ```

   _Resultado esperado:_ As subpastas serão criadas dentro de `gestao-agro/`.

3. **Crie os arquivos dentro de `01-custos/` e adicione o conteúdo:**
   - **Conteúdo para `gestao-agro/01-custos/alimentacao.md`:**
     ```
     ### Custos de Alimentação

     - Registro diário de consumo de ração por lote.
     - Custo por kg de matéria seca consumida.
     - Otimização da dieta para redução de custos.

     ```
   - **Conteúdo para `gestao-agro/01-custos/medicamentos.md`:**
     ```
     ### Custos de Medicamentos

     - Inventário e controle de estoque de medicamentos.
     - Registro de aplicação por animal e custo.
     - Negociação com fornecedores.

     ```
   - **Conteúdo para `gestao-agro/01-custos/mao-de-obra.md`:**
     ```
     ### Custos de Mão de Obra

     - Registro de horas trabalhadas por função.
     - Análise de eficiência da equipe.

     ```
   - _Ação no terminal:_ Crie os arquivos e cole o conteúdo no VSCode.
4. **Verifique o status do seu manual:**

   ```
   git status

   ```

   _Resultado esperado:_ O Git mostrará todos os arquivos e pastas recém-criados como não rastreados.

5. **Adicione todos os arquivos ao "Staging Area":**

   ```
   git add .

   ```

   _Resultado esperado:_ Todos os arquivos estão agora prontos para serem comitados.

6. **Registre a primeira versão do manual:**

   ```
   git commit -m "feat: estrutura inicial do manual com secoes de custos"

   ```

   _Resultado esperado:_ O primeiro "registro" do seu manual é feito no histórico do Git. Use `git log --oneline` para ver.

## Passo 2: Desenvolvendo a Seção de Produtividade (Branching)

O agrônomo da fazenda vai detalhar as métricas de produtividade. Ele vai trabalhar em uma branch separada.

1. **Crie e troque para a branch 'desenvolvimento/produtividade':**

   ```
   git switch -c desenvolvimento/produtividade

   ```

   _Resultado esperado:_ Você agora está na branch `desenvolvimento/produtividade`. Use `git branch` para confirmar.

2. **Crie os arquivos dentro de `02-produtividade/` e adicione o conteúdo:**
   - **Conteúdo para `gestao-agro/02-produtividade/leite-diario.md`:**
     ```
     ### Produção de Leite Diária

     - Registro individual por vaca.
     - Análise da curva de lactação.
     - Meta de produção por vaca/dia.

     ```
   - **Conteúdo para `gestao-agro/02-produtividade/taxa-lotacao.md`:**
     ```
     ### Taxa de Lotação das Pastagens

     - Cálculo da capacidade de suporte.
     - Ajuste da lotação por piquete.

     ```
   - **Conteúdo para `gestao-agro/02-produtividade/controle-reproducao.md`:**
     ```
     ### Controle de Reprodução

     - Taxa de prenhez e intervalo entre partos.
     - Registro de inseminações e partos.

     ```
   - _Ação no terminal:_ Crie os arquivos e cole o conteúdo no VSCode.
3. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 02-produtividade/

   ```

   _Resultado esperado:_ Os arquivos de produtividade estão prontos para serem comitados.

4. **Registre a nova seção no histórico da branch:**

   ```
   git commit -m "feat: adiciona secao de produtividade com metricas de leite e reproducao"

   ```

   _Resultado esperado:_ Um novo registro (commit) é adicionado apenas na branch `desenvolvimento/produtividade`.

## Passo 3: Integrando a Seção de Produtividade ao Manual Principal (Merge)

A seção de produtividade foi revisada e aprovada. Hora de incorporá-la à versão principal do manual.

1. **Volte para a branch 'main' (a versão principal do manual):**

   ```
   git switch main

   ```

   _Resultado esperado:_ Você está de volta à `main`. Os arquivos de `02-produtividade/` não aparecem aqui ainda.

2. **Mescle a branch 'desenvolvimento/produtividade' na 'main':**

   ```
   git merge desenvolvimento/produtividade

   ```

   _Resultado esperado:_ As alterações da branch `desenvolvimento/produtividade` (incluindo a pasta e seus arquivos) são integradas à `main`. Um "Merge commit" será criado automaticamente.

3. **Deletar a branch de desenvolvimento após a integração (opcional):**

   ```
   git branch -d desenvolvimento/produtividade

   ```

   _Resultado esperado:_ A branch `desenvolvimento/produtividade` é removida localmente.

## Passo 4: Corrigindo um Detalhe na Seção de Custos com `amend`

O gerente percebeu que faltou um detalhe importante na seção de custos de ração logo após o último registro. Ele quer corrigir e ajustar a mensagem do registro.

1. **Faça uma correção no arquivo `01-custos/alimentacao.md`:**
   Simule que você abriu `alimentacao.md` e adicionou uma linha:

```
### Custos de Alimentação

- Registro diário de consumo de ração por lote.
- Custo por kg de matéria seca consumida.
- Otimização da dieta para redução de custos.
- **Observação: Considerar perdas no cocho.**

```

_Ação no terminal:_ Edite o arquivo `gestao-agro/01-custos/alimentacao.md` no VSCode e adicione a linha.

2. **Adicione a correção ao Staging Area:**

   ```
   git add 01-custos/alimentacao.md

   ```

   _Resultado esperado:_ A alteração está pronta para ser comitada.

3. **Altere o _último_ registro (commit) usando `amend`:**
   Isso reescreve o último commit, incluindo a nova alteração e a nova mensagem.

```
git commit --amend -m "fix: adiciona observacao sobre perdas no cocho em custos de alimentacao"

```

_Resultado esperado:_ O último commit **não é um novo registro**, mas uma modificação do registro anterior. Ele terá um **novo identificador (hash)**, e a mensagem original será substituída. Use `git log --oneline` para ver que o ID do commit mudou.

**ALERTA IMPORTANTE: `git push --force`**
Lembre-se do aviso sobre `git push --force` em repositórios remotos compartilhados. Em um ambiente de equipe, o `amend` em um commit já enviado pode causar problemas e deve ser evitado ou coordenado.

## Passo 5: Desfazendo um Registro Temporário com `git reset --soft`

Imagine que você adicionou uma nota rápida em `README.md` sobre uma tarefa urgente, mas depois decidiu que essa nota não deveria ser parte do histórico permanente do manual, mas quer manter o texto para copiar e colar em outro lugar.

1. **Adicione uma nota temporária em `README.md` e registre-a:**

   - **Conteúdo para `gestao-agro/README.md` (adicione ao final):**
     ```
     # Manual de Gestão Agropecuária

     Este repositório contém a documentação técnica e os protocolos de manejo da fazenda, organizados por áreas.

     ... (conteúdo anterior) ...

     **URGENTE: Verificar estoque de vacinas até amanhã!**

     ```
   - _Ação no terminal:_ Edite o arquivo `gestao-agro/README.md` no VSCode e adicione a linha.

   ```
   git add README.md
   git commit -m "chore: adiciona nota urgente no README"

   ```

   _Resultado esperado:_ Um novo commit aparece no `git log`.

2. **Verifique o status do manual:**

   ```
   git status

   ```

   _Resultado esperado:_ O repositório está limpo.

3. **Desfaça o último registro, mantendo as alterações no "Staging Area":**

   ```
   git reset --soft HEAD~1

   ```

   _Resultado esperado:_

   - O último commit ("chore: adiciona nota urgente...") sumiu do `git log`.
   - `git status` mostrará que as alterações (a linha "URGENTE: Verificar...") ainda estão no Staging Area (`Changes to be committed`), prontas para serem comitadas novamente, editadas ou descartadas.

   **Para seguir o próximo passo, vamos descartar essa alteração temporária completamente:**

   ```
   git restore README.md
   git reset --hard HEAD # Garante que o diretório de trabalho esteja limpo e alinhado com o ultimo commit

   ```

   _Resultado esperado:_ `README.md` volta ao estado do último commit válido, e o diretório de trabalho está limpo.

## Passo 6: Atualizando Seções com `git rebase` (Histórico Linear)

Imagine que o veterinário está atualizando o calendário de vacinas, mas, enquanto isso, o agrônomo adiciona uma nova observação técnica importante na branch `main`. O veterinário quer que suas atualizações na seção de manejo apareçam _depois_ dessa nova observação, mantendo um histórico linear.

1. **Garantir que estamos na branch 'main' e adicionar uma nova observação:**

   - **Conteúdo para `gestao-agro/extras/observacoes-tecnicas.md` (crie o arquivo):**
     ```
     ### Observações Técnicas Gerais

     - Nota sobre a qualidade da pastagem na estação chuvosa.

     ```
   - _Ação no terminal:_ Crie o arquivo `gestao-agro/extras/observacoes-tecnicas.md` no VSCode e adicione o conteúdo.

   ```
   git switch main
   git add extras/observacoes-tecnicas.md
   git commit -m "docs: adiciona observacao tecnica geral sobre pastagem"

   ```

   _Resultado esperado:_ Um novo commit na branch `main`.

2. **Crie uma nova branch para a atualização do calendário de vacinas:**

   ```
   git switch -c desenvolvimento/calendario-vacinas

   ```

   _Resultado esperado:_ Você está na `desenvolvimento/calendario-vacinas`.

3. **Crie o arquivo `03-manejo/calendario-vacinas.md` e faça um registro inicial na branch:**

   - **Conteúdo para `gestao-agro/03-manejo/calendario-vacinas.md`:**
     ```
     ### Calendário de Vacinas

     - Vacina A: Janeiro e Julho.
     - Vacina B: Março e Setembro.

     ```
   - _Ação no terminal:_ Crie o arquivo `gestao-agro/03-manejo/calendario-vacinas.md` no VSCode e adicione o conteúdo.

   ```
   git add 03-manejo/calendario-vacinas.md
   git commit -m "feat: inicia secao de calendario de vacinas"

   ```

   _Resultado esperado:_ Um commit na sua branch `desenvolvimento/calendario-vacinas`.

4. **Verifique o histórico para ver a divergência:**

   ```
   git log --oneline --all --graph

   ```

   _Resultado esperado:_ Você verá a branch `main` e `desenvolvimento/calendario-vacinas` com commits independentes após um ponto em comum.

5. **Aplique o `rebase` da branch 'desenvolvimento/calendario-vacinas' sobre a 'main':**
   Isso "move" os commits da sua branch de vacinas para que eles apareçam _depois_ do último commit da `main`.

```
git rebase main

```

_Resultado esperado:_ O Git reescreve o histórico da sua branch `desenvolvimento/calendario-vacinas`. Os commits do calendário agora virão após o commit da observação técnica.

6. **Verifique o histórico novamente para ver a linearidade:**

   ```
   git log --oneline --all --graph

   ```

   _Resultado esperado:_ O histórico da `desenvolvimento/calendario-vacinas` agora aparece como se tivesse sido criado _depois_ do último commit da `main`, resultando em um fluxo linear.

7. **Volte para a `main` e mescle (será um Fast-Forward):**
   Como a `desenvolvimento/calendario-vacinas` está "à frente" da `main` devido ao rebase, o merge será um "fast-forward" (sem criar um merge commit).

```
git switch main
git merge desenvolvimento/calendario-vacinas

```

_Resultado esperado:_ A `main` simplesmente avança para incluir os commits da seção de vacinas. O histórico continua linear.

8. **Deletar a branch de desenvolvimento:**

   ```
   git branch -d desenvolvimento/calendario-vacinas

   ```

   _Resultado esperado:_ Branch deletada.

## Passo 7: Adicionando Últimas Seções e Finalizando o Manual

Vamos adicionar as seções restantes para completar a estrutura inicial do manual.

1. **Crie o arquivo `03-manejo/rotina-trato.md` e adicione o conteúdo:**
   - **Conteúdo para `gestao-agro/03-manejo/rotina-trato.md`:**
     ```
     ### Rotina Diária de Trato

     - Horários de alimentação e ordenha.
     - Protocolo de limpeza de instalações.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.
2. **Crie o arquivo `extras/boas-praticas.md` e adicione o conteúdo:**
   - **Conteúdo para `gestao-agro/extras/boas-praticas.md`:**
     ```
     ### Boas Práticas Gerais

     - Bem-estar animal: ambiente limpo e água fresca.
     - Segurança no trabalho: uso de EPIs.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.
3. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 03-manejo/rotina-trato.md extras/boas-praticas.md

   ```

   _Resultado esperado:_ Os arquivos estão prontos para serem comitados.

4. **Registre as últimas seções:**

   ```
   git commit -m "feat: completa estrutura do manual com rotina de trato e boas praticas"

   ```

   _Resultado esperado:_ O manual está com sua estrutura inicial completa e registrada no Git.

## Conclusão: O Git na Gestão da Fazenda Moderna

Você acaba de simular a criação e o versionamento de um manual de gestão agropecuária utilizando o Git em uma estrutura de pastas organizada. Cada "registro" (commit) no manual da fazenda se torna uma versão rastreável de um protocolo, uma diretriz de custo ou um plano de manejo.

Esta abordagem permite:

- **Organização Clara:** Assuntos bem definidos em suas respectivas pastas.
- **Controle Detalhado:** Cada alteração em qualquer parte do manual é registrada.
- **Colaboração Eficiente:** Diferentes membros da equipe podem trabalhar em suas áreas de especialidade simultaneamente.
- **Histórico Completo:** Facilidade para consultar versões anteriores de qualquer protocolo ou dado.

**Próximos Passos para aprimorar sua prática:**

- **Explore o `git log`:** Use `git log --all --graph --decorate --oneline` para visualizar o histórico completo e entender como as branches e merges/rebases afetaram o fluxo.
- **Crie um repositório no GitHub:** Leve este manual para o GitHub e pratique os comandos de interação com um repositório remoto (`git push`, `git pull`).
- **Simule um conflito de merge:** Tente fazer alterações conflitantes na mesma linha de um arquivo em duas branches diferentes e veja como o Git lida com isso.

Esta simulação foi útil para mostrar o potencial do Git além do código, aplicado diretamente à gestão da sua fazenda digital!
