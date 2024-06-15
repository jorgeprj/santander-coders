# React - Básico

## Introdução ao ReactJS

### O que é?

ReactJS é uma biblioteca JavaScript para a construção de interfaces de usuário. Criada pelo Facebook, o React facilita a criação de UIs interativas e eficientes ao usar uma abordagem baseada em componentes, onde cada parte da interface é encapsulada em um componente reutilizável.

### Como o ReactJS funciona?

O ReactJS funciona criando uma árvore de componentes que representa a interface do usuário. Quando o estado de um componente muda, o React compara a árvore atual com uma nova versão (usando um algoritmo de reconciliação chamado "Virtual DOM") e atualiza apenas as partes da interface que realmente mudaram, tornando a atualização da UI eficiente.

### Compilers + Bundlers

Compilers como Babel são usados para converter o código JavaScript moderno (ES6+) em uma versão compatível com todos os navegadores. Bundlers como Webpack ou Parcel são usados para empacotar todos os arquivos JavaScript, CSS e outros ativos em um ou mais arquivos otimizados para a produção, gerando um código final eficiente e fácil de incluir em uma página web.

### Rendering Patterns

Existem vários padrões de renderização que podem ser usados com React, como renderização no lado do cliente (Client-Side Rendering - CSR), renderização no lado do servidor (Server-Side Rendering - SSR) e renderização estática (Static Site Generation - SSG). Cada um tem suas vantagens e desvantagens, e a escolha depende das necessidades específicas da aplicação.

## Componentização

### O que é?

Componentização é o processo de dividir a interface do usuário em partes menores e reutilizáveis chamadas componentes. Cada componente é responsável por uma parte específica da UI e pode ser combinado com outros componentes para formar a interface completa.

#### Vantagens

- **Reutilização de Código**: Componentes podem ser reutilizados em diferentes partes da aplicação.
- **Facilidade de Manutenção**: Componentes menores são mais fáceis de entender, testar e manter.
- **Modularidade**: Facilita a divisão do trabalho entre diferentes desenvolvedores.
- **Melhoria na Performance**: Atualizações são limitadas aos componentes afetados, não à aplicação inteira.

#### Atomic Design

O Atomic Design é uma metodologia de design que propõe a criação de sistemas de interface a partir de cinco níveis: átomos, moléculas, organismos, templates e páginas. No contexto do React, isso significa criar componentes básicos (átomos), combiná-los em componentes mais complexos (moléculas e organismos), e finalmente formar a interface completa (templates e páginas).

### Como funciona no React?

No React, a componentização é feita criando classes ou funções JavaScript que retornam JSX (uma extensão de sintaxe que permite escrever código semelhante a HTML em JavaScript). Esses componentes podem receber dados (props) e gerenciar seu próprio estado interno, permitindo a construção de UIs dinâmicas e interativas.

## Props e Estados

- **Props**: São dados passados de um componente pai para um componente filho. São imutáveis e são usadas para personalizar e configurar componentes.

    ```jsx
    // Exemplo de componente que utiliza props
    function Saudacao(props) {
      return <h1>Olá, {props.nome}!</h1>;
    }

    // Uso do componente Saudacao
    <Saudacao nome="Maria" />
    ```

- **Estado (State)**: São dados gerenciados dentro de um componente. Eles podem mudar ao longo do tempo e, quando mudam, o componente é re-renderizado para refletir essas mudanças.

    ```jsx
    import React, { useState } from 'react';

    function Contador() {
      const [contador, setContador] = useState(0);

      return (
        <div>
          <p>Você clicou {contador} vezes</p>
          <button onClick={() => setContador(contador + 1)}>
            Clique aqui
          </button>
        </div>
      );
    }
    ```

## Ciclo de Vida

O ciclo de vida dos componentes no React descreve as fases pelas quais um componente passa desde sua criação até sua destruição. Ele é dividido em três fases principais:

### Fases

1. **Montagem**: A fase em que o componente é criado e inserido no DOM.
2. **Atualização**: Ocorre quando as props ou o estado do componente mudam, levando a um re-render.
3. **Desmontagem**: A fase em que o componente é removido do DOM.

### Métodos do Ciclo de Vida

#### Montagem

- **constructor()**: Inicializa o componente. Pode ser usado para definir o estado inicial e para vincular métodos.

    ```jsx
    class Saudacao extends React.Component {
      constructor(props) {
        super(props);
        this.state = { nome: 'Mundo' };
      }

      render() {
        return <h1>Olá, {this.state.nome}!</h1>;
      }
    }
    ```

- **componentDidMount()**: Chamado imediatamente após o componente ser montado no DOM. Ideal para inicializações que requerem um DOM, como chamadas a APIs.

    ```jsx
    class DadosUsuario extends React.Component {
      constructor(props) {
        super(props);
        this.state = { dados: null };
      }

      componentDidMount() {
        fetch('/api/dados')
          .then(response => response.json())
          .then(data => this.setState({ dados: data }));
      }

      render() {
        const { dados } = this.state;
        return (
          <div>
            {dados ? <p>Usuário: {dados.nome}</p> : <p>Carregando...</p>}
          </div>
        );
      }
    }
    ```

#### Atualização

- **componentDidUpdate(prevProps, prevState)**: Chamado imediatamente após a atualização do componente. Pode ser usado para operar com o DOM quando as props ou o estado mudam.

    ```jsx
    class Contador extends React.Component {
      constructor(props) {
        super(props);
        this.state = { contador: 0 };
      }

      componentDidUpdate(prevProps, prevState) {
        if (prevState.contador !== this.state.contador) {
          console.log(`O contador foi atualizado para ${this.state.contador}`);
        }
      }

      incrementar = () => {
        this.setState((state) => ({ contador: state.contador + 1 }));
      };

      render() {
        return (
          <div>
            <p>Contador: {this.state.contador}</p>
            <button onClick={this.incrementar}>Incrementar</button>
          </div>
        );
      }
    }
    ```

#### Desmontagem

- **componentWillUnmount()**: Chamado imediatamente antes do componente ser desmontado e destruído. Ideal para limpeza, como cancelar assinaturas de eventos ou timers.

    ```jsx
    class Relogio extends React.Component {
      constructor(props) {
        super(props);
        this.state = { hora: new Date() };
      }

      componentDidMount() {
        this.timerID = setInterval(() => this.tick(), 1000);
      }

      componentWillUnmount() {
        clearInterval(this.timerID);
      }

      tick() {
        this.setState({ hora: new Date() });
      }

      render() {
        return (
          <div>
            <h2>São {this.state.hora.toLocaleTimeString()}.</h2>
          </div>
        );
      }
    }
    ```