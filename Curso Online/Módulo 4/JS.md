## Lógica de programação básica com Javascript

### O que é JavaScript?
JavaScript é uma linguagem de programação de alto nível, interpretada e orientada a objetos. Ela é amplamente utilizada para desenvolver aplicações web interativas e dinâmicas. Originalmente criada para adicionar dinamismo e interatividade às páginas da web, hoje em dia o JavaScript pode ser executado tanto no lado do cliente (navegador) quanto no lado do servidor (por exemplo, usando Node.js).

### Gerenciamento de memória dinâmica

No JavaScript, a alocação de memória para variáveis é feita automaticamente, e a linguagem gerencia a liberação de memória por meio da coleta de lixo. Diferentes tipos de variáveis em JavaScript, como `let`, `const` e `var`, têm escopos e comportamentos distintos que podem afetar o gerenciamento de memória e o desempenho de uma aplicação.

#### Var

- **Escopo:** O escopo de uma variável declarada com `var` é a função onde ela é definida ou o escopo global se não estiver dentro de uma função.
- **Hoisting:** As variáveis declaradas com `var` são içadas para o topo do seu escopo, ou seja, você pode utilizá-las antes da declaração no código, mas o valor será `undefined` até a linha onde a declaração ocorre.

```javascript
function exemploVar() {
    console.log(nome); // undefined
    var nome = "Alice";
    console.log(nome); // "Alice"
}
```

#### Let

- **Escopo:** O escopo de uma variável declarada com `let` é o bloco onde ela é definida (por exemplo, dentro de um `if` ou `for`), ao contrário de `var`, que tem escopo de função.
- **Hoisting:** As variáveis declaradas com `let` também são içadas, mas não são inicializadas. Você não pode utilizá-las antes da declaração no código (temporal dead zone).

```javascript
function exemploLet() {
    // console.log(idade); // ReferenceError: Cannot access 'idade' before initialization
    let idade = 25;
    console.log(idade); // 25
}
```

#### Const

- **Escopo:** O escopo de uma variável declarada com `const` é o mesmo que `let` — bloco onde é definida.
- **Hoisting:** As variáveis declaradas com `const` também são içadas, mas, assim como `let`, não são inicializadas e estão sujeitas à temporal dead zone.
- **Imutabilidade:** A principal característica de `const` é que você deve atribuir um valor no momento da declaração, e esse valor não pode ser reatribuído. No entanto, para objetos e arrays, você ainda pode modificar as propriedades ou elementos internos.

```javascript
function exemploConst() {
    // console.log(cidade); // ReferenceError: Cannot access 'cidade' before initialization
    const cidade = "São Paulo";
    console.log(cidade); // "São Paulo"
    // cidade = "Rio de Janeiro"; // TypeError: Assignment to constant variable.

    const pessoa = { nome: "João" };
    pessoa.nome = "Pedro"; // Isso é permitido
    console.log(pessoa.nome); // "Pedro"
}
```

### Diferenças entre `var`, `let` e `const`:

1. **Escopo:**
   - `var`: Escopo de função.
   - `let` e `const`: Escopo de bloco.

2. **Hoisting:**
   - `var`: Içada e inicializada com `undefined`.
   - `let` e `const`: Içadas mas não inicializadas, resultando em erro se acessadas antes da declaração.

3. **Reatribuição:**
   - `var` e `let`: Permitem reatribuição.
   - `const`: Não permite reatribuição do valor, mas permite alteração de propriedades internas em objetos e arrays.
.

### Condicionais

As condicionais em JavaScript permitem que você execute diferentes blocos de código com base em certas condições. Existem várias formas de escrever condicionais em JavaScript, incluindo `if`, `else if`, `else` e `switch`.

#### If, Else If, Else

O `if` é usado para executar um bloco de código se uma condição for verdadeira. O `else if` permite adicionar condições adicionais e o `else` executa um bloco de código se nenhuma das condições anteriores for verdadeira.

```javascript
let idade = 18;

if (idade < 18) {
    console.log("Você é menor de idade.");
} else if (idade === 18) {
    console.log("Você acabou de se tornar maior de idade.");
} else {
    console.log("Você é maior de idade.");
}
```

#### Switch

O `switch` é usado para executar um dos muitos blocos de código com base no valor de uma expressão.

```javascript
let dia = 3;
let diaSemana;

switch (dia) {
    case 1:
        diaSemana = "Domingo";
        break;
    case 2:
        diaSemana = "Segunda-feira";
        break;
    case 3:
        diaSemana = "Terça-feira";
        break;
    case 4:
        diaSemana = "Quarta-feira";
        break;
    case 5:
        diaSemana = "Quinta-feira";
        break;
    case 6:
        diaSemana = "Sexta-feira";
        break;
    case 7:
        diaSemana = "Sábado";
        break;
    default:
        diaSemana = "Dia inválido";
        break;
}

console.log(diaSemana); // "Terça-feira"
```