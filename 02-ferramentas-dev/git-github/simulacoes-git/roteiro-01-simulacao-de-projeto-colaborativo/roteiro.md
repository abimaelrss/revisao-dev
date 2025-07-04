# 🧭 Roteiro 1 - Simulação de Projeto Colaborativo

### 🧱 Etapa 1: Preparação do Projeto

1. Crie um novo repositório no GitHub:
   - Nome: `fluxo-git-pratico`
   - Inicialize com um `README.md`
2. Clone o repositório localmente:

   ```bash
   git clone https://github.com/seu-usuario/fluxo-git-pratico.git
   cd fluxo-git-pratico
   ```

3. Crie um arquivo principal:

   ```bash
   touch index.html
   echo "<h1>Olá, mundo!</h1>" > index.html
   git add index.html
   git commit -m "feat: adiciona arquivo index.html com título inicial"
   git push origin main
   ```

---

### 🌿 Etapa 2: Criação e uso de branches

1. Crie e mude para uma nova branch chamada `feature/header`:

   ```bash
   git checkout -b feature/header
   ```

2. Adicione um header ao `index.html`, faça o commit e o push:

   ```html
   <header><h2>Menu</h2></header>
   ```

   ```bash
   git add index.html
   git commit -m "feat: adiciona header ao index"
   git push origin feature/header
   ```

---

### 🔀 Etapa 3: Merge com a branch `main`

1. Volte para a `main`:

   ```bash
   git checkout mai
   ```

2. Faça o merge da feature:

   ```bash
   git merge feature/header
   git push origin main
   ```

---

### ⚔️ Etapa 4: Simulando um conflito

1. Crie uma nova branch:

   ```bash
   git checkout -b feature/footer
   ```

2. Adicione um `<footer>` ao `index.html`, faça o commit e o push.
3. Enquanto isso, **volte pra `main`** e edite o **mesmo lugar do arquivo** (ex: escreva outro `<footer>` diferente), e faça commit e push.
4. Tente dar merge da `feature/footer` na `main`:

   ```bash
   git merge feature/footer
   ```

5. Resolva o conflito no VS Code (ou editor de sua escolha), depois:

   ```bash
   git add index.html
   git commit -m "fix: resolve conflito entre main e feature/footer"
   git push origin main
   ```

---

### 🏷️ Etapa 5: Criação de uma tag de versão

1. Após o merge, crie uma tag da versão:

   ```bash
   git tag -a v1.0.0 -m "Versão 1.0.0 com header e footer"
   git push origin v1.0.0
   ```

---

### 📂 Etapa 6: Comandos extras pra revisar

```bash
git log --oneline --graph --all   # Ver a árvore do histórico
git status                        # Ver o que está staged ou não
git diff                          # Ver mudanças ainda não commitadas
git remote -v                     # Ver repositórios remotos
```

---

### ✅ Missão Final: Documentar tudo

1. No `README.md`, explique o que você fez.
2. Use uma lista assim:

```markdown
## Comandos usados

- git clone
- git checkout -b
- git merge
- git push
- git pull
- git tag
- git log
- git status
- git diff
```

---
