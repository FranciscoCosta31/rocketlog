# RocketLog 🚀

O **RocketLog** é uma API para gestão de entregas e logs, permitindo o controle de usuários, encomendas e o histórico de estados de cada entrega em tempo real.

## 🛠 Tecnologias Utilizadas

* **Node.js** & **TypeScript**
* **Express**: Framework web.
* **Prisma ORM**: Manipulação da base de dados PostgreSQL.
* **Zod**: Validação de esquemas e dados.
* **Jest**: Framework de testes automatizados.
* **Docker**: Para subir o banco de dados rapidamente.

## 📋 Funcionalidades

* **Gestão de Usuários**: Registro e autenticação (suporta papéis como `ADMIN` e `CUSTOMER`).
* **Gestão de Entregas**: Criação, atualização de status e listagem.
* **Logs de Entrega**: Registro detalhado de ocorrências de cada encomenda.
* **Autenticação JWT**: Segurança nas rotas privadas.

## 🚀 Como Executar

1. **Clone o repositório:**
```bash
git clone https://github.com/teu-utilizador/rocketlog.git
cd rocketlog

```


2. **Instale as dependências:**
```bash
npm install

```


3. **Configure o ambiente:**
Crie um arquivo `.env` na raiz do projeto seguindo o modelo do `.env-example`.
4. **Inicie o banco de dados (Docker):**
```bash
docker-compose up -d

```


5. **Execute as Migrations e inicie o servidor:**
```bash
npx prisma migrate dev
npm run dev

```



---

## 💜 Testando a API com Insomnia

Para facilitar os testes das rotas (Users, Sessions, Deliveries, etc.), foi incluído um arquivo de coleção do Insomnia no projeto.

**Como utilizar:**

1. Abra o [Insomnia](https://insomnia.rest/).
2. Clique em **Import** (ou `Ctrl + Shift + I`).
3. Selecione o arquivo `Insomnia_2026-01-13.yaml` localizado na raiz deste projeto.
4. O Insomnia irá carregar todas as rotas configuradas, incluindo os ambientes e as variáveis de base (URL).
5. Certifique-se de executar o login (`Sessions`) primeiro para obter o token de autenticação, caso as rotas exijam.

---

## 🧪 Testes Automatizados

Para rodar os testes unitários e de integração:

```bash
npm test

```

## 🛣 Rotas Principais

* `POST /users`: Cadastro de usuário.
* `POST /sessions`: Login e geração de token JWT.
* `POST /deliveries`: Criação de nova entrega (requer ADMIN).
* `PATCH /deliveries/:id/status`: Atualizar estado da entrega.
* `GET /delivery-logs/:delivery_id`: Listar histórico de uma entrega.

