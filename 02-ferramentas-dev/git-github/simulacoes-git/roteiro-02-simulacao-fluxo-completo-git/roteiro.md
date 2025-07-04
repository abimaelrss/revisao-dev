# 🧭 Roteiro 2 - Simulação de um Fluxo Completo de Git

## 🎯 **Objetivo**

Te colocar no papel de um Dev Junior contribuindo com um projeto: criando novas funcionalidades, resolvendo conflitos e marcando versões.

---

## 🛠️ **1. Inicialização do Projeto**

### 📌 Comandos:

```bash
git init
```

Crie um diretório de projeto local com um arquivo básico (`index.html`, por exemplo) e inicialize o repositório.

---

## 🔄 **2. Criação de Commits Básicos**

### 📌 Comandos:

```bash
git add .
git commit -m "feat: cria estrutura inicial do projeto"
```

Adicione arquivos e faça commits com mensagens claras, seguindo uma convenção (ex: `feat:`, `fix:`, `docs:`).

> ✅ Dica: Use mensagens descritivas. Pense que outro dev vai ler.

---

## 🌿 **3. Criação e Troca de Branches**

Você quer criar uma nova feature chamada "tela de login".

### 📌 Comandos:

```bash
git branch feature/login
git checkout feature/login
```

> 💡 Você pode usar git switch -c feature/login também.

Faça alterações no projeto (ex: adicione `login.html`) e depois:

```bash
git add login.html
git commit -m "feat: adiciona tela de login"
```

---

## 📦 **4. Merge da Branch (sem conflitos)**

Volte para a `main` e una sua feature nela:

```bash
git checkout main
git merge feature/login
```

> 🧠 Aqui o Git vai tentar fazer o merge automático. Se tudo der certo, a branch se une sem conflitos.

---

## 🧨 **5. Simulação de Conflito**

Crie outra branch chamada `feature/home`, mude a mesma linha do `index.html` e depois volte pra `main` e edite essa mesma linha.

### 📌 Passo a passo:

```bash
git checkout -b feature/home
```

Acrescente um <header> no `index.html`, salve, commit:

```bash
git add index.html
git commit -m "feat: altera header na feature/home"
```

Depois volte pra `main`, altere **a mesma linha**, e comite:

```bash
git checkout main
# altera a mesma linha
git add index.html
git commit -m "feat: altera header na main"
```

Agora tente dar merge:

```bash
git merge feature/home
```

Você verá um **conflito**. O Git vai marcar o arquivo com `<<<<<<<`, `=======` e `>>>>>>>`.

Resolva manualmente e depois:

```bash
git add index.html
git commit -m "merge: resolve conflito entre main e feature/home"
```

---

## 🔍 **6. Análise do Histórico**

Veja os commits com:

```bash
git log --oneline --graph --all
```

Compare diferenças:

```bash
git diff
```

---

## 🔗 **7. Conectar a um repositório remoto**

Crie um repositório vazio no GitHub, copie a URL e rode:

```bash
git remote add origin https://github.com/seu-usuario/seu-repo.git
git branch -M main
git push -u origin main
```

Depois, envie também as branches secundárias, se quiser:

```bash
git push origin feature/login
git push origin feature/home
```

---

## 🔖 **8. Criar Tags de Versão**

Simule que sua aplicação chegou à versão 1.0:

```bash
git tag -a v1.0 -m "Versão inicial estável"
git push origin v1.0
```

---

## 🧪 **9. Limpeza de Branches**

Branches já fundidas podem ser apagadas:

```bash
git branch -d feature/login
git push origin --delete feature/login
```

---
