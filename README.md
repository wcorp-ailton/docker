# Comandos Docker

![](https://repository-images.githubusercontent.com/288003065/c430d800-dfed-11ea-93ec-922490b0070c)



### - Docker info 
#### Comando de verificação das informações do nosso Docker Host
> docker info
___


### - Docker version
#### Comando de verificação da versão do nosso Client
> docker version
___


## - Docker images

### - Docker images
#### Comando de verificação das imagens disponíveis no nosso Docker Host
> docker images
- Repository: Repositório;
- TAG: Tag utilizada no repositório;
- IMAGE ID: O id na nossa imagem;
- Created: Data de quando nós criamos a nossa imagem;
- Size: Tamanho da imagem;

<br>

### - Docker images -a
#### Comando de verificação das imagens disponíveis em execução/processamento no nosso Docker Host
> docker images -a
- Repository: Repositório;
- TAG: Tag utilizada no repositório;
- IMAGE ID: O id na nossa imagem;
- Created: Data de quando nós criamos a nossa imagem;
- Size: Tamanho da imagem;

<br>

### - Docker images -a -q
#### Comando de verificação das imagens disponíveis em execução/processamento no nosso Docker Host por image id
> docker images -a -q
- IMAGE ID: O id na nossa imagem;

<br>

### - Docker rmi
#### Comando para deletar/remover imagem
> docker rmi (nome da imagem ou id da imagem)

` * Caso a imagem esteja em execução/processamento por algum container, deverá ser incluso a flag -f,  para que sua execução/processamento seja parada e sua remoção ocorra. `

> docker rmi (nome da imagem ou id da imagem) -f
##### - (nome da imagem) - Ex.: Web01, Web02, containerX, hash(564874d45555)...
___


### - Docker search
#### Comando de verificação de imagens disponíveis para download
> docker search (parametro)
##### - (parametro) - Ex.: ubuntu, dotnetcore, node...
___


### - Docker run
#### Comando de criação/execução da imagem
> docker run (nome da imagem)
##### - (nome da imagem) - Ex.: ubuntu, dotnetcore, node...

#### Comando de criação/execução da imagem de exemplo
> docker run -d --name=web01 -p 8080:80 -v $(pwd):/usr/share/nginx/html --net=net01 nginx

#### Comando de criação/execução da imagem informativo
> docker run -d --name=(nome do container) -p (porta de acesso):(porta de redirecionamento) -v (nome do volume) --net=(nome da network) (nome da imagem)
##### - (porta de acesso) - Ex.: 8080,9090,7070...
##### - (porta de redirecionamento) - Ex.: 80,90,70...
##### - (nome do container) - Ex.: web01, web02, app-xpto...
##### - (nome do volume) - Ex.: volume-x, volume-y...
##### - (nome da network) - Ex.: net01, net02, net03...
##### - (nome da imagem) - Ex.: ubuntu, dotnetcore, node...

` * Quando for dado o comando docker run (nome da imagem), o docker irá buscar a imagem no Docker Host, caso ele não encontre, fará o download. `
___


### - Docker ps
#### Comando de verificação do status do container em execução
> docker ps 

### Docker ps -a
#### Comando de verificação do status do container, mesmo que ele já tenha sido finalizado.
> docker ps -a

### - Docker ps -a -q
#### Comando para listar todas os containers id (em execução/processamento ou finalizados).
> docker ps -a -q

` * O container é criado execultado/processado e finalizado. `
___


### - Docker status
#### Comando de verificação de informações do container
> docker stats (id ou apelido do nome do container)
##### - (id ou apelido do container) - Ex.: Web01, Web02, containerX, hash(564874d45555)...
- CONTAINER — ID do Container;
- CPU % — uso de CPU em porcentagem;
- MEM USAGE / LIMIT — Memória usada/Limite que você pode ter setado;
- MEM — uso de memória em porcentagem;
- NET I/O — I/O de Internet;
- BLOCK IO — Outros processos de I/O;
___


### - Docker inspect
#### Comando de verificação deinformações referentes a imagem, seu retorno é um json que irá retornar todas as informações relacionadas a busca.
> docker inspect (id da imagem ou nome do container)
##### - (id da imagem ou container) - Ex.: Web01, Web02, containerX, hash(564874d45555)...
___

### - Docker rm
#### Comando para deletar/remover container 
> docker rm (id do container ou name do container)

### Docker rm $(docker ps -a -q) -f
#### Comando para deletar/remover todos os container de uma só vez
> docker rm $(docker ps -a -q) -f
- $(docker ps -a -q): 
- -f: 

` * Caso o container esteja em execução/processamento, deverá ser incluso a flag -f, para que sua execução/processamento seja interrompida e em seguida ocorra sua exclusão. `

> docker rm  (id do container ou name do container) -f
___


### - Docker exec
#### Execução de comandos diretamente no container.
> docker exec (id do container ou nome do container) 

> docker exec -it (id do container ou nome do container) bash

> docker exec -it -d (id do container ou nome do container)  bash

##### - (bash: Opção de terminal) - Ex.: bash, zsh...

- -i permite interagir com o container
- -t associa o seu terminal ao terminal do container
- -it é apenas uma forma reduzida de escrever -i -t
- --name algum-nome permite atribuir um nome ao container em execução
- -p 8080:80 mapeia a porta 80 do container para a porta 8080 do host
- -d executa o container em background
- -v /pasta/host:/pasta/container cria um volume '/pasta/container' dentro do container com o conteúdo da pasta '/pasta/host' do host

Exemplos de criação de diretório direto no container:
> docker exec (id do container ou nome do container) mkdir /temp/

Exemplos de criação de arquivo dentro do diretório, direto no container:
> docker exec (id do container ou nome do container) touch /temp/dotnetsp.txt

` * Para sair do terminal digite exit. `
___


### - Docker attach
#### 
> docker attach (id do container ou nome do container)

` * ` 
___


### - Docker start
#### Comando para matar o container em execução/processamento
> docker start (id do container ou nome do container)
___


### - Docker stop
#### Comando para parar o container que esteja em execução/processamento
> docker stop (id do container ou nome do container)
___

## - Docker volume 

### - Docker volume create
#### Comando para criação de volume no Docker Host
> docker volume create (nome do volume)
##### - (nome do volume) - Ex.: volume01, volume02...

<br>

### - Docker volume ls
#### Comando de verificação dos volumes disponíveis no Docker Host
> docker volume ls
- Driver: 
- Volume Name: Nome do Volume

<br>

### - Docker volume ls -q
#### Comando de verificação dos volumes disponíveis no Docker Host por nome.
> docker volume ls -q
- Volume Name: Nome do Volume

<br>

### - Docker volume inspect
#### Comando para inspecionar informações do volume
> docker volume inspect (nome do volume)
##### - (nome do volume) - Ex.: volume01, volume02...
- CreatedAt: Data e hora da criação do volume
- Driver:
- Labels:
- Mountpoint: Local de montagem do volume
- Name: Nome do volume 
- Options:
- Scope:

<br>

### - Docker volume rm
#### Comando de remoção de volumes disponíveis no Docker Host
> docker volume rm (nome do volume)

` * Se o volume estiver sendo usado por algum container, ele não permitirá a exclusão. `

<br>

### - Docker volume rm $(docker volume ls -q)
#### Comando de remoção de todos os volumes disponíveis no Docker Host de uma só vez.
> docker volume rm $(docker volume ls -q)

` * Se o volume estiver sendo usado por algum container, ele não permitirá a exclusão. `

<br>

### - Docker volume prune
#### Comando para remoção/exclusão de todos os volumes no Docker Host de uma só vez.
> docker volume prune

` * Aplicando esse comando, será perguntado a certeza de remoção/exclusão [y] ou [n].
** Caso o volume esteja em uso por algum container, ele não poderá ser excluído, enquato a execução/processamento não for parado. `

<br>

### - Docker run -d --name=web01 -p 8080:80 -v /var/volumex nginx
#### Comando de criação de imagem com volume especificado
> docker run -d --name=web01 -p 8080:80 -v /var/volumex nginx
___


### - Docker login
#### Comando para fazer login no Dockerhub
> docker login

` * Caso já esteja logado no Dockerhub, ele retornará [Login Succeeded]. `
___


## - Docker network

### - Docker network ls
#### Comando para listar todas as redes
> docker network ls

- Network id: Hash de id
- Name: Nome da network
- Driver: 
- Scope:

` * `

<br>


### - Docker network create
#### Comando para criar network 
> docker network create -d bridge (nome da network)

` * Driver Default: bridge e Scope:local`

<br>

### - Docker network inspect
#### Comando para verificar informações da network
> docker network inspect (nome da network)
##### - (nome da network) - Ex.: net01,net02,net03...
` * `

<br>

### - Docker network rm
#### Comando para verificar informações da network
> docker network rm (nome da network ou id da network)
##### - (nome da network) - Ex.: net01,net02,net03...
##### - (id da network) - Ex.: hash...
` * Caso a network esteja sendo usada por algum container, primeiro deverá ser desconectada `

<br>

### - Docker network prune
#### Comando para excluir/remover todas as networks que não estiverem sendo usadas
> docker network prune

` * Caso a network esteja sendo usada por algum container, primeiro deverá ser desconectada, ** Como são várias networks, abrirá um warming [y] ou [n]. `

<br>

___ 

### - Docker commit
#### Comando para 
> docker commit (nome do container ou id do container) ailtonmacedo/nginx-commit:v2

___


### - Docker push
#### Comando para 
> docker push (nome da imagem)

___


### - Docker pull
#### Comando para baixar imagens do Dockerhub
> docker pull (parametro)
##### - (parametro) - Ex.: ubuntu, dotnetcore, node...

` * Quando for dado o comando docker pull (nome da imagem), o docker irá buscar a imagem no Docker Host, caso ele não encontre, fará o download. `

___

![](https://repository-images.githubusercontent.com/288003065/15b03400-e75f-11ea-9341-6696b161a9e2)
<br>
[fonte da imagem](http://www.w3big.com/pt/docker/docker-architecture.html)