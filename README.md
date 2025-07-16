# Store API

**Autor: Denis - Geração Tech**

API RESTful para backend de e-commerce, com gerenciamento de usuários, produtos e categorias.

## Tecnologias
- Node.js
- Express.js
- Sequelize (PostgreSQL)
- Docker
- JWT (autenticação)
- Bcrypt.js (hash de senhas)
- Jest & Supertest (testes)

## Funcionalidades
- CRUD de Usuários, Produtos e Categorias
- Autenticação JWT
- Proteção de rotas via middleware
- Busca avançada de produtos
- Estrutura de serviços para lógica de negócio

## Endpoints Principais
Prefixo: `/v1`

| Método | Endpoint                | Descrição                        | Auth |
| ------ | ---------------------- | -------------------------------- | ---- |
| POST   | /usuario               | Cria usuário                     | Não  |
| POST   | /usuario/token         | Login e token JWT                | Não  |
| GET    | /usuario/:id           | Busca usuário por ID             | Não  |
| PUT    | /usuario/:id           | Atualiza usuário                 | Sim  |
| POST   | /categoria             | Cria categoria                   | Sim  |
| GET    | /categoria/pesquisa    | Busca categorias                 | Não  |
| POST   | /produto               | Cria produto                     | Sim  |
| GET    | /produto/pesquisa      | Busca produtos                   | Não  |
| GET    | /produto/:id           | Busca produto por ID             | Não  |

## Como executar

Pré-requisitos: Node.js 16+, Docker Desktop

```bash
# Instale dependências
yarn install # ou npm install

# Copie o .env de exemplo
yarn copy .env.example .env # ou copy .env.example .env (Windows)

# Inicie o banco PostgreSQL com Docker
docker run --name store-db -e POSTGRES_PASSWORD=docker -e POSTGRES_USER=docker -e POSTGRES_DB=store_db -p 5432:5432 -d postgres

# Rode a API
yarn dev # ou npm run dev

# Testes
yarn test # ou npm test
```

A API estará disponível em http://localhost:3001

