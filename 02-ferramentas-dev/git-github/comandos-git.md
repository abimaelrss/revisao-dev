# Git e GitHub

## 💡 O que é o Git?

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
| `git reset --hard HEAD~1` | Volta ao último commit |
| `git reset --hard <id-do-commit>` |  |
| `git reset --soft HEAD~1` | Volta ao último commit, mantendo os arquivos no staging |
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

### 🔡 Commits semânticos

Commits semânticos (Convention Commits) é uma maneira de formatar as mensagens dos commits de forma objetiva e clara.

- Usar commits semânticos traz mais clareza do histórico do projeto.
- Permite o versionamento semântico, geração automática de changelogs.
- Melhora a qualidade do código.
- Facilita a manutenção do código.

---

### 🧱 Estrutura básica

<tipo>: <mensagem curta e objetiva no imperativo>

---

### Tipos mais usados

| Tipo | Descrição | Exemplo |
| --- | --- | --- |
| `feat` | Adiciona uma nova funcionalidade | feat: adiciona componente de login |
| `fix` | Corrige um bug | fix: corrige erro no botão de envio |
| `docs` | Mudanças na documentação do projeto | docs: atualiza README com instruções de uso |
| `style` | Mudança de formatação (espaços, ponto e vírgula, etc.) | style: remove espaços extras no CSS |
| `refactor` | Refatoração de código (sem alterar comportamento) | refactor: melhora legibilidade da função de cálculo |
| `test` | Adição ou alteração de testes | test: adiciona teste para componente Header |
| `chore` | Tarefas que não afetam o código (ex: configs) | chore: atualiza dependências do projeto |

---

# 👨🏻‍💻 Projetos práticos para praticar comandos Git

---