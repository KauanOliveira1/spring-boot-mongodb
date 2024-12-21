    
# Spring Boot com MongoDB

Este é um projeto de exemplo que demonstra como integrar o framework **Spring Boot** com o banco de dados **MongoDB**. A aplicação é uma API RESTful que permite gerenciar entidades, exemplificando práticas modernas de desenvolvimento em Java.

## 📋 Funcionalidades

- CRUD de usuários (Create, Read, Update, Delete).
- Integração com MongoDB utilizando o Spring Data.
- Endpoints RESTful para operações no banco de dados.
- Configuração simplificada para execução local.

## 🛠️ Tecnologias Utilizadas

- **Java 17**: Linguagem de programação.
- **Spring Boot**: Framework para desenvolvimento rápido de aplicações.
  - **Spring Data MongoDB**: Biblioteca para integração com MongoDB.
  - **Spring Web**: Para criação de APIs RESTful.
  - **Spring Boot Starter Test**: Inclui bibliotecas para testes unitários e de integração.
- **MongoDB**: Banco de dados NoSQL.
- **Maven**: Gerenciador de dependências.
- **Postman** (opcional): Para testes de APIs.

## 🔍 Arquitetura do Projeto

A aplicação segue a arquitetura MVC (Model-View-Controller):

- **Model**: Representa as entidades da aplicação. Neste caso, as classes de modelo correspondem às coleções do MongoDB.
- **Repository**: Interfaces que estendem `MongoRepository` para fornecer operações CRUD automáticas.
- **Service**: Contém a lógica de negócios, intermediando as operações entre o controlador e o repositório.
- **Controller**: Gerencia as requisições HTTP e direciona as respostas apropriadas.

## 📚 Bibliotecas do Spring Utilizadas

- **Spring Boot Starter Data MongoDB**: Fornece integração com o MongoDB, permitindo operações de banco de dados de forma simplificada.
- **Spring Boot Starter Web**: Facilita a criação de aplicações web, incluindo dependências para desenvolvimento de APIs RESTful.
- **Spring Boot Starter Test**: Inclui bibliotecas para testes unitários e de integração, como JUnit e Mockito.

## 🚀 Como Executar o Projeto

### Pré-requisitos

- **Java 17** instalado.
- **Maven** instalado.
- **MongoDB** instalado e em execução.

### Passos

1. Clone este repositório:  
   ```bash
   git clone https://github.com/KauanOliveira1/spring-boot-mongodb.git
   cd spring-boot-mongodb
   ```

2. Configuração do MongoDB:  
   Por padrão, o Spring Boot tenta se conectar a uma instância do MongoDB hospedada localmente. Para configurar detalhes de conexão, como o banco de dados a ser utilizado e a URL/porta do host que executa o MongoDB, você pode adicionar as seguintes propriedades no arquivo `application.properties`:

   ```properties
   spring.data.mongodb.host=localhost
   spring.data.mongodb.port=27017
   spring.data.mongodb.database=nome_do_banco_de_dados
   ```

3. Compile e execute o projeto:  
   ```bash
   mvn spring-boot:run
   ```

4. Acesse a aplicação:  
   A API estará disponível em `http://localhost:8080`.

## 📝 Endpoints da API

### Usuários

- **GET** `/users`: Retorna todos os usuários.
- **GET** `/users/{id}`: Retorna um usuário específico por ID.
- **POST** `/users`: Cria um novo usuário.  
  **Exemplo de Body JSON**:  
  ```json
  {
    "name": "João da Silva",
    "email": "joao@example.com"
  }
  ```
- **PUT** `/users/{id}`: Atualiza um usuário existente.  
  **Exemplo de Body JSON**:  
  ```json
  {
    "name": "João da Silva Atualizado",
    "email": "joao.atualizado@example.com"
  }
  ```
- **DELETE** `/users/{id}`: Exclui um usuário por ID.

## 🧪 Testes

Você pode usar ferramentas como **Postman** ou **cURL** para testar os endpoints da API.

Exemplo usando cURL:

```bash
curl -X GET http://localhost:8080/users
```

## 📦 Dependências

As dependências do projeto são gerenciadas pelo Maven. No arquivo `pom.xml`, as seguintes dependências são declaradas:

```xml
<dependencies>
    <!-- Dependência para o Spring Boot Starter Data MongoDB -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-mongodb</artifactId>
    </dependency>
    <!-- Dependência para o Spring Boot Starter Web -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <!-- Dependência para o Spring Boot Starter Test -->
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>
</dependencies>
```
