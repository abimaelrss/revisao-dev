# 🧱 Fundamentos de CSS

Este guia cobre os conceitos essenciais do **CSS (Cascading Style Sheets)** — a linguagem de estilos responsável por dar vida e aparência às páginas web.

---

## 🚀 Conhecendo o CSS

### O que é CSS?

**CSS (Cascading Style Sheets)** é a linguagem que define a **apresentação** de documentos HTML.

Enquanto o HTML é o **esqueleto** e o conteúdo, o CSS é a **pele** e a **roupa** da página.

Com ele, controlamos:

- Cores
- Tipografia
- Espaçamentos
- Layout
- Animações

Sem CSS, um site seria apenas um texto sem formatação.

---

### Comentários

Servem para deixar **anotações** no código ou **desativar** trechos temporariamente.

Não são renderizados pelo navegador.

```css
/* Comentário de uma linha */

/*
Comentário
de múltiplas linhas
*/
```

---

### Anatomia de uma Regra CSS

Uma regra CSS é composta por:

- **Seletor** → Elemento(s) HTML a estilizar
- **Propriedades** → Características que serão modificadas
- **Valores** → Como a propriedade será aplicada

```css
h1 {
  color: blue; /* Cor do texto */
  font-size: 24px; /* Tamanho da fonte */
  text-align: center; /* Alinhamento do texto */
}
```

---

## 🌊 A Cascata e Especificidade

### O que é “Cascading”

Quando múltiplas regras afetam o mesmo elemento, o navegador segue esta ordem:

1. **Origem do estilo**
   - Estilo padrão do navegador
   - Estilo do desenvolvedor (você)
   - Estilo definido pelo usuário (ex.: configurações de acessibilidade)
2. **Especificidade**
3. **Ordem no código** (última regra vence em empate)

💡 **Dica:** Algumas propriedades herdam valores dos elementos pais, como `color` e `font-family`. Outras não (ex.: `margin`, `border`).

---

### Especificidade (Pontuação)

| Tipo de seletor                 | Pontos |
| ------------------------------- | ------ |
| Inline (`style="..."`)          | 1000   |
| ID (`#menu`)                    | 100    |
| Classe, atributo, pseudo-classe | 10     |
| Elemento ou pseudo-elemento     | 1      |

Exemplo:

```css
#meu-id {
  color: blue;
} /* 100 */
.minha-classe {
  color: red;
} /* 10 */
p {
  color: green;
} /* 1 */
```

HTML:

```html
<p id="meu-id" class="minha-classe">Texto</p>
```

Resultado: **azul** (maior especificidade).

---

### `!important`

Sobrescreve especificidade e ordem, mas deve ser usado **apenas em último caso**.

```css
p {
  color: red !important;
}
```

💡 **Evite:** dificulta manutenção e depuração.

---

## 📏 Valores e Unidades

### Unidades Absolutas

| Unidade | Descrição   | Exemplo            |
| ------- | ----------- | ------------------ |
| px      | Pixel fixo  | `font-size: 16px;` |
| cm      | Centímetros | `width: 10cm;`     |
| in      | Polegadas   | `height: 1in;`     |

💡 **Uso comum:** `px`.

`cm` e `in` raramente usados, exceto para impressão.

---

### Unidades Relativas

| Unidade | Relativo a...                     | Exemplo              |
| ------- | --------------------------------- | -------------------- |
| em      | Fonte do elemento pai             | `padding: 2em;`      |
| rem     | Fonte do elemento raiz (`<html>`) | `font-size: 1.2rem;` |
| %       | Dimensão do pai                   | `width: 80%;`        |
| vw      | Largura da janela                 | `width: 50vw;`       |
| vh      | Altura da janela                  | `height: 100vh;`     |

```css
body {
  font-size: 16px;
}
h1 {
  font-size: 2rem;
} /* 32px */
```

---

## 🎯 Seletores e Combinadores

### Seletores Básicos

| Tipo      | Exemplo            | Seleciona                         |
| --------- | ------------------ | --------------------------------- |
| Tipo      | `p {}`             | Todos os `<p>`                    |
| Classe    | `.item {}`         | Elementos com `class="item"`      |
| ID        | `#menu {}`         | Elemento com `id="menu"`          |
| Universal | `* {}`             | Todos os elementos                |
| Atributo  | `[type="text"] {}` | Elementos `<input>` do tipo texto |

---

### Combinadores

| Combinador            | Exemplo   | Seleciona                                   |
| --------------------- | --------- | ------------------------------------------- |
| Descendente (espaço)  | `div p`   | `<p>` dentro de `<div>`                     |
| Filho direto (`>`)    | `ul > li` | `<li>` diretamente dentro de `<ul>`         |
| Irmão adjacente (`+`) | `h1 + p`  | Primeiro `<p>` logo após `<h1>`             |
| Irmão geral (`~`)     | `h1 ~ p`  | Todos `<p>` depois de `<h1>` no mesmo nível |
| Agrupamento (`,`)     | `h1, h2`  | Aplica a ambos seletores                    |

---

## 🎁 Formas de Adicionar CSS

1. **Externo (preferido)**

```html
<link rel="stylesheet" href="style.css" />
```

1. **Interno**

```html
<style>
  body {
    background: lightblue;
  }
</style>
```

1. **Inline**

```html
<p style="color: red;">Texto</p>
```

---

## 📦 Box Model

Cada elemento é uma caixa composta por:

1. **Content** → Área do conteúdo (`width`, `height`)
2. **Padding** → Espaço interno
3. **Border** → Contorno
4. **Margin** → Espaço externo

💡 **Diferença importante:**

- `content-box` (padrão) → `width` não inclui `padding` e `border`
- `border-box` → `width` inclui `padding` e `border`

```css
* {
  box-sizing: border-box;
}
```

---

### Display

| Valor        | Comportamento                                          |
| ------------ | ------------------------------------------------------ |
| block        | Ocupa toda a largura, quebra linha                     |
| inline       | Ocupa apenas o necessário, não aceita `width`/`height` |
| inline-block | Mistura dos dois comportamentos                        |

---

## ✒️ Fontes e Textos

Principais propriedades:

```css
body {
  font-family: "Helvetica Neue", Arial, sans-serif;
  font-size: 1rem;
  font-weight: 400;
  color: #333;
  text-align: justify;
}
```

💡 **Dica:** Prefira `rem` para tamanho de fonte → acessibilidade.

---

## 🎨 Cores e Fundos

### Formatos de cor

```css
color: red; /* Nome */
color: #ff0000; /* Hex */
color: rgb(255, 0, 0);
color: hsl(0, 100%, 50%);
```

### Fundos

```css
body {
  background: url("imagem.jpg") no-repeat center/cover;
}
```

💡 Também é possível usar gradientes:

```css
background: linear-gradient(to right, red, yellow);
```

---

## 📌 Resumo Rápido

```css
/* =========================
   FUNDAMENTOS DE CSS - REVISÃO
   ========================= */

/* ===== Seletores ===== */
h1,
h2,
h3,
h4,
h5,
h6 {
  color: blue; /* Cor do texto */
}

#titulo-principal {
  color: darkred; /* Seleção por ID */
}

.texto-destaque {
  color: orange; /* Seleção por classe */
}

/* ===== Cores ===== */
.cor-nome {
  color: green; /* Nome da cor */
  color: #ff5733; /* HEX */
  color: rgb(255, 87, 51); /* RGB */
  color: rgba(255, 87, 51, 0.7); /* RGB com transparência */
}

/* ===== Tipografia ===== */
.texto-tipografia {
  font-family: Arial, Helvetica, sans-serif; /* Família de fontes */
  font-size: 18px; /* Tamanho da fonte */
  font-weight: bold; /* Peso da fonte */
  font-style: italic; /* Estilo da fonte */
  text-align: center; /* Alinhamento do texto */
  text-decoration: underline; /* Decoração do texto */
  line-height: 1.5; /* Espaçamento entre linhas */
  letter-spacing: 2px; /* Espaçamento entre letras */
}

/* ===== Background ===== */
.bg-cor {
  background-color: lightblue; /* Cor de fundo */
  background-image: url("exemplo.jpg"); /* Imagem de fundo */
  background-repeat: no-repeat; /* Repetição da imagem */
  background-size: cover; /* Cobrir toda a área */
  background-position: center; /* Posição centralizada */
}

/* ===== Bordas ===== */
.borda {
  border: 2px solid black; /* Largura, estilo e cor */
  border-radius: 10px; /* Arredondamento */
}

/* ===== Espaçamentos ===== */
.espacamentos,
div,
section,
article {
  padding: 10px; /* Espaçamento interno */
  margin: 10px 0; /* Margem externa */
  border: 1px solid #ccc; /* Borda cinza */
  border-radius: 5px; /* Bordas arredondadas */
}

/* ===== Dimensões ===== */
.dimensoes {
  width: 200px; /* Largura */
  height: 100px; /* Altura */
  max-width: 100%; /* Largura máxima */
  min-height: 50px; /* Altura mínima */
}

/* ===== Display ===== */
.display {
  display: block; /* Ocupa toda a largura */
  display: inline; /* Ocupa apenas o conteúdo */
  display: inline-block; /* Mistura características de block e inline */
}

/* ===== Shorthand ===== */
.shorthand-margin {
  margin: 10px 20px 30px 40px; /* top, right, bottom, left */
  padding: 15px 25px; /* vertical, horizontal */
  border: 3px dashed red; /* largura, estilo, cor */
  background: lightblue url("exemplo.jpg") no-repeat center/cover; /* cor, imagem, repetição, posição/tamanho */
  font: italic bold 16px/1.5 Arial, sans-serif; /* estilo, peso, tamanho/linha, família */
}
```
