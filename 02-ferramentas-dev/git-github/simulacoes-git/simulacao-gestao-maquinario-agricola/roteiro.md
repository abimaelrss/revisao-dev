# 🚜 Simulação Git Aplicada: Gestão e Manutenção de Maquinário Agrícola

Este guia detalha uma simulação de como o Git pode ser utilizado para criar e gerenciar um sistema de documentação para a gestão e manutenção de maquinário agrícola. O objetivo é registrar de forma transparente e versionada o histórico de cada equipamento, incluindo manutenções, horas de uso e inspeções.

Siga cada instrução no seu terminal e crie os arquivos e pastas no seu VSCode (ou editor de texto preferido) conforme o conteúdo fornecido.

## Preparação do Ambiente: Montando o Dossiê da Frota

Vamos começar criando a pasta principal para o sistema de gestão de maquinário e inicializando o repositório Git.

1. **Crie a pasta raiz do projeto e navegue até ela:**
    
    ```
    mkdir gestao-maquinario-agricola
    cd gestao-maquinario-agricola
    
    ```
    
    *Resultado esperado:* Você terá uma nova pasta `gestao-maquinario-agricola`.
    
2. **Inicialize o repositório Git:**
    
    ```
    git init
    
    ```
    
    *Resultado esperado:* O Git cria a pasta `.git` oculta, transformando `gestao-maquinario-agricola` em um repositório Git.
    
3. **Configure seu nome e e-mail para os registros de manutenção:** (Substitua pelos seus dados)
    
    ```
    git config user.name "Mecânico Chefe"
    git config user.email "mecanico@fazenda.com"
    
    ```
    
    *Resultado esperado:* Suas informações serão associadas a cada registro de manutenção.
    
4. **Defina a branch principal como 'frota-ativa':**
Esta branch representará o estado atual e consolidado da documentação da frota.
    
  ```
  git config init.defaultBranch frota-ativa
  
  ```
  
  *Resultado esperado:* A branch principal do seu repositório será chamada `frota-ativa`.
    

## Passo 1: Estrutura Inicial e Registro de um Equipamento

Vamos criar a estrutura de pastas para os diferentes equipamentos e registrar o primeiro deles.

1. **Crie o arquivo `README.md` na raiz do projeto (`gestao-maquinario-agricola/README.md`):**
    - **Conteúdo para `gestao-maquinario-agricola/README.md`:**
        
        ```
        # Sistema de Gestão e Manutenção de Maquinário Agrícola
        
        Este repositório documenta o histórico de manutenção e uso de cada equipamento da frota.
        
        ## Estrutura do Sistema:
        
        - `tratores/`: Documentação de tratores.
        - `colheitadeiras/`: Documentação de colheitadeiras.
        - `pulverizadores/`: Documentação de pulverizadores.
        - `implementos/`: Documentação de implementos diversos.
        - `protocolos-manutencao/`: Manuais e diretrizes gerais de manutenção.
        
        ```
        
    - *Ação no terminal:* Crie o arquivo e cole o conteúdo no VSCode.
2. **Crie as pastas conforme a estrutura sugerida:**
    
    ```
    mkdir tratores
    mkdir colheitadeiras
    mkdir pulverizadores
    mkdir implementos
    mkdir protocolos-manutencao
    
    ```
    
    *Resultado esperado:* As subpastas serão criadas.
    
3. **Crie os arquivos para o primeiro trator (`tratores/trator-01.md`) e adicione o conteúdo:**
    - **Conteúdo para `gestao-maquinario-agricola/tratores/trator-01.md`:**
        
        ```
        # Trator John Deere 6100J - ID: TRATOR-01
        
        ## Informações Gerais:
        
        - **Modelo:** John Deere 6100J
        - **Ano de Fabricação:** 2020
        - **Horímetro Inicial:** 0h
        - **Última Atualização:** 01/07/2025
        
        ```
        
    - *Ação no terminal:* Crie o arquivo e cole o conteúdo no VSCode.
4. **Crie o arquivo `tratores/trator-01-historico.md` para o histórico de manutenção:**
    - **Conteúdo para `gestao-maquinario-agricola/tratores/trator-01-historico.md`:**
        
        ```
        ### Histórico de Manutenção - TRATOR-01
        
        - **01/07/2025:** Registro inicial do equipamento.
        
        ```
        
    - *Ação no terminal:* Crie o arquivo e cole o conteúdo no VSCode.
5. **Verifique o status do seu sistema:**
    
    ```
    git status
    
    ```
    
    *Resultado esperado:* O Git mostrará todos os arquivos e pastas recém-criados como não rastreados.
    
6. **Adicione todos os arquivos ao "Staging Area":**
    
    ```
    git add .
    
    ```
    
    *Resultado esperado:* Todos os arquivos estão agora prontos para serem comitados.
    
7. **Registre as informações iniciais do trator:**
    
    ```
    git commit -m "feat: registra Trator-01 e inicia historico de manutencao"
    
    ```
    
    *Resultado esperado:* O primeiro "registro" do seu sistema é feito no histórico do Git. Use `git log --oneline` para ver.
    

## Passo 2: Registrando uma Manutenção Preventiva (Branching e Merge)

O trator-01 passou pela manutenção preventiva de 500 horas. O mecânico responsável vai documentar essa manutenção.

1. **Crie e troque para a branch 'manutencao/trator-01-500h':**
    
    ```
    git switch -c manutencao/trator-01-500h
    
    ```
    
    *Resultado esperado:* Você agora está na branch `manutencao/trator-01-500h`. Use `git branch` para confirmar.
    
2. **Atualize o arquivo `tratores/trator-01.md` com o horímetro atual:**
    - **Conteúdo para `gestao-maquinario-agricola/tratores/trator-01.md` (altere a linha `Horímetro Atual`):**
        
        ```
        # Trator John Deere 6100J - ID: TRATOR-01
        
        ## Informações Gerais:
        
        - **Modelo:** John Deere 6100J
        - **Ano de Fabricação:** 2020
        - **Horímetro Inicial:** 0h
        - **Horímetro Atual:** 500h
        - **Última Atualização:** 05/07/2025
        
        ```
        
    - *Ação no terminal:* Edite o arquivo no VSCode e altere o horímetro.
3. **Atualize o arquivo `tratores/trator-01-historico.md` com os detalhes da manutenção:**
    - **Conteúdo para `gestao-maquinario-agricola/tratores/trator-01-historico.md` (adicione ao final):**
        
        ```
        ### Histórico de Manutenção - TRATOR-01
        
        - **01/07/2025:** Registro inicial do equipamento.
        - **05/07/2025 (500h):** Manutenção preventiva. Troca de óleo do motor, filtros (óleo, combustível, ar), verificação de níveis.
        
        ```
        
    - *Ação no terminal:* Edite o arquivo no VSCode e adicione a linha.
4. **Adicione os arquivos alterados ao Staging Area:**
    
    ```
    git add tratores/trator-01.md tratores/trator-01-historico.md
    
    ```
    
    *Resultado esperado:* Os arquivos estão prontos para serem comitados.
    
5. **Registre a manutenção preventiva:**
    
    ```
    git commit -m "feat: registra manutencao preventiva de 500h para Trator-01"
    
    ```
    
    *Resultado esperado:* Um novo registro (commit) é adicionado apenas na branch `manutencao/trator-01-500h`.
    

## Passo 3: Integrando o Registro de Manutenção (Merge)

A manutenção foi concluída e documentada. Agora, o registro precisa ser incorporado ao histórico principal da frota.

1. **Volte para a branch 'frota-ativa' (a versão principal da documentação):**
    
    ```
    git switch frota-ativa
    
    ```
    
    *Resultado esperado:* Você está de volta à `frota-ativa`. As atualizações do trator-01 não aparecem aqui ainda.
    
2. **Mescle a branch 'manutencao/trator-01-500h' na 'frota-ativa':**
    
    ```
    git merge manutencao/trator-01-500h
    
    ```
    
    *Resultado esperado:* As alterações da branch `manutencao/trator-01-500h` são integradas à `frota-ativa`. Um "Merge commit" será criado automaticamente.
    
3. **Deletar a branch de manutenção após a integração (opcional):**
    
    ```
    git branch -d manutencao/trator-01-500h
    
    ```
    
    *Resultado esperado:* A branch `manutencao/trator-01-500h` é removida localmente.
    

## Passo 4: Corrigindo um Detalhe de Peça Trocada com `amend`

O mecânico percebeu que esqueceu de especificar a marca do filtro de óleo trocado, logo após o último registro. Ele quer corrigir e ajustar a mensagem do registro.

1. **Faça uma correção no arquivo `tratores/trator-01-historico.md`:**
Simule que você abriu `trator-01-historico.md` e adicionou a marca do filtro:
    
  ```
  ### Histórico de Manutenção - TRATOR-01
  
  - **01/07/2025:** Registro inicial do equipamento.
  - **05/07/2025 (500h):** Manutenção preventiva. Troca de óleo do motor, filtros (óleo **(Marca X)**, combustível, ar), verificação de níveis.
  
  ```
  
  *Ação no terminal:* Edite o arquivo `gestao-maquinario-agricola/tratores/trator-01-historico.md` no VSCode e adicione a marca.
    
2. **Adicione a correção ao Staging Area:**
    
    ```
    git add tratores/trator-01-historico.md
    
    ```
    
    *Resultado esperado:* A alteração está pronta para ser comitada.
    
3. **Altere o *último* registro (commit) usando `amend`:**
Isso reescreve o último commit, incluindo a nova alteração e a nova mensagem.
    
  ```
  git commit --amend -m "fix: adiciona marca do filtro de oleo na manutencao de 500h do Trator-01"
  
  ```
  
  *Resultado esperado:* O último commit **não é um novo registro**, mas uma modificação do registro anterior. Ele terá um **novo identificador (hash)**, e a mensagem original será substituída. Use `git log --oneline` para ver que o ID do commit mudou.
  
  **ALERTA IMPORTANTE: `git push --force`**
  Lembre-se do aviso sobre `git push --force` em repositórios remotos compartilhados. Em um ambiente de equipe, o `amend` em um commit já enviado pode causar problemas e deve ser evitado ou coordenado.
    

## Passo 5: Descartando um Registro de Consumo de Combustível Incorreto com `git reset --soft`

Imagine que um operador registrou o consumo de combustível para uma tarefa, mas depois percebeu que o valor estava errado e precisa ser refeito. Você quer remover esse registro do histórico, mas manter a anotação para correção.

1. **Crie o arquivo `tratores/trator-01-consumo.md` e adicione um registro temporário e registre-o:**
    - **Conteúdo para `gestao-maquinario-agricola/tratores/trator-01-consumo.md`:**
        
        ```
        ### Consumo de Combustível - TRATOR-01
        
        - **06/07/2025 (Plantio):** 120 litros (valor incorreto).
        
        ```
        
    - *Ação no terminal:* Crie o arquivo `gestao-maquinario-agricola/tratores/trator-01-consumo.md` no VSCode e adicione o conteúdo.
    
    ```
    git add tratores/trator-01-consumo.md
    git commit -m "data: registra consumo de combustivel para plantio (valor a ser verificado)"
    
    ```
    
    *Resultado esperado:* Um novo commit aparece no `git log`.
    
2. **Verifique o status do sistema:**
    
    ```
    git status
    
    ```
    
    *Resultado esperado:* O repositório está limpo.
    
3. **Desfaça o último registro, mantendo as alterações no "Staging Area":**
    
    ```
    git reset --soft HEAD~1
    
    ```
    
    *Resultado esperado:*
    
    - O último commit ("data: registra consumo...") sumiu do `git log`.
    - `git status` mostrará que as alterações (o arquivo `trator-01-consumo.md` com o valor incorreto) ainda estão no Staging Area (`Changes to be committed`), prontas para serem comitadas novamente (com o valor correto e uma nova mensagem) ou descartadas.
    
    **Para seguir o próximo passo, vamos descartar essa alteração temporária completamente:**
    
    ```
    git restore tratores/trator-01-consumo.md
    git reset --hard HEAD # Garante que o diretório de trabalho esteja limpo e alinhado com o ultimo commit
    
    ```
    
    *Resultado esperado:* `trator-01-consumo.md` volta ao estado do último commit válido, e o diretório de trabalho está limpo.
    

## Passo 6: Atualizando Protocolos de Manutenção Preventiva com `git rebase` (Histórico Linear)

Imagine que a equipe de manutenção está revisando os protocolos de manutenção preventiva para colheitadeiras. Enquanto eles trabalham, a branch `frota-ativa` recebe uma atualização importante sobre a inspeção de segurança para todos os equipamentos. A equipe de manutenção quer que seus registros de protocolo apareçam *depois* dessa atualização de segurança, mantendo um histórico linear.

1. **Garantir que estamos na branch 'frota-ativa' e adicionar um protocolo de inspeção de segurança:**
    - **Conteúdo para `gestao-maquinario-agricola/protocolos-manutencao/inspecao-seguranca.md` (crie o arquivo):**
        
        ```
        ### Protocolo de Inspeção de Segurança
        
        - **Frequência:** Mensal.
        - **Itens:** Freios, iluminação, pneus, extintor.
        
        ```
        
    - *Ação no terminal:* Crie o arquivo `gestao-maquinario-agricola/protocolos-manutencao/inspecao-seguranca.md` no VSCode e adicione o conteúdo.
    
    ```
    git switch frota-ativa
    git add protocolos-manutencao/inspecao-seguranca.md
    git commit -m "docs: adiciona protocolo de inspecao de seguranca da frota"
    
    ```
    
    *Resultado esperado:* Um novo commit na branch `frota-ativa`.
    
2. **Crie uma nova branch para os protocolos de colheitadeira:**
    
    ```
    mkdir colheitadeiras # Crie a pasta se ainda não existir
    git switch -c desenvolvimento/protocolos-colheitadeira
    
    ```
    
    *Resultado esperado:* Você está na `desenvolvimento/protocolos-colheitadeira`.
    
3. **Crie o arquivo `colheitadeiras/protocolo-manutencao.md` e faça um registro inicial na branch de colheitadeira:**
    - **Conteúdo para `gestao-maquinario-agricola/colheitadeiras/protocolo-manutencao.md`:**
        
        ```
        ### Protocolo de Manutenção - Colheitadeira
        
        - **Pré-safra:** Lubrificação geral, verificação de correias.
        - **Pós-safra:** Limpeza profunda, armazenamento de componentes.
        
        ```
        
    - *Ação no terminal:* Crie o arquivo no VSCode e adicione o conteúdo.
    
    ```
    git add colheitadeiras/protocolo-manutencao.md
    git commit -m "feat: inicia protocolo de manutencao para colheitadeira"
    
    ```
    
    *Resultado esperado:* Um commit na sua branch `desenvolvimento/protocolos-colheitadeira`.
    
4. **Verifique o histórico para ver a divergência:**
    
    ```
    git log --oneline --all --graph
    
    ```
    
    *Resultado esperado:* Você verá a branch `frota-ativa` e `desenvolvimento/protocolos-colheitadeira` com commits independentes após um ponto em comum.
    
5. **Aplique o `rebase` da branch 'desenvolvimento/protocolos-colheitadeira' sobre a 'frota-ativa':**
Isso "move" os commits da sua branch de protocolo para que eles apareçam *depois* do último commit da `frota-ativa`.
    
  ```
  git rebase frota-ativa
  
  ```
  
  *Resultado esperado:* O Git reescreve o histórico da sua branch `desenvolvimento/protocolos-colheitadeira`. Os commits do protocolo agora virão após o commit da inspeção de segurança.
    
6. **Verifique o histórico novamente para ver a linearidade:**
    
    ```
    git log --oneline --all --graph
    
    ```
    
    *Resultado esperado:* O histórico da `desenvolvimento/protocolos-colheitadeira` agora aparece como se tivesse sido criado *depois* do último commit da `frota-ativa`, resultando em um fluxo linear.
    
7. **Volte para a `frota-ativa` e mescle (será um Fast-Forward):**
Como a `desenvolvimento/protocolos-colheitadeira` está "à frente" da `frota-ativa` devido ao rebase, o merge será um "fast-forward" (sem criar um merge commit).
    
  ```
  git switch frota-ativa
  git merge desenvolvimento/protocolos-colheitadeira
  
  ```
  
  *Resultado esperado:* A `frota-ativa` simplesmente avança para incluir os commits da seção de colheitadeiras. O histórico continua linear.
    
8. **Deletar a branch de desenvolvimento:**
    
    ```
    git branch -d desenvolvimento/protocolos-colheitadeira
    
    ```
    
    *Resultado esperado:* Branch deletada.
    

## Passo 7: Adicionando Últimas Seções e Finalizando o Sistema

Vamos adicionar as seções restantes para completar a estrutura inicial do sistema de gestão de maquinário.

1. **Crie os arquivos para um pulverizador e um implemento:**
    - **Crie a pasta `pulverizadores/` se ainda não existir.**
    - **Conteúdo para `gestao-maquinario-agricola/pulverizadores/pulverizador-01.md`:**
        
        ```
        # Pulverizador Jacto Condor - ID: PULV-01
        
        ## Informações Gerais:
        
        - **Modelo:** Jacto Condor 800
        - **Ano:** 2022
        - **Capacidade Tanque:** 800L
        
        ```
        
    - **Crie a pasta `implementos/` se ainda não existir.**
    - **Conteúdo para `gestao-maquinario-agricola/implementos/plantadeira-01.md`:**
        
        ```
        # Plantadeira Tatu Marchesan - ID: PLANT-01
        
        ## Informações Gerais:
        
        - **Modelo:** PST Super
        - **Linhas:** 11
        - **Ano:** 2019
        
        ```
        
    - *Ação no terminal:* Crie os arquivos no VSCode e adicione o conteúdo.
2. **Crie o arquivo `protocolos-manutencao/registro-horas-uso.md` e adicione o conteúdo:**
    - **Conteúdo para `gestao-maquinario-agricola/protocolos-manutencao/registro-horas-uso.md`:**
        
        ```
        ### Protocolo de Registro de Horas de Uso
        
        - **Frequência:** Diária, ao final do turno.
        - **Responsável:** Operador.
        - **Formato:** Planilha digital (link: [link para planilha]).
        
        ```
        
    - *Ação no terminal:* Crie o arquivo no VSCode e adicione o conteúdo.
3. **Adicione os novos arquivos ao Staging Area:**
    
    ```
    git add pulverizadores/pulverizador-01.md implementos/plantadeira-01.md protocolos-manutencao/registro-horas-uso.md
    
    ```
    
    *Resultado esperado:* Os arquivos estão prontos para serem comitados.
    
4. **Registre as últimas seções:**
    
    ```
    git commit -m "feat: adiciona pulverizador, plantadeira e protocolo de registro de horas"
    
    ```
    
    *Resultado esperado:* O sistema de gestão de maquinário está com sua estrutura inicial completa e registrada no Git.
    

## Conclusão: Git na Gestão Estratégica de Maquinário Agrícola

Você acaba de simular a criação e o versionamento de um sistema de gestão e manutenção para maquinário agrícola utilizando o Git. Esta abordagem permite que a gestão da sua frota seja:

- **Detalhista:** Cada máquina tem seu próprio dossiê com histórico completo.
- **Transparente:** Todas as manutenções, peças trocadas e horas de uso são registradas e rastreáveis.
- **Colaborativa:** Mecânicos, operadores e gerentes podem contribuir para o histórico de cada equipamento.
- **Base para Decisões:** Ajuda a identificar máquinas com alto custo de manutenção, planejar substituições e otimizar o uso.
- **Valorização do Ativo:** Um histórico de manutenção bem documentado agrega valor ao equipamento na hora da venda.

**Próximos Passos para aprimorar sua prática:**

- **Explore o `git log`:** Use `git log --all --graph --decorate --oneline` para visualizar o histórico completo e entender como as branches e merges/rebases afetaram o fluxo da documentação do seu maquinário.
- **Crie um repositório no GitHub:** Leve este sistema para o GitHub e pratique os comandos de interação com um repositório remoto (`git push`, `git pull`).
- **Simule um conflito de merge:** Tente fazer alterações conflitantes em um histórico de manutenção de uma máquina em duas branches diferentes e veja como o Git lida com isso.