# NoDevs - Quem precisa de programador?!

Frontend AngularJS

## Endereços

* Produção:
* Staging:

## Desenvolvimento

### Instalação

Instalar o `grunt` e o `bower`, caso não estejam instalados:

```sh
sudo npm -g install grunt-cli karma bower
```

Instalar os pacotes do NPM e do Bower:

```sh
npm install
bower install
```

### Build

Durante o desenvolvimento, pode-se executar o projeto utilizando:

```sh
grunt watch
```
## Implantação

### Build & Push

Realizar o build do projeto

#### Versão de desenvolvimento

```
docker login nao_tenho_ainda
fab push_develop
```

#### Release Version (Production)

1. Criar uma nova release usando o [git-flow](http://danielkummer.github.io/git-flow-cheatsheet/)
1. Atualizar o número da versão em `fabfile.py`, `bower.json` e `package.json` na release criada
1. Comitar as alterações referenciando a release a ser criada.
1. Finalizar a release
1. Executar os comandos abaixo substituindo VERSAO pela versão do release:

```
make push
```

### Deploy

Executar os comandos no contexto `compose` no servidor.

#### Versão de desenvolvimento

```
docker-compose -f nodevs.yml -f env-staging.yml pull nodevs_angularjs
docker-compose -f nodevs.yml -f env-staging.yml up -d nodevs_angularjs
```

#### Versão de produção

```
docker-compose -f nodevs.yml pull nodevs_angularjs
docker-compose -f nodevs.yml up -d nodevs_angularjs
```

### Accessing

```
docker exec -it nodevs_angularjs /bin/bash
```
