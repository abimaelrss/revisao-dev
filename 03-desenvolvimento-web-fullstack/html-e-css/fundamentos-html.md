# 🧱 Fundamentos de HTML

Um guia prático e aprofundado para entender a base da criação de páginas web.

---

## 🚀 O que é HTML?

HTML (**HyperText Markup Language**) é a linguagem que dá **estrutura** às páginas web.

Com ele, organizamos **títulos, textos, imagens, links e outros elementos** para que o navegador possa exibir o conteúdo corretamente.

---

## 💬 Comentários

Comentários servem para inserir anotações no código, sem aparecer para o usuário.

São úteis para **organizar** e **documentar**.

```html
<!-- Comentário de uma linha -->

<!--
    Comentário
    de várias linhas
-->
```

---

## 🏗 Estrutura das Tags

A maioria dos elementos HTML tem:

- **Tag de abertura**: `<p>`
- **Conteúdo**: `Este é o texto.`
- **Tag de fechamento**: `</p>`

Exemplo:

```html
<p>Olá, mundo!</p>
```

Algumas tags são **autofecháveis**:

```html
<img src="foto.jpg" alt="Minha foto" />
<br />
```

---

## 📏 Espaços e Quebras de Linha

O navegador **ignora múltiplos espaços** e trata tudo como um único espaço.

Para criar quebras de linha, use `<p>` ou `<br>`.

```html
<p>Texto com vários espaços (exibido como um só).</p>
<p>Parágrafo novo.</p>
<br />
Nova linha aqui.
```

---

## 📚 Fluxo HTML

O navegador lê o HTML **de cima para baixo** e **da esquerda para a direita**:

- **Bloco (block)**: ocupa toda a largura e quebra a linha (`<p>`, `<h1>`, `<div>`).
- **Inline**: ocupa só o espaço do conteúdo, sem quebrar linha (`<a>`, `<span>`, `<strong>`).

---

## 🔗 Aninhamento Correto

Feche a tag **interna** antes da **externa**:

✅ Correto:

```html
<p>Texto com <strong>negrito</strong>.</p>
```

❌ Incorreto:

```html
<p>Texto com <strong>negrito.</p></strong>

```

---

## ⚠ Caracteres Reservados

Alguns símbolos precisam de códigos especiais:

| Símbolo | Código HTML |
| ------- | ----------- |
| `<`     | `&lt;`      |
| `>`     | `&gt;`      |
| `&`     | `&amp;`     |
| `"`     | `&quot;`    |
| `'`     | `&apos;`    |
| Espaço  | `&nbsp;`    |

---

## 🏷️ Atributos

Os atributos dão **informações extras** para as tags.

```html
<a href="https://google.com" target="_blank">Google</a>
```

- **Booleanos**: só a presença já ativa (`checked`, `disabled`).
- **Globais**: podem ser usados em qualquer tag (`id`, `class`, `data-*`, `style`).

---

## 📝 Elementos de Conteúdo

- **Títulos**: `<h1>` até `<h6>` (hierarquia importa).
- **Parágrafos**: `<p>`.
- **Formatação**: `<strong>`, `<em>`, `<b>`, `<i>`, `<u>`, `<mark>`, `<sup>`, `<sub>`.
- **Listas**: `<ul>` (não ordenada), `<ol>` (ordenada), `<li>` (item).
- **Código**: `<code>` (inline), `<pre>` (bloco).
- **Links**: `<a href="...">`.
- **Imagens**: `<img src="..." alt="..." />`.

---

## 🖼 Estrutura de Página

Um documento HTML básico tem:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Título</title>
  </head>
  <body>
    Conteúdo
  </body>
</html>
```

Tags comuns para layout:

- `<header>` – Cabeçalho
- `<nav>` – Navegação
- `<main>` – Conteúdo principal
- `<aside>` – Barra lateral
- `<footer>` – Rodapé
- `<section>` – Agrupamento de conteúdo
- `<article>` – Conteúdo independente
- `<div>` e `<span>` – Contêineres genéricos

---

## 📂 Caminhos de Arquivos

- **Absoluto**: caminho completo
  `https://site.com/imagem.png`
- **Relativo (mesma pasta)**:
  `imagem.png` ou `./imagem.png`
- **Relativo (subindo pasta)**:
  `../imagens/foto.jpg`

## 📌 Resumo Rápido

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <title>Revisão de HTML</title>
  </head>
  <body>
    <!-- Cabeçalho da página -->
    <header>
      <h1>Título Principal da Página</h1>
      <nav>
        <!-- Navegação com links -->
        <a href="#secao1">Seção 1</a> |
        <a href="#secao2">Seção 2</a> |
        <a href="#secao3">Seção 2</a>
      </nav>
    </header>

    <!-- Conteúdo principal da página -->
    <main>
      <!-- Primeira seção -->
      <section id="secao1">
        <h2>Subtítulo da Seção 1</h2>
        <p>
          Este é um parágrafo com <strong>negrito</strong> e <em>itálico</em>.
        </p>
        <p>
          Outro parágrafo com <b>negrito visual</b> e <i>itálico visual</i>.
        </p>

        <!-- Lista não ordenada -->
        <ul>
          <li>Item 1</li>
          <li>Item 2</li>
        </ul>

        <!-- Lista ordenada -->
        <ol>
          <li>Passo 1</li>
          <li>Passo 2</li>
        </ol>

        <!-- Código inline e pré-formatado -->
        <p>Exemplo de código inline: <code>&lt;p&gt;Olá&lt;/p&gt;</code></p>
        <pre>
					function soma(a, b) {
					  return a + b;
					}
        </pre>

        <!-- Link -->
        <p>
          <a
            href="https://www.google.com"
            target="_blank"
            rel="noopener noreferrer"
            >Ir para o Google</a
          >
        </p>
      </section>

      <!-- Segunda seção com conteúdo relacionado -->
      <section id="secao2">
        <h2>Subtítulo da Seção 2</h2>
        <p>
          Este parágrafo contém um <u>texto sublinhado</u> e
          <mark>marcado</mark>.
        </p>
        <p>
          Exemplo de sobrescrito: H<sub>2</sub>O e sobrescrito: 2<sup>3</sup>
        </p>

        <!-- Conteúdo dentro de div e span -->
        <div>
          <p>
            Este é um parágrafo dentro de uma div, com
            <span>texto destacado em span</span>.
          </p>
        </div>
      </section>

      <!-- Terceira seção com imagens -->
      <section id="secao3">
        <h2>Subtítulo da Seção de Imagens</h2>

        <!-- Imagem com caminho absoluto na web -->
        <img
          src="https://placehold.co/600x400/000000/FFFFFF/png?text=Minha+Imagem"
          alt="Uma imagem de exemplo em preto e branco com o texto 'Minha Imagem'."
          width="600"
          height="400"
        />

        <!-- Imagem com caminho absoluto no Windows -->
        <img src="C:\Users\SeuNome\Documentos\Projetos\imagens\logo.png" />

        <!-- Imagem com caminho absoluto no Linux/macOS -->
        <img src="/home/seunome/projetos/imagens/logo.png" />

        <!-- Imagem com caminho relativo à mesma pasta -->
        <img src="./imagem.jpg" alt="Imagem de exemplo - mesma pasta" />

        <!-- Imagem com caminho relativo em pastas diferentes -->
        <img
          src="../imagens/foto.jpg"
          alt="Imagem de exemplo - subindo um nível"
        />

        <!-- Imagem com caminho relativo -->
        <img
          src="\imagem.png"
          alt="Imagem de exemplo - caminho relativo"
          width="600"
          height="400"
        />
      </section>

      <!-- Barra lateral (aside) -->
      <aside>
        <p>Conteúdo adicional, notas ou links relacionados.</p>
      </aside>
    </main>

    <!-- Rodapé da página -->
    <footer>
      <p>© 2025 Minha Página de Revisão de HTML</p>
    </footer>
  </body>
</html>
```
