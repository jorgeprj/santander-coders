## CSS

### O que é CSS?

CSS (Cascading Style Sheets) é uma linguagem de estilo utilizada para descrever a apresentação de um documento escrito em HTML ou XML. CSS define como os elementos HTML devem ser exibidos na tela, papel, ou em outras mídias.

### Como usar o CSS?

#### Inline

CSS inline é utilizado diretamente dentro do atributo `style` de um elemento HTML. 

```html
<p style="color: red;">Este texto é vermelho.</p>
```

#### Tag Style

CSS dentro da tag `<style>` é colocado na seção `<head>` do documento HTML.

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        p {
            color: blue;
        }
    </style>
</head>
<body>
    <p>Este texto é azul.</p>
</body>
</html>
```

#### Arquivo Externo

CSS em um arquivo externo é referenciado através da tag `<link>` no documento HTML.

```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
    <p>Este texto será estilizado pelo arquivo externo.</p>
</body>
</html>
```

### Sintaxe do CSS

#### Seletores

- **Tag**: Seleciona todos os elementos de uma determinada tag.

```css
p {
    color: green;
}
```

- **Classe**: Seleciona todos os elementos que possuem uma determinada classe.

```css
.highlight {
    background-color: yellow;
}
```

- **Id**: Seleciona o elemento que possui um determinado id.

```css
#main {
    font-size: 20px;
}
```

- **Mais**: Existem outros seletores como os seletores de atributo, pseudo-classes, pseudo-elementos, entre outros.

### Cores, Background e Textos

- **Cores**: Utilizadas para definir a cor do texto, bordas, e background dos elementos.

```css
p {
    color: red;
    background-color: yellow;
}
```

- **Background**: Propriedades relacionadas ao plano de fundo de elementos.

```css
div {
    background-image: url('background.jpg');
    background-size: cover;
}
```

- **Textos**: Propriedades para estilização de textos.

```css
h1 {
    text-align: center;
    text-transform: uppercase;
}
```

### Fontes, Medidas e Links

- **Fontes**: Definem a aparência do texto.

```css
body {
    font-family: Arial, sans-serif;
    font-size: 16px;
}
```

- **Medidas**: Unidades de medida como pixels, em, rem, porcentagem, entre outras.

```css
div {
    width: 100px;
    height: 200px;
}
```

- **Links**: Estilizam os estados dos links (visitado, não visitado, ao passar o mouse, ao clicar).

```css
a:link {
    color: blue;
}
a:visited {
    color: purple;
}
a:hover {
    color: red;
}
a:active {
    color: green;
}
```

### Listas, Tabelas, Box Model e Display

- **Listas**: Estilização de listas ordenadas e não ordenadas.

```css
ul {
    list-style-type: square;
}
```

- **Tabelas**: Estilização de tabelas, suas células e cabeçalhos.

```css
table {
    border-collapse: collapse;
}
td, th {
    border: 1px solid black;
    padding: 8px;
}
```

- **Box Model**: Modelo de caixa que envolve elementos, incluindo margens, bordas, preenchimento e conteúdo.

```css
div {
    margin: 10px;
    padding: 20px;
    border: 2px solid black;
}
```

- **Display**: Define como os elementos são exibidos no documento.

```css
.block-element {
    display: block;
}
.inline-element {
    display: inline;
}
```

### Position e introdução a Flexbox

#### Position

- **static**: Valor padrão, os elementos são posicionados de acordo com o fluxo normal do documento.

```css
div {
    position: static;
}
```

- **relative**: Posiciona o elemento em relação à sua posição normal.

```css
div {
    position: relative;
    top: 10px;
    left: 20px;
}
```

- **absolute**: Posiciona o elemento em relação ao seu elemento pai mais próximo com posição relativa, absoluta ou fixa.

```css
div {
    position: absolute;
    top: 50px;
    left: 100px;
}
```

- **fixed**: Posiciona o elemento em relação à janela do navegador.

```css
div {
    position: fixed;
    bottom: 0;
    right: 0;
}
```

- **sticky**: O elemento é tratado como relativo até que seu container pai seja rolado até um ponto, onde ele se comporta como fixo.

```css
div {
    position: sticky;
    top: 0;
}
```

### Flexbox e Alinhamentos

Flexbox é um layout model que fornece uma maneira eficiente de distribuir espaço e alinhar itens em um container, mesmo quando seu tamanho é desconhecido.

#### Justify-content

A propriedade `justify-content` alinha os itens flexíveis ao longo do eixo principal.

- **flex-start**: Alinha os itens ao início do container.

```css
.container {
    justify-content: flex-start;
}
```

- **flex-end**: Alinha os itens ao final do container.

```css
.container {
    justify-content: flex-end;
}
```

- **center**: Centraliza os itens no container.

```css
.container {
    justify-content: center;
}
```

- **space-between**: Distribui os itens com espaço igual entre eles.

```css
.container {
    justify-content: space-between;
}
```

- **space-around**: Distribui os itens com espaço igual ao redor deles.

```css
.container {
    justify-content: space-around;
}
```

#### Display

A propriedade `display` define o tipo de caixa de renderização usado por um elemento.

- **block**: O elemento é renderizado como um bloco.

```css
div {
    display: block;
}
```

- **inline**: O elemento é renderizado como um elemento inline.

```css
span {
    display: inline;
}
```

- **flex**: O elemento se torna um container flexível.

```css
div {
    display: flex;
}
```

- **grid**: O elemento se torna um container de grid.

```css
div {
    display: grid;
}
```

### Seletores, Responsividades e Animações

#### Seletores

Além dos básicos, existem seletores avançados como seletores de descendentes, filhos, irmãos adjacentes, irmãos gerais, pseudo-classes, e pseudo-elementos.

```css
/* Seleciona todos os <p> dentro de <div> */
div p {
    color: blue;
}

/* Seleciona todos os <p> que são filhos diretos de <div> */
div > p {
    color: green;
}

/* Seleciona o primeiro <p> após <div> */
div + p {
    color: red;
}
```

#### Responsividades

Media queries permitem aplicar estilos diferentes para dispositivos diferentes.

```css
@media (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}
```

#### Animações

Animações permitem transições suaves entre estilos.

```css
@keyframes example {
    from {background-color: red;}
    to {background-color: yellow;}
}

div {
    animation-name: example;
    animation-duration: 4s;
}
```

### Grid Layout e Unidade "fr"

Grid Layout é um sistema de layout bidimensional que pode lidar tanto com colunas quanto com linhas.

#### Unidade "fr"

A unidade `fr` representa uma fração do espaço disponível no grid container.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;
}
```

Este código cria um container de grid com três colunas, onde a segunda coluna ocupa duas frações do espaço disponível enquanto as outras ocupam uma fração cada.