\\'_'/



# Projeto: Aplicação Hello World em Node.js com Docker e Kubernetes

## Descrição

Este projeto consiste em uma aplicação simples desenvolvida em Node.js que retorna "Hello World" em um endpoint. O objetivo é demonstrar o uso de Docker para criar uma imagem multistaging, publicá-la no Docker Hub e realizar o deploy em um cluster Kubernetes utilizando Minikube.


## Pré-requisitos

- [Docker](https://docs.docker.com/get-docker/) instalado
- [Minikube](https://minikube.sigs.k8s.io/docs/start/) instalado
- Conta no [Docker Hub](https://hub.docker.com/) 

## Configuração e Execução

### 1. Clonar o Repositório

Clone este repositório em sua máquina local:

```bash
git clone https://github.com/seu_usuario/seu_repositorio.git
cd seu_repositorio
```

### 2. Construir a Imagem Docker
Construa a imagem Docker utilizando o seguinte comando:

```bash
docker build -t seu_usuario/node-app:latest .
```

## 3. Publicar a Imagem no Docker Hub
Faça login no Docker Hub:

```bash
docker login
```
Publique a imagem criada:

```bash
docker push seu_usuario/node-app:latest
```

### 4. Iniciar o Minikube
Inicie um cluster Minikube:
```bash
minikube start
```

### 5. Realizar o Deploy
Crie um Deployment utilizando a imagem publicada:

```bash
kubectl apply -f deployment.yaml
```
Exponha a aplicação com um Service do tipo NodePort:

```bash
kubectl apply -f service.yaml
```

# 6. Acessar a Aplicação
Para acessar a aplicação, execute:

```bash
minikube service nome-do-seu-service --url
```
### Pipeline CI/CD
A configuração da pipeline CI/CD está no diretório .github/workflows. Ela realiza os seguintes passos:

Faz o checkout do código.
Realiza o login no Docker Hub.
Constrói a imagem Docker e publica no Docker Hub.
Conclusão
Este projeto exemplifica o uso de Docker e Kubernetes para desenvolver, containerizar e implementar uma aplicação Node.js simples.


## Autores

- [Tayane Cibely](https://github.com/tayanecibely
