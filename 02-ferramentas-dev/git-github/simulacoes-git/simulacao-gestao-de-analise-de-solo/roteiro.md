# 🌱 Simulação Git Aplicada: Sistema de Gestão de Análise de Solo

Este guia detalha uma simulação de como o Git pode ser utilizado para versionar e gerenciar um "Sistema de Gestão de Análise de Solo". O objetivo é documentar de forma transparente e rastreável todos os protocolos de coleta, resultados de laboratório, recomendações agronômicas e o histórico de fertilidade de cada área da fazenda.

Siga cada instrução no seu terminal e crie os arquivos e pastas no seu VSCode (ou editor de texto preferido) conforme o conteúdo fornecido.

## Preparação do Ambiente: Configurando o Laboratório de Solo Digital

Vamos começar criando a pasta principal para o sistema de análise de solo e inicializando o repositório Git.

1. **Crie a pasta raiz do projeto e navegue até ela:**

   ```
   mkdir analise-solo-git
   cd analise-solo-git

   ```

   _Resultado esperado:_ Você terá uma nova pasta `analise-solo-git`.

2. **Inicialize o repositório Git:**

   ```
   git init

   ```

   _Resultado esperado:_ O Git cria a pasta `.git` oculta, transformando `analise-solo-git` em um repositório Git.

3. **Configure seu nome e e-mail para os registros do sistema:** (Substitua pelos seus dados)

   ```
   git config user.name "Agrônomo da Fazenda"
   git config user.email "agronomo@fazenda.com"

   ```

   _Resultado esperado:_ Suas informações serão associadas a cada registro de análise de solo.

4. **Defina a branch principal como 'solo-produtivo':**
   Esta branch representará a versão consolidada e ativa do sistema de gestão de solo.

```
git config init.defaultBranch solo-produtivo

```

_Resultado esperado:_ A branch principal do seu repositório será chamada `solo-produtivo`.

## Passo 1: Estrutura Inicial e Protocolos Básicos

Vamos criar a estrutura de pastas e os arquivos iniciais do sistema, registrando os primeiros protocolos.

1. **Crie o arquivo `README.md` na raiz do projeto (`analise-solo-git/README.md`):**
   - **Conteúdo para `analise-solo-git/README.md`:**
     ```
     # Sistema de Gestão de Análise de Solo

     Este repositório documenta os protocolos, resultados e recomendações para o manejo do solo da fazenda.

     ## Estrutura do Sistema:

     - `01-protocolos-coleta/`: Diretrizes para amostragem de solo.
     - `02-resultados-analises/`: Relatórios de laboratório e interpretações.
     - `03-recomendacoes-adubacao/`: Planos de adubação e calagem.
     - `04-historico-talhoes/`: Histórico de fertilidade por área.
     - `documentos-gerais/`: Visão geral e diretrizes.

     ```
   - _Ação no terminal:_ Crie o arquivo e cole o conteúdo no VSCode.
2. **Crie as pastas conforme a estrutura sugerida:**

   ```
   mkdir 01-protocolos-coleta
   mkdir 02-resultados-analises
   mkdir 03-recomendacoes-adubacao
   mkdir 04-historico-talhoes
   mkdir documentos-gerais

   ```

   _Resultado esperado:_ As subpastas serão criadas.

3. **Crie os arquivos dentro de `documentos-gerais/` e `01-protocolos-coleta/` e adicione o conteúdo:**
   - **Conteúdo para `analise-solo-git/documentos-gerais/visao-geral.md`:**
     ```
     ### Visão Geral do Sistema de Solo

     - **Objetivo:** Otimizar a fertilidade do solo para maximizar a produtividade e sustentabilidade.
     - **Frequência de Análise:** Anual para lavouras, bienal para pastagens.

     ```
   - **Conteúdo para `analise-solo-git/01-protocolos-coleta/amostragem-pastagem.md`:**
     ```
     ### Protocolo de Amostragem de Pastagem

     - **Profundidade:** 0-20 cm.
     - **Pontos de Coleta:** 20 subamostras por piquete (em zigue-zague).
     - **Época:** Antes da adubação de correção.

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

6. **Registre a estrutura inicial e os protocolos básicos:**

   ```
   git commit -m "feat: estrutura inicial do sistema de solo e protocolo de amostragem de pastagem"

   ```

   _Resultado esperado:_ O primeiro "registro" do seu sistema é feito no histórico do Git. Use `git log --oneline` para ver.

## Passo 2: Detalhando Resultados e Interpretações (Branching e Merge)

O técnico agrícola recebeu os resultados de uma análise de solo de um talhão específico e precisa registrá-los e interpretá-los.

1. **Crie e troque para a branch 'desenvolvimento/resultados-talhao-5':**

   ```
   git switch -c desenvolvimento/resultados-talhao-5

   ```

   _Resultado esperado:_ Você agora está na branch `desenvolvimento/resultados-talhao-5`. Use `git branch` para confirmar.

2. **Crie os arquivos dentro de `02-resultados-analises/` e adicione o conteúdo:**
   - **Conteúdo para `analise-solo-git/02-resultados-analises/talhao-5-analise-2025.md`:**
     ```
     ### Análise de Solo - Talhão 5 (2025)

     - **Data da Análise:** 01/07/2025
     - **pH:** 5.2
     - **P (Fósforo):** 8.5 mg/dm³ (baixo)
     - **K (Potássio):** 0.15 cmolc/dm³ (médio)
     - **Matéria Orgânica (MO):** 2.5%

     ```
   - **Conteúdo para `analise-solo-git/02-resultados-analises/talhao-5-interpretacao-2025.md`:**
     ```
     ### Interpretação da Análise - Talhão 5 (2025)

     - **Conclusão:** Solo ácido, com deficiência de Fósforo. Potássio em nível adequado.
     - **Necessidade:** Calagem e adubação fosfatada.

     ```
   - _Ação no terminal:_ Crie os arquivos e cole o conteúdo no VSCode.
3. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 02-resultados-analises/

   ```

   _Resultado esperado:_ Os arquivos de resultados e interpretação estão prontos para serem comitados.

4. **Registre a nova seção no histórico da branch:**

   ```
   git commit -m "feat: adiciona resultados e interpretacao da analise de solo do Talhao 5 (2025)"

   ```

   _Resultado esperado:_ Um novo registro (commit) é adicionado apenas na branch `desenvolvimento/resultados-talhao-5`.

## Passo 3: Integrando os Resultados da Análise (Merge)

Os resultados e a interpretação foram revisados e aprovados. Agora, precisam ser incorporados à versão principal do sistema.

1. **Volte para a branch 'solo-produtivo':**

   ```
   git switch solo-produtivo

   ```

   _Resultado esperado:_ Você está de volta à `solo-produtivo`. Os arquivos de `02-resultados-analises/` não aparecem aqui ainda.

2. **Mescle a branch 'desenvolvimento/resultados-talhao-5' na 'solo-produtivo':**

   ```
   git merge desenvolvimento/resultados-talhao-5

   ```

   _Resultado esperado:_ As alterações da branch `desenvolvimento/resultados-talhao-5` (incluindo a pasta e seus arquivos) são integradas à `solo-produtivo`. Um "Merge commit" será criado automaticamente.

3. **Deletar a branch de desenvolvimento após a integração (opcional):**

   ```
   git branch -d desenvolvimento/resultados-talhao-5

   ```

   _Resultado esperado:_ A branch `desenvolvimento/resultados-talhao-5` é removida localmente.

## Passo 4: Corrigindo uma Recomendação de Calagem com `amend`

O agrônomo percebeu que a dose de calcário na recomendação estava incorreta, logo após o último registro. Ele quer corrigir e ajustar a mensagem do registro.

1. **Crie o arquivo `03-recomendacoes-adubacao/recomendacao-talhao-5-2025.md` e adicione o conteúdo inicial:**

   - **Conteúdo para `analise-solo-git/03-recomendacoes-adubacao/recomendacao-talhao-5-2025.md`:**
     ```
     ### Recomendação de Adubação e Calagem - Talhão 5 (2025)

     - **Calagem:** 2.5 ton/ha de Calcário (dose incorreta).
     - **Adubação Fosfatada:** 100 kg/ha de P2O5.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.

   ```
   git add 03-recomendacoes-adubacao/recomendacao-talhao-5-2025.md
   git commit -m "feat: adiciona recomendacao de adubacao e calagem para Talhao 5"

   ```

   _Resultado esperado:_ Um novo commit com a recomendação.

2. **Faça uma correção no arquivo `03-recomendacoes-adubacao/recomendacao-talhao-5-2025.md`:**
   Simule que você abriu `recomendacao-talhao-5-2025.md` e corrigiu a dose de calcário:

```
### Recomendação de Adubação e Calagem - Talhão 5 (2025)

- **Calagem:** **3.0 ton/ha** de Calcário (dose correta).
- **Adubação Fosfatada:** 100 kg/ha de P2O5.

```

_Ação no terminal:_ Edite o arquivo `analise-solo-git/03-recomendacoes-adubacao/recomendacao-talhao-5-2025.md` no VSCode e altere a dose.

3. **Adicione a correção ao Staging Area:**

   ```
   git add 03-recomendacoes-adubacao/recomendacao-talhao-5-2025.md

   ```

   _Resultado esperado:_ A alteração está pronta para ser comitada.

4. **Altere o _último_ registro (commit) usando `amend`:**
   Isso reescreve o último commit, incluindo a nova alteração e a nova mensagem.

```
git commit --amend -m "fix: corrige dose de calcario para 3.0 ton/ha para Talhao 5"

```

_Resultado esperado:_ O último commit **não é um novo registro**, mas uma modificação do registro anterior. Ele terá um **novo identificador (hash)**, e a mensagem original será substituída. Use `git log --oneline` para ver que o ID do commit mudou.

**ALERTA IMPORTANTE: `git push --force`**
Lembre-se do aviso sobre `git push --force` em repositórios remotos compartilhados. Em um ambiente de equipe, o `amend` em um commit já enviado pode causar problemas e deve ser evitado ou coordenado.

## Passo 5: Descartando uma Anotação de Campo Preliminar com `git reset --soft`

Imagine que um técnico de campo fez uma anotação rápida sobre uma observação visual do solo (ex: "solo compactado em alguns pontos"), mas depois de uma análise mais profunda, essa observação foi descartada como não representativa. Você quer remover esse registro do histórico principal, mas manter a anotação para referência interna.

1. **Crie o arquivo `04-historico-talhoes/talhao-5-observacoes-preliminares.md` e adicione uma nota temporária e registre-a:**

   - **Conteúdo para `analise-solo-git/04-historico-talhoes/talhao-5-observacoes-preliminares.md`:**
     ```
     ### Observações Preliminares - Talhão 5

     - **Data:** 02/07/2025
     - **Observação:** Solo com sinais de compactação em 10% da área (observação inicial).

     ```
   - _Ação no terminal:_ Crie o arquivo `analise-solo-git/04-historico-talhoes/talhao-5-observacoes-preliminares.md` no VSCode e adicione o conteúdo.

   ```
   git add 04-historico-talhoes/talhao-5-observacoes-preliminares.md
   git commit -m "chore: adiciona observacao preliminar de compactacao no Talhao 5"

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

   - O último commit ("chore: adiciona observacao...") sumiu do `git log`.
   - `git status` mostrará que as alterações (o arquivo `talhao-5-observacoes-preliminares.md` com a observação) ainda estão no Staging Area (`Changes to be committed`), prontas para serem comitadas novamente (com uma nova mensagem, por exemplo, "Observação de compactação - descartada, mantida para registro interno") ou descartadas.

   **Para seguir o próximo passo, vamos descartar essa alteração temporária completamente:**

   ```
   git restore 04-historico-talhoes/talhao-5-observacoes-preliminares.md
   git reset --hard HEAD # Garante que o diretório de trabalho esteja limpo e alinhado com o ultimo commit

   ```

   _Resultado esperado:_ `talhao-5-observacoes-preliminares.md` volta ao estado do último commit válido, e o diretório de trabalho está limpo.

## Passo 6: Atualizando Protocolos de Coleta para Lavouras com `git rebase` (Histórico Linear)

Imagine que a equipe de solo está detalhando os protocolos de amostragem para lavouras. Enquanto eles trabalham, a branch `solo-produtivo` recebe uma atualização importante sobre a frequência de análise de solo. A equipe de solo quer que seus registros de protocolo de amostragem de lavoura apareçam _depois_ dessa atualização de frequência, mantendo um histórico linear.

1. **Garantir que estamos na branch 'solo-produtivo' e adicionar uma atualização na frequência de análise:**

   - **Conteúdo para `analise-solo-git/documentos-gerais/visao-geral.md` (adicione uma linha):**
     ```
     ### Visão Geral do Sistema de Solo

     - **Objetivo:** Otimizar a fertilidade do solo para maximizar a produtividade e sustentabilidade.
     - **Frequência de Análise:** Anual para lavouras, bienal para pastagens.
     - **NOVO: Análise de micronutrientes a cada 3 anos.**

     ```
   - _Ação no terminal:_ Edite o arquivo `analise-solo-git/documentos-gerais/visao-geral.md` no VSCode e adicione a linha.

   ```
   git switch solo-produtivo
   git add documentos-gerais/visao-geral.md
   git commit -m "docs: atualiza visao geral com frequencia de analise de micronutrientes"

   ```

   _Resultado esperado:_ Um novo commit na branch `solo-produtivo`.

2. **Crie uma nova branch para os protocolos de amostragem de lavoura:**

   ```
   git switch -c desenvolvimento/amostragem-lavoura

   ```

   _Resultado esperado:_ Você está na `desenvolvimento/amostragem-lavoura`.

3. **Crie o arquivo `01-protocolos-coleta/amostragem-lavoura.md` e faça um registro inicial na branch de amostragem:**

   - **Conteúdo para `analise-solo-git/01-protocolos-coleta/amostragem-lavoura.md`:**
     ```
     ### Protocolo de Amostragem de Lavoura

     - **Profundidade:** 0-20 cm e 20-40 cm (para P e K).
     - **Pontos de Coleta:** 20 subamostras por gleba (em zigue-zague).
     - **Época:** Pós-colheita, antes do preparo do solo.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.

   ```
   git add 01-protocolos-coleta/amostragem-lavoura.md
   git commit -m "feat: inicia protocolo de amostragem para lavouras"

   ```

   _Resultado esperado:_ Um commit na sua branch `desenvolvimento/amostragem-lavoura`.

4. **Verifique o histórico para ver a divergência:**

   ```
   git log --oneline --all --graph

   ```

   _Resultado esperado:_ Você verá a branch `solo-produtivo` e `desenvolvimento/amostragem-lavoura` com commits independentes após um ponto em comum.

5. **Aplique o `rebase` da branch 'desenvolvimento/amostragem-lavoura' sobre a 'solo-produtivo':**
   Isso "move" os commits da sua branch de amostragem para que eles apareçam _depois_ do último commit da `solo-produtivo`.

```
git rebase solo-produtivo

```

_Resultado esperado:_ O Git reescreve o histórico da sua branch `desenvolvimento/amostragem-lavoura`. Os commits do protocolo de amostragem agora virão após o commit da frequência de análise de micronutrientes.

6. **Verifique o histórico novamente para ver a linearidade:**

   ```
   git log --oneline --all --graph

   ```

   _Resultado esperado:_ O histórico da `desenvolvimento/amostragem-lavoura` agora aparece como se tivesse sido criado _depois_ do último commit da `solo-produtivo`, resultando em um fluxo linear.

7. **Volte para a `solo-produtivo` e mescle (será um Fast-Forward):**
   Como a `desenvolvimento/amostragem-lavoura` está "à frente" da `solo-produtivo` devido ao rebase, o merge será um "fast-forward" (sem criar um merge commit).

```
git switch solo-produtivo
git merge desenvolvimento/amostragem-lavoura

```

_Resultado esperado:_ A `solo-produtivo` simplesmente avança para incluir os commits da seção de amostragem de lavouras. O histórico continua linear.

8. **Deletar a branch de desenvolvimento:**

   ```
   git branch -d desenvolvimento/amostragem-lavoura

   ```

   _Resultado esperado:_ Branch deletada.

## Passo 7: Adicionando Últimas Seções e Finalizando o Sistema

Vamos adicionar as seções restantes para completar a estrutura inicial do sistema de gestão de análise de solo.

1. **Crie os arquivos para resultados e histórico adicionais:**
   - **Conteúdo para `analise-solo-git/02-resultados-analises/talhao-6-analise-2024.md`:**
     ```
     ### Análise de Solo - Talhão 6 (2024)

     - **Data da Análise:** 15/08/2024
     - **pH:** 6.0
     - **P (Fósforo):** 12.0 mg/dm³ (médio)

     ```
   - **Conteúdo para `analise-solo-git/04-historico-talhoes/talhao-5-historico-fertilidade.md`:**
     ```
     ### Histórico de Fertilidade - Talhão 5

     - **2023:** pH 4.8, P 5.0, K 0.10
     - **2024:** pH 5.0, P 7.0, K 0.12
     - **2025:** pH 5.2, P 8.5, K 0.15 (atual)

     ```
   - _Ação no terminal:_ Crie os arquivos no VSCode e adicione o conteúdo.
2. **Crie o arquivo `03-recomendacoes-adubacao/recomendacao-pastagem-2025.md` e adicione o conteúdo:**
   - **Conteúdo para `analise-solo-git/03-recomendacoes-adubacao/recomendacao-pastagem-2025.md`:**
     ```
     ### Recomendação de Adubação - Pastagem (2025)

     - **Adubação de Manutenção:** 50 kg/ha de NPK 20-05-20.
     - **Aplicação:** Após pastejo, início da estação chuvosa.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.
3. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 02-resultados-analises/talhao-6-analise-2024.md 04-historico-talhoes/talhao-5-historico-fertilidade.md 03-recomendacoes-adubacao/recomendacao-pastagem-2025.md

   ```

   _Resultado esperado:_ Os arquivos estão prontos para serem comitados.

4. **Registre as últimas seções:**

   ```
   git commit -m "feat: completa sistema com analise Talhao 6, historico Talhao 5 e recomendacao pastagem"

   ```

   _Resultado esperado:_ O sistema de gestão de análise de solo está com sua estrutura inicial completa e registrada no Git.

## Conclusão: Git como Base para a Fertilidade do Solo

Você acaba de simular a criação e o versionamento de um sistema de gestão de análise de solo utilizando o Git. Esta abordagem permite que a gestão da fertilidade do solo seja:

- **Científica e Precisa:** Protocolos, resultados e recomendações são documentados de forma rigorosa.
- **Histórico Completo:** Acompanhe a evolução da fertilidade de cada talhão/piquete ao longo dos anos.
- **Colaboração Eficiente:** Agrônomos, técnicos e consultores podem trabalhar juntos na interpretação e recomendação.
- **Base para Decisões Estratégicas:** Identifique tendências, otimize o uso de insumos e planeje a recuperação de áreas degradadas.
- **Transparência e Auditoria:** Fundamental para certificações e comprovação de boas práticas de manejo.

Sua formação em Zootecnia e ADS é um casamento perfeito para aplicar essas tecnologias e otimizar a produção no campo.

**Próximos Passos para aprimorar sua prática:**

- **Explore o `git log`:** Use `git log --all --graph --decorate --oneline` para visualizar o histórico completo e entender como as branches e merges/rebases afetaram o fluxo do seu sistema de solo.
- **Crie um repositório no GitHub:** Leve este sistema para o GitHub e pratique os comandos de interação com um repositório remoto (`git push`, `git pull`).
- **Simule um conflito de merge:** Tente fazer alterações conflitantes em um arquivo de recomendação de adubação em duas branches diferentes e veja como o Git lida com isso.
