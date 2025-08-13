# 💡 O que é o Git?

Git é um sistema de controle de versão distribuído, criado por Linus Torvalds, que permite acompanhar o histórico de alterações em arquivos de um projeto.

Com ele, é possível registrar cada modificação feita no código, voltar a versões anteriores, trabalhar em equipe com segurança e sincronizar com plataformas como o GitHub.

> Em resumo: o Git ajuda a organizar, versionar e compartilhar projetos de forma eficiente e confiável.
> 

## 🎮 Comandos básicos de Git

Este arquivo contém um resumo dos principais comandos básicos de Git.

---

### 📌 Comandos de configuração

| Comando | Finalidade |
| --- | --- |
| `git config --global user.name "Seu Nome"` | Configura o nome de usuário para os commits |
| `git config --global user.email "email@email.com"` | Configura o email de commit |
| `git config --global init.defaultBranch main` | Define a branch padrão como "main" (em vez de "master") |
| `--global` | A opção `--global` configura usuário e email padrão para todos os projetos. Para sobrepor usuário e email em projetos específicos, executar os comandos sem a opção `--global` |

---

### 📁 Comandos para repositório local

| Comando | Finalidade |
| --- | --- |
| `git init` | Inicia um novo repositório Git no diretório atual |
| `git add .` | Adiciona todos os arquivos modificados e novos arquivos ao staging |
| `git add <arquivo>` | Adiciona um arquivo específico ao staging |
| `git status` | Verifica o estado atual do repositório (arquivos modificados, staged, etc.) |
| `git diff` | Mostra as linhas que foram adicionadas e removidas |
| `git commit -m "mensagem"` | Cria um novo commit com a mensagem informada |
| `git commit --amend -m "nova mensagem"` | Altera a mensagem do último commit (antes de enviar para o remoto). Se já enviou para um remoto e outras pessoas já puxaram, usar `--amend` e forçar `push` pode causar problemas para o time |
| `git reset` | Move o ponteiro do HEAD para um commit anterior, podendo também modificar a staging area e o diretório de trabalho, conforme a opção usada (--soft, --mixed, --hard) |
| `git reset --soft HEAD~1`	| Volta um commit, mantendo todas as alterações na staging area (index). Ideal para refazer o último commit |
| `git reset --soft <id-do-commit>`	| Move o HEAD para o commit especificado, mantendo as alterações dos commits seguintes na staging area |
| `git reset --hard HEAD~1` | Volta um commit e descarta completamente as alterações da staging area e do diretório de trabalho. Irreversível |
| `git reset --hard <id-do-commit>`	| Move o HEAD para o commit especificado e apaga todas as alterações posteriores, inclusive do diretório de trabalho. Cuidado: essa operação é destrutiva |
| `git rm -f <arquivo>` | Remove um arquivo do staging e do diretório |
| `git rm --cached <arquivo>` | Remove um arquivo do staging sem apagar localmente |
| `git restore <arquivo>` | Desfaz modificações locais em um arquivo |
| `git restore --staged <arquivo>` | Retira um arquivo do staging area, mas sem remover o arquivo |
| `git log` | Mostra o histórico de commits |
| `git checkout <id-do-commit>` | Volta temporariamente para um commit anterior (modo detached HEAD) |
| `git checkout -b <nova-branch>` | Cria e troca para uma nova branch |
| `git switch <nome-da-branch>` | (Alternativa moderna) Troca para outra branch |
| **`.gitignore`** | Arquivo de texto que lista os nomes de arquivos e diretórios que o Git deve ignorar e não rastrear (ex: `node_modules/`, `build/`, `.env` com senhas, arquivos de sistema operacional, arquivos temporários). |
| **`.gitkeep`** | Arquivo vazio usado como convenção para forçar o Git a versionar diretórios vazios (já que ele os ignora por padrão). |

---

### 🌐 Comandos para repositório remoto

| Comando | Finalidade |
| --- | --- |
| `git remote -v` | Lista os repositórios remotos configurados |
| `git remote add origin <url>` | Conecta o repositório local a um repositório remoto |
| `git push origin main` | Envia os commits locais para a branch "main" no GitHub |
| `git push origin main --force` | Força o envio do commit (útil após `--amend`). Cuidado no uso desse comando em branches compartilhadas. É uma operação perigosa que reescreve o histórico e pode bagunçar o trabalho de outras pessoas. É uma boa prática evitar o uso do `push --force` **em branches que não sejam exclusivas** ou sem coordenação do time. |
| `git pull origin main` | Baixa alterações do repositório remoto e mescla com o local |
| `git fetch` | Baixa as alterações do repositório remoto, mas não as integra na branch local. Ele apenas atualiza as referências remotas |
| `git clone <url>` | Cria uma cópia local de um repositório remoto existente |

---

### 🔀 Comandos para gerenciameno de Branches (Ramificações)

| Comando | Finalidade |
| --- | --- |
| `git branch` | Lista as branches locais |
| `git branch <nome-da-branch>` | Cria uma nova branch  |
| `git switch <nome-da-branch>` | (Recomendado!) Troca para uma branch existente. É mais seguro e claro que `git checkout` para esa finalidade |
| `git switch -c <nome-da-branch>` | Cria e troca para uma nova branch |
| `git branch -d <nome-da-branch>` | Deleta uma branch local (se ela já foi merged) |
| **`git merge <nome-da-branch>`** | Combina as alterações de uma branch (preserva o histórico) |
| **`git rebase <nome-da-branch>`** | Move/aplica os commits de uma branch em cima de outra, criando um histórico mais linear (altera o histórico) |

---

## ☑️ Boas práticas de commits

### O que são Commits Semânticos?

Commits semânticos (ou *Conventional Commits*) são uma forma padronizada de escrever mensagens de commit. Eles seguem uma estrutura simples que inclui um **tipo** e uma **descrição**, e opcionalmente um **escopo** e um **corpo** mais detalhado.

**Estrutura básica:**`<tipo>: <mensagem curta e objetiva>`

**Benefícios:**

- **Clareza no Histórico:** Facilita a compreensão do que cada commit faz.
- **Automação:** Permite a geração automática de changelogs (listas de mudanças) e o versionamento semântico (`v1.0.0`, `v1.0.1`, etc.).
- **Colaboração:** Ajuda a equipe a navegar e entender o desenvolvimento do projeto.

---

### Tipos Comuns de Commits Semânticos e Exemplos

| Tipo | Descrição |
| --- | --- |
| `feat` | Adiciona uma nova funcionalidade ou recurso. |
| `fix` | Corrige um bug. |
| `docs` | Mudanças na documentação (README, comentários, etc.). |
| `style` | Mudanças de formatação que não afetam o significado do código (espaços em branco, ponto e vírgula, formatação de código). |
| `refactor` | Refatoração de código que não altera o comportamento, apenas a estrutura/legibilidade. |
| `test` | Adiciona, corrige ou melhora testes. |
| `chore` | Tarefas de manutenção que não afetam o código de produção (atualização de dependências, configurações de build, scripts). |
| `perf` | Melhorias de performance. |
| `build` | Mudanças que afetam o sistema de build ou dependências externas (npm, yarn, gulp, etc.). |
| `ci` | Mudanças nos arquivos e scripts de CI (Continuous Integration). |
| `revert` | Reverte um commit anterior. |

---

### Exemplos Detalhados de Mensagens de Commit

### `feat` (Feature - Nova Funcionalidade)

- `feat: adiciona componente de login de usuario`
- `feat(dashboard): implementa grafico de vendas por mes`
- `feat: permite cadastro de novos produtos no sistema`
- `feat(api): cria endpoint para listagem de clientes`
- `feat: adiciona funcionalidade de busca por nome na lista de animais`

### `fix` (Fix - Correção de Bug)

- `fix: corrige erro de digitacao no formulario de contato`
- `fix(autenticacao): resolve problema de login com senhas invalidas`
- `fix: ajusta layout responsivo em dispositivos moveis`
- `fix(relatorio): corrige calculo de media no relatorio de produtividade`
- `fix: impede quebra da aplicacao ao carregar imagem grande`

### `docs` (Docs - Documentação)

- `docs: atualiza README com instrucoes de instalacao`
- `docs(api): adiciona documentacao para novo endpoint de usuarios`
- `docs: corrige erros de portugues nos comentarios do codigo`
- `docs: cria guia de contribuicao para o projeto`
- `docs(manual): detalha protocolo de vacinacao de bezerros`

### `style` (Style - Estilo/Formatação)

- `style: remove espacos em branco extras no CSS`
- `style(lint): aplica padrao de formatacao com Prettier`
- `style: padroniza uso de ponto e virgula em arquivos JS`
- `style: ajusta indentacao em arquivos de configuracao`
- `style: organiza imports em ordem alfabetica`

### `refactor` (Refactor - Refatoração de Código)

- `refactor: melhora legibilidade da funcao de calculo de GPMD`
- `refactor(autenticacao): reestrutura modulo de autenticacao para melhor manutencao`
- `refactor: extrai logica de validacao para funcao separada`
- `refactor: renomeia variaveis para maior clareza`
- `refactor: otimiza estrutura de dados de registro de animais`

### `test` (Test - Testes)

- `test: adiciona teste unitario para componente Header`
- `test(api): cria testes de integracao para endpoint de produtos`
- `test: corrige falha em teste de validacao de formulario`
- `test: implementa cobertura de testes para funcao de calculo de custos`
- `test: adiciona mock para servico externo em testes`

### `chore` (Chore - Tarefas de Manutenção)

- `chore: atualiza dependencias do projeto para versoes mais recentes`
- `chore: configura ambiente de desenvolvimento local`
- `chore: remove arquivos temporarios nao utilizados`
- `chore: adiciona script para deploy automatico`
- `chore: ajusta configuracao de linter`

### `perf` (Perf - Performance)

- `perf: otimiza carregamento de imagens na pagina inicial`
- `perf(database): melhora performance de consulta de historico de animais`
- `perf: reduz tempo de execucao de algoritmo de analise de solo`
- `perf: implementa cache para dados de pastagem`
- `perf: minimiza uso de memoria em processamento de dados`

### `build` (Build - Sistema de Build/Dependências)

- `build: atualiza versao do Node.js no package.json`
- `build(deps): adiciona nova dependencia para geracao de relatorios`
- `build: configura webpack para otimizacao de assets`
- `build: ajusta script de build para ambiente de producao`
- `build: remove dependencia nao utilizada`

### `ci` (CI - Integração Contínua)

- `ci: configura pipeline de CI/CD no GitHub Actions`
- `ci: adiciona etapa de teste automatico ao workflow`
- `ci: corrige erro de permissao no script de deploy`
- `ci: configura notificacoes de build para o Slack`
- `ci: otimiza tempo de execucao do pipeline de CI`

### `revert` (Revert - Reversão de Commit)

- `revert: reverte commit "feat: adiciona funcionalidade experimental"`
- `revert: "fix: corrige problema de cache" - causou novos bugs`

---

### Dicas Adicionais:

- **Mantenha a mensagem concisa:** A primeira linha deve ter no máximo 50-72 caracteres.
- **Use o imperativo:** "adiciona", "corrige", "remove", e não "adicionei", "corrigi".
- **Escopo (opcional):** Use parênteses para indicar a parte do projeto afetada (`feat(autenticacao):`).
- **Corpo (opcional):** Para commits mais complexos, adicione uma linha em branco após a primeira linha e escreva um parágrafo mais detalhado sobre o "porquê" da mudança.

Praticar esses exemplos vai te ajudar a internalizar a estrutura e a pensar de forma mais organizada sobre cada mudança que você faz no seu projeto.

Bons estudos, cumpanheiro!

---
