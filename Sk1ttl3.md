# Sk1ttl3
##### [Link do desafio](https://snewspaper.discloud.app/)

Este é um desafio de exploração web, sendo sua principal vulnerabilidade um sql injection

## Resolução

A página inicial do desafio é um portal de notícias, meu primeiro passo é analisar o HTML para tentar encontrar um endpoint, código, etc. 

Acabei encontrando um comentário mensionando um endpoint `admin.php`

<img width="1802" height="683" alt="image" src="https://github.com/user-attachments/assets/bfc92c48-7683-45ce-996d-8f4e50862051" />

Uma outra forma de encontrar essa rota é usando o `robots.xt`

<img width="209" height="47" alt="image" src="https://github.com/user-attachments/assets/7dfe408f-a45f-4224-9fb6-136530447444" />


Ao colocar o `admin.php` na URL do desafio, sou redirecionado para um painel de login

<img width="574" height="108" alt="image" src="https://github.com/user-attachments/assets/f36fc738-9617-4fd2-a08d-2ed23244bf47" />

Ao tentar `usuário = admin` e `senha = admin` não é retornado nada

Então resolvo analisar o HTML, lá encontro um comentário sobre banco de dados sql

<img width="1799" height="375" alt="image" src="https://github.com/user-attachments/assets/9a0c4c4e-6f48-40ee-86a5-012dcc183726" />

Apartir disso, uso o payload clássico de sql injection `' OR 1=1;--`

<img width="571" height="99" alt="image" src="https://github.com/user-attachments/assets/c607909f-1599-425b-ab47-63ddbecfc3d9" />

Com isso consigo a *flag*

<img width="1919" height="325" alt="image" src="https://github.com/user-attachments/assets/d7022fc7-2c9a-48ac-b2f0-f3f9ae53d97d" />

### FLAG: DUCK{SK1TTL3_N3W5_2077_SQL1NJ3CT10N_H45_B33N_H4CK3D}

## MITIGAÇÃO DO SQL INJECTION













