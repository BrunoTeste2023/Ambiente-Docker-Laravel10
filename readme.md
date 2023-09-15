
# Ambiente Padrão - Laravel 10.x #

## Sobre o ambiente

Repositório criado com o intuito de facilitar a criação de novos projeto Laravel utilizando docker

### Stack utilizada

- PHP
- Laravel
- Nginx
- Docker

### Ambiente de desenvolvimento

- Instale o docker no WSL (Windows Subsystem for Linux) com Ubuntu LTS ou diretamente no Ubuntu.

### Configurando containers, nomes e IPs
Copiar arquivo ".env.example" como ".env" e preencher as configurações de acordo com o projeto

APP_NAME= Nome do Projeto
NGINX_PORT= Porta para acessar o sistema
NGINX_IP= IP (Rede docker) do NGINX

PHP_PORT= Port (Rede docker) do NGINX
PHP_IP= IP (Rede docker) do NGINX

NETWORK_SUBNET= Subnet que será utilizada pelos containers


Exemplo de configuração preenchida no arquivo


### Construindo container e configurando ambiente
Criando containers

Linux:
```shell script
sudo docker compose up -d
```
Windows:
```shell script
docker compose up -d
```

Acesse o container da aplicação

Linux:
```shell script
sudo docker compose exec app bash
```
Windows:
```shell script
docker compose exec app bash
```

Esse ambiente já contem dentro da pasta "src" um projeto Laravel vazio, caso queira baixar a base Laravel novamente será preciso "limpar" a pasta src e seguir os passos abaixo (com os containers rodando):

1) Acessar o container da aplicação

Linux:
```shell script
sudo docker compose exec app bash
```
Windows:
```shell script
docker compose exec app bash
```

2) Acessar via bash a pasta onde devem ficar os arquivos e executar:

Linux:
```shell script
sudo composer create-project laravel/laravel ./
```
Windows:
```shell script
composer create-project laravel/laravel ./
```