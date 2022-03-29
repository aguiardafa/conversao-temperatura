# Conteirizando sua aplicação NodeJS

Neste repositório apresento o resultado do encapsulamento de uma aplicação construída em NodeJS em um Container Docker. O arquivo de encapsulamento <b>Dockerfile</b> segue uma configuração básica, cujo  o principal objetivo é demonstra a facilidade na configuração, distribuição e execução de uma aplicação encapsulada em containers.

Há diversos benefícios em encapsular uma aplicação em container, mas o principal é a <b>portabilidade</b>, já que o projeto pode ser executado em qualquer máquina que possua o [Docker](https://docs.docker.com/get-docker/) instalado, tornando a Aplicação independente de sistema operacional e/ou qualquer outra configuração/instalação.

### Iniciativa Kubernetes - Aula 01:

Este repositório é parte da atividade pártica da Aula 01 do Curso [Iniciativa Kubernetes](https://iniciativakubernetes.com.br/), ocorrido de 28 de março a 01 de abril de 2022, promovido pela [Kubedev.io](https://kubedev.io/).

## 🛒 Requisitos do Projeto:

Antes de começar, você vai precisar ter instalado em sua máquina os seguintes recursos:

- [Git](https://git-scm.com/); e
- [Docker](https://docs.docker.com/get-docker/).

## 📀 Executando o Projeto:

Para testarmos a aplicação, temos que executar os 4 passos a seguir:
1. [Fazer download do Projeto](#download-github)
2. [Criar Imagem Docker](#build-image)
2. [Executar Container](#run-container)
3. [Acessar a Aplicação](#acessando-app)

<a name="download-github"></a>
### 1. Fazer downloado do Projeto

- Baixe este Repositório, executando o comando Git: 
```bash
git clone https://github.com/aguiardafa/conversao-temperatura
```

<a name="build-image"></a>
### 2. Criar Imagem Docker do Projeto

1. Acesse a pasta `src` do Repositório pelo terminal de comandos;
2. Execute o comando abaixo para criar a imagem Docker do projeto:
```bash
docker image build -t aguiardafa/conversao-temperatura:v1 .
```
3. Ainda pelo terminal, aberto na raiz da pasta `src` do Repositório, execute o comando para verificar se a criação da imagem foi bem sucedida:
```bash
docker image ls
```
- <b>Obs.:</b>Você terá uma resposta semelhante ao texto abaixo:
```bash
REPOSITORY                           TAG       IMAGE ID       CREATED         SIZE
aguiardafa/conversao-temperatura     v1        704a74ad5acf   2 hours ago     982MB
```

<a name="run-container"></a>
### 3. Executar Container do Projeto

1. Ainda na pasta `src` do Repositório, pelo terminal de comandos;
2. Execute o comando abaixo, que irá criar e executar o Container do projeto, com base na imagem criada:
```bash
docker container run -d --rm --name conversor -p 8080:8080 aguiardafa/conversao-temperatura:v1
```
3. Execute o comando para verificar se a criação do container foi bem sucedida:
```bash
docker container ls
```
- <b>Obs.:</b>Você terá uma resposta semelhante ao texto abaixo:
```bash
CONTAINER ID   IMAGE                                 COMMAND                  CREATED         STATUS         PORTS                                       NAMES
25e2187f9f4d   aguiardafa/conversao-temperatura:v1   "docker-entrypoint.s…"   7 seconds ago   Up 4 seconds   0.0.0.0:8080->8080/tcp, :::8080->8080/tcp   conversor
```

<a name="acessando-app"></a>
### 4. Acessar a Aplicação NodeJS

1. Pelo navegador de sua preferência, acesse a url `http://localhost:8080` para visualizar a Aplicação;
2. Se os passos anteriores foram executados corretamente, a resposta será semelhante a tela abaixo:
<p align="center"><img alt="Conversor de temperatura" id="foto1" title="#FotoProjeto" height="450px" src="https://raw.githubusercontent.com/aguiardafa/conversao-temperatura/main/.github/conversor-de-temperatura.png" /></p>

## 👨‍💻Autor
<a href="https://github.com/aguiardafa" style="text-decoration: none;">
<img style="border-radius: 50% !important;" src="https://avatars.githubusercontent.com/u/16319889?v=4" width="48px" height="48px" alt="Diego Aguiar"/>
<br />
<span> Feito por Diego Aguiar 👋 Entre em contato! </span> 
</a>
