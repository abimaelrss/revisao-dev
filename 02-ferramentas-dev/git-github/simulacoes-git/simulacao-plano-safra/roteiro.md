# 🌾 Simulação Git Aplicada: Plano de Safra com Versionamento

Este guia detalha uma simulação de como o Git pode ser utilizado para versionar e gerenciar um "Plano de Safra" agrícola. Cada passo demonstra um comando Git no contexto de atualizações, revisões e colaboração na documentação técnica de uma cultura específica (ex: soja, milho, café).

Siga cada instrução no seu terminal e crie os arquivos e pastas no seu VSCode (ou editor de texto preferido) conforme o conteúdo fornecido.

## Preparação do Ambiente: Criando o Plano Digital da Safra

Vamos começar criando a pasta principal do projeto do plano de safra e inicializando o repositório Git.

1. **Crie a pasta raiz do projeto e navegue até ela:**

   ```
   mkdir plano-safra
   cd plano-safra

   ```

   _Resultado esperado:_ Você terá uma nova pasta `plano-safra`.

2. **Inicialize o repositório Git:**

   ```
   git init

   ```

   _Resultado esperado:_ O Git cria a pasta `.git` oculta, transformando `plano-safra` em um repositório Git.

3. **Configure seu nome e e-mail para os registros do plano:** (Substitua pelos seus dados)

   ```
   git config user.name "Engenheiro Agrônomo"
   git config user.email "agronomo@fazenda.com"

   ```

   _Resultado esperado:_ Suas informações serão associadas a cada "edição" do plano.

4. **Defina a branch principal como 'safra-atual':**
   Esta será a branch que representa o plano de safra vigente.

```
git config init.defaultBranch safra-atual

```

_Resultado esperado:_ A branch principal do seu plano será chamada `safra-atual`.

## Passo 1: Estrutura Inicial e Planejamento Geral da Safra

Vamos criar a estrutura de pastas e os arquivos iniciais do plano, registrando a primeira versão.

1. **Crie o arquivo `README.md` na raiz do projeto (`plano-safra/README.md`):**
   - **Conteúdo para `plano-safra/README.md`:**
     ```
     # Plano de Safra - [Ano da Safra]

     Este repositório documenta o planejamento e a execução da safra agrícola.

     ## Estrutura do Plano:

     - `01-planejamento-geral/`: Objetivos e cronograma da safra.
     - `02-manejo-solo-plantio/`: Análise de solo e protocolos de plantio.
     - `03-manejo-fitossanitario/`: Controle de pragas e doenças.
     - `04-irrigacao-nutricao/`: Planos de irrigação e adubação.
     - `05-colheita-pos-colheita/`: Protocolos de colheita e armazenamento.

     ```
   - _Ação no terminal:_ Crie o arquivo e cole o conteúdo no VSCode.
2. **Crie as pastas conforme a estrutura sugerida:**

   ```
   mkdir 01-planejamento-geral
   mkdir 02-manejo-solo-plantio
   mkdir 03-manejo-fitossanitario
   mkdir 04-irrigacao-nutricao
   mkdir 05-colheita-pos-colheita

   ```

   _Resultado esperado:_ As subpastas serão criadas dentro de `plano-safra/`.

3. **Crie os arquivos dentro de `01-planejamento-geral/` e adicione o conteúdo:**
   - **Conteúdo para `plano-safra/01-planejamento-geral/cronograma-safra.md`:**
     ```
     ### Cronograma da Safra

     - **Outubro:** Preparo do solo, análise.
     - **Novembro:** Plantio da cultura X.
     - **Dezembro-Fevereiro:** Manejo vegetativo.
     - **Março:** Colheita.

     ```
   - **Conteúdo para `plano-safra/01-planejamento-geral/objetivos-producao.md`:**
     ```
     ### Objetivos de Produção

     - Meta de produtividade: 60 sacas/hectare.
     - Qualidade: Umidade < 14%.

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

6. **Registre a primeira versão do plano de safra:**

   ```
   git commit -m "feat: estrutura inicial do plano de safra e planejamento geral"

   ```

   _Resultado esperado:_ O primeiro "registro" do seu plano é feito no histórico do Git. Use `git log --oneline` para ver.

## Passo 2: Atualizando Protocolos de Manejo Fitossanitário (Branching e Merge)

Um novo monitoramento de pragas identificou a necessidade de ajustar o protocolo de controle. O especialista em fitossanidade vai trabalhar nessa atualização.

1. **Crie e troque para a branch 'desenvolvimento/fitossanitario':**

   ```
   git switch -c desenvolvimento/fitossanitario

   ```

   _Resultado esperado:_ Você agora está na branch `desenvolvimento/fitossanitario`. Use `git branch` para confirmar.

2. **Crie os arquivos dentro de `03-manejo-fitossanitario/` e adicione o conteúdo:**
   - **Conteúdo para `plano-safra/03-manejo-fitossanitario/controle-pragas.md`:**
     ```
     ### Controle de Pragas

     - Monitoramento semanal de lagartas e percevejos.
     - **Protocolo de aplicação:** Inseticida X (dose Y) se infestacao > Z%.

     ```
   - **Conteúdo para `plano-safra/03-manejo-fitossanitario/controle-doencas.md`:**
     ```
     ### Controle de Doenças

     - Monitoramento quinzenal de ferrugem.
     - Aplicação preventiva de fungicida A.

     ```
   - _Ação no terminal:_ Crie os arquivos e cole o conteúdo no VSCode.
3. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 03-manejo-fitossanitario/

   ```

   _Resultado esperado:_ Os arquivos de manejo fitossanitário estão prontos para serem comitados.

4. **Registre a nova seção no histórico da branch:**

   ```
   git commit -m "feat: adiciona secao de manejo fitossanitario"

   ```

   _Resultado esperado:_ Um novo registro (commit) é adicionado apenas na branch `desenvolvimento/fitossanitario`.

## Passo 3: Integrando os Protocolos Fitossanitários (Merge)

Os novos protocolos foram validados e agora precisam ser incorporados ao plano de safra principal.

1. **Volte para a branch 'safra-atual' (a versão principal do plano):**

   ```
   git switch safra-atual

   ```

   _Resultado esperado:_ Você está de volta à `safra-atual`. Os arquivos de `03-manejo-fitossanitario/` não aparecem aqui ainda.

2. **Mescle a branch 'desenvolvimento/fitossanitario' na 'safra-atual':**

   ```
   git merge desenvolvimento/fitossanitario

   ```

   _Resultado esperado:_ As alterações da branch `desenvolvimento/fitossanitario` (incluindo a pasta e seus arquivos) são integradas à `safra-atual`. Um "Merge commit" será criado automaticamente.

3. **Deletar a branch de desenvolvimento após a integração (opcional):**

   ```
   git branch -d desenvolvimento/fitossanitario

   ```

   _Resultado esperado:_ A branch `desenvolvimento/fitossanitario` é removida localmente.

## Passo 4: Ajustando a Recomendação de Adubação com `amend`

O agrônomo percebeu que a dose de um fertilizante foi digitada incorretamente na seção de adubação, logo após o último registro. Ele quer corrigir e ajustar a mensagem do registro.

1. **Crie o arquivo `04-irrigacao-nutricao/adubacao.md` e adicione o conteúdo inicial:**

   - **Conteúdo para `plano-safra/04-irrigacao-nutricao/adubacao.md`:**
     ```
     ### Plano de Adubação

     - Adubação de base: 150 kg/ha de NPK 08-28-16.
     - Adubação de cobertura: 80 kg/ha de Ureia.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.

   ```
   git add 04-irrigacao-nutricao/adubacao.md
   git commit -m "feat: adiciona plano inicial de adubacao"

   ```

   _Resultado esperado:_ Um novo commit com o plano de adubação.

2. **Faça uma correção no arquivo `04-irrigacao-nutricao/adubacao.md`:**
   Simule que você abriu `adubacao.md` e corrigiu a dose da ureia:

```
### Plano de Adubação

- Adubação de base: 150 kg/ha de NPK 08-28-16.
- Adubação de cobertura: **90 kg/ha** de Ureia.

```

_Ação no terminal:_ Edite o arquivo `plano-safra/04-irrigacao-nutricao/adubacao.md` no VSCode e altere a dose.

3. **Adicione a correção ao Staging Area:**

   ```
   git add 04-irrigacao-nutricao/adubacao.md

   ```

   _Resultado esperado:_ A alteração está pronta para ser comitada.

4. **Altere o _último_ registro (commit) usando `amend`:**
   Isso reescreve o último commit, incluindo a nova alteração e a nova mensagem.

```
git commit --amend -m "fix: corrige dose de ureia na adubacao de cobertura para 90 kg/ha"

```

_Resultado esperado:_ O último commit **não é um novo registro**, mas uma modificação do registro anterior. Ele terá um **novo identificador (hash)**, e a mensagem original será substituída. Use `git log --oneline` para ver que o ID do commit mudou.

**ALERTA IMPORTANTE: `git push --force`**
Lembre-se do aviso sobre `git push --force` em repositórios remotos compartilhados. Em um ambiente de equipe, o `amend` em um commit já enviado pode causar problemas e deve ser evitado ou coordenado.

## Passo 5: Descartando uma Nota Temporária de Campo com `git reset --soft`

Imagine que você adicionou uma nota rápida em `README.md` sobre uma observação de campo que era temporária e não precisa ser parte do histórico permanente do plano.

1. **Adicione uma nota temporária em `README.md` e registre-a:**

   - **Conteúdo para `plano-safra/README.md` (adicione ao final):**
     ```
     # Plano de Safra - [Ano da Safra]

     ... (conteúdo anterior) ...

     **NOTA DE CAMPO: Presença de lagartas em talhão 5. Monitorar!**

     ```
   - _Ação no terminal:_ Edite o arquivo `plano-safra/README.md` no VSCode e adicione a linha.

   ```
   git add README.md
   git commit -m "chore: adiciona nota temporaria de monitoramento de pragas"

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

   - O último commit ("chore: adiciona nota temporaria...") sumiu do `git log`.
   - `git status` mostrará que as alterações (a linha "NOTA DE CAMPO: Presença...") ainda estão no Staging Area (`Changes to be committed`), prontas para serem comitadas novamente, editadas ou descartadas.

   **Para seguir o próximo passo, vamos descartar essa alteração temporária completamente:**

   ```
   git restore README.md
   git reset --hard HEAD # Garante que o diretório de trabalho esteja limpo e alinhado com o ultimo commit

   ```

   _Resultado esperado:_ `README.md` volta ao estado do último commit válido, e o diretório de trabalho está limpo.

## Passo 6: Pesquisa de Nova Variedade de Cultura com `git rebase` (Histórico Linear)

Imagine que a equipe de pesquisa está testando uma nova variedade de cultura em um pequeno talhão. Enquanto eles documentam os resultados, o plano de safra principal (`safra-atual`) recebe uma atualização importante sobre o protocolo de plantio. A equipe de pesquisa quer que seus registros apareçam _depois_ dessa atualização, mantendo um histórico linear.

1. **Garantir que estamos na branch 'safra-atual' e adicionar uma atualização no protocolo de plantio:**

   - **Conteúdo para `plano-safra/02-manejo-solo-plantio/protocolo-plantio.md` (crie o arquivo):**
     ```
     ### Protocolo de Plantio

     - Espaçamento: 45 cm entre linhas.
     - Profundidade: 3 cm.

     ```
   - _Ação no terminal:_ Crie o arquivo `plano-safra/02-manejo-solo-plantio/protocolo-plantio.md` no VSCode e adicione o conteúdo.

   ```
   git switch safra-atual
   git add 02-manejo-solo-plantio/protocolo-plantio.md
   git commit -m "docs: adiciona protocolo inicial de plantio"

   ```

   _Resultado esperado:_ Um novo commit na branch `safra-atual`.

2. **Crie uma nova branch para a pesquisa da nova variedade:**

   ```
   git switch -c pesquisa/nova-variedade-x

   ```

   _Resultado esperado:_ Você está na `pesquisa/nova-variedade-x`.

3. **Crie o arquivo `pesquisa/variedade-x.md` e faça um registro inicial na branch de pesquisa:**

   - **Crie a pasta `pesquisa/` primeiro:**
     ```
     mkdir pesquisa

     ```
   - **Conteúdo para `plano-safra/pesquisa/variedade-x.md`:**
     ```
     ### Pesquisa: Variedade X

     - **Data de Plantio:** 15/11/2024
     - **Observacao Inicial:** Bom vigor de germinacao.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.

   ```
   git add pesquisa/variedade-x.md
   git commit -m "feat: inicia registro de pesquisa para nova variedade X"

   ```

   _Resultado esperado:_ Um commit na sua branch `pesquisa/nova-variedade-x`.

4. **Verifique o histórico para ver a divergência:**

   ```
   git log --oneline --all --graph

   ```

   _Resultado esperado:_ Você verá a branch `safra-atual` e `pesquisa/nova-variedade-x` com commits independentes após um ponto em comum.

5. **Aplique o `rebase` da branch 'pesquisa/nova-variedade-x' sobre a 'safra-atual':**
   Isso "move" os commits da sua branch de pesquisa para que eles apareçam _depois_ do último commit da `safra-atual`.

```
git rebase safra-atual

```

_Resultado esperado:_ O Git reescreve o histórico da sua branch `pesquisa/nova-variedade-x`. Os commits da pesquisa agora virão após o commit do protocolo de plantio.

6. **Verifique o histórico novamente para ver a linearidade:**

   ```
   git log --oneline --all --graph

   ```

   _Resultado esperado:_ O histórico da `pesquisa/nova-variedade-x` agora aparece como se tivesse sido criado _depois_ do último commit da `safra-atual`, resultando em um fluxo linear.

7. **Volte para a `safra-atual` e mescle (será um Fast-Forward):**
   Como a `pesquisa/nova-variedade-x` está "à frente" da `safra-atual` devido ao rebase, o merge será um "fast-forward" (sem criar um merge commit).

```
git switch safra-atual
git merge pesquisa/nova-variedade-x

```

_Resultado esperado:_ A `safra-atual` simplesmente avança para incluir os commits da seção de pesquisa. O histórico continua linear.

8. **Deletar a branch de desenvolvimento:**

   ```
   git branch -d pesquisa/nova-variedade-x

   ```

   _Resultado esperado:_ Branch deletada.

## Passo 7: Adicionando Últimas Seções e Finalizando o Plano

Vamos adicionar as seções restantes para completar a estrutura inicial do plano de safra.

1. **Crie o arquivo `02-manejo-solo-plantio/analise-solo.md` e adicione o conteúdo:**
   - **Conteúdo para `plano-safra/02-manejo-solo-plantio/analise-solo.md`:**
     ```
     ### Análise de Solo

     - Resultados da análise de fertilidade (pH, N, P, K).
     - Recomendação de correção e adubação.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.
2. **Crie o arquivo `04-irrigacao-nutricao/plano-irrigacao.md` e adicione o conteúdo:**
   - **Conteúdo para `plano-safra/04-irrigacao-nutricao/plano-irrigacao.md`:**
     ```
     ### Plano de Irrigação

     - Frequência e volume de água por fase da cultura.
     - Monitoramento da umidade do solo.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.
3. **Crie os arquivos dentro de `05-colheita-pos-colheita/` e adicione o conteúdo:**
   - **Conteúdo para `plano-safra/05-colheita-pos-colheita/protocolo-colheita.md`:**
     ```
     ### Protocolo de Colheita

     - Ponto de maturidade ideal.
     - Regulagem da colheitadeira.

     ```
   - **Conteúdo para `plano-safra/05-colheita-pos-colheita/armazenamento.md`:**
     ```
     ### Armazenamento

     - Limpeza do silo/armazém.
     - Controle de umidade e temperatura.

     ```
   - _Ação no terminal:_ Crie os arquivos no VSCode e adicione o conteúdo.
4. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 02-manejo-solo-plantio/analise-solo.md 04-irrigacao-nutricao/plano-irrigacao.md 05-colheita-pos-colheita/

   ```

   _Resultado esperado:_ Os arquivos estão prontos para serem comitados.

5. **Registre as últimas seções:**

   ```
   git commit -m "feat: completa estrutura do plano de safra com manejo de solo, irrigacao e colheita"

   ```

   _Resultado esperado:_ O plano de safra está com sua estrutura inicial completa e registrada no Git.

## Conclusão: O Git na Gestão Inteligente da Safra

Você acaba de simular a criação e o versionamento de um plano de safra agrícola utilizando o Git em uma estrutura de pastas organizada. Esta abordagem permite que a gestão da sua safra seja:

- **Transparente:** Cada decisão e ajuste no plano é registrado.
- **Colaborativa:** Agrônomos, técnicos e gerentes podem trabalhar juntos nas diferentes seções do plano.
- **Rastreável:** É possível voltar no tempo para ver qual era o protocolo de adubação em uma safra anterior ou como um plano foi ajustado devido a condições climáticas.
- **Base de Conhecimento:** O plano se torna um documento vivo, que evolui com a experiência de cada safra.

**Próximos Passos para aprimorar sua prática:**

- **Explore o `git log`:** Use `git log --all --graph --decorate --oneline` para visualizar o histórico completo e entender como as branches e merges/rebases afetaram o fluxo do seu plano de safra.
- **Crie um repositório no GitHub:** Leve este plano de safra para o GitHub e pratique os comandos de interação com um repositório remoto (`git push`, `git pull`).
- **Simule um conflito de merge:** Tente fazer alterações conflitantes na mesma linha de um arquivo em duas branches diferentes e veja como o Git lida com isso.
