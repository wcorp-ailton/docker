
![](https://repository-images.githubusercontent.com/288003065/0f781400-ed6c-11ea-9336-a2902c999870)

<br>

[fonte da imagem](http://www.w3big.com/pt/docker/docker-architecture.html)

### - Daemon Docker
#### O Docker daemon `( dockerd)` escuta as solicitações da API Docker e gerencia objetos Docker, como imagens, contêineres, redes e volumes. Um daemon também pode se comunicar com outros daemons para gerenciar os serviços Docker.
___

### - Client Docker
#### O cliente Docker `( docker)` é a principal maneira pela qual muitos usuários do Docker interagem com o Docker. Quando você usa comandos como `docker run`, o cliente envia esses comandos para `dockerd`, que os executa. O `docker` comando usa a API Docker. O cliente Docker pode se comunicar com mais de um daemon.
___

### - Docker registries
#### Um registro Docker armazena imagens Docker. O Docker Hub é um registro público que qualquer pessoa pode usar e o Docker está configurado para procurar imagens no Docker Hub por padrão. Você pode até executar seu próprio registro privado. Quando você usa os comandos `docker pull` ou `docker run`, as imagens necessárias são retiradas do registro configurado. Quando você usa o `docker push` comando, sua imagem é enviada para o registro configurado.
___

### - Host Docker
####
___

### - Container
####
___ 

### - Images
#### Uma imagem é um modelo somente leitura com instruções para criar um contêiner Docker. Freqüentemente, uma imagem é baseada em outra imagem, com alguma personalização adicional. Por exemplo, você pode construir uma imagem que é baseada na `ubuntu` imagem, mas instala o servidor web Apache e seu aplicativo, bem como os detalhes de configuração necessários para fazer seu aplicativo funcionar.

<br>

#### Você pode criar suas próprias imagens ou usar apenas aquelas criadas por terceiros e publicadas em um registro. Para construir sua própria imagem, você cria um Dockerfile com uma sintaxe simples para definir as etapas necessárias para criar a imagem e executá-la. Cada instrução em um Dockerfile cria uma camada na imagem. Quando você altera o Dockerfile e reconstrói a imagem, apenas as camadas que foram alteradas são reconstruídas. Isso é parte do que torna as imagens tão leves, pequenas e rápidas, quando comparadas a outras tecnologias de virtualização.
___

### - Services
#### Os serviços permitem que você dimensione contêineres em vários daemons do Docker, que funcionam juntos como um enxame com vários gerentes e trabalhadores . Cada membro de um swarm é um daemon do Docker e todos os daemons se comunicam usando a API Docker. Um serviço permite que você defina o estado desejado, como o número de réplicas do serviço que devem estar disponíveis a qualquer momento. Por padrão, o serviço tem balanceamento de carga em todos os nós de trabalho. Para o consumidor, o serviço Docker parece ser um único aplicativo. O Docker Engine suporta o modo swarm no Docker 1.12 e superior.
___

### - Volume
####
___

### - Network
####
___

### - Dockerhub
####
___

### - Dockerfile
####

