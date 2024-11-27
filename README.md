
---

# CRUD de Produtos com Spring Boot

Este repositório contém um projeto básico de CRUD (Create, Read, Update, Delete) para gerenciamento de produtos, desenvolvido em **Java** usando **Spring Boot**. O sistema utiliza um banco de dados em memória **H2** para armazenamento e apresenta endpoints RESTful para as operações.

## **Índice**

1. [Visão Geral](#visão-geral)
2. [Funcionalidades](#funcionalidades)
3. [Tecnologias Utilizadas](#tecnologias-utilizadas)
4. [Configurações do Projeto](#configurações-do-projeto)
5. [Como Rodar o Projeto](#como-rodar-o-projeto)
6. [Endpoints da API](#endpoints-da-api)
7. [Exemplo de Requisições](#exemplo-de-requisições)
8. [Acesso ao Banco de Dados H2](#acesso-ao-banco-de-dados-h2)
9. [Melhorias Futuras](#melhorias-futuras)
10. [Contribuição](#contribuição)

---

## **Visão Geral**

Este projeto foi criado para fins de aprendizado e prática no desenvolvimento de APIs RESTful utilizando Spring Boot. Ele pode ser usado como base para projetos maiores ou como referência para estudantes e desenvolvedores iniciantes.

O sistema permite o gerenciamento de produtos com as operações básicas:

- Criar (POST)
- Listar (GET)
- Atualizar (PUT)
- Deletar (DELETE)

---

## **Funcionalidades**

- Gerenciamento de produtos via API RESTful.
- Operações CRUD (Create, Read, Update, Delete).
- Banco de dados em memória **H2** para armazenamento.
- Teste e consumo de endpoints usando ferramentas como **Postman** ou **cURL**.
- Console do H2 acessível para visualização do banco de dados.

---

## **Tecnologias Utilizadas**

- **Java 17**
- **Spring Boot 3.0**
  - Spring Web
  - Spring Data JPA
- **H2 Database** (Banco de dados em memória)
- **Maven** (Gerenciador de dependências)

---

## **Configurações do Projeto**

Certifique-se de ter as seguintes ferramentas instaladas no seu sistema:

- **Java JDK 17 ou superior** 
- **Maven** 
- **Postman** ou outra ferramenta para teste de APIs (opcional)

---

## **Como Rodar o Projeto**

Siga os passos abaixo para configurar e rodar o projeto:

### 1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/nome-do-repositorio.git
cd nome-do-repositorio
```

### 2. Construir o projeto com Maven

```bash
mvn clean install
```

### 3. Rodar a aplicação

```bash
mvn spring-boot:run
```

O servidor será iniciado na porta **8080**.

### 4. Acessar a API

A API estará disponível em:

```
http://localhost:8080
```

---

## **Endpoints da API**

Aqui estão os endpoints disponíveis:

### 1. Listar todos os produtos
- **Método**: GET  
- **URL**: `/produtos`  
- **Descrição**: Retorna a lista de todos os produtos.

### 2. Obter um produto pelo ID
- **Método**: GET  
- **URL**: `/produtos/{id}`  
- **Descrição**: Retorna os detalhes de um produto específico.  

### 3. Criar um novo produto
- **Método**: POST  
- **URL**: `/produtos`  
- **Descrição**: Cria um novo produto no sistema.  
- **Body Exemplo**:
  ```json
  {
    "nome": "Produto A",
    "preco": 100.0
  }
  ```

### 4. Atualizar um produto existente
- **Método**: PUT  
- **URL**: `/produtos/{id}`  
- **Descrição**: Atualiza as informações de um produto.  
- **Body Exemplo**:
  ```json
  {
    "nome": "Produto Atualizado",
    "preco": 120.0
  }
  ```

### 5. Deletar um produto
- **Método**: DELETE  
- **URL**: `/produtos/{id}`  
- **Descrição**: Remove um produto do sistema.

---

## **Exemplo de Requisições**

### 1. Criar Produto

**Requisição**:
```http
POST /produtos
Content-Type: application/json

{
  "nome": "Produto X",
  "preco": 150.0
}
```

**Resposta**:
```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": 1,
  "nome": "Produto X",
  "preco": 150.0
}
```

### 2. Listar Produtos

**Requisição**:
```http
GET /produtos
```

**Resposta**:
```http
HTTP/1.1 200 OK
Content-Type: application/json

[
  {
    "id": 1,
    "nome": "Produto X",
    "preco": 150.0
  }
]
```

---

## **Acesso ao Banco de Dados H2**

O console do H2 pode ser acessado em:

```
http://localhost:8080/h2-console
```

- **JDBC URL**: `jdbc:h2:mem:produtos`
- **User Name**: `sa`
- **Password**: `password`

---

## **Melhorias Futuras**

Aqui estão algumas sugestões para expandir o projeto:

1. Implementar autenticação e autorização (ex.: Spring Security).
2. Adicionar paginação na listagem de produtos.
3. Integrar com um banco de dados real, como MySQL ou PostgreSQL.
4. Implementar tratamento de erros mais robusto.
5. Criar testes automatizados com JUnit.

---

## **Contribuição**

Sinta-se à vontade para contribuir com melhorias! Para isso:

1. Faça um fork do projeto.
2. Crie uma branch com sua feature ou correção.
3. Envie um Pull Request.

---
