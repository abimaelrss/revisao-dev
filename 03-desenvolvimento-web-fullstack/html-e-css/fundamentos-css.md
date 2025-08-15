# 🧱 Fundamentos de CSS

Este documento cobre os conceitos fundamentais do CSS, a linguagem de estilo que dá vida e aparência às páginas web.

## 🚀 Conhecendo o CSS

### O que é CSS?

**CSS (Cascading Style Sheets)** é a linguagem de folhas de estilo que atua em conjunto com o HTML para a criação de sites. Enquanto o HTML define a **estrutura** e o **conteúdo** da página (o esqueleto), o CSS é responsável por toda a parte de **estilo** e **apresentação** (a pele e a roupa). Com ele, você controla cores, tipografia, espaçamento, animações e a organização dos elementos na tela. Sem o CSS, os sites seriam apenas documentos de texto sem formatação.

### Comentários

Comentários são trechos de código que não são processados pelo navegador. Eles são usados para deixar anotações, explicar a lógica de um estilo, ou para desativar temporariamente um bloco de código durante o desenvolvimento e depuração. A sintaxe é a mesma para comentários de uma ou várias linhas.

**Sintaxe:**

```css
/* Este é um comentário de uma linha. */

/*
  Este é um comentário
  de múltiplas linhas,
  que pode ser muito útil para
  documentar blocos de código.
*/
```

### Anatomia

Uma regra CSS é a unidade básica de estilo. Ela é composta por um **seletor**, que aponta para o(s) elemento(s) HTML que você quer estilizar, seguido por um bloco de declaração entre chaves `{}`. Dentro desse bloco, estão as **propriedades** e os **valores**, que formam a declaração.

```css
/* Seletor */
h1 {
  /* Propriedade: valor; */
  color: blue;
  font-size: 24px;
  text-align: center;
}
```

- `h1`: O **seletor**.
- `color`, `font-size`, `text-align`: As **propriedades** que você está modificando.
- `blue`, `24px`, `center`: Os **valores** atribuídos a essas propriedades.

### Cascading (A Cascata)

O termo "Cascading" (Cascata) no CSS refere-se ao processo de resolução de conflitos quando um mesmo elemento HTML recebe estilos de múltiplas regras. O navegador segue uma hierarquia para decidir qual estilo aplicar, considerando três fatores principais:

1. **Origem do Estilo:**
   - **Estilos do Agente do Usuário:** Estilos padrão do navegador (ex: `<a>` é azul e sublinhado).
   - **Estilos do Autor:** Os estilos que você, o desenvolvedor, escreve.
   - **Estilos do Usuário:** Estilos personalizados que o usuário pode ter configurado no seu navegador (por exemplo, para acessibilidade).
   - Os estilos do autor geralmente têm prioridade sobre os do agente do usuário.
2. **Especificidade:** A pontuação que uma regra CSS possui. Uma regra mais específica tem prioridade.
3. **Ordem de Declaração:** Se a especificidade for a mesma, a última regra declarada é a que "vence".

### Especificidade

A especificidade é o peso de um seletor. Quanto mais específico o seletor, maior a sua prioridade. A pontuação é calculada da seguinte forma:

- **1000 pontos:** Estilos **inline** (`<p style="color: red;">`). Estes têm a maior prioridade.
- **100 pontos:** Seletor de **ID** (`#meu-id`). Use-o com moderação, pois é muito específico.
- **10 pontos:** Seletor de **Classe** (`.minha-classe`), **Atributo** (`[type="text"]`) ou **Pseudo-classe** (`:hover`).
- **1 ponto:** Seletor de **Elemento/Tag** (`h1`, `p`), ou **Pseudo-elemento** (`::before`).

  **Exemplo de Especificidade:**

  ```css
  /* Especificidade: 100 pontos */
  #meu-elemento {
    color: blue;
  }

  /* Especificidade: 10 pontos */
  .minha-classe {
    color: red;
  }

  /* Especificidade: 1 ponto */
  div {
    color: green;
  }
  ```

Se o HTML for `<div id="meu-elemento" class="minha-classe">Conteúdo</div>`, a cor aplicada será **azul**, pois o seletor de ID tem a maior especificidade.

### O Poder do `!important`

A palavra-chave `!important` sobrepõe a cascata e a especificidade. A declaração com `!important` sempre terá prioridade, exceto se outra declaração com `!important` e maior especificidade estiver presente. **Evite o uso de `!important` ao máximo**, pois ele dificulta a manutenção e a depuração do código.

```css
p {
  color: red !important; /* Irá sobrescrever qualquer outra regra */
}
```

### Valores e Unidades de Medida

Existem diversas unidades de medida. É importante saber quando usar cada uma para criar layouts flexíveis e responsivos.

- **Unidades Absolutas:**
  - `px` (pixels): Tamanho fixo, não muda.
  - `cm` (centímetro): Equivale a 1/10 de 1mm ou 96px/2.54.
  - `in` (polegada): Equivale a 2.54cm.
  ```css
  .caixa {
    width: 300px; /* Largura fixa em pixels */
    height: 15cm; /* Altura fixa em centímetros */
  }
  ```
- **Unidades Relativas:**

  - `em`: Relativo ao tamanho da fonte do **elemento pai**.
  - `rem`: Relativo ao tamanho da fonte do **elemento raiz** (`<html>`). É ideal para acessibilidade, pois permite que o usuário altere o tamanho da fonte no navegador e o site se ajuste.
  - `%`: Relativo ao tamanho do elemento pai.
  - `vw` (viewport width): 1% da largura da tela.
  - `vh` (viewport height): 1% da altura da tela.

  ```css
  body {
    font-size: 16px; /* Definindo o tamanho da fonte raiz */
  }

  h1 {
    font-size: 2rem; /* 2 vezes o tamanho da fonte raiz (32px) */
  }

  .texto-pequeno {
    font-size: 0.8em; /* 80% do font-size do elemento pai */
  }

  .container-principal {
    width: 80%; /* Ocupa 80% da largura do elemento pai */
  }

  .header {
    height: 10vh; /* Altura que é 10% da altura visível do navegador */
  }
  ```

### Seletores

Os seletores CSS são usados para selecionar e estilizar elementos HTML específicos em uma página web. Os tipos mais comuns incluem seletores de tipo (como `p {}`), classe (como `.exemplo {}`), ID (como `#unico {}`), universal (`* {}`), de atributo (como `[type="text"] {}`), e relacionais/descendência (como `div p {}`para parágrafos dentro de divs).

**Seletores Básicos**

- **Seletor de Tipo (ou Elemento):** Seleciona todos os elementos de um tipo específico.
  - **Exemplo HTML**: `<h1>Um título</h1>`
  - **Exemplo CSS**: `h1 { color: green;` `}` (Colore todos os cabeçalhos `<h1>` de verde).
- **Seletor de Classe:** Aplica estilos a elementos que possuem uma classe específica, identificada por um ponto (`.`).
  - **Exemplo HTML**: `<p class="destaque">Este texto é em destaque.</p>`
  - **Exemplo CSS**: `.destaque { font-weight: bold;` `}` (Torna em negrito o texto do parágrafo que tem a classe "destaque").
- **Seletor de ID:** Seleciona um único elemento que possui um ID específico, identificado por um hash (`#`).
  - **Exemplo HTML**: `<div id="cabecalho">Bem-vindo!</div>`
  - **Exemplo CSS**: `#cabecalho { background-color: blue;` `}` (Define a cor de fundo da div com ID "cabecalho").
- **Seletor Universal:** Seleciona todos os elementos da página.
  - **Exemplo CSS**: `* { margin: 0;` `padding: 0;` `}` (Remove a margem e o preenchimento de todos os elementos).
- **Seletor de Atributo:** Seleciona elementos com base em seus atributos e seus valores.
  - **Exemplo CSS**: `a[target="_blank"] { color: red;` `}` (Colore de vermelho todos os links que abrem em uma nova aba (`target="_blank"`)).

**Seletores Combinados e Relacionais**

- **Descendente (espaço):** Seleciona elementos que estão dentro de outro elemento, não importa o quão aninhado esteja.
  - **Exemplo CSS**: `div p { font-style: italic;` `}` (Aplica itálico a todos os parágrafos dentro de uma div).
- **Filho Direto (`>`):** Seleciona apenas os elementos que são filhos diretos de outro elemento.
  - **Exemplo CSS**: `ul > li { color: blue;` `}` (Colore apenas os itens (`<li>`) que são filhos diretos de uma lista não ordenada (`<ul>`)).
- **Irmão Adjacente (`+`):** Seleciona o primeiro elemento que é imediatamente precedido por outro.
  - **Exemplo CSS**: `h1 + p { margin-top: 0;` `}` (Remove a margem superior do primeiro parágrafo que aparece imediatamente após um cabeçalho `<h1>`).
- **Agrupamento (vírgula `,`):** Permite aplicar o mesmo estilo a múltiplos seletores.
  - **Exemplo CSS**: `h1, h2, h3 { color: navy;` `}` (Define a cor azul marinho para todos os cabeçalhos h1, h2 e h3).

### Combinators

Combinadores são a forma de combinar seletores para criar regras mais sofisticadas e específicas.

- **Seletor Descendente (espaço):** `ul li { ... }` (seleciona todos os `<li>` que estão **dentro** de um `<ul>`).
- **Seletor em Lista (**`,`**):** `h1, h2, p { ... }` (seleciona vários seletores diferesntes e aplica a mesma rera. Isso evita a repetição de código.
- **Seletor Filho Direto (`>`):** `ul > li { ... }` (seleciona todos os `<li>` que são **filhos diretos** de um `<ul>`).
- **Seletor Irmão Adjacente (`+`):** `h1 + p { ... }` (seleciona o `<p>` que vem **imediatamente após** um `<h1>` e está no mesmo nível).
- **Seletor Irmão Geral (`~`):** `h1 ~ p { ... }` (seleciona **todos** os `<p>` que vêm após um `<h1>` e estão no mesmo nível).

### Adicionando CSS no HTML

A melhor prática é sempre usar um arquivo CSS externo.

1. **CSS Externo (melhor prática):** Linka um arquivo `.css` separado no `<head>` do HTML.

   ```html
   <head>
     <link rel="stylesheet" href="caminho/para/meu-estilo.css" />
   </head>
   ```

2. **CSS Interno:** Usado dentro da tag `<style>` no `<head>`. Útil para estilos que só se aplicam àquela página específica.

   ```html
   <head>
     <style>
       body {
         background-color: lightblue;
       }
     </style>
   </head>
   ```

3. **CSS Inline:** Adicionado diretamente na tag HTML com o atributo `style`. Use apenas em casos muito específicos, como para overrides em componentes ou para testes rápidos.

   ```html
   <p style="color: red;"></p>
   ```

## 📦 Box Model

### Box Model

O Box Model é um dos conceitos mais importantes do CSS. Ele define que todo elemento HTML é uma **caixa retangular**. Essa caixa é composta por quatro partes, de dentro para fora:

1. **Content (Conteúdo):** A área onde o texto, imagens e outros elementos são exibidos. O `width` e `height` definem esta área.
2. **Padding (Preenchimento):** O espaço entre o conteúdo e a borda. Ele empurra a borda para fora do conteúdo.
3. **Border (Borda):** A linha que envolve o preenchimento e o conteúdo.
4. **Margin (Margem):** O espaço **fora** da borda. Ele cria o espaço entre um elemento e outro.

### Display Block e Display Inline

- `display: block`: O elemento ocupa 100% da largura disponível, quebra a linha e permite que você defina `width`, `height`, `margin` e `padding`. Exemplos: `<h1>`, `<p>`, `<div>`.
- `display: inline`: O elemento ocupa apenas o espaço necessário para seu conteúdo e não quebra a linha. Ele ignora `width` e `height`, e só aceita `margin` horizontal (`margin-left` e `margin-right`). Exemplos: `<a>`, `<span>`, `<strong>`.
- `display: inline-block`: O melhor dos dois mundos. O elemento não quebra a linha como um `inline`, mas permite que você defina `width`, `height` e todas as margens e paddings como um `block`.

### Border

A borda pode ser customizada em vários aspectos.

- `border-width`: Espessura da borda.
- `border-style`: Estilo da borda (`solid`, `dashed`, `dotted`, `double`, etc.).
- `border-color`: Cor da borda.
- `border-radius`: Arredonda os cantos da borda.
- `border`: A forma **shorthand** de definir a borda.

```css
.card {
  border: 2px solid #ccc;
  border-radius: 8px; /* Arredonda os cantos */
}
```

### Width e Height

Definem a largura e a altura da área de conteúdo da caixa.

### Margin

A `margin` é o espaço **externo** da caixa. Ela cria distância entre o elemento atual e os outros elementos.

```css
.exemplo {
  margin: 20px; /* 20px em todos os lados */
  margin: 10px 20px; /* 10px em cima e embaixo, 20px nas laterais */
  margin: 5px 10px 15px 20px; /* cima, direita, baixo, esquerda */
}
```

**Colapso de Margens:** Margens verticais de elementos vizinhos podem se colapsar, ou seja, a maior margem entre os dois elementos é a que prevalece.

### Padding

O `padding` é o espaço **interno** da caixa, entre o conteúdo e a borda. Ele é usado para dar "respiro" ao conteúdo.

```css
.exemplo {
  padding: 15px; /* 15px em todos os lados */
  padding: 10px 0; /* 10px em cima e embaixo, 0 nas laterais */
}
```

### Box Sizing

Por padrão, `width` e `height` definem apenas o tamanho da área de conteúdo. O `padding` e a `border` são adicionados a este valor, o que pode causar layouts inesperados. `box-sizing: border-box` resolve este problema: o `width` e `height` passam a incluir o `padding` e a `border`.

**Recomendação:** Aplique `box-sizing: border-box` a todos os elementos para facilitar a construção de layouts.

```css
* {
  box-sizing: border-box;
}
```

## ✒️ Fontes e Textos

### Fundamentos

Essas propriedades controlam a tipografia e o estilo do texto, garantindo legibilidade e coesão visual.

### Font Family

Define a família da fonte. É crucial fornecer uma lista de fontes de fallback, terminando com uma família genérica (`serif`, `sans-serif`, `monospace`), caso a fonte principal não esteja disponível no dispositivo do usuário.

```css
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
```

### Font Size

Define o tamanho da fonte.

- `px`: Ideal para elementos que não precisam de escalabilidade.
- `rem`: Recomendado para a maioria dos textos, pois permite que o usuário aumente ou diminua o tamanho da fonte base do navegador, melhorando a acessibilidade.
- `%`: Funciona de forma similar ao `em`, mas é relativo ao tamanho da fonte do pai.

### Font Style, Font Weight

- `font-style: italic;` ou `oblique;`: Aplica estilo de itálico ao texto.
- `font-weight: bold;` ou `400`, `700`: Define a espessura da fonte. Os valores numéricos de 100 a 900 dão mais granularidade (o valor padrão é 400, negrito é 700).

### Color, Text-Transform, Text-Decoration

- `color: #333;`: Define a cor do texto.
- `text-transform: uppercase;`: Transforma o texto para maiúsculas. Outros valores: `lowercase`, `capitalize`.
- `text-decoration: underline;`: Aplica um sublinhado. Outros valores: `line-through`, `none`.

### Text Align, Line Height

- `text-align`: Alinha o texto na horizontal (`left`, `center`, `right`, `justify`).
- `line-height`: Define o espaçamento vertical entre as linhas do texto. Um valor numérico (`1.5`) é a melhor prática, pois é um multiplicador do tamanho da fonte atual, garantindo que o espaçamento seja consistente em diferentes tamanhos de fonte.

### Letter Spacing, Word Spacing

- `letter-spacing`: Define o espaço entre as letras. Pode ser útil para títulos.
- `word-spacing`: Define o espaço entre as palavras.

### Shorthand Font

A propriedade `font` é um atalho que define várias propriedades de fonte de uma vez. A ordem é crucial.

```css
p {
  /* font: font-style font-variant font-weight font-size/line-height font-family */
  font: italic bold 16px/1.5 "Arial", sans-serif;
}
```

### Web Fonts

Fontes que são carregadas de um servidor externo (como Google Fonts) e não precisam estar instaladas no computador do usuário.

```css
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");

body {
  font-family: "Roboto", sans-serif;
}
```

## 🎨 Cores e Fundos

### Cores e Fundos

Propriedades essenciais para estilizar o plano de fundo e a cor de elementos.

### Cores: Nomes, Hex, RGB, HSL

Além do nome da cor (`red`) e do formato hexadecimal (`#ff0000`), existem outros formatos mais flexíveis:

- `rgb(vermelho, verde, azul)`: Valores de 0 a 255.
- `rgba(vermelho, verde, azul, alfa)`: Adiciona um canal **alfa** para **transparência** (0.0 a 1.0).
- `hsl(hue, saturação, luminosidade)`: Um modelo de cores baseado em matiz (0-360), saturação e luminosidade (0-100%).
- `hsla(hue, saturação, luminosidade, alfa)`: Adiciona o canal alfa ao HSL.

### Background Color, Background Image, Background Repeat

- `background-color`: Define a cor de fundo.
- `background-image`: Define uma imagem de fundo. Use `url('caminho/para/imagem.jpg')`.
- `background-repeat`: Controla a repetição da imagem.
  - `no-repeat`: Não repete.
  - `repeat-x`: Repete apenas na horizontal.
  - `repeat-y`: Repete apenas na vertical.

### Background-Position, Background-Size

- `background-position`: Posiciona a imagem de fundo. Pode usar palavras-chave (`center`, `top right`) ou valores em pixels/porcentagem (`50% 50%`).
- `background-size`: Controla o tamanho da imagem de fundo.
  - `cover`: Redimensiona a imagem para cobrir toda a área, cortando o que for necessário.
  - `contain`: Redimensiona a imagem para caber na área, mantendo a proporção.

### Background Shorthand

É o atalho para definir todas as propriedades de fundo em uma única declaração. A ordem não é rígida, mas uma convenção comum é: `background: color image repeat attachment position / size;`

```css
.header {
  background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
    url("caminho/para/imagem.jpg") no-repeat fixed center/cover;
}
```

Neste exemplo, estamos usando um gradiente semi-transparente por cima de uma imagem de fundo.
