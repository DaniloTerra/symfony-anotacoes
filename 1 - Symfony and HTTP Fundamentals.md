Symfony foi construído com base em ideias vindas de muitas tecnologias, ou seja, caso você aprenda Symfony, você não estará somente aprendendo Symfony, mas estará aprendendo sobre os Fundamentos da WEB, Melhores Práticas de Desenvolvimento e como Utilizar Bibliotecas PHP

# HTTP is Simple
HTTP é uma linguagem de texto que permite que duas máquinas conversem entre si, e é só isso

Não importa como você desenvolve para a WEB, o objetivo do seu servidor SEMPRE vai ser entender uma Request HTTP e retornar uma Response HTTP

## Step 1: The Client Sends a Request
Toda conversa na WEB começa com uma Request HTTP

Uma Request HTTP é uma mensagem em formato de texto criada pelo Client (browser, aplicativo em um smartphone, aplicativo de um desktop) seguindo uma estruta específica (especificação HTTP)

O Client envia essa Request para o Server e então, aguarda uma Response do Server

## Step 2: The Server Returns a Response
Uma vez que o servidor recebe uma Request, ele sabe, ou deveria saber, qual recurso o Client deseja interagir (por meio da URN) e como ele deseja interagir (verbo HTTP)

Assim como uma Request HTTP, uma Response HTTP pode conter conteúdo em seu corpo (body) e sempre é acompanha de uma linha inicial e HEADERS HTTP, que fornecem informações adicionais para o Client

## Requests, Responses and Web Development
Essa dinâmica de Request/Response é que está por trás e faz a web funcionar

Não importa em qual tecnologia você está trabalhando, a metodologia que você segue, seu objetivo SEMPRE vai ser interpretar as Requests HTTP e retornar uma Response HTTP de forma apropriada

# Requests and Responses in PHP
O PHP abstrai o processo de interpretação de uma Request e facilita o processo de Response

De forma automática, por meio de várias chamada SUPERGLOBALS o PHP armazena todas as informações que vem de uma Request HTTP

Por meio da função header() você pode adicionar Headers as Responses HTTP. Para adicionar conteúdo ao Body da Request HTTP, basta "printar" algo na saída da aplicação (com as funções echo ou print, por exemplo)

# Requests and Responses in Symfony
O projeto Symfony fornece uma alternativa para trabalhar com Requests e Responses HTTP de uma maneira orientada a objetos, ao invés de trabalhar com PHP puro

Dentro de componente HttpFoundation, há uma classe para interpretar as Requests HTTP, e há uma classe para contruir as Responses HTTP

# The Journey from the Request to the Response
O verdadeiro desafio que existe na construção de uma aplicação Web é desenvolver a lógica que existe entre a Request e a Response. Provavelmente sua aplicação faz várias coisas complexas, como enviar emails, gerenciar submissões de formulário HTML, salvar/recuperar coisas de um banco de dados e ainda se preocuparar com questões de segurança

## The Front Controller
Tradicionalmente, as aplicações PHP eram escritas de uma forma que, cada arquivo .php representava um recurso (URL). Esse modelo implicava em várias desvantagens, porque não incentivada a reutilização de código e uma falta de flexibilidade quanto a mudança de recursos (mudar a URL para acessar um recuros)

Uma alternativa muito melhor para ser utilizada é o conceito de Front Controller. Onde apenas uma código PHP é executado sempre que uma Request é feita (isso pode ser configurado no WebServer que irá ficar entre a aplicação PHP e o Client). Com essa abordagem, a própria aplicação decide, com base na interpretação da Request, qual código deve ser executado e promove uma maior reutilização de código

## Stay Organized
As coisas podem fugir do seu controle caso, no FrontController você coloque todo o código para interpretar as Requests e criar as Response, mesmo isso sendo possível

## The Symfony Application Flow
Quando você permite ao Symfony interpretar toda e qualquer requisição HTTP, a vida fica bem mais fácil. Isso porque a mesma lógica é aplicada para todas as requisições

No modelo Symfony, todas as Requests são interpretadas por um FrontController e são "passadas" para um métod de uma classe Controller, que por sua vez gera a Response

- Toda Request HTTP executa um mesmo arquivo Front Controller
- O Rounting System determina qual método deve ser executado
- O código PHP correto é executado, o qual monta e retorna a Response apropriada

## A Symfony Request in Action
Exemplo citado

# Symfony: Build your app, not your Tools
- Symfony é uma coleção de mais de 20 bibliotecas independentes que podem ser utilizadas em conjuntos ou de forma separada. Essas bibliotecas, chamadas de Symfony Components, contém funcionalidades úteis para casos específicos

- Symfony Framework é uma biblioteca PHP que fornece basicamente duas coisas: Uma coleção de bibliotecas PHP e um skeleto com arquivos de configuração para sua aplicação