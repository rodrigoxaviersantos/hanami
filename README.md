
<h1 align="center">  Projeto Hanami </h1>

<p align="center">
  Template WebAPI 
</p>

# Pré-requisitos

1. Java Development Kit (JDK) 8 ou superior
2. Maven
3. MySQL Server
4. MySQL Workbench (opcional, para gerenciar o banco de dados)
5. IDE (como IntelliJ IDEA, Eclipse, VS Code, etc.)

1. Criação do Projeto Spring Boot

Spring Initializr (https://start.spring.io/) para gerar o esqueleto do projeto.

* Project: Maven Project
* Language: Java
* Spring Boot Version: 2.7.5 (ou a versão mais recente)
* Group: com.example
* Artifact: webapi-template
* Name: webapi-template
* Package Name: com.example.webapi
* Packaging: Jar
* Java Version: 8 ou superior
* Dependencies: Spring Web, Spring Data JPA, MySQL Driver

2. Configuração do pom.xml

```xml

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>webapi-template</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <packaging>jar</packaging>

    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.7.5</version>
        <relativePath/> 
    </parent>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-data-jpa</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <scope>runtime</scope>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>
</project>

```

3. Configuração do Banco de Dados

No arquivo src/main/resources/application.properties, configure a conexão com o banco de dados MySQL:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/nome_do_banco?useSSL=false&serverTimezone=UTC
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect

```

Substitua nome_do_banco, seu_usuario e sua_senha pelos valores apropriados.

4. Estrutura de Diretórios

```css
src
└── main
    ├── java
    │   └── com
    │       └── example
    │           └── webapi
    │               ├── WebapiApplication.java
    │               ├── controller
    │               ├── model
    │               ├── repository
    │               └── service
    └── resources
        ├── application.properties
        └── static
```


5. Criação das Entidades, Repositórios e Serviços

* Entidade
* Repositório
* Serviço
*  Criação dos Controladores
*  Classe Principal

## Executando a Aplicação

1. Criar o Banco de Dados: No MySQL Workbench, crie um banco de dados com o nome especificado no application.properties.
   
2. Rodar a Aplicação: Execute a classe WebapiApplication a partir da sua IDE ou utilize o comando mvn spring-boot:run no terminal.

## Testando a API

* Para listar todos os usuários: GET http://localhost:8080/api/usuarios
  
* Para criar um novo usuário: POST http://localhost:8080/api/usuarios com um corpo JSON, por exemplo:

```json
{
    "nome": "João",
    "email": "joao@example.com"
}

```














