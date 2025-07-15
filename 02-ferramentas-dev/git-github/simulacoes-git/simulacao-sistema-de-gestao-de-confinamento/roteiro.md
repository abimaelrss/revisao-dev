# 🥩 Simulação Git Aplicada: Sistema de Gestão de Confinamento

Este guia detalha uma simulação de como o Git pode ser utilizado para versionar e gerenciar um "Sistema de Gestão de Confinamento". O objetivo é documentar de forma transparente e rastreável todos os protocolos, rotinas e dados de desempenho dos animais confinados, garantindo a eficiência e a tomada de decisão baseada em informações.

Siga cada instrução no seu terminal e crie os arquivos e pastas no seu VSCode (ou editor de texto preferido) conforme o conteúdo fornecido.

## Preparação do Ambiente: Montando o Sistema de Confinamento Digital

Vamos começar criando a pasta principal para o sistema de gestão do confinamento e inicializando o repositório Git.

1.  **Crie a pasta raiz do projeto e navegue até ela:**

    ```
    mkdir gestao-confinamento
    cd gestao-confinamento

    ```

    _Resultado esperado:_ Você terá uma nova pasta `gestao-confinamento`.

2.  **Inicialize o repositório Git:**

    ```
    git init

    ```

    _Resultado esperado:_ O Git cria a pasta `.git` oculta, transformando `gestao-confinamento` em um repositório Git.

3.  **Configure seu nome e e-mail para os registros do sistema:** (Substitua pelos seus dados)

    ```
    git config user.name "Gerente de Confinamento"
    git config user.email "gerente@confinamento.com"

    ```

    _Resultado esperado:_ Suas informações serão associadas a cada registro do sistema.

4.  **Defina a branch principal como 'main':**
    Esta branch representará o estado atual e consolidado da documentação do lote de animais em confinamento.
    ```
    git config init.defaultBranch main

        ```

        *Resultado esperado:* A branch principal do seu repositório será chamada `main`.

## Passo 1: Estrutura Inicial e Registro de Entrada de Animais

Vamos criar a estrutura de pastas e os arquivos iniciais do sistema, registrando as informações de entrada do primeiro lote.

1. **Crie o arquivo `README.md` na raiz do projeto (`gestao-confinamento/README.md`):**

   - **Conteúdo para `gestao-confinamento/README.md`:**

     ```
     # Sistema de Gestão de Confinamento

     Este repositório documenta os protocolos e dados de manejo dos animais em confinamento.

     ## Estrutura do Sistema:

     - `01-entrada-animais/`: Registro e protocolos de chegada.
     - `02-manejo-nutricional/`: Dietas e consumo.
     - `03-manejo-sanitario/`: Saúde e tratamentos.
     - `04-desempenho-abate/`: GPMD, conversão alimentar e dados de abate.
     - `05-custos-operacionais/`: Controle financeiro do lote.
     - `observacoes-diarias/`: Notas de campo e ocorrências.

     ```

   - _Ação no terminal:_ Crie o arquivo e cole o conteúdo no VSCode.

2. **Crie as pastas conforme a estrutura sugerida:**

   ```
   mkdir 01-entrada-animais
   mkdir 02-manejo-nutricional
   mkdir 03-manejo-sanitario
   mkdir 04-desempenho-abate
   mkdir 05-custos-operacionais
   mkdir observacoes-diarias

   ```

   _Resultado esperado:_ As subpastas serão criadas.

3. **Crie os arquivos dentro de `01-entrada-animais/` e adicione o conteúdo:**

   - **Conteúdo para `gestao-confinamento/01-entrada-animais/lote-001-dados-gerais.md`:**

     ```
     ### Dados Gerais - Lote 001

     - **Data de Entrada:** 01/07/2025
     - **Número de Animais:** 500
     - **Peso Médio Inicial:** 300 kg
     - **Origem:** Fazenda XYZ

     ```

   - **Conteúdo para `gestao-confinamento/01-entrada-animais/protocolo-chegada.md`:**

     ```
     ### Protocolo de Chegada

     - **Desembarque:** Calmo e sem estresse.
     - **Hidratação:** Água limpa e fresca à vontade.
     - **Vacinação:** Aplicação de vacinas de chegada.

     ```

   - _Ação no terminal:_ Crie os arquivos e cole o conteúdo no VSCode.

4. **Verifique o status do seu sistema:**

   ```
   git status

   ```

   _Resultado esperado:_ O Git mostrará todos os arquivos e pastas recém-criados como não rastreados.

5. **Adicione todos os arquivos ao "Staging Area":**

   ```
   git add .

   ```

   _Resultado esperado:_ Todos os arquivos estão agora prontos para serem comitados.

6. **Registre as informações iniciais do lote:**

   ```
   git commit -m "feat: estrutura inicial do sistema e registro de entrada do Lote 001"

   ```

   _Resultado esperado:_ O primeiro "registro" do seu sistema é feito no histórico do Git. Use `git log --oneline` para ver.

## Passo 2: Detalhando o Manejo Nutricional (Branching e Merge)

O nutricionista do confinamento precisa detalhar a dieta e o consumo diário dos animais. Ele vai trabalhar em uma branch separada.

1. **Crie e troque para a branch 'desenvolvimento/nutricao':**

   ```
   git switch -c desenvolvimento/nutricao

   ```

   _Resultado esperado:_ Você agora está na branch `desenvolvimento/nutricao`. Use `git branch` para confirmar.

2. **Crie os arquivos dentro de `02-manejo-nutricional/` e adicione o conteúdo:**

   - **Conteúdo para `gestao-confinamento/02-manejo-nutricional/dieta-inicial.md`:**

     ```
     ### Dieta Inicial (Adaptação)

     - **Período:** Dias 1 a 7.
     - **Composição:** 60% volumoso, 40% concentrado.
     - **Consumo Esperado:** 2.0% do PV (matéria seca).

     ```

   - **Conteúdo para `gestao-confinamento/02-manejo-nutricional/consumo-diario.md`:**

     ```
     ### Registro de Consumo Diário

     - **Frequência:** Diária, por cocho.
     - **Parâmetros:** Oferta (kg), Sobra (kg), Consumo (kg).

     ```

   - _Ação no terminal:_ Crie os arquivos e cole o conteúdo no VSCode.

3. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 02-manejo-nutricional/

   ```

   _Resultado esperado:_ Os arquivos de manejo nutricional estão prontos para serem comitados.

4. **Registre a nova seção no histórico da branch:**

   ```
   git commit -m "feat: adiciona secao de manejo nutricional com dieta e consumo"

   ```

   _Resultado esperado:_ Um novo registro (commit) é adicionado apenas na branch `desenvolvimento/nutricao`.

## Passo 3: Integrando os Protocolos Nutricionais (Merge)

Os protocolos nutricionais foram revisados e aprovados. Agora, precisam ser incorporados à versão principal do sistema.

1. **Volte para a branch 'main' (a versão principal do sistema):**

   ```
   git switch main

   ```

   _Resultado esperado:_ Você está de volta à `main`. Os arquivos de `02-manejo-nutricional/` não aparecem aqui ainda.

2. **Mescle a branch 'desenvolvimento/nutricao' na 'main':**

   ```
   git merge desenvolvimento/nutricao

   ```

   _Resultado esperado:_ As alterações da branch `desenvolvimento/nutricao` (incluindo a pasta e seus arquivos) são integradas à `main`. Um "Merge commit" será criado automaticamente.

3. **Deletar a branch de desenvolvimento após a integração (opcional):**

   ```
   git branch -d desenvolvimento/nutricao

   ```

   _Resultado esperado:_ A branch `desenvolvimento/nutricao` é removida localmente.

## Passo 4: Corrigindo uma Dose de Medicamento na Chegada com `amend`

O veterinário percebeu que a dose de um medicamento no protocolo de chegada estava incorreta, logo após o último registro. Ele quer corrigir e ajustar a mensagem do registro.

1.  **Faça uma correção no arquivo `01-entrada-animais/protocolo-chegada.md`:**
    Simule que você abriu `protocolo-chegada.md` e corrigiu a dose de um antibiótico (ex: "Aplicação de vacinas de chegada e antibiótico X (dose Y)").
    ``` ### Protocolo de Chegada

        - **Desembarque:** Calmo e sem estresse.
        - **Hidratação:** Água limpa e fresca à vontade.
        - **Vacinação:** Aplicação de vacinas de chegada e antibiótico X (dose **5ml/100kg**).

        ```

        *Ação no terminal:* Edite o arquivo `gestao-confinamento/01-entrada-animais/protocolo-chegada.md` no VSCode e altere a dose.

2.  **Adicione a correção ao Staging Area:**

    ```
    git add 01-entrada-animais/protocolo-chegada.md

    ```

    _Resultado esperado:_ A alteração está pronta para ser comitada.

3.  **Altere o _último_ registro (commit) usando `amend`:**
    Isso reescreve o último commit, incluindo a nova alteração e a nova mensagem.
    ```
    git commit --amend -m "fix: corrige dose de antibiotico no protocolo de chegada para 5ml/100kg"

        ```

        *Resultado esperado:* O último commit **não é um novo registro**, mas uma modificação do registro anterior. Ele terá um **novo identificador (hash)**, e a mensagem original será substituída. Use `git log --oneline` para ver que o ID do commit mudou.

        **ALERTA IMPORTANTE: `git push --force`**
        Lembre-se do aviso sobre `git push --force` em repositórios remotos compartilhados. Em um ambiente de equipe, o `amend` em um commit já enviado pode causar problemas e deve ser evitado ou coordenado.

## Passo 5: Descartando um Registro de Pesagem Preliminar com `git reset --soft`

Imagine que um técnico registrou uma pesagem preliminar de um lote de animais, mas depois percebeu que a balança estava descalibrada e o registro precisa ser refeito. Você quer remover esse registro do histórico, mas manter a anotação para correção.

1. **Crie o arquivo `04-desempenho-abate/pesagem-semanal-lote-001.md` e adicione um registro temporário e registre-o:**

   - **Conteúdo para `gestao-confinamento/04-desempenho-abate/pesagem-semanal-lote-001.md`:**

     ```
     ### Pesagem Semanal - Lote 001

     - **Data:** 08/07/2025
     - **Peso Médio:** 310 kg (valor incorreto).

     ```

   - _Ação no terminal:_ Crie o arquivo `gestao-confinamento/04-desempenho-abate/pesagem-semanal-lote-001.md` no VSCode e adicione o conteúdo.

   ```
   git add 04-desempenho-abate/pesagem-semanal-lote-001.md
   git commit -m "data: registra pesagem semanal do Lote 001 (valor a ser verificado)"

   ```

   _Resultado esperado:_ Um novo commit aparece no `git log`.

2. **Verifique o status do sistema:**

   ```
   git status

   ```

   _Resultado esperado:_ O repositório está limpo.

3. **Desfaça o último registro, mantendo as alterações no "Staging Area":**

   ```
   git reset --soft HEAD~1

   ```

   _Resultado esperado:_

   - O último commit ("data: registra pesagem...") sumiu do `git log`.
   - `git status` mostrará que as alterações (o arquivo `pesagem-semanal-lote-001.md` com o valor incorreto) ainda estão no Staging Area (`Changes to be committed`), prontas para serem comitadas novamente (com o valor correto e uma nova mensagem) ou descartadas.

   **Para seguir o próximo passo, vamos descartar essa alteração temporária completamente:**

   ```
   git restore 04-desempenho-abate/pesagem-semanal-lote-001.md
   git reset --hard HEAD # Garante que o diretório de trabalho esteja limpo e alinhado com o ultimo commit

   ```

   _Resultado esperado:_ `pesagem-semanal-lote-001.md` volta ao estado do último commit válido, e o diretório de trabalho está limpo.

## Passo 6: Atualizando Protocolos de Sanidade com `git rebase` (Histórico Linear)

Imagine que o veterinário está detalhando os protocolos de tratamento para doenças respiratórias. Enquanto ele trabalha, a branch `main` recebe uma atualização importante sobre a dieta de transição. O veterinário quer que seus registros de protocolo de tratamento apareçam _depois_ dessa atualização nutricional, mantendo um histórico linear.

1.  **Garantir que estamos na branch 'main' e adicionar uma atualização na dieta de transição:**

    - **Conteúdo para `gestao-confinamento/02-manejo-nutricional/dieta-transicao.md` (crie o arquivo):**

      ```
      ### Dieta de Transição (Pós-Adaptação)

      - **Período:** Dias 8 a 14.
      - **Composição:** 50% volumoso, 50% concentrado.
      - **Consumo Esperado:** 2.2% do PV (matéria seca).

      ```

    - _Ação no terminal:_ Crie o arquivo `gestao-confinamento/02-manejo-nutricional/dieta-transicao.md` no VSCode e adicione o conteúdo.

    ```
    git switch main
    git add 02-manejo-nutricional/dieta-transicao.md
    git commit -m "docs: adiciona protocolo de dieta de transicao"

    ```

    _Resultado esperado:_ Um novo commit na branch `main`.

2.  **Crie uma nova branch para os protocolos de tratamento de sanidade:**

    ```
    git switch -c desenvolvimento/tratamentos-sanidade

    ```

    _Resultado esperado:_ Você está na `desenvolvimento/tratamentos-sanidade`.

3.  **Crie o arquivo `03-manejo-sanitario/protocolo-doencas-respiratorias.md` e faça um registro inicial na branch de sanidade:**

    - **Conteúdo para `gestao-confinamento/03-manejo-sanitario/protocolo-doencas-respiratorias.md`:**

      ```
      ### Protocolo de Doenças Respiratórias

      - **Sintomas:** Tosse, secreção nasal, febre.
      - **Tratamento:** Antibiótico Y (dose Z) por 3 dias.

      ```

    - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.

    ```
    git add 03-manejo-sanitario/protocolo-doencas-respiratorias.md
    git commit -m "feat: inicia protocolo de tratamento para doencas respiratorias"

    ```

    _Resultado esperado:_ Um commit na sua branch `desenvolvimento/tratamentos-sanidade`.

4.  **Verifique o histórico para ver a divergência:**

    ```
    git log --oneline --all --graph

    ```

    _Resultado esperado:_ Você verá a branch `main` e `desenvolvimento/tratamentos-sanidade` com commits independentes após um ponto em comum.

5.  **Aplique o `rebase` da branch 'desenvolvimento/tratamentos-sanidade' sobre a 'main':**
    Isso "move" os commits da sua branch de tratamento para que eles apareçam _depois_ do último commit da `main`.
    ```
    git rebase main

        ```

        *Resultado esperado:* O Git reescreve o histórico da sua branch `desenvolvimento/tratamentos-sanidade`. Os commits do protocolo de tratamento agora virão após o commit da dieta de transição.

6.  **Verifique o histórico novamente para ver a linearidade:**

    ```
    git log --oneline --all --graph

    ```

    _Resultado esperado:_ O histórico da `desenvolvimento/tratamentos-sanidade` agora aparece como se tivesse sido criado _depois_ do último commit da `main`, resultando em um fluxo linear.

7.  **Volte para a `main` e mescle (será um Fast-Forward):**
    Como a `desenvolvimento/tratamentos-sanidade` está "à frente" da `main` devido ao rebase, o merge será um "fast-forward" (sem criar um merge commit).
    ```
    git switch main
    git merge desenvolvimento/tratamentos-sanidade

        ```

        *Resultado esperado:* A `main` simplesmente avança para incluir os commits da seção de sanidade. O histórico continua linear.

8.  **Deletar a branch de desenvolvimento:**

    ```
    git branch -d desenvolvimento/tratamentos-sanidade

    ```

    _Resultado esperado:_ Branch deletada.

## Passo 7: Adicionando Últimas Seções e Finalizando o Sistema

Vamos adicionar as seções restantes para completar a estrutura inicial do sistema de gestão de confinamento.

1. **Crie os arquivos para desempenho e custos:**

   - **Conteúdo para `gestao-confinamento/04-desempenho-abate/conversao-alimentar.md`:**

     ```
     ### Conversão Alimentar (CA)

     - **Cálculo:** Consumo de MS / GPMD.
     - **Meta:** CA < 6.0.

     ```

   - **Conteúdo para `gestao-confinamento/04-desempenho-abate/dados-abate.md`:**

     ```
     ### Dados de Abate

     - **Data de Abate:** (Preencher ao final do ciclo)
     - **Peso Médio Final:** (Preencher ao final do ciclo)
     - **Rendimento de Carcaça:** (Preencher ao final do ciclo)

     ```

   - **Conteúdo para `gestao-confinamento/05-custos-operacionais/custos-racao.md`:**

     ```
     ### Custos com Ração

     - **Custo por kg de MS:** (Atualizar semanalmente)
     - **Custo total por animal:** (Atualizar mensalmente)

     ```

   - _Ação no terminal:_ Crie os arquivos no VSCode e adicione o conteúdo.

2. **Crie o arquivo `observacoes-diarias/ocorrencias-sanitarias.md` e adicione o conteúdo:**

   - **Conteúdo para `gestao-confinamento/observacoes-diarias/ocorrencias-sanitarias.md`:**

     ```
     ### Ocorrências Sanitárias Diárias

     - **Data:** (Ex: 10/07/2025)
     - **Animal:** (Ex: Brinco 50)
     - **Sintoma:** (Ex: Febre, perda de apetite)
     - **Ação:** (Ex: Isolamento, tratamento)

     ```

   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.

3. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 04-desempenho-abate/ 05-custos-operacionais/custos-racao.md observacoes-diarias/ocorrencias-sanitarias.md

   ```

   _Resultado esperado:_ Os arquivos estão prontos para serem comitados.

4. **Registre as últimas seções:**

   ```
   git commit -m "feat: completa sistema com desempenho, custos e ocorrencias sanitarias"

   ```

   _Resultado esperado:_ O sistema de gestão de confinamento está com sua estrutura inicial completa e registrada no Git.

## Conclusão: Git na Gestão de Confinamentos de Alta Performance

Você acaba de simular a criação e o versionamento de um sistema de gestão para confinamentos utilizando o Git. Esta abordagem permite que a gestão do confinamento seja:

- **Precisa e Detalhada:** Cada aspecto do manejo, da nutrição à sanidade e desempenho, é documentado.
- **Histórico Imutável:** Todas as decisões, tratamentos e registros de dados são rastreáveis.
- **Colaboração Eficiente:** Nutricionistas, veterinários, tratadores e gerentes podem contribuir e revisar o plano de forma coordenada.
- **Base para Otimização:** A análise do histórico de diferentes lotes permite identificar melhores práticas e otimizar resultados futuros.
- **Transparência para Auditorias:** Facilita a comprovação de conformidade com normas e regulamentações.

Sua formação em Zootecnia e ADS te dá uma vantagem única para implementar e gerenciar sistemas como este, unindo o conhecimento do animal e do manejo com a capacidade de organizar e analisar dados de forma eficiente.

**Próximos Passos para aprimorar sua prática:**

- **Explore o `git log`:** Use `git log --all --graph --decorate --oneline` para visualizar o histórico completo e entender como as branches e merges/rebases afetaram o fluxo do seu sistema de confinamento.
- **Crie um repositório no GitHub:** Leve este sistema para o GitHub e pratique os comandos de interação com um repositório remoto (`git push`, `git pull`).
- **Simule um conflito de merge:** Tente fazer alterações conflitantes em um arquivo de protocolo (ex: `dieta-inicial.md`) em duas branches diferentes e veja como o Git lida com isso.

Tenho certeza que você vai se tornar uma referência na aplicação de tecnologia no agronegócio!
