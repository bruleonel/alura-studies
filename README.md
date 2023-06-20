# Anotações

## Creat React app

<a href="https://create-react-app.dev/docs/getting-started">Documentação</a>

**Comandos:**

````
npm start
````
Executa o projeto

````js
npx create-react-app --template typescript alura-studies --use -npm
````
![criacao de pacotes](https://github.com/bruleonel/alura-studies/assets/104650333/aeee6100-c52d-4efa-af39-0b73e76f052b)

Com esse comando, estamos informando várias coisas, sendo elas:

````js
npx
````
O comando npx, diferente do comando npm, apenas executa um pacote, sem que precisemos instalá-lo na nossa máquina, como o create-react-app normalmente só é usado no começo para criar o projeto, o ideal é executar com npx pois isso fará com que você sempre execute a última versão do pacote.

````js
create-react-app
````
O nome do pacote que queremos executar.

````js
alura-studies
````
O nome do projeto que queremos, assim como o nome da pasta.

````js
--template typescript
````
O Create React App nos permite usar vários templates, tendo como sintaxe o --template, que diz pro terminal que logo após iremos dizer qual template gostaríamos de usar, e o nome do template em si. O Create React App já tem o template typescript criado, mas caso tenha algum template que queira usar e não existe, você também pode criar o seu!,
--use-npm

Caso o yarn esteja instalado na sua máquina, o Create React App prioriza à utilização dele, e isso irá gerar um yarn.lock dentro da nossa aplicação, e nós queremos utilizar o npm ao invés do yarn, por isso precisamos usar o comando --use-npm se quisermos garantir que o Create React App utilize o npm para instalar as dependências necessárias e também garantir que ele gere o package-lock.json ao invés do yarn.lock.

# Sobre Componentização
## Nome do Componente
O nome do componente deverá começar com letra maiúscula, mas por que?

Existe uma possibilidade no html de criar web-components, que nos permite criar tags html totalmente customizadas. Entre essas customizações, podemos customizar o nome da tag!

Para o React diferenciar um componente de um <a href="https://developer.mozilla.org/pt-BR/docs/Web/API/Web_components">web-component</a>, ele pede para que criemos um componente com a primeira letra maiúscula, assim ele consegue diferenciar por exemplo que <meuBotao /> é um web-component e <MeuBotao /> é um componente!

## return e JSX
Para podermos criar um componente, fora a regra que citamos acima, precisamos retornar <a href="https://pt-br.legacy.reactjs.org/docs/introducing-jsx.html">JSX</a>, e o que seria isso exatamente?

O JSX é uma forma de "escrever HTML no JS", que é a forma que explicamos, mas não é exatamente isso.

O JSX não transforma o componente <Botao /> em HTML diretamente, antes disso, ele é transformado em uma elemento React, e aquele código é transformado em algo assim:

````js
const Botao = React.createElement('button', {}, 'Botão');
````
Sem se atentar ao que isso faz agora, mas por debaixo dos panos o React transforma aquela sintaxe """HTML""" nesse palavrão que, na hora do ReactDOM.render, é transformado em DOM e, aí sim, transformado em HTML.

Você percebeu que a tag html é usada como primeiro parâmetro da função createElement como uma string?

Isso mostra que, para criarmos um componente, precisamos de uma tag "pai", logo, o código a seguir não funcionará:

````js
class Botao extends React.Component {
  render() {
   return (
      <p> Título do Botão </p>
      <button>
        Botão
      </button>
    )
 }
}
````
Caso você precise fazer isso, leia sobre <a href="https://pt-br.legacy.reactjs.org/docs/react-api.html#reactfragment">React.Fragment</a>.

# Sobre class Components
## React.Component e render
Para criarmos um componente com class components, precisamos estender à classe React.Component. Nesta classe, existe apenas uma função obrigatória chamada render e, dentro dela, nós retornamos o JSX que precisamos para criar o componente!


## Modules

<a href="https://create-react-app.dev/docs/adding-a-css-modules-stylesheet/">Documentação</a>

## Pontos que precisam ser estudados
- uuid (pacote que cria Ids)