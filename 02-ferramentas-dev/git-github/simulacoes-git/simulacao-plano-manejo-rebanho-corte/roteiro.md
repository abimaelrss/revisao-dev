# 🐂 Simulação Git Aplicada: Plano de Manejo de Rebanho de Corte

Este guia detalha uma simulação de como o Git pode ser utilizado para versionar e gerenciar um "Plano de Manejo de Rebanho de Corte". O objetivo é documentar de forma transparente e rastreável todos os protocolos, rotinas e dados de desempenho do rebanho, desde a cria até a engorda.

Siga cada instrução no seu terminal e crie os arquivos e pastas no seu VSCode (ou editor de texto preferido) conforme o conteúdo fornecido.

## Preparação do Ambiente: Montando o Plano Digital do Rebanho

Vamos começar criando a pasta principal para o plano de manejo e inicializando o repositório Git.

1.  **Crie a pasta raiz do projeto e navegue até ela:**

    ```
    mkdir plano-manejo-corte
    cd plano-manejo-corte

    ```

    _Resultado esperado:_ Você terá uma nova pasta `plano-manejo-corte`.

2.  **Inicialize o repositório Git:**

    ```
    git init

    ```

    _Resultado esperado:_ O Git cria a pasta `.git` oculta, transformando `plano-manejo-corte` em um repositório Git.

3.  **Configure seu nome e e-mail para os registros do plano:** (Substitua pelos seus dados)

    ```
    git config user.name "Zootecnista da Fazenda"
    git config user.email "zootecnista@fazenda.com"

    ```

    _Resultado esperado:_ Suas informações serão associadas a cada edição do plano.

4.  **Defina a branch principal como 'rebanho-atual':**
    Esta branch representará a versão mais atual e estável do plano de manejo do rebanho.

    ```
    git config init.defaultBranch rebanho-atual

    ```

    _Resultado esperado:_ A branch principal do seu plano será chamada `rebanho-atual`.

## Passo 1: Estrutura Inicial e Planejamento Geral do Rebanho

Vamos criar a estrutura de pastas e os arquivos iniciais do plano, registrando a primeira versão.

1. **Crie o arquivo `README.md` na raiz do projeto (`plano-manejo-corte/README.md`):**

   - **Conteúdo para `plano-manejo-corte/README.md`:**

     ```
     # Plano de Manejo de Rebanho de Corte

     Este repositório documenta os protocolos e dados de manejo do rebanho de corte da fazenda.

     ## Estrutura do Plano:

     - `01-planejamento-geral/`: Objetivos e cronograma do rebanho.
     - `02-manejo-sanitario/`: Protocolos de saúde e vacinação.
     - `03-manejo-nutricional/`: Planos de alimentação e suplementação.
     - `04-manejo-reprodutivo/`: Estratégias de reprodução.
     - `05-dados-desempenho/`: Métricas de produtividade e ganho de peso.
     - `observacoes-campo/`: Notas e incidentes diários.

     ```

   - _Ação no terminal:_ Crie o arquivo e cole o conteúdo no VSCode.

2. **Crie as pastas conforme a estrutura sugerida:**

   ```
   mkdir 01-planejamento-geral
   mkdir 02-manejo-sanitario
   mkdir 03-manejo-nutricional
   mkdir 04-manejo-reprodutivo
   mkdir 05-dados-desempenho
   mkdir observacoes-campo

   ```

   _Resultado esperado:_ As subpastas serão criadas dentro de `plano-manejo-corte/`.

3. **Crie os arquivos dentro de `01-planejamento-geral/` e adicione o conteúdo:**

   - **Conteúdo para `plano-manejo-corte/01-planejamento-geral/objetivos-rebanho.md`:**

     ```
     ### Objetivos do Rebanho

     - **Ganho de Peso Médio Diário (GPMD):** 800g/animal/dia.
     - **Idade ao Abate:** 24 meses.
     - **Taxa de Prenhez:** 85%.

     ```

   - **Conteúdo para `plano-manejo-corte/01-planejamento-geral/cronograma-anual.md`:**

     ```
     ### Cronograma Anual de Manejo

     - **Outubro-Dezembro:** Estação de Monta.
     - **Abril-Maio:** Vacinação contra Febre Aftosa.
     - **Junho:** Desmame.

     ```

   - _Ação no terminal:_ Crie os arquivos e cole o conteúdo no VSCode.

4. **Verifique o status do seu plano:**

   ```
   git status

   ```

   _Resultado esperado:_ O Git mostrará todos os arquivos e pastas recém-criados como não rastreados.

5. **Adicione todos os arquivos ao "Staging Area":**

   ```
   git add .

   ```

   _Resultado esperado:_ Todos os arquivos estão agora prontos para serem comitados.

6. **Registre a primeira versão do plano de manejo:**

   ```
   git commit -m "feat: estrutura inicial do plano de manejo de rebanho de corte"

   ```

   _Resultado esperado:_ O primeiro "registro" do seu plano é feito no histórico do Git. Use `git log --oneline` para ver.

## Passo 2: Desenvolvendo Protocolos Sanitários (Branching e Merge)

O veterinário da fazenda precisa revisar e atualizar os protocolos de vacinação. Ele vai trabalhar em uma branch separada.

1. **Crie e troque para a branch 'desenvolvimento/sanidade':**

   ```
   git switch -c desenvolvimento/sanidade

   ```

   _Resultado esperado:_ Você agora está na branch `desenvolvimento/sanidade`. Use `git branch` para confirmar.

2. **Crie os arquivos dentro de `02-manejo-sanitario/` e adicione o conteúdo:**

   - **Conteúdo para `plano-manejo-corte/02-manejo-sanitario/protocolo-vacinas.md`:**

     ```
     ### Protocolo de Vacinação

     - **Febre Aftosa:** Abril e Novembro (todos os animais).
     - **Brucelose:** Fêmeas de 3 a 8 meses (dose única).
     - **Clostridioses:** Bezerros ao desmame (reforço 30 dias após).

     ```

   - **Conteúdo para `plano-manejo-corte/02-manejo-sanitario/controle-parasitas.md`:**

     ```
     ### Controle de Parasitas

     - **Endoparasitas:** Vermifugação estratégica (3x ao ano).
     - **Ectoparasitas:** Banhos carrapaticidas conforme infestação.

     ```

   - _Ação no terminal:_ Crie os arquivos e cole o conteúdo no VSCode.

3. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 02-manejo-sanitario/

   ```

   _Resultado esperado:_ Os arquivos de manejo sanitário estão prontos para serem comitados.

4. **Registre a nova seção no histórico da branch:**

   ```
   git commit -m "feat: adiciona secao de manejo sanitario com vacinas e parasitas"

   ```

   _Resultado esperado:_ Um novo registro (commit) é adicionado apenas na branch `desenvolvimento/sanidade`.

## Passo 3: Integrando os Protocolos Sanitários (Merge)

Os novos protocolos sanitários foram validados e agora precisam ser incorporados à versão principal do plano de manejo.

1. **Volte para a branch 'rebanho-atual' (a versão principal do plano):**

   ```
   git switch rebanho-atual

   ```

   _Resultado esperado:_ Você está de volta à `rebanho-atual`. Os arquivos de `02-manejo-sanitario/` não aparecem aqui ainda.

2. **Mescle a branch 'desenvolvimento/sanidade' na 'rebanho-atual':**

   ```
   git merge desenvolvimento/sanidade

   ```

   _Resultado esperado:_ As alterações da branch `desenvolvimento/sanidade` (incluindo a pasta e seus arquivos) são integradas à `rebanho-atual`. Um "Merge commit" será criado automaticamente.

3. **Deletar a branch de desenvolvimento após a integração (opcional):**

   ```
   git branch -d desenvolvimento/sanidade

   ```

   _Resultado esperado:_ A branch `desenvolvimento/sanidade` é removida localmente.

## Passo 4: Corrigindo uma Dose de Medicamento com `amend`

O veterinário percebeu que a dose de um vermífugo foi digitada incorretamente no protocolo, logo após o último registro. Ele quer corrigir e ajustar a mensagem do registro.

1.  **Faça uma correção no arquivo `02-manejo-sanitario/controle-parasitas.md`:**
    Simule que você abriu `controle-parasitas.md` e corrigiu a dose de um vermífugo (ex: "Vermifugação estratégica (3x ao ano) com produto X (dose Y)").

    ```
    ### Controle de Parasitas

    - **Endoparasitas:** Vermifugação estratégica (3x ao ano) com produto X (dose **1ml/50kg**).
    - **Ectoparasitas:** Banhos carrapaticidas conforme infestação.

    ```

    _Ação no terminal:_ Edite o arquivo `plano-manejo-corte/02-manejo-sanitario/controle-parasitas.md` no VSCode e altere a dose.

2.  **Adicione a correção ao Staging Area:**

    ```
    git add 02-manejo-sanitario/controle-parasitas.md

    ```

    _Resultado esperado:_ A alteração está pronta para ser comitada.

3.  **Altere o _último_ registro (commit) usando `amend`:**
    Isso reescreve o último commit, incluindo a nova alteração e a nova mensagem.

    ```
    git commit --amend -m "fix: corrige dose de vermifugo para 1ml/50kg no controle de parasitas"

    ```

    _Resultado esperado:_ O último commit **não é um novo registro**, mas uma modificação do registro anterior. Ele terá um **novo identificador (hash)**, e a mensagem original será substituída. Use `git log --oneline` para ver que o ID do commit mudou.

    **ALERTA IMPORTANTE: `git push --force`**
    Lembre-se do aviso sobre `git push --force` em repositórios remotos compartilhados. Em um ambiente de equipe, o `amend` em um commit já enviado pode causar problemas e deve ser evitado ou coordenado.

## Passo 5: Descartando uma Observação de Campo Não Relevante com `git reset --soft`

Imagine que um vaqueiro registrou uma observação diária sobre o comportamento de um animal, mas depois foi determinado que era um comportamento normal e não relevante para o histórico permanente do plano. Você quer remover esse registro do histórico, mas manter a anotação para referência interna.

1. **Crie o arquivo `observacoes-campo/notas-diarias.md` e adicione uma nota temporária e registre-a:**

   - **Conteúdo para `plano-manejo-corte/observacoes-campo/notas-diarias.md`:**

     ```
     ### Notas Diárias de Campo

     - **01/07/2025:** Animal X (Brinco 123) com comportamento agitado (observação inicial).

     ```

   - _Ação no terminal:_ Crie o arquivo `plano-manejo-corte/observacoes-campo/notas-diarias.md` no VSCode e adicione o conteúdo.

   ```
   git add observacoes-campo/notas-diarias.md
   git commit -m "chore: adiciona observacao de comportamento animal"

   ```

   _Resultado esperado:_ Um novo commit aparece no `git log`.

2. **Verifique o status do plano:**

   ```
   git status

   ```

   _Resultado esperado:_ O repositório está limpo.

3. **Desfaça o último registro, mantendo as alterações no "Staging Area":**

   ```
   git reset --soft HEAD~1

   ```

   _Resultado esperado:_

   - O último commit ("chore: adiciona observacao...") sumiu do `git log`.
   - `git status` mostrará que as alterações (a linha "Animal X com comportamento agitado...") ainda estão no Staging Area (`Changes to be committed`), prontas para serem comitadas novamente (com uma nova mensagem, por exemplo, "Observação de comportamento - descartada, mantida para registro interno") ou descartadas.

   **Para seguir o próximo passo, vamos descartar essa alteração temporária completamente:**

   ```
   git restore observacoes-campo/notas-diarias.md
   git reset --hard HEAD # Garante que o diretório de trabalho esteja limpo e alinhado com o ultimo commit

   ```

   _Resultado esperado:_ `notas-diarias.md` volta ao estado do último commit válido, e o diretório de trabalho está limpo.

## Passo 6: Atualizando o Plano Nutricional com `git rebase` (Histórico Linear)

Imagine que o zootecnista está detalhando o plano de suplementação mineral para a recria. Enquanto ele trabalha, a branch `rebanho-atual` recebe uma atualização importante sobre a estação de monta. O zootecnista quer que seus registros nutricionais apareçam _depois_ dessa atualização reprodutiva, mantendo um histórico linear.

1.  **Garantir que estamos na branch 'rebanho-atual' e adicionar uma atualização na estação de monta:**

    - **Conteúdo para `plano-manejo-corte/04-manejo-reprodutivo/estacao-monta.md` (crie o arquivo):**

      ```
      ### Estação de Monta

      - **Período:** 90 dias (Outubro a Dezembro).
      - **Touros:** 1 touro para cada 25 vacas.

      ```

    - _Ação no terminal:_ Crie o arquivo `plano-manejo-corte/04-manejo-reprodutivo/estacao-monta.md` no VSCode e adicione o conteúdo.

    ```
    git switch rebanho-atual
    git add 04-manejo-reprodutivo/estacao-monta.md
    git commit -m "docs: adiciona protocolo de estacao de monta"

    ```

    _Resultado esperado:_ Um novo commit na branch `rebanho-atual`.

2.  **Crie uma nova branch para o plano nutricional da recria:**

    ```
    git switch -c desenvolvimento/nutricao-recria

    ```

    _Resultado esperado:_ Você está na `desenvolvimento/nutricao-recria`.

3.  **Crie o arquivo `03-manejo-nutricional/suplementacao-recria.md` e faça um registro inicial na branch de nutrição:**

    - **Conteúdo para `plano-manejo-corte/03-manejo-nutricional/suplementacao-recria.md`:**

      ```
      ### Suplementação da Recria

      - **Fase:** Pós-desmame até 18 meses.
      - **Produto:** Suplemento Mineral Proteico (consumo 0.3% PV).

      ```

    - _Ação no terminal:_ Crie o arquivo `plano-manejo-corte/03-manejo-nutricional/suplementacao-recria.md` no VSCode e adicione o conteúdo.

    ```
    git add 03-manejo-nutricional/suplementacao-recria.md
    git commit -m "feat: inicia plano de suplementacao para recria"

    ```

    _Resultado esperado:_ Um commit na sua branch `desenvolvimento/nutricao-recria`.

4.  **Verifique o histórico para ver a divergência:**

    ```
    git log --oneline --all --graph

    ```

    _Resultado esperado:_ Você verá a branch `rebanho-atual` e `desenvolvimento/nutricao-recria` com commits independentes após um ponto em comum.

5.  **Aplique o `rebase` da branch 'desenvolvimento/nutricao-recria' sobre a 'rebanho-atual':**
    Isso "move" os commits da sua branch de nutrição para que eles apareçam _depois_ do último commit da `rebanho-atual`.

    ```
    git rebase rebanho-atual

    ```

    _Resultado esperado:_ O Git reescreve o histórico da sua branch `desenvolvimento/nutricao-recria`. Os commits de nutrição agora virão após o commit da estação de monta.

6.  **Verifique o histórico novamente para ver a linearidade:**

    ```
    git log --oneline --all --graph

    ```

    _Resultado esperado:_ O histórico da `desenvolvimento/nutricao-recria` agora aparece como se tivesse sido criado _depois_ do último commit da `rebanho-atual`, resultando em um fluxo linear.

7.  **Volte para a `rebanho-atual` e mescle (será um Fast-Forward):**
    Como a `desenvolvimento/nutricao-recria` está "à frente" da `rebanho-atual` devido ao rebase, o merge será um "fast-forward" (sem criar um merge commit).

    ```
    git switch rebanho-atual
    git merge desenvolvimento/nutricao-recria

    ```

    _Resultado esperado:_ A `rebanho-atual` simplesmente avança para incluir os commits da seção de nutrição. O histórico continua linear.

8.  **Deletar a branch de desenvolvimento:**

    ```
    git branch -d desenvolvimento/nutricao-recria

    ```

    _Resultado esperado:_ Branch deletada.

## Passo 7: Adicionando Últimas Seções e Finalizando o Plano

Vamos adicionar as seções restantes para completar a estrutura inicial do plano de manejo.

1. **Crie os arquivos dentro de `03-manejo-nutricional/` e `04-manejo-reprodutivo/` e adicione o conteúdo:**

   - **Conteúdo para `plano-manejo-corte/03-manejo-nutricional/dieta-engorda.md`:**

     ```
     ### Dieta de Engorda

     - **Fase:** Pré-abate (últimos 90 dias).
     - **Produto:** Concentrado de alto grão (consumo 1.5% PV).

     ```

   - **Conteúdo para `plano-manejo-corte/04-manejo-reprodutivo/controle-partos.md`:**

     ```
     ### Controle de Partos

     - **Período:** Julho a Setembro.
     - **Protocolo:** Monitoramento 24h, auxílio em distocias.

     ```

   - _Ação no terminal:_ Crie os arquivos no VSCode e adicione o conteúdo.

2. **Crie os arquivos dentro de `05-dados-desempenho/` e `observacoes-campo/` e adicione o conteúdo:**

   - **Conteúdo para `plano-manejo-corte/05-dados-desempenho/ganho-peso-medio.md`:**

     ```
     ### Ganho de Peso Médio

     - **Registro:** Pesagens mensais.
     - **Meta:** GPMD de 800g/dia.

     ```

   - **Conteúdo para `plano-manejo-corte/05-dados-desempenho/taxa-desmame.md`:**

     ```
     ### Taxa de Desmame

     - **Cálculo:** Bezerros desmamados / vacas expostas à monta.
     - **Meta:** 80%.

     ```

   - **Conteúdo para `plano-manejo-corte/observacoes-campo/incidentes.md`:**

     ```
     ### Registro de Incidentes

     - **Data:** (Ex: 05/07/2025)
     - **Animal:** (Ex: Brinco 456)
     - **Descrição:** (Ex: Lesão na pata direita)
     - **Ação:** (Ex: Tratamento com anti-inflamatório)

     ```

   - _Ação no terminal:_ Crie os arquivos no VSCode e adicione o conteúdo.

3. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 03-manejo-nutricional/dieta-engorda.md 04-manejo-reprodutivo/controle-partos.md 05-dados-desempenho/ observacoes-campo/incidentes.md

   ```

   _Resultado esperado:_ Os arquivos estão prontos para serem comitados.

4. **Registre as últimas seções:**

   ```
   git commit -m "feat: completa plano de manejo com nutricao, reproducao, desempenho e incidentes"

   ```

   _Resultado esperado:_ O plano de manejo de rebanho de corte está com sua estrutura inicial completa e registrada no Git.

## Conclusão: Git na Gestão de Rebanhos de Corte

Você acaba de simular a criação e o versionamento de um plano de manejo para rebanhos de corte utilizando o Git. Esta abordagem permite que a gestão do rebanho seja:

- **Abrangente e Detalhada:** Todos os aspectos do manejo são documentados e organizados.
- **Histórico Completo:** Cada alteração em um protocolo ou registro de desempenho é rastreável.
- **Colaboração Facilitada:** Zootecnistas, veterinários, vaqueiros e gerentes podem contribuir e revisar o plano de forma coordenada.
- **Base para Tomada de Decisão:** A evolução dos protocolos e o registro de dados de desempenho fornecem insights valiosos para otimização.

**Próximos Passos para aprimorar sua prática:**

- **Explore o `git log`:** Use `git log --all --graph --decorate --oneline` para visualizar o histórico completo e entender como as branches e merges/rebases afetaram o fluxo do seu plano de manejo.
- **Crie um repositório no GitHub:** Leve este plano para o GitHub e pratique os comandos de interação com um repositório remoto (`git push`, `git pull`).
- **Simule um conflito de merge:** Tente fazer alterações conflitantes em um arquivo de protocolo (ex: `protocolo-vacinas.md`) em duas branches diferentes e veja como o Git lida com isso.

Espero que esta simulação tenha sido útil para você ver o potencial do Git em um cenário tão robusto como a gestão de rebanhos de corte!
