# heroku-commands
Lista de comando da CLI da Heroku

## Faz executar o comando "bower install" depois do push/deploy no servidor baixando as dependências do Bower
echo '{"name": "multitest", "scripts": {"compile": ["bower install"] } }' > composer.json

## Criação do Procfile
echo 'web: vendor/bin/heroku-php-apache2' > Procfile

## Criação do Procfile com uma pasta padrão de execução da Heroku
echo 'web: vendor/bin/heroku-php-apache2 www/' > Procfile

## Alterar nome do aplicativo
heroku apps:rename novoNome

## Deleta o aplicativo na cloud da heroku e remove ele do seu git local
heroku apps:destroy Nome-do-aplicativo --confirm Nome-do-aplicativo

## Para dar um restart no seridor
heroku restart

## Lista buildpacks da aplicação
heroku buildpacks

## Altera o buildpack padrão para PHP
heroku buildpacks:set https:#github.com/heroku/heroku-buildpack-php

## Adiciona o NodeJs como um segundo buildpack, para com isso executar comomandos como "bower install" para instalar as dependências
heroku buildpacks:add --index 2 https:#github.com/heroku/heroku-buildpack-nodejs

## Remover um BuildPack
heroku config:unset BUILDPACK_URL
heroku config:unset https:#github.com/heroku/heroku-buildpack-nodejs
