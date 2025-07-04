# 🚀 Simulação Git Imersiva: Aprendendo na Prática

Este guia detalhado simula um projeto real para que você possa praticar e entender o fluxo de trabalho do Git, utilizando comandos essenciais como `branch`, `merge`, `rebase`, `amend` e `reset`.

Siga cada passo no seu terminal, e observe as mudanças no seu repositório.

## Preparação do Ambiente

Crie uma pasta para este projeto e navegue até ela no seu terminal.

```
mkdir projeto-git-imersivo
cd projeto-git-imersivo

```

## Passo 1: Início do Projeto e Primeiro Commit

Vamos inicializar o repositório Git e criar os arquivos básicos.

1.  **Inicializar o repositório:**

    ```bash
    git init

    ```

    _Resultado esperado:_ O Git cria uma pasta `.git` oculta, transformando seu diretório em um repositório.

2.  **Configurar seu nome e e-mail:** (Substitua pelos seus dados)

    ```bash
    git config user.name "Seu Nome"
    git config user.email "seu.email@example.com"

    ```

    _Resultado esperado:_ Suas informações serão associadas aos commits que você fizer.

3.  **Definir a branch padrão como 'main':**

    ```bash
    git config init.defaultBranch main

    ```

    _Resultado esperado:_ Novas inicializações de repositório usarão `main` como branch principal.

4.  **Criar o arquivo `README.md`:**
    Crie o arquivo e adicione o conteúdo.

    ```
    echo "# Projeto de Simulação Git" > README.md
    echo "Este é um projeto para praticar comandos Git." >> README.md

    ```

    _Resultado esperado:_ Um arquivo `README.md` é criado na sua pasta.

5.  **Criar o arquivo `index.txt`:**

    ```
    echo "Conteúdo inicial do site." > index.txt

    ```

    _Resultado esperado:_ Um arquivo `index.txt` é criado.

6.  **Verificar o status dos arquivos:**

    ```
    git status

    ```

    _Resultado esperado:_ O Git mostrará `README.md` e `index.txt` como arquivos não rastreados (`Untracked files`).

7.  **Adicionar todos os arquivos ao Staging Area:**

    ```
    git add .

    ```

    _Resultado esperado:_ O Git moverá `README.md` e `index.txt` para o Staging Area (`Changes to be committed`). Verifique com `git status` novamente.

8.  **Fazer o primeiro commit:**

    ```
    git commit -m "feat: configura estrutura inicial do projeto"

    ```

    _Resultado esperado:_ Um novo commit é criado no histórico. Use `git log --oneline` para ver.

## Passo 2: Desenvolvendo uma Nova Funcionalidade (Branching)

Vamos adicionar uma nova funcionalidade em uma branch separada para não interferir na `main`.

1. **Criar e trocar para uma nova branch:**

   ```
   git switch -c feature/contato

   ```

   _Resultado esperado:_ Você agora estará na branch `feature/contato`. Use `git branch` para confirmar.

2. **Criar o arquivo `contato.txt` para a nova funcionalidade:**

   ```
   echo "Página de contato: entre em contato conosco." > contato.txt

   ```

   _Resultado esperado:_ Um novo arquivo `contato.txt` é criado.

3. **Adicionar o novo arquivo ao Staging Area:**

   ```
   git add contato.txt

   ```

   _Resultado esperado:_ O `contato.txt` está pronto para ser comitado.

4. **Fazer o commit da nova funcionalidade:**

   ```
   git commit -m "feat: implementa pagina de contato"

   ```

   _Resultado esperado:_ Um commit é adicionado apenas na branch `feature/contato`.

## Passo 3: Mesclando a Nova Funcionalidade (Merge)

Agora que a funcionalidade está pronta, vamos integrá-la à branch principal (`main`).

1. **Voltar para a branch `main`:**

   ```
   git switch main

   ```

   _Resultado esperado:_ Você está de volta à `main`. Observe que `contato.txt` desaparece temporariamente, pois ele não existia na `main` ainda.

2. **Mesclar a branch `feature/contato` na `main`:**

   ```
   git merge feature/contato

   ```

   _Resultado esperado:_ As alterações da `feature/contato` (incluindo `contato.txt`) são integradas à `main`. Um "Merge commit" será criado automaticamente, a menos que seja um "Fast-Forward merge".

3. **Deletar a branch de funcionalidade (opcional, após o merge):**

   ```
   git branch -d feature/contato

   ```

   _Resultado esperado:_ A branch `feature/contato` é removida localmente. Verifique com `git branch`.

## Passo 4: Corrigindo um Commit com `amend` (Cuidado com Force Push)

Imagine que você comitou uma pequena alteração e percebeu que a mensagem do commit ou o conteúdo precisava de um ajuste _imediato_, antes de enviar para um repositório remoto.

1.  **Fazer uma pequena alteração em `index.txt`:**

    ```
    echo "Conteúdo inicial do site. (Atualizado para 2024)" > index.txt

    ```

    _Resultado esperado:_ O `index.txt` é modificado.

2.  **Comitar a alteração (com uma mensagem que você quer mudar depois):**

    ```
    git add index.txt
    git commit -m "chore: atualiza ano"

    ```

    _Resultado esperado:_ Um novo commit é adicionado. Verifique com `git log --oneline`.

3.  **Alterar o último commit usando `amend`:**
    Vamos corrigir a mensagem do commit e adicionar mais uma pequena alteração (simulando que você esqueceu algo). - **Faça outra pequena mudança no `index.txt`:**

    ```
    echo "Conteúdo inicial do site. (Atualizado para 2024) - Versao 1.0" > index.txt

    ```

    - **Adicione a nova mudança ao staging:**

      ```
      git add index.txt

      ```

    - **Execute o `amend` com a nova mensagem:**

      ```
      git commit --amend -m "refactor: atualiza texto do index e adiciona versao"

      ```

    _Resultado esperado:_ O último commit **não será um novo commit**, mas sim uma modificação do commit anterior. Ele terá um **novo ID (hash)**, e a mensagem original será substituída. Use `git log --oneline` para ver que o ID do commit mudou.

    **IMPORTANTE: Alerta sobre `git push --force`**
    Se você já tivesse enviado o commit original para um repositório remoto (como o GitHub) e depois usasse `git commit --amend`, o histórico local e remoto ficariam diferentes. Para "forçar" a atualização do histórico remoto, você precisaria usar `git push --force origin main`.

    **CUIDADO:** `git push --force` **reescreve o histórico do repositório remoto.** Nunca use em branches compartilhadas sem extrema necessidade e coordenação com sua equipe, pois pode apagar o trabalho de outras pessoas!

## Passo 5: Desfazendo um Commit com `git reset --soft`

Imagine que você fez um commit, mas depois decidiu que ele não deveria ter sido um commit separado. Você quer desfazer o commit, mas manter as alterações prontas para comitar de novo (ou editar).

1. **Fazer uma nova alteração e comitar:**

   ```
   echo "Adicionando uma linha de teste para reset." >> index.txt
   git add index.txt
   git commit -m "test: adiciona linha de teste para demonstrar reset"

   ```

   _Resultado esperado:_ Um novo commit aparece no `git log`.

2. **Verificar o status atual:**

   ```
   git status

   ```

   _Resultado esperado:_ O repositório está limpo (sem alterações pendentes).

3. **Executar `git reset --soft HEAD~1`:**`HEAD~1` significa "um commit antes do HEAD" (o commit atual). `-soft` significa que o Git desfaz o commit, mas mantém as alterações no Staging Area.

   ```
   git reset --soft HEAD~1

   ```

   _Resultado esperado:_

   - O último commit sumiu do `git log`.
   - `git status` mostrará que as alterações (a linha que você adicionou) estão no Staging Area (`Changes to be committed`), prontas para serem comitadas novamente ou modificadas.
   - Você pode agora fazer `git commit -m "Nova mensagem para o commit"` ou `git restore --staged index.txt` para tirar do staging.

   **Para seguir o próximo passo, vamos desfazer essas alterações do reset (descartá-las completamente):**

   ```
   git restore index.txt
   git reset --hard HEAD # Desfaz qualquer coisa pendente e retorna ao último commit

   ```

   _Resultado esperado:_ `index.txt` volta ao estado do último commit válido.

## Passo 6: Histórico Linear com `git rebase`

O `rebase` é uma alternativa ao `merge` para integrar alterações, criando um histórico mais linear (sem commits de merge).

1.  **Garantir que estamos na `main` e fazer um novo commit nela:**
    Isso simula que a `main` avançou enquanto você trabalhava em uma feature branch.

    ```
    git switch main
    echo "Adicionando feature importante na main." >> main-feature.txt
    git add main-feature.txt
    git commit -m "feat: adiciona funcionalidade critica na main"

    ```

    _Resultado esperado:_ Um novo commit na `main`.

2.  **Criar uma nova feature branch:**

    ```
    git switch -c feature/nova-funcionalidade

    ```

    _Resultado esperado:_ Você está na `feature/nova-funcionalidade`.

3.  **Fazer um commit na `feature/nova-funcionalidade`:**

    ```
    echo "Conteúdo da nova funcionalidade." > nova-func.txt
    git add nova-func.txt
    git commit -m "feat: implementa nova funcionalidade"

    ```

    _Resultado esperado:_ Um commit na sua feature branch.

4.  **Ver o histórico antes do rebase:**

    ```
    git log --oneline --all --graph

    ```

    _Resultado esperado:_ Você verá a `main` e `feature/nova-funcionalidade` divergindo, com a feature branch começando a partir de um commit anterior da `main`.

5.  **Aplicar o `rebase` da `feature/nova-funcionalidade` sobre a `main`:**

    ```
    git rebase main

    ```

    _Resultado esperado:_ O Git "pega" os commits da sua `feature/nova-funcionalidade` e os "replica" _após_ os commits mais recentes da `main`. Isso reescreve o histórico da sua feature branch.

6.  **Ver o histórico depois do rebase:**

    ```
    git log --oneline --all --graph

    ```

    _Resultado esperado:_ O histórico da `feature/nova-funcionalidade` agora aparece como se tivesse sido criado _depois_ do último commit da `main`, resultando em um fluxo linear.

7.  **Voltar para a `main` e mesclar (agora será Fast-Forward):**
    Como a `feature/nova-funcionalidade` está "à frente" da `main` devido ao rebase, o merge será um "fast-forward" (sem criar um merge commit).

    ```
    git switch main
    git merge feature/nova-funcionalidade

    ```

    _Resultado esperado:_ A `main` simplesmente avança para o último commit da `feature/nova-funcionalidade`. O histórico continua linear.

8.  **Deletar a branch:**

    ```
    git branch -d feature/nova-funcionalidade

    ```

    _Resultado esperado:_ Branch deletada.

## Passo 7: Simulando Colaboração (Fetch e Pull) - Conceitual

Para simular `pull` e `fetch` de forma completa, você precisaria de um repositório remoto (como no GitHub). No entanto, podemos entender o conceito:

- **`git fetch`**: Este comando baixa as informações mais recentes do repositório remoto (como novas branches ou commits que outros desenvolvedores fizeram), mas **não integra** essas alterações em suas branches locais. É como "dar uma olhada" no que mudou no remoto sem afetar seu trabalho atual.

  ```
  # Exemplo (se você tivesse um remoto configurado):
  # git remote add origin <URL_DO_SEU_REPOSITORIO_REMOTO>
  # git fetch origin

  ```

  _Resultado esperado:_ O Git atualiza suas referências de branches remotas (`origin/main`, `origin/feature-x`), mas seus arquivos locais e sua branch atual permanecem inalterados.

- **`git pull`**: Este comando é um atalho que executa `git fetch` e, em seguida, um `git merge` (ou `git rebase`, dependendo da sua configuração) para integrar as alterações baixadas na sua branch local atual. É a forma mais comum de "sincronizar" seu repositório local com o remoto.

  ```
  # Exemplo:
  # git pull origin main

  ```

  _Resultado esperado:_ Suas branches locais são atualizadas com as alterações do remoto, e os arquivos em seu diretório de trabalho refletirão essas mudanças.

## Conclusão e Próximos Passos

Você concluiu uma simulação abrangente dos principais comandos Git em um cenário prático. A prática contínua é a chave para a maestria.

**Recomendações:**

- **Repita esta simulação** algumas vezes para fixar os comandos e entender o impacto de cada um no histórico.
- **Tente criar seus próprios cenários:** Desafie-se a simular um conflito de merge e resolvê-lo.
- **Comece a usar o GitHub (ou outra plataforma Git):** Conecte seu repositório local a um remoto e pratique `push` e `pull` em um ambiente real.

Se tiver mais alguma dúvida ou quiser explorar outros cenários, é só avisar, cumpanheiro!
