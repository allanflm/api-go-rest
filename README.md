# API REST com Go, Docker e React

## Índice
1. [Introdução](#introdução)
2. [Tecnologias Utilizadas](#tecnologias-utilizadas)
3. [Arquitetura do Projeto](#arquitetura-do-projeto)
4. [Funcionalidades](#funcionalidades)

---

## 1. Introdução

Este projeto consiste em uma API RESTful desenvolvida com a linguagem Go (Golang). A API permite a criação, leitura, atualização e exclusão (CRUD) de produtos, conectando-se a um banco de dados via Docker. O projeto também inclui a integração com um front-end React, implementando políticas de segurança, como CORS (Cross-Origin Resource Sharing), e middlewares para controlar o fluxo de requisições.

A principal motivação foi criar uma aplicação backend robusta, escalável e modular, utilizando boas práticas do padrão MVC (Model-View-Controller).

---

## 2. Tecnologias Utilizadas

### Back-end:
- **Go (Golang)**: Linguagem principal do projeto, escolhida por sua eficiência, simplicidade e forte suporte a concorrência.
- **Docker**: Utilizado para gerenciar e orquestrar o banco de dados (PostgreSQL, MySQL, ou outro).
- **GORM**: ORM utilizado para interagir com o banco de dados de maneira mais fácil e eficiente.
- **gorilla/mux**: Biblioteca utilizada para o roteamento das requisições HTTP.

### Front-end:
- **React**: Interface gráfica que consome os endpoints da API e exibe os dados de maneira dinâmica.
  
### Banco de Dados:
- **PostgreSQL/MySQL**: O banco de dados foi gerenciado através de containers Docker, garantindo um ambiente isolado e configurável.

---

## 3. Arquitetura do Projeto

A aplicação segue o padrão **MVC (Model-View-Controller)**:

- **Model**: Representa a estrutura dos dados e as regras de negócio. Implementado com structs do Go e usando o GORM para a persistência de dados.
- **Controller**: Contém a lógica para processar as requisições HTTP, receber dados do frontend e devolver as respostas.
- **View**: Neste contexto, o "View" é o front-end React que consome os dados da API.
  
### Organização de Pastas:
- `/controllers`: Controladores da API (regras de negócio).
- `/models`: Modelos de dados e conexões com o banco.
- `/routes`: Configuração dos endpoints e roteamento.
- `/middlewares`: Funções intermediárias para tratamento das requisições (e.g., autenticação, CORS, logs).
- `/docker`: Configuração do Docker (e.g., Dockerfile, docker-compose.yml).

---

## 4. Funcionalidades

A API implementa operações CRUD básicas para a entidade "Produto", que inclui campos como:
- **ID**: Identificador único.
- **Nome**: Nome do produto.
- **Descrição**: Descrição detalhada.
- **Preço**: Valor monetário.
- **Quantidade**: Quantidade disponível no estoque.

### CRUD:
- **Criar produto**: Adiciona um novo produto no banco de dados.
- **Listar produtos**: Retorna uma lista com todos os produtos.
- **Buscar produto por ID**: Retorna um produto específico.
- **Atualizar produto**: Atualiza os detalhes de um produto existente.
- **Deletar produto**: Remove um produto do banco de dados.

---
