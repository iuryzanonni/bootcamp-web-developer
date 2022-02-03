# Containers

## Criando um novo container

Para criar um novo container utilizamos o verbo **run** + o nome da imagem que será executada.

```powershell
docker run ubunto #cria um container executando a imagem do Ubuntu

docker run node #cria um container executando a imagem do Node
```

## Listando os containers em execução

Para listar os container em execução podemos utilizar:

```powershell
docker ps

#ou

docker container ls
```

Para lista todos os containers executados e em execução:

```powershell
docker ps -a
#ou
docker container ls -a
```

## Executando um container em background

Esta funcionalidade é quando não necessitamos que um determinado container fique ocupando uma aba de um terminal. Para isso utilizamos a flag **-d** (detached). Ela fara nosso container executar em segundo plano.

```docker
docker run -d ngnix
```

## Exportando uma porta do container

Como os container não possuem conexão com nada externo, precisamos expor as portas com o uso da flag **-p**.

```docker
docker run -d -p 80:80 nginx
```

A nomenclatura 700:80 significa que a porta 80 do container será refletida para a porta 700 do computador.

## Parando um container

Para para um container utilizamos o verbo ***stop*** utilizando o CONTAINER ID OU NAME:

```powershell
docker stop strange_yaloy
#ou
docker stop e2df52d415
```

## Iniciando um container

Para rodar um container que que foi parado, utilizamos o comando **start.** Valido lembrar que quando executamos este comando ele reinicia um container com todas as configurações

```powershell
docker start e2df52d415
```

## Nomeando um container

Para dar nome à um container utilizamos a flag **—name.** Sem esta flag será gerado um nome aleatório.

```powershell
docker run -d -p 80:80 --name ngnix_app nginx
```

## Acessando os logs de um container

Para acessar os logs de um container utilizamos a flag **logs + id**

```powershell
docker logs nginx_app
```

Para visualizarmos os logs em tempo real, passamos o parâmetro -f antes do nome do container

```powershell
docker logs -f nginx_app
```

## Removendo um container do PC

Para remover um container utilizamos a flag **rm** + id do container.

```powershell
docker rm 8d4
#ou
docker rm ngnix_app
```