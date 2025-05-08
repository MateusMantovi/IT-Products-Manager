# Sistema de Gerenciamento de Produtos de Informática - **GerTi**

O **GerTi** (Gerenciador de Tecnologia da Informação) é um sistema completo para controle de produtos de informática, desenvolvido com **Spring Boot 3.4.5**, **PostgreSQL** e **Maven**.

---

##  Tecnologias Utilizadas

| Tecnologia      | Versão   | Descrição                               |
|-----------------|----------|-----------------------------------------|
| Java            | 22      | Linguagem principal do backend          |
| Spring Boot     | 3.4.5    | Framework para APIs REST                |
| PostgreSQL      | 17     | Banco de dados relacional               |
| Maven           | 3.9.6    | Gerenciador de dependências             |
| Lombok          | 1.18.30  | Redução de boilerplate code             |
| JPA/Hibernate   | 3.6.0    | ORM para persistência de dados          |
| Spring Web      | -        | Construção de endpoints REST            |
| Spring Data JPA | -        | Repositórios e consultas automatizadas  |

---

## Estrutura do Projeto

```bash
backend/
├── src/
│   ├── main/
│   │   ├── java/com/gerti/backend/
│   │   │   ├── config/             # Configurações globais (CORS, segurança)
│   │   │   ├── controller/         # Endpoints REST (@RestController)
│   │   │   ├── dto/                # Objetos de transferência de dados (DTOs)
│   │   │   ├── exception/          # Tratamento de erros global
│   │   │   ├── model/              # Entidades JPA (Product, Category, etc.)
│   │   │   ├── repository/         # Interfaces Spring Data JPA
│   │   │   ├── service/            # Lógica de negócio
│   │   │   └── BackendApplication.java  # Classe principal
│   │   └── resources/
│   │       ├── application.properties   # Configurações do app
│   │       └── data.sql                 # Dados iniciais (opcional)
│   └── test/                            # Testes unitários e integração
└── pom.xml                              # Dependências Maven
## ⚙ Configuração do Banco de Dados

## Crie o banco no PostgreSQL:

Para configurar o banco de dados, primeiramente, crie um banco de dados chamado `gerti_db` no seu servidor PostgreSQL. Você pode fazer isso executando o seguinte comando SQL:

```sql
CREATE DATABASE gerti_db;
Após criar o banco de dados, você precisará configurar a conexão da sua aplicação com ele. Isso geralmente é feito no arquivo application.properties (ou application.yml, dependendo da sua configuração Spring Boot). Adicione ou modifique as seguintes linhas com as suas configurações:

Properties

spring.datasource.url=jdbc:postgresql://localhost:5432/gerti_db
spring.datasource.username=postgres
spring.datasource.password=postgres
spring.jpa.hibernate.ddl-auto=update
Observações:

Certifique-se de que o spring.datasource.url esteja correto, apontando para o seu servidor PostgreSQL (neste caso, rodando localmente na porta padrão 5432) e para o banco de dados gerti_db.
Altere spring.datasource.username e spring.datasource.password com as credenciais de acesso ao seu banco de dados PostgreSQL, se necessário.
A propriedade spring.jpa.hibernate.ddl-auto=update configura o Hibernate para atualizar o schema do banco de dados automaticamente com base nas suas entidades JPA. Em ambientes de produção, pode ser preferível usar outras estratégias de gerenciamento de schema.

## Executar

Via Maven (PowerShell)
Se você estiver utilizando o Maven como ferramenta de build, você pode executar a aplicação diretamente a partir da linha de comando, utilizando o PowerShell (ou outro terminal):

PowerShell

cd backend
mvn clean install
mvn spring-boot:run

