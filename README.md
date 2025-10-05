# Gerenciador de Tarefas - Atividade de DevOps

![Status do Pipeline CI/CD](https://github.com/ScarletYkaro10/ci-cd-atividade-devops/actions/workflows/cicd-pipeline.yml/badge.svg)

Este é um projeto desenvolvido para a matéria de "Processos de Software e Gerência de Configuração com DevOps". O objetivo é criar uma API RESTful simples para gerenciamento de tarefas e, principalmente, construir um pipeline de CI/CD completo utilizando GitHub Actions.

## ✨ Funcionalidades

* API RESTful com operações CRUD completas para tarefas (Criar, Ler, Atualizar, Deletar).
* [cite_start]Utiliza banco de dados em memória H2 para simplicidade e testes. [cite: 17]
* Pipeline de CI/CD totalmente automatizado.

## 🚀 Tecnologias Utilizadas

* Java 21
* Spring Boot
* Spring Web
* Spring Data JPA
* Maven
* H2 Database
* Docker
* GitHub Actions

## ⚙️ Pipeline de CI/CD

O pipeline automatizado, configurado no arquivo `.github/workflows/cicd-pipeline.yml`, executa os seguintes jobs:

1.  [cite_start]**Build & Test:** A cada `push` ou `pull request` para a branch `main`, o código é compilado e os testes automatizados são executados com o Maven. [cite: 52, 59]
2.  [cite_start]**Build & Push Docker Image:** Se o job de build for bem-sucedido, uma imagem Docker da aplicação é construída e publicada no GitHub Container Registry. [cite: 76, 77]
3.  [cite_start]**(Próximos Passos) Deploy:** Etapas futuras para implantar a imagem em ambientes de homologação (staging) e produção. [cite: 101, 102]

## ⚡ Como Executar Localmente

1.  Clone o repositório:
    ```bash
    git clone [https://github.com/ScarletYkaro10/ci-cd-atividade-devops.git](https://github.com/ScarletYkaro10/ci-cd-atividade-devops.git)
    ```
2.  Navegue até a pasta do projeto Java:
    ```bash
    cd ci-cd-atividade-devops/gerenciadortarefas
    ```
3.  Execute a aplicação com o Maven:
    ```bash
    mvn spring-boot:run
    ```
4.  A API estará disponível em `http://localhost:8081`.

## Endpoints da API

| Método | Endpoint             | Descrição                  |
| :----- | :------------------- | :------------------------- |
| `POST` | `/api/tarefas`       | Cria uma nova tarefa       |
| `GET`  | `/api/tarefas`       | Lista todas as tarefas     |
| `GET`  | `/api/tarefas/{id}`  | Busca uma tarefa por ID    |
| `PUT`  | `/api/tarefas/{id}`  | Atualiza uma tarefa        |
| `DELETE`| `/api/tarefas/{id}`  | Deleta uma tarefa          |
