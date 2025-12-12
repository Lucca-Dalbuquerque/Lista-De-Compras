# 🛒 Lista de Compras

Aplicação web fullstack para gerenciamento de lista de compras, desenvolvida com foco em simplicidade, arquitetura REST e boas práticas de DevOps. O sistema permite criar, visualizar, atualizar e remover itens de uma lista de compras, com estatísticas em tempo real e ambiente totalmente containerizado com Docker.

---

## 📌 Visão Geral

O **Simple Task Manager** é uma aplicação web que resolve o problema de organização de listas de compras de forma simples e eficiente. A aplicação pode ser acessada via navegador e funciona em qualquer dispositivo, sem necessidade de instalação.

O projeto segue o modelo **Frontend + Backend + Banco de Dados**, utilizando uma API REST para comunicação entre as camadas.

---

## 🚀 Funcionalidades

* ➕ Adicionar itens à lista (nome e quantidade)
* 📋 Listar todos os itens cadastrados
* ✅ Marcar e desmarcar itens como comprados
* 🗑️ Remover itens individualmente
* 🧹 Limpar todos os itens comprados
* 📊 Visualizar estatísticas em tempo real:

  * Total de itens
  * Itens pendentes
  * Itens comprados
* ❤️ Health check da API

---

## 🏗️ Arquitetura

A aplicação segue o padrão **Cliente-Servidor em 3 camadas**:

```
Usuário
   ↓
Frontend (HTML/CSS/JS - Nginx)
   ↓  HTTP / JSON
Backend (Node.js + Express)
   ↓  SQL
Banco de Dados (PostgreSQL)
```

* **Frontend**: Interface web responsiva
* **Backend**: API REST responsável pela lógica de negócio
* **Banco de Dados**: Persistência dos dados

---

## 🧰 Tecnologias Utilizadas

### Backend

* Node.js 18
* Express.js
* PostgreSQL (pg)
* CORS

### Frontend

* HTML5
* CSS3 (Flexbox, Grid, Gradientes)
* JavaScript (Fetch API)
* Nginx

### DevOps / Infraestrutura

* Docker
* Docker Compose
* Git & GitHub
* AWS EC2 (deploy)

### Testes e Documentação

* Postman
* cURL

---

## 📁 Estrutura do Projeto

```
simple-task-manager/
│
├── backend/
│   ├── server.js          # API REST
│   ├── package.json       # Dependências
│   └── Dockerfile         # Container do backend
│
├── frontend/
│   ├── index.html         # Interface web
│   └── Dockerfile         # Container do frontend
│
├── postman/
│   └── Shopping_List_API.postman_collection.json
│
├── docker-compose.yml     # Orquestração dos containers
├── .gitignore
├── README.md
└── COMMANDS.md
```

---

## 🔗 API REST

### Base URL

```
http://localhost:3000/api
```

### Endpoints Principais

| Método | Endpoint   | Descrição            |
| ------ | ---------- | -------------------- |
| GET    | /items     | Lista todos os itens |
| POST   | /items     | Cria um novo item    |
| GET    | /items/:id | Busca item por ID    |
| PUT    | /items/:id | Atualiza um item     |
| DELETE | /items/:id | Remove um item       |
| GET    | /stats     | Retorna estatísticas |
| GET    | /health    | Health check da API  |

### Exemplo de Resposta

```json
{
  "success": true,
  "data": {
    "id": 1,
    "name": "Arroz",
    "quantity": 2,
    "purchased": false,
    "created_at": "2024-12-10T10:30:00.000Z"
  }
}
```

---

## 🗄️ Banco de Dados

Tabela principal: **shopping_items**

| Campo      | Tipo      | Descrição           |
| ---------- | --------- | ------------------- |
| id         | SERIAL    | Identificador único |
| name       | VARCHAR   | Nome do item        |
| quantity   | INTEGER   | Quantidade          |
| purchased  | BOOLEAN   | Status de compra    |
| created_at | TIMESTAMP | Data de criação     |

---

## 🐳 Docker & Containerização

Todos os serviços são executados via **Docker Compose**.

### Containers

* Backend (Node.js)
* Frontend (Nginx)
* Banco de Dados (PostgreSQL)

### Comandos Principais

```bash
# Subir a aplicação
docker-compose up -d

# Ver logs
docker-compose logs -f

# Parar serviços
docker-compose down

# Rebuild
docker-compose up -d --build
```

---

## ☁️ Deploy (AWS)

A aplicação pode ser executada em uma instância **AWS EC2**, utilizando Docker.

### Passos resumidos

```bash
# Clonar o repositório
git clone https://github.com/usuario/simple-task-manager.git
cd simple-task-manager

# Subir os containers
docker-compose up -d
```

### Portas Utilizadas

| Serviço    | Porta |
| ---------- | ----- |
| Frontend   | 8080  |
| Backend    | 3000  |
| PostgreSQL | 5432  |

---

## 🧪 Testes

* Testes manuais via Postman
* Testes de API com cURL
* Testes de integração do fluxo completo
* Testes de responsividade (Desktop, Tablet e Mobile)

---

## 📊 Resultados

* API REST funcional
* Interface responsiva e intuitiva
* Persistência de dados funcionando
* Containers estáveis
* Deploy em nuvem operacional

---

## 🔮 Próximas Melhorias

* Autenticação de usuários
* Múltiplas listas de compras
* Compartilhamento de listas
* CI/CD automatizado
* Testes unitários
* HTTPS com certificado SSL

---

## 📄 Licença

Projeto desenvolvido para fins educacionais.

---

## ✅ Status

✔️ Concluído e funcional
