# 🧱 Fundamentos de HTML

Este documento cobre os conceitos fundamentais do HTML de forma aprofundada, servindo como uma excelente fonte de consulta.

## 🚀 Primeiros Passos

### O que é HTML?

HTML (**HyperText Markup Language**) é a linguagem de marcação padrão para a criação de páginas web. Ela é responsável por estruturar o conteúdo de um site, organizando elementos como títulos, parágrafos, imagens e links.

### Comentários no HTML

Comentários são usados para adicionar notas e explicações ao código, sem que elas sejam exibidas no navegador. São essenciais para a organização e colaboração.

**Exemplo:**

```html
<!-- Este é um comentário de uma linha. -->

<!--
    Este é um comentário
    de múltiplas linhas.
-->
```

### Anatomia das Tags

A maioria dos elementos HTML é composta por uma **tag de abertura**, o **conteúdo** e uma **tag de fechamento**.

- **Tag de Abertura:** `<p>` - Marca o início do elemento.
- **Conteúdo:** `Este é o meu parágrafo.` - O que o usuário verá.
- **Tag de Fechamento:** `</p>` - Marca o final do elemento.

O conjunto completo de abertura, conteúdo e fechamento é chamado de **elemento**.

**Exemplo:**

```html
<p>Olá, mundo!</p>
```

Algumas tags são **autofecháveis** e não contêm conteúdo.

**Exemplo:**

```html
<img src="foto.jpg" alt="Minha foto" /> <br />
```

### Espaços e quebras de linha

O HTML ignora múltiplos espaços, tabulações e quebras de linha. O navegador trata tudo como um único espaço. Para criar novas linhas, você deve usar elementos como `<p>` ou `<br>`.

**Exemplo:**

```html
<p>Este texto tem vários espaços, mas será exibido como um só.</p>

<p>Este é um parágrafo.</p>
<br />
Este texto virá em uma nova linha.
```

### Fluxo HTML

Fluxo HTML é a forma como o navegador lê e renderiza o conteúdo de uma página web, seguindo a ordem em que os elementos HTML aparecem no código. Ele começa a ler o seu arquivo HTML do topo para baixo e da esquerda para a direita. Cada vez que encontra uma **tag HTML**, ele a processa e a posiciona na página.

Existem dois tipos principais de fluxo que guiam esse processo:

- **Fluxo de Bloco (block):** Elementos de bloco, como `<p>`, `<h1>` e `<div>`, ocupam toda a largura disponível e criam uma nova linha. Eles se empilham verticalmente, um abaixo do outro.
- **Fluxo em Linha (inline):** Elementos em linha, como `<a>`, `<span>` e `<strong>`, ocupam apenas o espaço necessário para o seu conteúdo e não quebram a linha. Eles se alinham horizontalmente, um ao lado do outro, até que não haja mais espaço, e então a próxima palavra é jogada para a próxima linha.

### Aninhamento de Tags

É a prática de colocar uma tag dentro da outra. É importante sempre fechar a tag interna antes de fechar a tag externa.

**Exemplo:**

```html
<p>Este é um parágrafo que contém um <strong>texto em negrito</strong>.</p>
<!-- Correto -->

<p>Este é um parágrafo que contém um <strong>texto em negrito.</p></strong>
<!-- Incorreto -->

```

### Caracteres reservados

Alguns caracteres, como `<`, `>` e `&` são reservados pelo HTML e não podem ser usados diretamente como texto. Você deve usar entidades de caractere para exibi-los.

- `&lt;` para `<`
- `&gt;` para `>`
- `&amp;` para `&`
- `&quot;` para `"`
- `&apos;` para `'`
- `&nbsp;` para ` ` (espaço)

## 🏷️ Atributos

Atributos fornecem informações adicionais sobre as tags, modificando seu comportamento ou aparência. Eles são sempre declarados na tag de abertura e vêm no formato `nome="valor"`.

**Exemplo:**

```html
<a href="https://www.google.com" target="_blank">Google</a>
```

Neste exemplo, `href` e `target` são atributos do elemento `<a>`.

### Atributos booleanos

São atributos que não precisam de um valor. A simples presença do atributo na tag já ativa sua funcionalidade.

**Exemplo:**

```html
<input type="checkbox" checked />
<!-- A caixa de seleção já vem marcada -->
 
<input type="text" disabled />
<!-- O campo de texto não pode ser editado -->
```

O atributo `checked` faz com que a caixa de seleção seja marcada por padrão. O atributo `disabled` faz com que o campo de texto não possa ser editada.

### Atributos globais

Atributos que podem ser usados em **qualquer tag HTML**.

- `id` é um identificador **único** na página. Ele é perfeito para:
  - **CSS:** Estilizar um elemento específico (`#meu-id`).
  - **JavaScript:** Acessar o elemento (`document.getElementById('meu-id')`).
  - **Links internos:** Criar links para seções específicas da página (`<a href="#contato">Contato</a>`).
- `class` é usado para agrupar elementos que compartilham o mesmo estilo ou comportamento. Um elemento pode ter várias classes.
  **Exemplo:**
  ```html
  <p class="titulo-destaque texto-maior">
    Este parágrafo será grande e destacado.
  </p>
  ```
- `data-*` permitem que você armazene dados personalizados em elementos HTML. Eles não têm efeito visual, mas podem ser acessados e manipulados com JavaScript.
  **Exemplo:**
  ```html
  <li data-produto-id="789" data-categoria="eletronicos">Notebook XZ</li>
  ```
  **Acesso com JavaScript:** `const id = li.dataset.produtoId;`
- O atributo `style` permite adicionar estilos CSS diretamente na tag HTML. É uma forma rápida, mas **não recomendada** para projetos grandes, pois dificulta a manutenção do código. O ideal é usar um arquivo CSS externo.
  **Exemplo:**
  ```html
  <p style="color: blue; font-weight: bold; font-size: 18px;">
    Texto estilizado.
  </p>
  ```

## 📝 Elementos de Conteúdo

### Semântica

HTML Semântico é a prática de usar tags que descrevem o significado do conteúdo. Isso não apenas torna o código mais legível para outros desenvolvedores, mas também é crucial para:

- **Acessibilidade:** Leitores de tela para pessoas com deficiência visual entendem a estrutura da página.
- **SEO (Search Engine Optimization):** Motores de busca como o Google compreendem o conteúdo da sua página e a classificam melhor.

**Exemplo:** `<header>`, `<nav>`, `<main>`...

```html
<header>
  <h1>Título do Site</h1>
  <nav>...</nav>
</header>
<main>...</main>
```

O código acima é mais claro do que usar várias `<div>` com classes como `<div id="header">`...

```html
<div id="header">
  <h1>Título do Site</h1>
  <div id="nav">...</div>
</div>
<div id="main">...</div>
```

### Títulos e parágrafos

- **`<h1>` a `<h6>`**: Usados para títulos e subtítulos. A hierarquia é importante: `<h1>` é o título principal da página (use apenas um por página), `<h2>` é um subtítulo, `<h3>` um subtítulo de `<h2>`, e assim por diante.
- **`<p>`**: Parágrafos. A tag fundamental para blocos de texto.

**Exemplo:**

```html
<h1>Título Principal</h1>
<h2>Subtítulo</h2>
<p>Este é um parágrafo de texto.</p>
```

### Formatação básica de textos

- `<strong>`: Indica texto de **importância** forte (geralmente negrito).
- `<em>`: Enfatiza o texto, indicando um `ê`nfase (geralmente itálico).
- `<b>`: Texto em negrito (visual, sem importância semântica).
- `<i>`: Texto em itálico (visual, sem ênfase semântica).
- `<u>`: Texto sublinhado.
- `<mark>`: Texto destacado ou marcado.
- `<sup>`: Texto sobrescrito (Ex: 2³).
- `<sub>`: Texto subscrito (Ex: H₂O).

**Exemplo:**

```html
<h1>Exemplo de Tags de Formatação</h1>

<p>
  <strong>Importância</strong>
  <em>Ênfase</em>
  <b>Negrito</b>
  <i>Itálico</i>
  <u>Sublinhado</u>
  <mark>Marcado</mark>
  <sup>Sobrescrito</sup>
  <sub>subscrito</sub>
</p>
```

### Listas

- `<ul>`: **U**nordered **L**ist (lista não ordenada, com marcadores).
- `<ol>`: **O**rdered **L**ist (lista ordenada, com números).
- `<li>`: **L**ist **I**tem (item da lista).

Exemplo:

```html
<ul>
  <li>Café</li>
  <li>Leite</li>
</ul>

<ol>
  <li>Passo 1</li>
  <li>Passo 2</li>
</ol>
```

### Representação de código de computador

- **`<code>`**: Para exibir um trecho de código **inline** (na mesma linha do texto).
- **`<pre>`**: Para exibir um bloco de texto **pré-formatado**. Ele preserva espaços, tabulações e quebras de linha.

**Exemplo:**

```html
<p>Para criar um parágrafo, use a tag <code>&lt;p&gt;</code>.</p>
<pre>
    function soma(a, b) {
        return a + b;
    }
</pre>
```

### Hiperlink

A tag `<a>` é usada para criar links. O atributo `href` é obrigatório e define o destino.

- **Link para outro site:**`target="_blank"` abre o link em uma nova aba.
  `rel="noopener noreferrer"` é uma prática de segurança recomendada com `target="_blank"`.
      **Exemplo:**

      ```html
      <a href="https://www.google.com" target="_blank" rel="noopener noreferrer">Ir para o Google</a>
      ```
- **Link para uma seção da mesma página:**
  **Exemplo:**
  ```html
  <a href="#contato">Ir para a seção de Contato</a>
  ```

### Imagens

A tag `<img>` insere uma imagem na página. É uma tag autofechável.

- `src`: O caminho para o arquivo da imagem.
- `alt`: O texto alternativo que descreve a imagem. Essencial para acessibilidade e SEO.
- `width` e `height`: Define a largura e altura da imagem.

**Exemplo:**

```html
<img
  src="https://placehold.co/600x400/000000/FFFFFF/png?text=Minha+Imagem"
  alt="Uma imagem de exemplo em preto e branco com o texto 'Minha Imagem'."
  width="600"
  height="400"
/>
```

## 🖼️ Elementos Estruturais

### Anatomia de um documento HTML

A estrutura básica de um documento.

- **`<!DOCTYPE html>`**: Declara o tipo de documento.
- **`<html>`**: O elemento raiz que contém todo o conteúdo da página.
- **`<head>`**: Contém metadados sobre a página (título, CSS, JavaScript, etc.).
- **`<body>`**: Contém todo o conteúdo visível para o usuário.

**Exemplo:**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Título da Página</title>
  </head>
  <body>
    <!-- Conteúdo principal do site -->
  </body>
</html>
```

### Desenhando uma página web

O layout de uma página web geralmente é dividido em seções semânticas. Pense na página como um jornal: o cabeçalho, as matérias principais, a barra lateral e o rodapé.

### Tags Header, Main, Aside e Footer

- `<header>`: Contém o cabeçalho do site, como o logo e a navegação.
- `<main>`: Contém o conteúdo principal e único da página.
- `<aside>`: Contém conteúdo relacionado, mas que pode ser separado do conteúdo principal, como uma barra lateral.
- `<footer>`: Contém o rodapé do site, com informações de contato, direitos autorais, etc.

### Tags Nav, Section e Article

- `<nav>`: Contém links de navegação. Deve ser usado dentro do `<header>` ou em outras partes da página com links importantes.
- `<section>`: Agrupa conteúdo relacionado, como capítulos, abas, etc.
- `<article>`: Conteúdo independente e autocontido, como um post de blog ou uma notícia.

**Exemplo:**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Título da Página</title>
  </head>
  <body>
    <header>
      <nav></nav>
    </header>

    <main>
      <section></section>
      <aside></aside>
    </main>

    <footer></footer>
  </body>
</html>
```

### Tags genéricas Div e Span

Use `<**div**>` e `<**span**>` apenas quando não houver uma tag semântica apropriada.

- **`<div>`**: É um contêiner de **bloco** genérico. Quebra a linha e ocupa a largura total disponível.
- **`<span>`**: É um contêiner **inline** genérico. Não quebra a linha e ocupa apenas o espaço do seu conteúdo.

**Exemplo:**

```html
<div>
  <!-- Contêiner de bloco -->
  <h1>Minha Seção</h1>
  <p>Este parágrafo contém um <span>texto destacado</span>.</p>
</div>
```

## 📂 Caminhos Absolutos e Relativos

### Caminhos absolutos e relativos

Caminhos indicam onde encontrar um arquivo (imagem, folha de estilo, etc.) em relação ao documento HTML atual.

### Caminhos absolutos

Caminhos que especificam a localização completa e exata de um arquivo, a partir do seu diretório raiz, seja no disco local ou em um servidor.

**Exemplo:**

```html
<!-- Caminho absoluto no Windows -->
<img src="C:\Users\SeuNome\Documentos\Projetos\imagens\logo.png" />

<!-- Caminho absoluto no Linux/macOS -->
<img src="/home/seunome/projetos/imagens/logo.png" />

<!-- Caminho absoluto na web-->
<img src="https://www.seusite.com/imagens/logo.png" />

<!-- Caminho absoluto no servidor -->
<img src="/var/www/html/seuprojeto/imagens/logo.png" />
```

### Caminhos relativos à mesma pasta

`./` indica a pasta atual. `nome-do-arquivo.html` também funciona para arquivos na mesma pasta.

**Exemplo:**

```html
<!-- Arquivos na mesma pasta -->
<a href="./sobre.html">Sobre nós</a>
<img src="imagem.jpg" />
```

### Caminhos relativos em pastas diferentes

- `../`: Sobe um nível de pasta.
- `pasta/`: Entra em uma pasta.

**Exemplo:**

```html
<!-- Subindo um nível para encontrar o arquivo -->
<img src="../imagens/foto.jpg" />

<!-- Entrando na pasta 'css' -->
<link rel="stylesheet" href="css/estilos.css" />
```
