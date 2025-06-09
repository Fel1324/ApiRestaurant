# ApiRestaurant

API para gerenciar pedidos das mesas de um restaurante.

## Descrição

Este projeto é uma API RESTful desenvolvida em Node.js com TypeScript, utilizando Express e Knex.js com banco de dados SQLite. Ela permite o gerenciamento de produtos, mesas, sessões de mesas e pedidos em um restaurante.

## Funcionalidades

- **Produtos:** Cadastro, listagem, atualização e remoção de produtos do cardápio.
- **Mesas:** Listagem das mesas do restaurante.
- **Sessões de Mesas:** Abertura, listagem e fechamento de sessões para controle de ocupação das mesas.
- **Pedidos:** Registro de pedidos vinculados a uma sessão de mesa, listagem dos pedidos e cálculo do total consumido.

## Rotas

### Produtos

- `GET /products` — Lista produtos (filtro opcional por nome).
- `POST /products` — Cadastra um novo produto.
- `PUT /products/:id` — Atualiza um produto existente.
- `DELETE /products/:id` — Remove um produto.

### Mesas

- `GET /tables` — Lista todas as mesas.

### Sessões de Mesas

- `GET /tables-sessions` — Lista sessões de mesas.
- `POST /tables-sessions` — Abre uma nova sessão para uma mesa.
- `PUT /tables-sessions/:id` — Fecha uma sessão de mesa.

### Pedidos

- `POST /orders` — Cria um novo pedido para uma sessão de mesa.
- `GET /orders/table-session/:table_session_id` — Lista pedidos de uma sessão de mesa.
- `GET /orders/table-session/:table_session_id/total` — Mostra o total consumido na sessão.

## Instalação

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/Fel1324/ApiRestaurant.git
   cd ApiRestaurant
   ```

2. **Instale as dependências:**
   ```bash
   npm install ou npm i
   ```

3. **Configure o banco de dados:**
   - As configurações estão em [`knexfile.ts`](knexfile.ts).
   - O banco utiliza SQLite e o arquivo será criado em `src/database/database.db`.

4. **Execute as migrations e seeds:**
   ```bash
   npm run knex migrate:latest
   npm run knex seed:run
   ```

5. **Inicie o servidor:**
   ```bash
   npm run dev
   ```

   O servidor estará disponível em `http://localhost:3333`.

## Estrutura do Projeto

- `src/controllers/` — Lógica das rotas.
- `src/routes/` — Definição das rotas da API.
- `src/database/` — Configuração do banco, migrations e seeds.
- `src/utils/` — Utilitários e classes auxiliares.
- `src/middlewares/` — Middlewares globais (ex: tratamento de erros).

## Tecnologias

- Node.js
- TypeScript
- Express
- Knex.js
- SQLite
- Zod (validação)

## Autor

Rafael Roberto de Oliveira

---

> Projeto desenvolvido para fins de estudo e demonstração de arquitetura de APIs RESTful.