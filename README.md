# Fundamentos do React

## Configuração de Ambiente React

- [Visual Studio Code](https://code.visualstudio.com/).
  - Sublime, Brackets, Atoms, JetBrains
- Node.js: Runtime de JavaScript desenvolvido em cima do motor JavaScript V8 (Chrome).
- Node Package Manager (NPM): Gerenciador de pacote padrão do node.
- Yarn: Gerenciador de pacotes para aplicar comandos prontos ao código de uma aplicação.

  - Instalação:

    ```shell
    npm install -g yarn
    ```

- React DevTools: Extensão para inspecionar a hierarquia de componentes do React nas Ferramentas do desenvolvedor do navegador.
- Extensões para VSCode:
  - ES7+ React/Redux/React-Native snippets: Fornece snippets de código para React, Redux, GraphQL e React Native.
  - ESLint: Ajuda a manter o código limpo e sem erros.

O **Yarn** é mais rápido que o NPM em termos de velocidade de instalação e resolução de dependências. Ele também tem um recurso de cache que permite que os pacotes sejam armazenados em cache localmente para instalações futuras. Além disso, o Yarn tem um arquivo lock que garante que as versões dos pacotes permaneçam as mesmas em diferentes máquinas.

O **NPM** é mais popular e tem uma comunidade maior do que o Yarn. Ele também é mais fácil de usar e tem uma documentação melhor do que o Yarn. Além disso, o NPM é integrado ao Node.js, o que significa que ele é instalado automaticamente quando você instala o Node.js.

## Primeiros Passos na Biblioteca React

React JS é uma biblioteca JavaScript para a criação de interfaces de usuário.

Para criar um projeto:

```shell
npx create-react-app <nome_projeto>
```

Uma aplicação React típica vai possuir uma organização similar:

- **my-app/**
  - **README.md**: Documentação do projeto.
  - **node_modules/**: Diretório onde são instaladas as dependências do projeto. Essa pasta não é versionada pelo controle de versão (por exemplo, Git).
  - **package.json**: Arquivo que contém as informações do projeto, como dependências, scripts de execução e metadados.
  - **.gitignore**: Arquivo que especifica quais arquivos e diretórios devem ser ignorados pelo Git durante o controle de versão.
  - **public/**: Diretório que contém arquivos públicos acessíveis pelo navegador.
    - **index.html**: O arquivo HTML principal do aplicativo React. É o ponto de entrada para a renderização do React no navegador.
    - **favicon.ico**: Ícone do aplicativo exibido na guia do navegador.
  - **src/**: Diretório raiz do código-fonte do aplicativo.
    - **index.js**: O ponto de entrada JavaScript do aplicativo React. É responsável por renderizar o componente raiz do aplicativo no DOM.
    - **App.js**: Componente raiz do aplicativo React. Pode ser modificado para definir a estrutura e o comportamento inicial do aplicativo.
    - **App.css**: Arquivo CSS relacionado ao app.js.
    - **components/**: Diretório que contém componentes reutilizáveis do aplicativo.
      - **Component1.js**
      - **Component2.js**
    - **assets/**: Diretório para armazenar ativos do aplicativo, como imagens, arquivos de fonte, estilos globais etc.
      - **images/**
      - **styles/**
    - **utils/**: Diretório opcional para arquivos de utilitários e funções auxiliares.
    - **services/**: Diretório opcional para arquivos relacionados a serviços, como chamadas de API.
    - ...

### Componentes

No React, um componente é uma unidade isolada e autocontida que pode ser composta por elementos HTML, outros componentes ou uma combinação de ambos. Cada componente tem sua própria lógica interna, estado (opcional) e pode receber propriedades (props) para interagir com o ambiente externo.

```jsx
class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

```jsx
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}
```

As props (propriedades) são os mecanismos usados para passar dados e configurações para um componente. São argumentos passados para a função do componente e podem ser acessados dentro do corpo da função por meio do objeto props. As props são imutáveis, ou seja, não devem ser modificadas dentro do componente.

O retorno de um componente funcional deve ser um elemento JSX, que é uma representação do código HTML/React no JavaScript. É possível retornar um único elemento JSX ou um fragmento (utilizando <React.Fragment>, ou a sintaxe abreviada <>...</>). O retorno JSX pode incluir outros componentes, elementos HTML e até mesmo lógica condicional.

```jsx
function Greeting(props) {
  if (props.name) {
    return <h1>Hello, {props.name}!</h1>;
  } else {
    return <h1>Hello, Stranger!</h1>;
  }
}

// Uso do componente:
<Greeting name="John" />;
```

### Ciclo de Vida

Componentes de Classe:

- Criação:
  - **constructor**: É chamado quando o componente é inicializado.
  - **componentDidMount**: Executado após a renderização inicial do componente.
- Atualização:
  - **componentDidUpdate**: Executado após a renderização e quando as propriedades (props) ou o estado do componente mudarem.
  - **shouldComponentUpdate**: Controla se o componente deve ser atualizado ou não, otimizando o desempenho.
  - **componentWillUnmount**: Executado antes de o componente ser removido do DOM.

Componentes Funcionais (com Hooks):

- Criação:
  - useState: Permite que um componente funcional tenha um estado interno.
  - useEffect (com dependências vazias): Executado após a renderização inicial do componente.
- Atualização:
  - useEffect (com dependências específicas): Executado após a renderização e quando as dependências especificadas mudarem.
  - useMemo: Memoriza um valor computado para evitar recálculos desnecessários.
  - useCallback: Memoriza uma função para evitar a criação de novas instâncias em cada renderização.
- Desmontagem:
  - useEffect (com retorno de função): Executado quando o componente é desmontado, permitindo a realização de operações de limpeza.

A Virtual DOM é uma abstração criada pelo React para otimizar o processo de atualização do DOM real. Em vez de atualizar diretamente o DOM sempre que ocorrerem alterações, o React compara a Virtual DOM com a versão atual e atualiza apenas as partes afetadas. Essa abordagem é mais eficiente e oferece um melhor desempenho em comparação com a atualização direta do DOM.

## Projetos

- [Criando Uma Calculadora Com React](https://github.com/Err0rGCeni/DIOProject_CalcReact)
