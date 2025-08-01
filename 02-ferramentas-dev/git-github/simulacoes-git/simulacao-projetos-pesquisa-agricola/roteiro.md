# 🔬 Simulação Git Aplicada: Gestão de Projetos de Pesquisa Agrícola

Para a próxima simulação, vamos mergulhar no mundo da **Pesquisa Agrícola**. Imagine que você faz parte de uma equipe que conduz diversos experimentos e estudos no campo. O Git será sua ferramenta para gerenciar os projetos, registrar metodologias, coletar dados brutos, analisar resultados e gerar relatórios, garantindo a rastreabilidade e a colaboração em cada etapa da pesquisa.

Esta simulação vai te permitir praticar o gerenciamento de múltiplos fluxos de trabalho e a integração de diferentes contribuições.

## Preparação do Ambiente: Montando o Laboratório Digital

Vamos começar criando a pasta principal para os projetos de pesquisa e inicializando o repositório Git.

1. **Crie a pasta raiz para os projetos de pesquisa e navegue até ela:**

   ```
   mkdir projetos-pesquisa-agricola
   cd projetos-pesquisa-agricola

   ```

   _Resultado esperado:_ Você terá uma nova pasta `projetos-pesquisa-agricola`.

2. **Inicialize o repositório Git:**

   ```
   git init

   ```

   _Resultado esperado:_ O Git cria a pasta `.git` oculta, transformando `projetos-pesquisa-agricola` em um repositório Git.

3. **Configure seu nome e e-mail para os registros da pesquisa:** (Substitua pelos seus dados)

   ```
   git config user.name "Pesquisador Chefe"
   git config user.email "pesquisador@fazenda.com"

   ```

   _Resultado esperado:_ Suas informações serão associadas a cada etapa da pesquisa.

4. **Defina a branch principal como 'master-pesquisa':**
   Esta será a branch que conterá os resultados consolidados e relatórios finais.

```
git config init.defaultBranch master-pesquisa

```

_Resultado esperado:_ A branch principal do seu repositório de pesquisa será chamada `master-pesquisa`.

## Passo 1: Início do Projeto de Pesquisa e Documentação Base

Vamos criar a estrutura inicial do repositório de pesquisa e os documentos fundamentais.

1. **Crie o arquivo `README.md` na raiz do projeto (`projetos-pesquisa-agricola/README.md`):**
   - **Conteúdo para `projetos-pesquisa-agricola/README.md`:**
     ```
     # Projetos de Pesquisa Agrícola

     Este repositório contém a documentação, dados e relatórios de diversos experimentos agrícolas.

     ## Estrutura dos Projetos:

     - `01-experimento-x/`: Detalhes do Experimento X (Metodologia, Dados, Análises).
     - `02-experimento-y/`: Detalhes do Experimento Y.
     - `relatorios-finais/`: Relatórios consolidados dos experimentos.
     - `documentos-gerais/`: Protocolos e diretrizes da equipe de pesquisa.

     ```
   - _Ação no terminal:_ Crie o arquivo e cole o conteúdo no VSCode.
2. **Crie as pastas para o primeiro experimento e documentos gerais:**

   ```
   mkdir 01-experimento-x
   mkdir relatorios-finais
   mkdir documentos-gerais

   ```

   _Resultado esperado:_ As subpastas serão criadas.

3. **Crie os arquivos dentro de `01-experimento-x/` e `documentos-gerais/` e adicione o conteúdo:**
   - **Conteúdo para `projetos-pesquisa-agricola/01-experimento-x/metodologia.md`:**
     ```
     ### Metodologia do Experimento X

     - **Objetivo:** Avaliar a eficiência do novo fertilizante orgânico.
     - **Área:** Talhão 5 (1 hectare).
     - **Tratamentos:** Controle (sem fertilizante), T1 (Fertilizante A), T2 (Fertilizante B).

     ```
   - **Conteúdo para `projetos-pesquisa-agricola/documentos-gerais/protocolo-coleta-dados.md`:**
     ```
     ### Protocolo de Coleta de Dados

     - Frequência: Semanal.
     - Parâmetros: Altura da planta, número de folhas, presença de pragas.

     ```
   - _Ação no terminal:_ Crie os arquivos e cole o conteúdo no VSCode.
4. **Verifique o status do seu repositório de pesquisa:**

   ```
   git status

   ```

   _Resultado esperado:_ O Git mostrará todos os arquivos e pastas recém-criados como não rastreados.

5. **Adicione todos os arquivos ao "Staging Area":**

   ```
   git add .

   ```

   _Resultado esperado:_ Todos os arquivos estão agora prontos para serem comitados.

6. **Registre a primeira versão do projeto de pesquisa:**

   ```
   git commit -m "feat: setup inicial do repositorio de pesquisa e Experimento X"

   ```

   _Resultado esperado:_ O primeiro "registro" do seu projeto é feito no histórico do Git. Use `git log --oneline` para ver.

## Passo 2: Coleta de Dados de Campo (Branching e Merge)

Um técnico de campo é responsável por registrar os dados brutos do Experimento X. Ele vai criar uma branch para suas atualizações diárias/semanais.

1. **Crie e troque para a branch 'dados/experimento-x':**

   ```
   git switch -c dados/experimento-x

   ```

   _Resultado esperado:_ Você agora está na branch `dados/experimento-x`. Use `git branch` para confirmar.

2. **Crie o arquivo `01-experimento-x/dados-brutos-semana1.csv` e adicione o conteúdo (simulando dados):**
   - **Conteúdo para `projetos-pesquisa-agricola/01-experimento-x/dados-brutos-semana1.csv`:**
     ```
     Data,Tratamento,Planta,Altura(cm),Folhas,Pragas(0/1)
     2024-07-01,Controle,P1,10.5,5,0
     2024-07-01,T1,P2,12.1,6,0
     2024-07-01,T2,P3,11.8,5,0

     ```
   - _Ação no terminal:_ Crie o arquivo e cole o conteúdo no VSCode.
3. **Adicione o novo arquivo de dados ao Staging Area:**

   ```
   git add 01-experimento-x/dados-brutos-semana1.csv

   ```

   _Resultado esperado:_ O arquivo de dados está pronto para ser comitado.

4. **Registre a coleta de dados da primeira semana:**

   ```
   git commit -m "data: adiciona dados brutos da semana 1 do Experimento X"

   ```

   _Resultado esperado:_ Um novo registro (commit) é adicionado apenas na branch `dados/experimento-x`.

## Passo 3: Integrando os Dados Brutos (Merge)

Os dados da primeira semana foram coletados e precisam ser integrados à branch principal de pesquisa para que a equipe possa acessá-los.

1. **Volte para a branch 'master-pesquisa':**

   ```
   git switch master-pesquisa

   ```

   _Resultado esperado:_ Você está de volta à `master-pesquisa`. O arquivo de dados brutos não aparece aqui ainda.

2. **Mescle a branch 'dados/experimento-x' na 'master-pesquisa':**

   ```
   git merge dados/experimento-x

   ```

   _Resultado esperado:_ As alterações da branch `dados/experimento-x` (incluindo o arquivo CSV) são integradas à `master-pesquisa`. Um "Merge commit" será criado automaticamente.

3. **Deletar a branch de dados após a integração (opcional, se não houver mais coletas nessa branch):**

   ```
   git branch -d dados/experimento-x

   ```

   _Resultado esperado:_ A branch `dados/experimento-x` é removida localmente.

## Passo 4: Corrigindo um Erro em Metodologia com `amend`

O pesquisador chefe revisou a metodologia do Experimento X e percebeu um erro na descrição dos tratamentos, logo após o último registro. Ele quer corrigir e ajustar a mensagem do registro.

1. **Faça uma correção no arquivo `01-experimento-x/metodologia.md`:**
   Simule que você abriu `metodologia.md` e corrigiu a descrição do Tratamento 2:

```
### Metodologia do Experimento X

- **Objetivo:** Avaliar a eficiência do novo fertilizante orgânico.
- **Área:** Talhão 5 (1 hectare).
- **Tratamentos:** Controle (sem fertilizante), T1 (Fertilizante A), **T2 (Fertilizante B - dose dupla)**.

```

_Ação no terminal:_ Edite o arquivo `projetos-pesquisa-agricola/01-experimento-x/metodologia.md` no VSCode e altere a descrição.

2. **Adicione a correção ao Staging Area:**

   ```
   git add 01-experimento-x/metodologia.md

   ```

   _Resultado esperado:_ A alteração está pronta para ser comitada.

3. **Altere o _último_ registro (commit) usando `amend`:**
   Isso reescreve o último commit, incluindo a nova alteração e a nova mensagem.

```
git commit --amend -m "fix: corrige descricao do Tratamento T2 na metodologia do Experimento X"

```

_Resultado esperado:_ O último commit **não é um novo registro**, mas uma modificação do registro anterior. Ele terá um **novo identificador (hash)**, e a mensagem original será substituída. Use `git log --oneline` para ver que o ID do commit mudou.

**ALERTA IMPORTANTE: `git push --force`**
Lembre-se do aviso sobre `git push --force` em repositórios remotos compartilhados. Em um ambiente de equipe, o `amend` em um commit já enviado pode causar problemas e deve ser evitado ou coordenado.

## Passo 5: Desfazendo um Rascunho de Análise Preliminar com `git reset --soft`

Imagine que um pesquisador fez uma análise preliminar rápida dos dados, gerou um rascunho de relatório e comitou, mas depois percebeu que a abordagem estava errada e precisa refazer a análise do zero. Ele quer remover o registro do rascunho do histórico, mas manter o arquivo para referência.

1. **Crie o arquivo `01-experimento-x/analise-preliminar-rascunho.md` e adicione um conteúdo temporário e registre-o:**

   - **Conteúdo para `projetos-pesquisa-agricola/01-experimento-x/analise-preliminar-rascunho.md`:**
     ```
     ### Análise Preliminar do Experimento X (Rascunho)

     - Observação: T1 parece ter maior crescimento. (Ainda não confirmado)

     ```
   - _Ação no terminal:_ Crie o arquivo `projetos-pesquisa-agricola/01-experimento-x/analise-preliminar-rascunho.md` no VSCode e adicione o conteúdo.

   ```
   git add 01-experimento-x/analise-preliminar-rascunho.md
   git commit -m "docs: adiciona rascunho de analise preliminar do Experimento X"

   ```

   _Resultado esperado:_ Um novo commit aparece no `git log`.

2. **Verifique o status do repositório:**

   ```
   git status

   ```

   _Resultado esperado:_ O repositório está limpo.

3. **Desfaça o último registro, mantendo as alterações no "Staging Area":**

   ```
   git reset --soft HEAD~1

   ```

   _Resultado esperado:_

   - O último commit ("docs: adiciona rascunho...") sumiu do `git log`.
   - `git status` mostrará que as alterações (o arquivo `analise-preliminar-rascunho.md`) ainda estão no Staging Area (`Changes to be committed`), prontas para serem comitadas novamente (com uma nova mensagem, por exemplo, "Rascunho de análise - descartado, mantido para histórico") ou descartadas.

   **Para seguir o próximo passo, vamos descartar essa alteração temporária completamente:**

   ```
   git restore 01-experimento-x/analise-preliminar-rascunho.md
   git reset --hard HEAD # Garante que o diretório de trabalho esteja limpo e alinhado com o ultimo commit

   ```

   _Resultado esperado:_ `analise-preliminar-rascunho.md` volta ao estado do último commit válido (ou é removido se não estava no commit anterior), e o diretório de trabalho está limpo.

## Passo 6: Desenvolvendo um Novo Experimento com `git rebase` (Histórico Linear)

Imagine que uma nova equipe começa a planejar o Experimento Y. Enquanto eles documentam a metodologia, a branch `master-pesquisa` recebe uma atualização importante no protocolo de coleta de dados. A equipe do Experimento Y quer que seus registros de planejamento apareçam _depois_ dessa atualização, mantendo um histórico linear.

1. **Garantir que estamos na branch 'master-pesquisa' e adicionar uma atualização no protocolo de coleta:**

   - **Conteúdo para `projetos-pesquisa-agricola/documentos-gerais/protocolo-coleta-dados.md` (adicione uma linha):**
     ```
     ### Protocolo de Coleta de Dados

     - Frequência: Semanal.
     - Parâmetros: Altura da planta, número de folhas, presença de pragas.
     - **NOVO: Usar aplicativo móvel para registro de dados.**

     ```
   - _Ação no terminal:_ Edite o arquivo `projetos-pesquisa-agricola/documentos-gerais/protocolo-coleta-dados.md` no VSCode e adicione a linha.

   ```
   git switch master-pesquisa
   git add documentos-gerais/protocolo-coleta-dados.md
   git commit -m "docs: atualiza protocolo de coleta de dados com uso de app"

   ```

   _Resultado esperado:_ Um novo commit na branch `master-pesquisa`.

2. **Crie uma nova branch para o Experimento Y:**

   ```
   mkdir 02-experimento-y # Crie a pasta para o novo experimento
   git switch -c desenvolvimento/experimento-y

   ```

   _Resultado esperado:_ Você está na `desenvolvimento/experimento-y`.

3. **Crie o arquivo `02-experimento-y/metodologia-y.md` e faça um registro inicial na branch do Experimento Y:**

   - **Conteúdo para `projetos-pesquisa-agricola/02-experimento-y/metodologia-y.md`:**
     ```
     ### Metodologia do Experimento Y

     - **Objetivo:** Testar resistência a seca de novas variedades.
     - **Variedades:** V1, V2, V3.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.

   ```
   git add 02-experimento-y/metodologia-y.md
   git commit -m "feat: inicia planejamento do Experimento Y"

   ```

   _Resultado esperado:_ Um commit na sua branch `desenvolvimento/experimento-y`.

4. **Verifique o histórico para ver a divergência:**

   ```
   git log --oneline --all --graph

   ```

   _Resultado esperado:_ Você verá a branch `master-pesquisa` e `desenvolvimento/experimento-y` com commits independentes após um ponto em comum.

5. **Aplique o `rebase` da branch 'desenvolvimento/experimento-y' sobre a 'master-pesquisa':**
   Isso "move" os commits da sua branch do Experimento Y para que eles apareçam _depois_ do último commit da `master-pesquisa`.

```
git rebase master-pesquisa

```

_Resultado esperado:_ O Git reescreve o histórico da sua branch `desenvolvimento/experimento-y`. Os commits do Experimento Y agora virão após o commit da atualização do protocolo de coleta.

6. **Verifique o histórico novamente para ver a linearidade:**

   ```
   git log --oneline --all --graph

   ```

   _Resultado esperado:_ O histórico da `desenvolvimento/experimento-y` agora aparece como se tivesse sido criado _depois_ do último commit da `master-pesquisa`, resultando em um fluxo linear.

7. **Volte para a `master-pesquisa` e mescle (será um Fast-Forward):**
   Como a `desenvolvimento/experimento-y` está "à frente" da `master-pesquisa` devido ao rebase, o merge será um "fast-forward" (sem criar um merge commit).

```
git switch master-pesquisa
git merge desenvolvimento/experimento-y

```

_Resultado esperado:_ A `master-pesquisa` simplesmente avança para incluir os commits do Experimento Y. O histórico continua linear.

8. **Deletar a branch de desenvolvimento:**

   ```
   git branch -d desenvolvimento/experimento-y

   ```

   _Resultado esperado:_ Branch deletada.

## Passo 7: Gerando um Relatório Final e Arquivando (Tagging)

Após a conclusão de um experimento, a equipe gera um relatório final e o "arquiva" no repositório, marcando uma versão específica com uma tag Git.

1. **Crie o arquivo `relatorios-finais/relatorio-experimento-x-v1.0.md` e adicione o conteúdo:**
   - **Conteúdo para `projetos-pesquisa-agricola/relatorios-finais/relatorio-experimento-x-v1.0.md`:**
     ```
     # Relatório Final - Experimento X (v1.0)

     ## Resultados:

     - O fertilizante B (T2) demonstrou 15% de aumento na altura da planta.
     - Não houve diferença significativa na incidência de pragas.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.
2. **Adicione o relatório ao Staging Area:**

   ```
   git add relatorios-finais/relatorio-experimento-x-v1.0.md

   ```

   _Resultado esperado:_ O relatório está pronto para ser comitado.

3. **Registre o relatório final:**

   ```
   git commit -m "docs: gera relatorio final v1.0 do Experimento X"

   ```

   _Resultado esperado:_ O relatório final está registrado no histórico.

4. **Crie uma tag para marcar esta versão do relatório:**

   ```
   git tag -a v1.0-experimento-x -m "Versao final 1.0 do relatorio do Experimento X"

   ```

   _Resultado esperado:_ Uma tag é criada no seu commit atual. Use `git tag` para listar as tags.

## Conclusão: Git na Gestão de Pesquisas Agrícolas

Você acaba de simular a criação e o versionamento de projetos de pesquisa agrícola utilizando o Git. Esta abordagem permite que a gestão da pesquisa seja:

- **Organizada:** Cada experimento e seus componentes (metodologia, dados, análises) ficam em pastas dedicadas.
- **Colaborativa:** Diferentes pesquisadores podem trabalhar em paralelo em seus experimentos ou análises.
- **Rastreável:** Cada alteração, desde um ajuste na metodologia até a adição de dados brutos ou a revisão de um relatório, é registrada.
- **Auditável:** É possível verificar o histórico completo de um experimento, o que é crucial para validação científica.
- **Versões Claras:** O uso de tags permite marcar versões específicas de relatórios ou fases de um experimento.

**Próximos Passos para aprimorar sua prática:**

- **Explore o `git log` com tags:** Use `git log --oneline --decorate --tags` para ver como as tags aparecem no histórico.
- **Crie um repositório no GitHub:** Leve este projeto de pesquisa para o GitHub e pratique os comandos de interação com um repositório remoto (`git push --tags`, `git pull`).
- **Simule um conflito de merge:** Tente fazer alterações conflitantes em um arquivo de dados ou metodologia em duas branches diferentes e veja como o Git lida com isso.
