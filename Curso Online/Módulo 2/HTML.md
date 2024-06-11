# HTML

## O que é HTML?

HTML (HyperText Markup Language) é a linguagem padrão utilizada para criar páginas web. Ele define a estrutura de um documento web e organiza o conteúdo por meio de elementos e tags.

## Dev Tools

Dev Tools são ferramentas integradas aos navegadores modernos, como Google Chrome, Firefox, Edge, entre outros. Elas permitem inspecionar e depurar o código HTML, CSS e JavaScript de uma página web.

## Estrutura básica

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Título da Página</title>
</head>
<body>
    <!-- Conteúdo da página -->
</body>
</html>
```

## Principais Tags

### Cabeçalhos

```html
<h1>Este é um cabeçalho de nível 1</h1>
<h2>Este é um cabeçalho de nível 2</h2>
<h3>Este é um cabeçalho de nível 3</h3>
<h4>Este é um cabeçalho de nível 4</h4>
<h5>Este é um cabeçalho de nível 5</h5>
<h6>Este é um cabeçalho de nível 6</h6>
```

### Parágrafo

```html
<p>Este é um parágrafo de texto.</p>
```

### Divisor e quebra de linhas

```html
<hr> <!-- Divisor horizontal -->
<br> <!-- Quebra de linha -->
```

### Links

```html
<a href="https://www.exemplo.com">Este é um link</a>
```

### Imagens

```html
<img src="caminho/para/imagem.jpg" alt="Descrição da imagem">
```

### Listas

#### Lista não ordenada

```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
```

#### Lista ordenada

```html
<ol>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ol>
```

### Tags genéricas (span e div)

```html
<div>Esta é uma div, um contêiner genérico de bloco.</div>
<span>Este é um span, um contêiner genérico de linha.</span>
```

### Tags de formatação de texto

- **Negrito**

```html
<b>Texto em negrito</b>
<strong>Texto com ênfase forte</strong>
```

- **Itálico**

```html
<i>Texto em itálico</i>
<em>Texto com ênfase</em>
```

- **Sublinhado** (Não indicado)

```html
<u>Texto sublinhado</u>
```

- **Riscado**

```html
<s>Texto riscado</s>
```

- **Destacando um texto**

```html
<mark>Texto destacado</mark>
```

- **Texto pré-formatado**

```html
<pre>
Texto pré-formatado preserva
    espaços e quebras de linha.
</pre>
```

- **Código**

```html
<code>console.log('Olá, mundo!');</code>
```

- **Citação**

```html
<blockquote>Este é um bloco de citação.</blockquote>
```

- **Subscrito**

```html
<sub>Texto subscrito</sub>
```

- **Sobrescrito**

```html
<sup>Texto sobrescrito</sup>
```

## Elementos semânticos

- **header**: Cabeçalho do documento ou de uma seção.
- **main**: Conteúdo principal do documento.
- **aside**: Conteúdo relacionado, como uma barra lateral.
- **footer**: Rodapé do documento ou de uma seção.
- **section**: Seção genérica do documento.
- **article**: Conteúdo independente e auto-suficiente.
- **figure**: Representação gráfica (imagem, ilustração).
- **nav**: Conjunto de links de navegação.

## Barra de navegação

```html
<header>
    <nav>
        <a href="#"><img src="logo.png" alt="Logo"></a>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">Sobre</a></li>
            <li><a href="#contact">Contato</a></li>
        </ul>
    </nav>
</header>
```

## Tabelas

### Cabeçalho e Corpo

```html
<table>
    <thead>
        <tr>
            <th>Cabeçalho 1</th>
            <th>Cabeçalho 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Dados 1</td>
            <td>Dados 2</td>
        </tr>
    </tbody>
</table>
```

### Linhas e colunas

```html
<table>
    <tr>
        <td>Linha 1, Coluna 1</td>
        <td>Linha 1, Coluna 2</td>
    </tr>
    <tr>
        <td>Linha 2, Coluna 1</td>
        <td>Linha 2, Coluna 2</td>
    </tr>
</table>
```

### Mesclando células (linhas ou colunas)

```html
<table>
    <tr>
        <td rowspan="2">Mesclando linhas</td>
        <td>Coluna 1</td>
    </tr>
    <tr>
        <td>Coluna 2</td>
    </tr>
    <tr>
        <td colspan="2">Mesclando colunas</td>
    </tr>
</table>
```

## Formulário

### Inputs

- **Text**

```html
<input type="text" name="nome">
```

- **Password**

```html
<input type="password" name="senha">
```

- **Email**

```html
<input type="email" name="email">
```

- **Number**

```html
<input type="number" name="idade">
```

- **Date**

```html
<input type="date" name="data">
```

- **Time**

```html
<input type="time" name="hora">
```

- **Checkbox**

```html
<input type="checkbox" name="aceito_termos">
```

- **File**

```html
<input type="file" name="arquivo">
```

- **URL**

```html
<input type="url" name="website">
```

- **Radio**

```html
<input type="radio" name="sexo" value="masculino"> Masculino
<input type="radio" name="sexo" value="feminino"> Feminino
```

- **Submit**

```html
<input type="submit" value="Enviar">
```

- **Color**

```html
<input type="color" name="cor_favorita">
```

- **Range**

```html
<input type="range" name="pontuacao" min="0" max="10">
```

- **Reset**

```html
<input type="reset" value="Redefinir">
```

### Select

- **Select**

```html
<select name="opcoes">
    <option value="opcao1">Opção 1</option>
    <option value="opcao2">Opção 2</option>
</select>
```

- **Props: value, selected, disabled**

```html
<option value="opcao3" selected>Opção 3</option>
<option value="opcao4" disabled>Opção 4</option>
```

### Submissão

```html
<form action="/enviar" method="post">
    <input type="text" name="nome">
    <input type="submit" value="Enviar">
</form>
```

## Integração com CSS

O HTML pode ser estilizado utilizando CSS (Cascading Style Sheets). A integração é feita através de três formas principais:

- **CSS Inline**: Estilo aplicado diretamente no elemento HTML.

```html
<p style="color: red;">Texto em vermelho</p>
```

- **CSS Interno**: Estilo definido dentro da tag `<style>` no `<head>` do documento HTML.

```html
<head>
    <style>
        p {
            color: blue;
        }
    </style>
</head>
```

- **CSS Externo**: Estilo definido em um arquivo .css separado e vinculado ao documento HTML.

```html
<head>
    <link rel="stylesheet" href="estilos.css">
</head>
```