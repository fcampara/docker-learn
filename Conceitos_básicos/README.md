# Conceitos básicos

- [O que são Containers](#o-que-são-containers)
- [Como funcionam os Containers](#como-funcionam-os-containers)
- [Como o Docker funciona](#como-o-docker-funciona)
- [Principais comandos utilizando Docker](#principais-comandos-utilizando-docker)
- [Dockerfile](#dockerfile)
- [Trabalhando com imagens Docker](#trabalhando-com-imagens-docker)

## O que são Containers

Um container é um padrão de unidade de software que empacota código e todas as dependências de uma aplicação fazendo que a mesma seja executada rapidamente de forma confiável de um ambiente computacional para o outro.

## Como funcionam os Containers

Ele utiliza images para executar um processo, certas informações pode ser escrever e ler informações do container pois existe uma camada de leitura e escrita no container. Logo todas as informações inseridas num contâiner serão sumidas após a finalização do container.

Com o [dockerfile](#dockerfile) pode gerar uma imagem que será utilizada dentro de um container.

### Namespaces

É um isolamento de processos, cada container possuí vários processos para ser executados, o container apenas enxerga os processos internos, os processos pode ser separados por PID, Users, Network e File system.

### Cgroups

É um controlador de recursos computacionais no containers, é uma forma de definir quanto de processo pode ser carregado por cada container para não haver interferências de outros processos

### File System

OFS (Overlay File System), é inteção de trabalhar com camadas, isso serve para evitar o reuso de dependências, sempre que houver a necessidade de aumentar o processo da minha aplicação não é necessário utilizar todas as minhas depedências novamente, apenas a aplicação.

### Imagens

As imagens são criadas a partir camadas (graças ao OFS), elas trabalham com depedências, resumindo uma image é um conjunto de depedências encadeada.

Todas as imagens são salvas em um IMAGE REGISTRY

- são imutáveis

## Como o Docker funciona

Docker criou uma solução que integra namespace, cgroups e file system. Todo isso fica rodando dentro do Docker Host e para se comunicar com ele basta utilizar o Docker Client

### Docker Host

Fica executando um processo (daemon) que disponibiliza uma API para se comunicar com o Host, também possui um cache, é utilizado para guarda as imagens que foram feitas Pull ou Push, ele utiliza o cache para não ter que ficar sempre fazer o download da imagem. Também possui um gerenciamento de volumes, possibilita compatilhar uma pasta do computador com o Docker Host. Por último existe a área de Network, ele possibilita uma comunicação entre os processos.

### Docker Client

O Docker Client sempre se comunica com o daemon disponibilizado dentro do Docker Host. Consegue executar os comandos necessários para trabalha com o Docker

- Containers
- Run, Pull, Push
- Volumes
- Network

## Principais comandos utilizando Docker

## Dockerfile

Uma forma de criação de imagens, é um arquivo declarativo onde é escrito como a image será construida.

### FROM

Nome da imagem que será baixada (irá baixar todas a imagem e suas depedências)

### RUN

Possibilita rodar comandos

### EXPOSE

Forma de criar uma exposição da imagem

## Trabalhando com imagens Docker
