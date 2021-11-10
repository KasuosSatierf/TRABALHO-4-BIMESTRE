# TRABALHO 4° BIMESTRE
## Validação de entradas em uma API HTTP construida de Node.js e Express
### **TRABALHO APRESENTADO PELOS ALUNOS - MATHEUS FELIPE S DIAS SOARES E KÉSIA VICTORIA REFERENTE A DISCIPLINA DE DESENVOLVIMENTO DE SISTEMAS PARA INTERNET, REFERENTE A  GRADE CURRICULAR DO CURSO TÉCNICO EM INFORMÁTICA, INTEGRADO AO ENSINO MÉDIO**

**VALIDAÇÃO** 

A validação é muito importante pois garante que os dados que entram na API não sejam incorretos para cada campo, garante também uma maior confiabilidade no software, previne ataques e tc.

Exibiremos um projeto básico com formulários que deve ser preenchido com JSON. Para simular a rota vamos usar o aplicativo insomnia que deve ser instalado previamente, criar uma Request Collection e criar uma New Requisição do tipo Post com text JSON.

![Imgur](https://imgur.com/Y07DIn5.png)

A principio o npm já deve estar instalado, pois é uma ferramenta essencial para a instalação de pacotes que vamos precisar:

![Imgur](https://imgur.com/wRcS82N.png)

Para rodar o projeto pronto pelo node:

![Imgur](https://imgur.com/wPChwOP.png)

Para iniciarmos instalaremos os pacotes que vamos utilizar para rodar o projeto. O express gerencia requisições, rotas e URLs. Já o nodemon reinicia automaticamente o servidor.

![Imgur](https://imgur.com/rp17efd.png)

Para rodar o arquivo pelo nodemon:

![Imgur](https://imgur.com/jZoaDKl.png)

Dependências que o projeto precisa: instalar o nodemon de forma global

![Imgur](https://imgur.com/7d29izD.png)

Com um projeto simples de rota já pronto, acessar pelo nodemon sua rota, como exemplo: http://localhost:8080  (para "pausar" o servidor: crtl+c).

Para validar os dados de cada campo é preciso instalar um biblioteca como o yup. Outras opções podem ser verificadas com express-validator ou toi.  No caso vamos usar o yup.

![Imgur](https://imgur.com/Ik3iFM5.png)

Para utilizarmos o yup é preciso importá-lo, geralmente como indicado:

![Imgur](https://imgur.com/7m84mVg.png)

Depois de colocar todas a requisições necessárias, criar sua rota e importar o yup, podemos validar um campo de cada vez, colocando o nome do campo ex: 'senha' , o tipo, ex: 'string', a mensagem que o usuário vai receber quando o campo não for preenchido ou for preenchido incorretamente.

O required serve para atribuir obrigação de transmitir outra mensagem quando o campo não é preenchido.
No campo senha atribuímos o min para ter o mínimo de caracteres que possa ser preenchido.
No campo email tem uma atribuição que valida ou não o email de acordo com as normas

![Imgur](https://imgur.com/ZsX6swa.png)

Para ter certeza que foi utilizado com sucesso usaremos o try/catch, que serve para especificar a resposta de um bloco que está sendo testado. Nesse caso se o erro for true, retornaremos o código de status 400 e será mostrado a mensagem personalizada de erro. Já se o erro for false retornaremos a mensagem: "Dados corretos!" 

![Imgur](https://imgur.com/25ccrfl.png)

Para testar é só utilizar o insomnia e colocar a rota:  http://localhost:8080/user

![Imgur](https://imgur.com/P373x1v.png)

Caso seja o projeto apresentado algum erro durante o processamento do script, é dever do desenvolvedor configurar a aplicação de acordo com as normas HTTP, onde as mesmas funcionam como maneira padrão de comunicação de erros ao usuário. Os principais códigos de status usados, e mais comumente aparentes nos sistemas são referentes aos mais diversos problemas. os status de problemas HTTP são organizados em quatro classes, sendo elas 

1. Respostas de informação (100-199),
2. Respostas de sucesso (200-299),
3. Redirecionamentos (300-399)
4. Erros do cliente (400-499)
5. Erros do servidor (500-599).

**100 Continue**

Essa resposta provisória indica que tudo ocorreu bem até agora e que o cliente deve continuar com a requisição ou ignorar se já concluiu o que gostaria.

**101 Switching Protocol**

Esse código é enviado em resposta a um cabeçalho de solicitação Upgrade (en-US) pelo cliente, e indica o protocolo a que o servidor está alternando.

**205 Reset Content**

Esta requisição é enviada após realizanda a solicitação para informar ao user agent redefinir a visualização do documento que enviou essa solicitação.

**206 Partial Content**

Esta resposta é usada por causa do cabeçalho de intervalo enviado pelo cliente para separar o download em vários fluxos.

**402 Payment Required **

Este código de resposta está reservado para uso futuro. O objetivo inicial da criação deste código era usá-lo para sistemas digitais de pagamento porém ele não está sendo usado atualmente.

**403 Forbidden**

O cliente não tem direitos de acesso ao conteúdo portanto o servidor está rejeitando dar a resposta. Diferente do código 401, aqui a identidade do cliente é conhecida.

**404 Not Found**

O servidor não pode encontrar o recurso solicitado. Este código de resposta talvez seja o mais famoso devido à frequência com que acontece na web.

**REFERÊNCIAS BIBLIOGRÁFICAS**

https://celke.com.br/new/material-gratuito/validar-form-nodejs-yup

https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Status


