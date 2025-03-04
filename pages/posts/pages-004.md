---

title: ENCRYPTION BCRYPT TYPE HASH

date: 2023/3/12

description: Learn more introduction about Bcrypt.

tag: news

author: You

---

Atualmente, o mercado de tecnologia possui uma gama de informações sensíveis e suscetíveis a qualquer usuário, que são essenciais para os negócios de uma organização.

Para evitar acessos não autorizados aos sistemas, utilizam-se alguns métodos de proteção de dados, como a criptografia de senhas, que dificulta o acesso a banco de dados.

    O que é criptografia e algoritmo de hashing?

A palavra criptografia origina-se do grego kryptós (“escondido”) e gráphein (“escrita”), que significa “tornar informações originais em informações ilegíveis”. Esse processo de “esconder a escrita” é realizado através da aplicação de algoritmos matemáticos que modificam qualquer bloco de dados em caracteres de comprimento fixos, transformando-os em hashes. O comprimento dos dados de entrada podem ter qualquer tamanho, porém, os dados de saída sempre terão valores de hash de mesmo comprimento. Um dos problemas encontrados no hash é a vulnerabilidade quanto aos ataques de dicionário (força bruta). Um ataque de dicionário nada mais é do que um ataque que tenta descobrir senhas de acesso ao tentar inúmeras combinatórias listadas em um banco de dados.

    O que é BCrypt?

O BCrypt foi desenvolvido por Niels Provos e David Mazières (1999) com o propósito de esconder senhas criadas pelos usuários em forma de texto “puro” em dados indecifráveis, utilizando o algoritmo hash. Essa é uma ferramenta segura para armazenar senhas no banco de dados e pode ser utilizada por qualquer linguagem (C, C ++, C #, Go, Java, JavaScript, Elixir, Perl, PHP, Python, Ruby e outros).

O BCrypt possui dois critérios importantes:

O salt é uma das vantagens do BCrypt, pois acrescenta aleatoriamente sequências de caracteres a senha, projetando resultados criptográficos complexos e aumentando a segurança contra ataques de força bruta, como o rainbow tables, ou seja, um hash sempre será diferente, mesmo que a senha seja igual.

A outra vantagem do BCrypt é a possibilidade de alterar valores do saltRounds (relacionado a custos), onde quanto maior o número fornecido, mais lento será o processamento para calcular o hash associado a senha. Por padrão, o valor utilizado é 10, mas é importante salientar que um valor mais alto demandará mais tempo para encontrar as possíveis senhas nos casos de ataque de força bruta. Então esse valor deve ser pequeno o suficiente para não demorar na verificação no login do usuário.

    Senha = 123456
    Salt = 4137445196
    Senha + Salt = 1413744519665432
    Senha criptografada = 4564137445196321

    Como funciona o processo de login?

O cadastro e a autenticação de usuários baseados em hash funcionam da seguinte forma:

1º O usuário cria um conta;

2º A senha é criptografada e salva no banco de dados;

3º Quando o usuário entrar com o login, o hash da senha digitada é verificado com o hash da senha original, ou seja, é feita uma comparação das senhas por meio do banco de dados;

4º No caso dos hashes corresponderem, o usuário conseguirá permissão de acesso. Caso contrário, retornará dados de login incorretos;

Esse processo ocorre sempre que o usuário pretende acessar a conta.

    Criptografando com BCrypt no Node.JS

Para instalar o BCrypt é só rodar o seguinte comando:

npm install bcrypt

Depois é só criar o arquivo app.js ou um nome qualquer contendo a extensão .js e acrescentar as informações abaixo:

    Entendendo o código linha a linha

Definindo o valor de caracteres:

const saltRounds = 10

Definindo a senha:

const testPass = ‘123456’

Criando o salt:

const salt = bcrypt.genSaltSync(saltRounds)

Criando o hash:

const hash = bcrypt.hashSync(testPass, salt)

Observação: se ao executar comando node app.js aparecer a seguinte mensagem de erro

… é só instalar o pacote npm install bcryptjs. Finalizado a instalação, execute novamente o comando node app.js e você terá como resultado;

$2a$08$4hzE36u4tMwJTxLR0yVcvOEG7ML9hN2v9s1OadVWtE5aYc4NhdhQ6

Cada vez que executar o comando, você obterá um novo hash:

node app.js$2a$08$lypO.Ri9nUV9s0YbSQvbn.TEpkRFGDJ7kKXc7807eDp/ucXDNn7/Snode app.js$2a$08$VjnacyE5mqm0MA3T2KnbhOb/WM3CFaLWpV..AyewSAS66PLMnJPsS

    Conclusão

Como podemos observar, as empresas perceberam a importância da segurança das informações e começaram a aplicar métodos e técnicas para proteger seus dados. Uma das técnicas conhecidas e muito utilizadas é a criptografia, que auxilia os desenvolvedores a criarem projetos de forma segura e controlada, evitando que usuários indesejados façam uso ou consigam ter acesso a informações privilegiadas. A segurança da informação é fundamental no dia a dia de qualquer empresa, independentemente do seu porte, faturamento ou atividade.


