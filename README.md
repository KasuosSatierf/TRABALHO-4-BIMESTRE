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
