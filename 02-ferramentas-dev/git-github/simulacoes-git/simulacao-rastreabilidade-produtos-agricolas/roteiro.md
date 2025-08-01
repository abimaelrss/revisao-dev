# 🔍 Simulação Git Aplicada: Sistema de Rastreabilidade de Produtos Agrícolas

Este guia detalha uma simulação de como o Git pode ser utilizado para criar e gerenciar um sistema de rastreabilidade para produtos agrícolas. O objetivo é documentar de forma transparente e versionada todo o ciclo de vida de um lote de produto, desde sua origem no campo até a distribuição.

Siga cada instrução no seu terminal e crie os arquivos e pastas no seu VSCode (ou editor de texto preferido) conforme o conteúdo fornecido.

## Preparação do Ambiente: Criando o Dossiê de Rastreabilidade

Vamos começar criando a pasta principal do projeto de rastreabilidade e inicializando o repositório Git.

1. **Crie a pasta raiz do projeto e navegue até ela:**

   ```
   mkdir rastreabilidade-lote-001
   cd rastreabilidade-lote-001

   ```

   _Resultado esperado:_ Você terá uma nova pasta `rastreabilidade-lote-001`.

2. **Inicialize o repositório Git:**

   ```
   git init

   ```

   _Resultado esperado:_ O Git cria a pasta `.git` oculta, transformando `rastreabilidade-lote-001` em um repositório Git.

3. **Configure seu nome e e-mail para os registros de rastreabilidade:** (Substitua pelos seus dados)

   ```
   git config user.name "Responsável pela Qualidade"
   git config user.email "qualidade@fazenda.com"

   ```

   _Resultado esperado:_ Suas informações serão associadas a cada registro de rastreabilidade.

4. **Defina a branch principal como 'lote-001':**
   Esta branch representará o histórico de rastreabilidade do lote específico.

```
git config init.defaultBranch lote-001

```

_Resultado esperado:_ A branch principal do seu dossiê será chamada `lote-001`.

## Passo 1: Origem e Produção no Campo

Vamos documentar as informações iniciais do produto, desde sua origem no campo.

1. **Crie o arquivo `README.md` na raiz do projeto (`rastreabilidade-lote-001/README.md`):**
   - **Conteúdo para `rastreabilidade-lote-001/README.md`:**
     ```
     # Dossiê de Rastreabilidade - Lote 001 (Tomates Orgânicos)

     Este repositório documenta a rastreabilidade completa do Lote 001 de tomates orgânicos.

     ## Estrutura do Dossiê:

     - `01-origem-producao/`: Informações do campo.
     - `02-processamento-embalagem/`: Detalhes do beneficiamento.
     - `03-transporte-distribuicao/`: Logística e entrega.
     - `04-controles-qualidade/`: Registros de inspeção e certificação.
     - `incidentes-observacoes/`: Ocorrências e feedbacks.

     ```
   - _Ação no terminal:_ Crie o arquivo e cole o conteúdo no VSCode.
2. **Crie as pastas conforme a estrutura sugerida:**

   ```
   mkdir 01-origem-producao
   mkdir 02-processamento-embalagem
   mkdir 03-transporte-distribuicao
   mkdir 04-controles-qualidade
   mkdir incidentes-observacoes

   ```

   _Resultado esperado:_ As subpastas serão criadas dentro de `rastreabilidade-lote-001/`.

3. **Crie os arquivos dentro de `01-origem-producao/` e adicione o conteúdo:**
   - **Conteúdo para `rastreabilidade-lote-001/01-origem-producao/talhao-origem.md`:**
     ```
     ### Talhão de Origem

     - **Identificação:** Talhão A3
     - **Coordenadas GPS:** -XX.XXXX, -YY.YYYY
     - **Cultura Anterior:** Milho (safra 2023/2024)

     ```
   - **Conteúdo para `rastreabilidade-lote-001/01-origem-producao/data-plantio-colheita.md`:**
     ```
     ### Datas de Plantio e Colheita

     - **Plantio:** 01/09/2024
     - **Colheita:** 20/11/2024

     ```
   - **Conteúdo para `rastreabilidade-lote-001/01-origem-producao/insumos-utilizados.md`:**
     ```
     ### Insumos Utilizados (Campo)

     - **Semente:** Tomate Variedade Z (Lote S-123)
     - **Fertilizante:** Composto Orgânico (Aplicação: 15/09/2024)
     - **Controle Biológico:** Agente W (Aplicação: 05/10/2024)

     ```
   - _Ação no terminal:_ Crie os arquivos e cole o conteúdo no VSCode.
4. **Verifique o status do seu dossiê:**

   ```
   git status

   ```

   _Resultado esperado:_ O Git mostrará todos os arquivos e pastas recém-criados como não rastreados.

5. **Adicione todos os arquivos ao "Staging Area":**

   ```
   git add .

   ```

   _Resultado esperado:_ Todos os arquivos estão agora prontos para serem comitados.

6. **Registre as informações de origem e produção:**

   ```
   git commit -m "feat: registra informacoes de origem e producao do Lote 001"

   ```

   _Resultado esperado:_ O primeiro "registro" do seu dossiê de rastreabilidade é feito no histórico do Git. Use `git log --oneline` para ver.

## Passo 2: Documentando Processamento e Embalagem (Branching e Merge)

O lote de tomates foi colhido e agora será processado e embalado. O responsável pela embalagem vai documentar esses passos.

1. **Crie e troque para a branch 'desenvolvimento/processamento':**

   ```
   git switch -c desenvolvimento/processamento

   ```

   _Resultado esperado:_ Você agora está na branch `desenvolvimento/processamento`. Use `git branch` para confirmar.

2. **Crie os arquivos dentro de `02-processamento-embalagem/` e adicione o conteúdo:**
   - **Conteúdo para `rastreabilidade-lote-001/02-processamento-embalagem/data-processamento.md`:**
     ```
     ### Data de Processamento

     - **Início:** 21/11/2024
     - **Término:** 21/11/2024

     ```
   - **Conteúdo para `rastreabilidade-lote-001/02-processamento-embalagem/lote-embalagem.md`:**
     ```
     ### Lote de Embalagem

     - **Identificação do Lote:** EMB-456
     - **Tipo de Embalagem:** Bandeja biodegradável (1kg)
     - **Quantidade:** 500 unidades

     ```
   - **Conteúdo para `rastreabilidade-lote-001/02-processamento-embalagem/condicoes-armazenamento.md`:**
     ```
     ### Condições de Armazenamento (Pós-Processamento)

     - **Local:** Câmara Fria 1
     - **Temperatura:** 12°C
     - **Umidade:** 85%

     ```
   - _Ação no terminal:_ Crie os arquivos e cole o conteúdo no VSCode.
3. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 02-processamento-embalagem/

   ```

   _Resultado esperado:_ Os arquivos de processamento estão prontos para serem comitados.

4. **Registre a nova seção no histórico da branch:**

   ```
   git commit -m "feat: documenta etapas de processamento e embalagem do lote"

   ```

   _Resultado esperado:_ Um novo registro (commit) é adicionado apenas na branch `desenvolvimento/processamento`.

## Passo 3: Integrando as Informações de Processamento (Merge)

As informações de processamento foram verificadas e agora precisam ser incorporadas ao dossiê principal do lote.

1. **Volte para a branch 'lote-001' (a versão principal do dossiê):**

   ```
   git switch lote-001

   ```

   _Resultado esperado:_ Você está de volta à `lote-001`. Os arquivos de `02-processamento-embalagem/` não aparecem aqui ainda.

2. **Mescle a branch 'desenvolvimento/processamento' na 'lote-001':**

   ```
   git merge desenvolvimento/processamento

   ```

   _Resultado esperado:_ As alterações da branch `desenvolvimento/processamento` (incluindo a pasta e seus arquivos) são integradas à `lote-001`. Um "Merge commit" será criado automaticamente.

3. **Deletar a branch de desenvolvimento após a integração (opcional):**

   ```
   git branch -d desenvolvimento/processamento

   ```

   _Resultado esperado:_ A branch `desenvolvimento/processamento` é removida localmente.

## Passo 4: Corrigindo um Registro de Insumo com `amend`

O responsável pelo campo percebeu que um insumo biológico foi registrado com a data errada na seção de origem, logo após o último registro. Ele quer corrigir e ajustar a mensagem do registro.

1. **Faça uma correção no arquivo `01-origem-producao/insumos-utilizados.md`:**
   Simule que você abriu `insumos-utilizados.md` e corrigiu a data de aplicação do Agente W:

```
### Insumos Utilizados (Campo)

- **Semente:** Tomate Variedade Z (Lote S-123)
- **Fertilizante:** Composto Orgânico (Aplicação: 15/09/2024)
- **Controle Biológico:** Agente W (Aplicação: **08/10/2024**)

```

_Ação no terminal:_ Edite o arquivo `rastreabilidade-lote-001/01-origem-producao/insumos-utilizados.md` no VSCode e altere a data.

2. **Adicione a correção ao Staging Area:**

   ```
   git add 01-origem-producao/insumos-utilizados.md

   ```

   _Resultado esperado:_ A alteração está pronta para ser comitada.

3. **Altere o _último_ registro (commit) usando `amend`:**
   Isso reescreve o último commit, incluindo a nova alteração e a nova mensagem.

```
git commit --amend -m "fix: corrige data de aplicacao do Agente W para 08/10/2024"

```

_Resultado esperado:_ O último commit **não é um novo registro**, mas uma modificação do registro anterior. Ele terá um **novo identificador (hash)**, e a mensagem original será substituída. Use `git log --oneline` para ver que o ID do commit mudou.

**ALERTA IMPORTANTE: `git push --force`**
Lembre-se do aviso sobre `git push --force` em repositórios remotos compartilhados. Em um ambiente de equipe, o `amend` em um commit já enviado pode causar problemas e deve ser evitado ou coordenado.

## Passo 5: Descartando uma Observação de Campo Não Confirmada com `git reset --soft`

Imagine que um técnico de campo registrou uma observação preliminar sobre uma possível praga, mas depois de uma inspeção mais detalhada, a observação não foi confirmada. Você quer remover esse registro do histórico, mas manter a anotação para referência futura.

1. **Crie o arquivo `incidentes-observacoes/ocorrencias-campo.md` e adicione uma nota temporária e registre-a:**

   - **Conteúdo para `rastreabilidade-lote-001/incidentes-observacoes/ocorrencias-campo.md`:**
     ```
     ### Ocorrências no Campo

     - **25/10/2024:** Suspeita de ataque de mosca branca (não confirmado).

     ```
   - _Ação no terminal:_ Crie o arquivo `rastreabilidade-lote-001/incidentes-observacoes/ocorrencias-campo.md` no VSCode e adicione o conteúdo.

   ```
   git add incidentes-observacoes/ocorrencias-campo.md
   git commit -m "chore: adiciona observacao preliminar de mosca branca"

   ```

   _Resultado esperado:_ Um novo commit aparece no `git log`.

2. **Verifique o status do dossiê:**

   ```
   git status

   ```

   _Resultado esperado:_ O repositório está limpo.

3. **Desfaça o último registro, mantendo as alterações no "Staging Area":**

   ```
   git reset --soft HEAD~1

   ```

   _Resultado esperado:_

   - O último commit ("chore: adiciona observacao preliminar...") sumiu do `git log`.
   - `git status` mostrará que as alterações (a linha "Suspeita de ataque...") ainda estão no Staging Area (`Changes to be committed`), prontas para serem comitadas novamente (com uma nova mensagem, por exemplo, "Observação de mosca branca - não confirmada, mantida para histórico") ou descartadas.

   **Para seguir o próximo passo, vamos descartar essa alteração temporária completamente:**

   ```
   git restore incidentes-observacoes/ocorrencias-campo.md
   git reset --hard HEAD # Garante que o diretório de trabalho esteja limpo e alinhado com o ultimo commit

   ```

   _Resultado esperado:_ `ocorrencias-campo.md` volta ao estado do último commit válido, e o diretório de trabalho está limpo.

## Passo 6: Atualizando Controles de Qualidade com `git rebase` (Histórico Linear)

Imagine que a equipe de qualidade está preparando a documentação para a certificação orgânica. Enquanto eles trabalham, uma nova inspeção final do lote é realizada e registrada na branch `lote-001`. A equipe de qualidade quer que seus registros de certificação apareçam _depois_ dessa inspeção final, mantendo um histórico linear.

1. **Garantir que estamos na branch 'lote-001' e adicionar um registro de inspeção final:**

   - **Conteúdo para `rastreabilidade-lote-001/04-controles-qualidade/inspecao-final-lote.md` (crie o arquivo):**
     ```
     ### Inspeção Final do Lote

     - **Data:** 22/11/2024
     - **Resultado:** Lote aprovado para distribuição.

     ```
   - _Ação no terminal:_ Crie o arquivo `rastreabilidade-lote-001/04-controles-qualidade/inspecao-final-lote.md` no VSCode e adicione o conteúdo.

   ```
   git switch lote-001
   git add 04-controles-qualidade/inspecao-final-lote.md
   git commit -m "docs: registra inspecao final do lote 001"

   ```

   _Resultado esperado:_ Um novo commit na branch `lote-001`.

2. **Crie uma nova branch para a documentação de certificações:**

   ```
   git switch -c desenvolvimento/certificacoes

   ```

   _Resultado esperado:_ Você está na `desenvolvimento/certificacoes`.

3. **Crie o arquivo `04-controles-qualidade/certificacoes-organicas.md` e faça um registro inicial na branch de certificações:**

   - **Conteúdo para `rastreabilidade-lote-001/04-controles-qualidade/certificacoes-organicas.md`:**
     ```
     ### Certificações Orgânicas

     - Certificado Orgânico Brasil (válido até 2025).
     - Auditoria interna realizada em 10/11/2024.

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.

   ```
   git add 04-controles-qualidade/certificacoes-organicas.md
   git commit -m "feat: inicia documentacao de certificacoes organicas"

   ```

   _Resultado esperado:_ Um commit na sua branch `desenvolvimento/certificacoes`.

4. **Verifique o histórico para ver a divergência:**

   ```
   git log --oneline --all --graph

   ```

   _Resultado esperado:_ Você verá a branch `lote-001` e `desenvolvimento/certificacoes` com commits independentes após um ponto em comum.

5. **Aplique o `rebase` da branch 'desenvolvimento/certificacoes' sobre a 'lote-001':**
   Isso "move" os commits da sua branch de certificações para que eles apareçam _depois_ do último commit da `lote-001`.

```
git rebase lote-001

```

_Resultado esperado:_ O Git reescreve o histórico da sua branch `desenvolvimento/certificacoes`. Os commits da certificação agora virão após o commit da inspeção final.

6. **Verifique o histórico novamente para ver a linearidade:**

   ```
   git log --oneline --all --graph

   ```

   _Resultado esperado:_ O histórico da `desenvolvimento/certificacoes` agora aparece como se tivesse sido criado _depois_ do último commit da `lote-001`, resultando em um fluxo linear.

7. **Volte para a `lote-001` e mescle (será um Fast-Forward):**
   Como a `desenvolvimento/certificacoes` está "à frente" da `lote-001` devido ao rebase, o merge será um "fast-forward" (sem criar um merge commit).

```
git switch lote-001
git merge desenvolvimento/certificacoes

```

_Resultado esperado:_ A `lote-001` simplesmente avança para incluir os commits da seção de certificações. O histórico continua linear.

8. **Deletar a branch de desenvolvimento:**

   ```
   git branch -d desenvolvimento/certificacoes

   ```

   _Resultado esperado:_ Branch deletada.

## Passo 7: Adicionando Últimas Seções e Finalizando o Dossiê

Vamos adicionar as seções restantes para completar a estrutura inicial do dossiê de rastreabilidade.

1. **Crie os arquivos dentro de `03-transporte-distribuicao/` e adicione o conteúdo:**
   - **Conteúdo para `rastreabilidade-lote-001/03-transporte-distribuicao/data-envio.md`:**
     ```
     ### Data de Envio

     - **Saída da Fazenda:** 22/11/2024

     ```
   - **Conteúdo para `rastreabilidade-lote-001/03-transporte-distribuicao/veiculo-responsavel.md`:**
     ```
     ### Veículo Responsável

     - **Placa:** ABC-1234
     - **Motorista:** João Silva

     ```
   - **Conteúdo para `rastreabilidade-lote-001/03-transporte-distribuicao/destino-final.md`:**
     ```
     ### Destino Final

     - **Cliente:** Supermercado X
     - **Endereço:** Rua das Flores, 123

     ```
   - _Ação no terminal:_ Crie os arquivos no VSCode e adicione o conteúdo.
2. **Crie o arquivo `incidentes-observacoes/feedback-consumidor.md` e adicione o conteúdo:**
   - **Conteúdo para `rastreabilidade-lote-001/incidentes-observacoes/feedback-consumidor.md`:**
     ```
     ### Feedback do Consumidor

     - **Data:** (Aguardando)
     - **Observações:** (Aguardando)

     ```
   - _Ação no terminal:_ Crie o arquivo no VSCode e adicione o conteúdo.
3. **Adicione os novos arquivos ao Staging Area:**

   ```
   git add 03-transporte-distribuicao/ incidentes-observacoes/feedback-consumidor.md

   ```

   _Resultado esperado:_ Os arquivos estão prontos para serem comitados.

4. **Registre as últimas seções:**

   ```
   git commit -m "feat: completa dossie com secoes de transporte e feedback do consumidor"

   ```

   _Resultado esperado:_ O dossiê de rastreabilidade está com sua estrutura inicial completa e registrada no Git.

## Conclusão: Git na Rastreabilidade Agrícola

Você acaba de simular a criação e o versionamento de um sistema de rastreabilidade para produtos agrícolas utilizando o Git em uma estrutura de pastas organizada. Esta abordagem permite que a gestão da rastreabilidade seja:

- **Transparente e Detalhada:** Cada etapa do produto é registrada com precisão.
- **Auditável:** O histórico do Git permite verificar quem, quando e o que foi alterado em cada registro.
- **Confiável:** Garante a integridade das informações de ponta a ponta.
- **Base para Certificações:** Facilita a comprovação de processos para certificações (orgânicas, de qualidade, etc.).

**Próximos Passos para aprimorar sua prática:**

- **Explore o `git log`:** Use `git log --all --graph --decorate --oneline` para visualizar o histórico completo e entender como as branches e merges/rebases afetaram o fluxo do seu dossiê de rastreabilidade.
- **Crie um repositório no GitHub:** Leve este dossiê para o GitHub e pratique os comandos de interação com um repositório remoto (`git push`, `git pull`).
- **Simule um conflito de merge:** Tente fazer alterações conflitantes na mesma linha de um arquivo em duas branches diferentes e veja como o Git lida com isso.
