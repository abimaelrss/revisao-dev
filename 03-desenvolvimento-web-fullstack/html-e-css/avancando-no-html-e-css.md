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

# 🎯 CSS Flexbox

O **Flexbox** é um modelo de layout no CSS que facilita alinhar, distribuir e organizar elementos dentro de um container.

Ele resolve problemas comuns de centralização e espaçamento sem precisar de floats ou hacks antigos.

---

## 🧩 Conceitos básicos

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

## 🧩 `justify-content`

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

## 🧩 `align-items`

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

## 🧩 `gap` e `margin`

- `gap` → cria espaço entre itens
- `margin` → espaço fora de cada item

```css
.container {
  display: flex;
  gap: 20px;
}
```

---

## 🧩 Multi-line (`flex-wrap`)

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

## 🧩 `flex-basis`

Define o tamanho **base** de um item.

```css
.item {
  flex-basis: 200px;
}
```

---

## 🧩 `flex-grow` e `flex-shrink`

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

## 🧩 Shorthand `flex`

Atalho para `flex-grow flex-shrink flex-basis`.

```css
.item {
  flex: 1 0 150px; /* grow | shrink | basis */
}
```

---

## 🧩 `order`

Define a ordem de exibição dos itens.

```css
.item {
  order: 2;
}
```

---

## 🧩 `flex-flow`

Atalho para `flex-direction` + `flex-wrap`.

```css
.container {
  display: flex;
  flex-flow: row wrap;
}
```

---

## 🧩 `align-content` (para várias linhas)

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

# 🎯 CSS Grid

## 🧩 Explicando o CSS Grid

- Sistema de layout em **duas dimensões** (linhas e colunas).
- Dá controle total sobre alinhamento, espaçamento e posicionamento.
- É como desenhar uma tabela flexível, mas muito mais poderosa.

## 🧩 Fundamentos do Grid no código

```css
.container {
  display: grid; /* ativa o grid */
  grid-template-columns: 200px 1fr 200px; /* 3 colunas */
  grid-template-rows: auto auto; /* 2 linhas automáticas */
}
```

---

## 🧩 Grid Template Columns / Rows

Define quantas colunas e linhas o grid terá e seus tamanhos.

```css
grid-template-columns: 1fr 2fr 1fr;
grid-template-rows: 100px auto 50px;
```

---

## 🧩 Grid Column / Grid Row

Permite um item ocupar várias colunas ou linhas.

```css
.item1 {
  grid-column: 1 / 3; /* ocupa da coluna 1 até antes da 3 */
  grid-row: 1 / 2; /* ocupa só a primeira linha */
}
```

---

## 🧩 Grid Template Areas

Nomeia áreas do layout para simplificar.

```css
.container {
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
}

.header {
  grid-area: header;
}
.sidebar {
  grid-area: sidebar;
}
.main {
  grid-area: main;
}
.footer {
  grid-area: footer;
}
```

---

## 🧩 Gap

Controla o espaço entre linhas e colunas.

```css
grid-gap: 20px; /* ou column-gap / row-gap */
```

---

## 🧩 Shorthand Grid Template

Agrupa linhas e colunas numa só propriedade.

```css
grid: auto-flow 100px / 1fr 1fr 1fr;
```

---

## 🧩 Introdução aos alinhamentos

- **justify-content** → alinha no eixo horizontal.
- **align-content** → alinha no eixo vertical.
- **justify-items** → alinha os itens dentro das células no eixo horizontal.
- **align-items** → alinha os itens dentro das células no eixo vertical.
- **align-self / justify-self** → alinhamento individual por item.

---

## 🧩 Propriedades grid-auto

Definem comportamento de linhas/colunas criadas automaticamente.

```css
grid-auto-rows: 100px;
grid-auto-columns: minmax(100px, auto);
grid-auto-flow: column; /* muda a direção padrão */
```

---

## 🧩 Grid ou Flex?

- Use **Flexbox** → quando o layout é em **uma dimensão só** (linha **ou** coluna).
- Use **Grid** → quando precisa de **duas dimensões** (linha **e** coluna juntas).

---

# 📝 Formulários em HTML

Formulários permitem que o usuário **envie dados** ou **interaja** com a aplicação.

Eles são a principal forma de coletar informações em páginas web.

---

## 📌 Estrutura básica

```html
<form action="/enviar" method="POST">
  <!-- campos do formulário -->
</form>
```

- **action** → URL de destino dos dados.
- **method** → define como os dados são enviados:
  - `GET` → anexa na URL (útil para buscas).
  - `POST` → envia no corpo da requisição (mais seguro).

---

## 🔘 Button

O elemento `button` é usado para disparar ações.

### Tipos principais

- `type="submit"` → envia o formulário.
- `type="reset"` → limpa os campos.
- `type="button"` → apenas um botão comum.

### Outros atributos

- `autofocus` → foca no botão ao carregar a página.
- `disabled` → desabilita o botão.
- `name` e `value` → identificam e enviam valores.

```html
<button type="submit">Enviar</button> <button type="reset">Limpar</button>
```

---

## ✏️ Input

Elemento mais usado em formulários.

### Atributos fundamentais

- `name` → nome do campo (essencial para envio).
- `type` → tipo de input (`text`, `email`, `number`...).

### Atributos gerais

- `value`, `autocomplete`, `size`, `autofocus`,
- `disabled`, `readonly`, `form`, `required`, `placeholder`.

---

### 🔤 Input Text

```html
<input type="text" name="nome" placeholder="Seu nome" required />
```

---

### 🔢 Input Number

- `min` → valor mínimo.
- `max` → valor máximo.
- `step` → intervalo.

```html
<input type="number" name="idade" min="0" max="120" step="1" />
```

---

### 📧 Input Email

- `multiple` → permite vários e-mails.
- `minlength`, `maxlength` → restringem tamanho.
- `pattern` → validação com regex.

```html
<input type="email" name="email" multiple required />
```

---

### 🔑 Input Password

- `minlength`, `maxlength`, `pattern`
- `title` → dica para o padrão.
- `inputmode` → define teclado no mobile.

```html
<input
  type="password"
  name="senha"
  minlength="6"
  required
  pattern="[A-Za-z0-9]{6,}"
  title="Use apenas letras e números"
/>
```

---

### 📂 Input File

- `enctype="multipart/form-data"` deve ser usado no `form`.
- `multiple` → vários arquivos.
- `accept` → restringe tipos (`.jpg,.png,.pdf`).

```html
<form enctype="multipart/form-data">
  <input type="file" name="curriculo" accept=".pdf" required />
</form>
```

---

### 🎚️ Input Range

```html
<input type="range" name="volume" min="0" max="100" step="10" />
```

---

### 🎨 Input Color

```html
<input type="color" name="cor" value="#ff0000" />
```

---

### ☑️ Checkbox

- Pode ter múltiplos valores.

```html
<input type="checkbox" name="linguagens" value="html" checked /> HTML
<input type="checkbox" name="linguagens" value="css" /> CSS
```

---

### 🔘 Radio

- Permite apenas uma opção por grupo (`name` igual).

```html
<input type="radio" name="genero" value="M" /> Masculino
<input type="radio" name="genero" value="F" /> Feminino
```

---

### 👻 Hidden

- Campo oculto usado para enviar informações extras.

```html
<input type="hidden" name="idUsuario" value="123" />
```

---

## 🏷️ Label

Associa texto descritivo a um campo → melhora acessibilidade.

```html
<label for="email">E-mail:</label>
<input type="email" id="email" name="email" />
```

---

## 📝 Textarea

Atributos: `rows`, `cols`, `maxlength`, `wrap`, `placeholder`.

```html
<textarea name="mensagem" rows="5" cols="30" required></textarea>
```

---

## 🔽 Select

- `multiple` → várias seleções.
- `size` → quantos itens aparecem.
- `optgroup` → agrupa opções.

```html
<select name="pais">
  <option value="br">Brasil</option>
  <option value="us">EUA</option>
</select>
```

---

## 📦 Fieldset

Usado para agrupar campos de forma semântica.

```html
<fieldset>
  <legend>Dados Pessoais</legend>
  <input type="text" name="nome" />
  <input type="number" name="idade" />
</fieldset>
```

---

## 🆕 Novos Inputs (HTML5)

- `date`, `time`, `datetime-local`
- `url`, `tel`, `search`
- `month`, `week`

📖 Sempre conferir compatibilidade em [caniuse.com](https://caniuse.com/).

---

## ✅ Próximos passos

- Estudo constante → documentação oficial MDN.
- Validação → aprender `required`, `pattern` e depois validação em **JavaScript**.
- Acessibilidade → sempre usar `label` e textos descritivos.

---

## 📝 Exemplo de Formulário Completo

```html
<form action="/cadastro" method="POST" enctype="multipart/form-data">
  <fieldset>
    <legend>Dados Pessoais</legend>

    <label for="nome">Nome completo:</label>
    <input
      type="text"
      id="nome"
      name="nome"
      placeholder="Seu nome"
      required
      minlength="3"
      maxlength="80"
    />
    <br /><br />

    <label for="idade">Idade:</label>
    <input
      type="number"
      id="idade"
      name="idade"
      min="0"
      max="120"
      step="1"
      required
    />
    <br /><br />

    <label for="email">E-mail:</label>
    <input
      type="email"
      id="email"
      name="email"
      placeholder="exemplo@email.com"
      required
      multiple
    />
    <br /><br />

    <label for="senha">Senha:</label>
    <input
      type="password"
      id="senha"
      name="senha"
      required
      minlength="6"
      maxlength="20"
      pattern="[A-Za-z0-9]{6,}"
      title="A senha deve ter entre 6 e 20 caracteres, apenas letras e números"
    />
    <br /><br />

    <label for="telefone">Telefone:</label>
    <input
      type="tel"
      id="telefone"
      name="telefone"
      placeholder="(00) 00000-0000"
      pattern="\(\d{2}\)\s\d{5}-\d{4}"
      title="Formato esperado: (00) 00000-0000"
    />
    <br /><br />

    <label for="site">Site pessoal:</label>
    <input type="url" id="site" name="site" placeholder="https://meusite.com" />
  </fieldset>

  <fieldset>
    <legend>Preferências</legend>

    <p>Gênero:</p>
    <input type="radio" id="masc" name="genero" value="M" checked />
    <label for="masc">Masculino</label>

    <input type="radio" id="fem" name="genero" value="F" />
    <label for="fem">Feminino</label>

    <input type="radio" id="outro" name="genero" value="O" />
    <label for="outro">Outro</label>
    <br /><br />

    <label>Áreas de interesse:</label><br />
    <input type="checkbox" id="html" name="interesses" value="html" checked />
    <label for="html">HTML</label>

    <input type="checkbox" id="css" name="interesses" value="css" />
    <label for="css">CSS</label>

    <input type="checkbox" id="js" name="interesses" value="js" />
    <label for="js">JavaScript</label>
    <br /><br />

    <label for="pais">País:</label>
    <select id="pais" name="pais" required>
      <option value="">Selecione...</option>
      <optgroup label="América">
        <option value="br" selected>Brasil</option>
        <option value="us">EUA</option>
      </optgroup>
      <optgroup label="Europa">
        <option value="pt">Portugal</option>
        <option value="es">Espanha</option>
      </optgroup>
    </select>
  </fieldset>

  <fieldset>
    <legend>Envios e Extras</legend>

    <label for="foto">Foto de perfil:</label>
    <input type="file" id="foto" name="foto" accept=".jpg,.png" required />
    <br /><br />

    <label for="cor">Cor favorita:</label>
    <input type="color" id="cor" name="cor" value="#ff0000" />
    <br /><br />

    <label for="satisfacao">Nível de satisfação:</label>
    <input
      type="range"
      id="satisfacao"
      name="satisfacao"
      min="0"
      max="10"
      step="1"
      value="5"
    />
    <br /><br />

    <label for="bio">Sobre você:</label><br />
    <textarea
      id="bio"
      name="bio"
      rows="4"
      cols="40"
      placeholder="Escreva algo sobre você..."
      maxlength="300"
    ></textarea>

    <input type="hidden" name="idCadastro" value="12345" />
  </fieldset>

  <br />
  <button type="submit">Enviar</button>
  <button type="reset">Limpar</button>
</form>
```

---
