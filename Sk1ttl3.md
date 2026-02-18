# Sk1ttl3
##### [Link do desafio](https://snewspaper.discloud.app/)

Este é um desafio de exploração web cuja principal vulnerabilidade é SQL Injection

## Contextualização

SQL Injection é uma vulnerabilidade que ocorre quando entradas do usuário são inseridas diretamente em consultas SQL sem validação ou tratamento adequado.

Isso permite que um atacante manipule a consulta original e execute comandos inesperados no banco de dados.

## Resolução

A página inicial do desafio apresenta um portal de notícias

Meu primeiro passo foi analisar o código-fonte HTML da página em busca de: Comentários, endpoints ocultos ou Scripts

Durante essa análise, encontrei um comentário mencionando o endpoint: `admin.php`

<img width="1802" height="683" alt="image" src="https://github.com/user-attachments/assets/bfc92c48-7683-45ce-996d-8f4e50862051" />

Outra forma de identificar essa rota foi verificando o arquivo `robots.txt`, que também indicava a existência dessa página administrativa

<img width="209" height="47" alt="image" src="https://github.com/user-attachments/assets/7dfe408f-a45f-4224-9fb6-136530447444" />

Ao acessar `admin.php`, fui redirecionado para um painel de login.

<img width="574" height="108" alt="image" src="https://github.com/user-attachments/assets/f36fc738-9617-4fd2-a08d-2ed23244bf47" />

Inicialmente, tentei credenciais simples: `Usuário: admin` e `Senha: admin`. Mas nenhum retorno foi obtido.

Então, voltei a analisar o código-fonte da página e encontrei um comentário indicando o uso de um banco de dados SQL, o que sugeria a possibilidade de SQL 
Injection no campo de login.

<img width="1799" height="375" alt="image" src="https://github.com/user-attachments/assets/9a0c4c4e-6f48-40ee-86a5-012dcc183726" />

Diante disso, utilizei o payload clássico: `' OR 1=1;--`

Esse payload funciona da seguinte forma:

`'` fecha a string original da consulta

`OR 1=1` adiciona uma condição sempre verdadeira

`;` delimitador o fim da instrução SQL 

> O ; nesse caso é optativo

`--` comenta o restante da consulta

Se a aplicação não tratar corretamente a entrada, a condição 1=1 torna a autenticação verdadeira, permitindo o acesso sem credenciais válidas.

<img width="571" height="99" alt="image" src="https://github.com/user-attachments/assets/c607909f-1599-425b-ab47-63ddbecfc3d9" />

Após inserir o payload no campo de login, consegui acessar a área restrita e obter a *flag*

<img width="1919" height="325" alt="image" src="https://github.com/user-attachments/assets/d7022fc7-2c9a-48ac-b2f0-f3f9ae53d97d" />

### FLAG: DUCK{SK1TTL3_N3W5_2077_SQL1NJ3CT10N_H45_B33N_H4CK3D}

## MITIGAÇÃO DO SQL INJECTION

Para mitigar essa vulnerabilidade, é fundamental:

1- Nunca confiar na entrada do usuário

2- Utilizar *queries* parametrizadas (prepared statements)

3- Implementar validação adequada de dados

4- Aplicar princípios de menor privilégio no banco de dados

Evitar apenas listas de caracteres permitidos não é suficiente em muitos casos. O método mais seguro é utilizar mecanismos próprios da linguagem ou do framework 
para separar dados de código SQL.
