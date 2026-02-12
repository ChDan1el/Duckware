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









