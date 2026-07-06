
# API de Usuários

API REST desenvolvida com **Spring Boot 3** para gerenciamento de usuários, autenticação com JWT e consulta automática de endereços utilizando a API do ViaCEP.

## Tecnologias

- Java 21
- Spring Boot 3.5
- Spring Security + JWT
- Spring Data JPA
- PostgreSQL
- OpenFeign
- Swagger / OpenAPI
- Lombok
- Docker / Docker Compose

## Funcionalidades

- Cadastro de usuários
- Login com autenticação JWT
- Consulta de usuário por e-mail
- Cadastro de endereços e telefones
- Busca automática de endereço pelo CEP (ViaCEP)
- Tratamento global de exceções
- Documentação da API com Swagger

## Estrutura do projeto

```
src/main/java
├── business           # Regras de negócio
├── controller         # Endpoints REST
├── infrastructure
│   ├── clients        # Cliente ViaCEP
│   ├── entity         # Entidades JPA
│   ├── repository     # Repositórios
│   ├── security       # JWT e configuração de segurança
│   └── exceptions     # Tratamento de erros
```

## Configuração

Configure o banco PostgreSQL em `application.properties`:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/db_usuario
spring.datasource.username=postgres
spring.datasource.password=senha123
```

## Executando

```bash
docker-compose up -d
./gradlew bootRun
```

Ou:

```bash
./gradlew build
java -jar build/libs/usuario-0.0.1-SNAPSHOT.jar
```

## Endpoints principais

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| POST | `/usuario` | Cadastrar usuário |
| POST | `/usuario/login` | Realizar login |
| GET | `/usuario?email=` | Buscar usuário por e-mail |

## Documentação

Após iniciar a aplicação:

```
http://localhost:8080/swagger-ui/index.html
```

## Autor

Desenvolvido por Guilherme Felipe.
