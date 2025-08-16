# 🏗️ Layout com CSS

O CSS evoluiu bastante ao longo do tempo. Hoje temos recursos poderosos como **Flexbox** e **Grid**, mas antes disso os layouts eram feitos de forma bem diferente. Vamos ver essa evolução e, em seguida, entrar em pontos fundamentais: `position`, variáveis e pseudo-elementos/classes.

---

## 🔄 Evolução dos Layouts

- **Tabelas**: usadas nos anos 90 para montar páginas inteiras (não recomendado hoje).
- **Floats**: usados para criar colunas, mas exigiam muitos “hacks” (`clear`, `clearfix`).
- **Flexbox**: trouxe alinhamento fácil em uma dimensão (linha **ou** coluna).
- **Grid**: permite organizar elementos em duas dimensões (linha **e** coluna).

> 📌 Hoje: Grid + Flex são as ferramentas principais para layout moderno.

---

## 📍 Position

A propriedade `position` define como um elemento é posicionado na página.

- **static**: padrão, segue o fluxo normal da página.
- **relative**: mantém a posição original, mas pode ser deslocado.
- **absolute**: sai do fluxo normal e é posicionado em relação ao ancestral mais próximo com `position: relative`.
- **fixed**: fica preso em uma posição, mesmo rolando a página.
- **sticky**: mistura relative + fixed; “cola” quando atinge certo ponto da rolagem.

### Exemplo:

```html
<div class="caixa">Caixa</div>
```

```css
.caixa {
  width: 100px;
  height: 100px;
  background: lightblue;
  position: absolute;
  top: 50px;
  left: 50px;
}
```

---

## 🎨 Variáveis CSS

Permitem guardar valores para reutilizar no código.

```css
:root {
  --cor-principal: #3498db;
  --espacamento: 1.5rem;
}

button {
  background: var(--cor-principal);
  padding: var(--espacamento);
}
```

> 💡 Vantagem: se você mudar --cor-principal no :root, todas as referências atualizam automaticamente.

---

## 🧩 Pseudo-classes e Pseudo-elementos

**Pseudo-classes**: representam estados ou condições dos elementos.

- `:hover` → quando o mouse passa por cima
- `:focus` → quando um campo está ativo
- `:nth-child()` → seleciona o n-ésimo elemento
- `:first-child` → seleciona o primeiro elemento
- `:last-child` → seleciona o último elemento
- `:visited` → quando um link já foi visitado
- `:valid / :invalid` → quando um input está válido ou inválido

---

**Pseudo-elementos**: criam elementos virtuais dentro do conteúdo.

- `::before` → insere conteúdo antes
- `::after` → insere conteúdo depois
- `::first-line` → seleciona a primeira linha do texto
- `::first-letter` → seleciona a primeira letra
- `::selection` → seleciona o trecho destacado pelo usuário

---

**Exemplos:**

```css
/* Pseudo-classes */
button:hover {
  background: darkblue;
  color: white;
}

input:focus {
  border: 2px solid dodgerblue;
}

li:nth-child(2) {
  color: red;
}

/* Pseudo-elementos */
h1::after {
  content: " 🔥";
}

p::first-line {
  font-weight: bold;
  color: darkblue;
}

::selection {
  background: yellow;
  color: black;
}
```

---

# 🎯 Módulo 2 — CSS Flexbox

O **Flexbox** é um modelo de layout no CSS que facilita alinhar, distribuir e organizar elementos dentro de um container.

Ele resolve problemas comuns de centralização e espaçamento sem precisar de floats ou hacks antigos.

---

### 🧩 Conceitos básicos

- **Flex Container** → o elemento pai com `display: flex;`
- **Flex Itens** → os elementos filhos dentro do container
- **Eixo principal (main axis)** → pode ser horizontal ou vertical
- **Eixo cruzado (cross axis)** → perpendicular ao eixo principal

Exemplo:

```css
.container {
  display: flex;
  border: 2px solid black;
}
```

---

### 🧩 `justify-content`

Alinha os itens **no eixo principal**.

- `flex-start` (padrão)
- `flex-end`
- `center`
- `space-between`
- `space-around`
- `space-evenly`

```css
.container {
  display: flex;
  justify-content: space-between;
}
```

---

### 🧩 `align-items`

Alinha os itens **no eixo cruzado**.

- `stretch` (padrão)
- `flex-start`
- `flex-end`
- `center`
- `baseline`

```css
.container {
  display: flex;
  align-items: center;
}
```

---

### 🧩 `gap` e `margin`

- `gap` → cria espaço entre itens
- `margin` → espaço fora de cada item

```css
.container {
  display: flex;
  gap: 20px;
}
```

---

### 🧩 Multi-line (`flex-wrap`)

Permite quebrar linha quando os itens não cabem.

- `nowrap` (padrão)
- `wrap`
- `wrap-reverse`

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

---

### 🧩 `flex-basis`

Define o tamanho **base** de um item.

```css
.item {
  flex-basis: 200px;
}
```

---

### 🧩 `flex-grow` e `flex-shrink`

- `flex-grow` → quanto o item **cresce** em relação aos outros
- `flex-shrink` → quanto o item **encolhe** em relação aos outros

```css
.item1 {
  flex-grow: 2;
}
.item2 {
  flex-grow: 1;
}
```

---

### 🧩 Shorthand `flex`

Atalho para `flex-grow flex-shrink flex-basis`.

```css
.item {
  flex: 1 0 150px; /* grow | shrink | basis */
}
```

---

### 🧩 `order`

Define a ordem de exibição dos itens.

```css
.item {
  order: 2;
}
```

---

### 🧩 `flex-flow`

Atalho para `flex-direction` + `flex-wrap`.

```css
.container {
  display: flex;
  flex-flow: row wrap;
}
```

---

### 🧩 `align-content` (para várias linhas)

Alinha o **conjunto das linhas** no eixo cruzado.

- `flex-start`
- `flex-end`
- `center`
- `space-between`
- `space-around`
- `stretch`

```css
.container {
  display: flex;
  flex-wrap: wrap;
  align-content: center;
}
```

---
