# Padrão Command

## Centro Universitário UNIESP

### Professora: Drª Alana Morais ([alanamm.prof@gmail.com](mailto:alanamm.prof@gmail.com))

### Aluno: Ericleiton Gomes de Macedo

### Apresentação: https://drive.google.com/file/d/1ha--tdnbc7gPY7ntCFgSVTVb-zF5iyyR/view

## Nome
O *Command* é um padrão de projeto comportamental que converte solicitações ou operações simples em objetos. Essa transformação permite que você controle métodos com diferentes pedidos, atrase ou coloque a execução do pedido em uma fila, e suporte operações que não podem ser feitas, ou seja, ele encapsula toda informação necessária para executar uma ação ou acionar uma ação em um momento posterior, quando for necessário.

## Problema
Imagine que você foi solicitado para realizar a criação de um sistema de um portão, onde ele consegue realizar várias atividades via comandos do seu software. Normalmente, seria criado uma classe Portao e várias outras subclasses para cada função ou ação na qual o portão realizaria. Essas subclasses conteriam o código que teria que ser executado em uma solicitação do sistema.

Porém essa abordagem é bastante falha, pois seu código ficaria totalmente dependente de um código volátil da lógica do negócio. De acordo com o numero de subclasses, você poderia quebrar o seu código cada vez que houvesse uma modificação na classe base do sistema. Podendo ficar ainda pior, se o fosse solicitado o crescimento do código e fosse necessário a adição de novas funções que precisassem ser invocadas de diversos outros lugares ou classes.


## Solução
Um bom projeto de software quase sempre se baseia no princípio da separação de interesses, o que geralmente resulta em dividir a aplicação em camadas. No command um objeto chama um método da lógica do negócio, passando alguns argumentos. Este processo é geralmente descrito como um objeto mandando um pedido para outro.

O padrão Command faz com que os objetos não enviem esses pedidos diretamente, ou seja, devesse extrair todos os detalhes da solicitação em questão, tais como o nome do método, a lista de argumentos em uma classe comando separada, que possui apenas um método que realiza a ação desse pedido e o objeto a ser chamado. Implementando esse padrão, o objeto não vai precisar saber qual objeto de logica de negocio vai receber o pedido ou como ele vai ser processado. O objeto deve acionar o comando, que irá realizar toda conexão necessária para realizar a determinada solicitação.

Após ser aplicado o padrão Command, não é mais necessário a aplicação de todas aquelas subclasses para realizar vários comportamentos. Será suficiente apenas um campo na classe Portao base, que irá armazenar a referencia para um objeto comando e fazer o portão executar uma ação apenas com um comando. Como resultado, os comandos se tornam uma camada intermédia conveniente que reduz o acoplamento entre as camadas.


## Consequências
As principais consequências do command são:
*	Command desacopla o objeto que invoca a operação daquele que sabe como executá-la.
*	Commands são objetos de primeira classe, ou seja, podem ser manipulados e estendidos como qualquer outro objeto.
*	Você pode introduzir novos comandos na aplicação sem quebrar o código cliente existente.
*	Você pode implementar desfazer/refazer.
*	Um comando pode ser composto por outros comandos. 
*	Você pode implementar a execução adiada de operações.
*	É fácil acrescentar novos Commands porque não é preciso mudar classes existentes.

A única característica ruim no Command é que o código pode ficar mais complicado uma vez que você está introduzindo uma nova camada entre remetentes e destinatários. É preciso um bom entendimento do padrão para que não se enrole no seu próprio código.

## Referencias:

* _FREEMAN, Eric – Use a cabeça!: Padrões de Projetos (Design Patterns)._
* _https://refactoring.guru/pt-br/design-patterns/command/java/example - (Data da Consulta 29/11/2020)_
* _https://medium.com/@danvitoriano/padr%C3%A3o-de-projeto-command-787a9d64fe8 - (Data da Consulta 29/11/2020)_
* _http://www.csi.uneb.br/padroes_de_projetos/command_2.html - (Data da Consulta 29/11/2020)_
