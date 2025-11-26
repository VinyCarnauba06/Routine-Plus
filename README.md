# Routine+

 Organização Pessoal com Dados Climáticos em Tempo Real

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Backend: Node.js](https://img.shields.io/badge/Backend-Node.js%20%26%20Express-43853D.svg?style=flat)]()
[![Database: MongoDB](https://img.shields.io/badge/Database-MongoDB-47A248.svg?style=flat)]()

---

## 1. Visão Geral do Projeto

O **Routine+** é um sistema web desenvolvido para auxiliar no gerenciamento de tarefas diárias, integrando informações climáticas obtidas em tempo real.
O projeto segue uma arquitetura Full-Stack organizada, onde o backend (Node.js/Express) fornece uma API REST e o frontend (HTML/CSS/JS) consome essa API.

O objetivo é oferecer:

* Controle de tarefas
* Categorias filtráveis
* Alertas inteligentes baseados no clima
* Persistência de dados em nuvem
* Deploy completo e acessível publicamente

---

## 2. Funcionalidades Principais

### • Gerenciamento de Tarefas

* Criar tarefas
* Listar apenas as tarefas pendentes
* Concluir tarefas
* Excluir tarefas

### • Categorias Filtráveis

O usuário pode visualizar tarefas por:

* Casa
* Trabalho
* Estudos
* Ao ar livre

### • Integração Climática

Para tarefas classificadas como **“Ao ar livre”**, o sistema:

1. Consulta a previsão do tempo via OpenWeather
2. Detecta risco de chuva
3. Exibe alertas sugerindo reprogramação da tarefa

### • Interface Web organizada

* Sidebar recolhível
* Design clean inspirado em tema de saúde
* Layout minimalista e responsivo

---

## 3. Estrutura do Projeto

```
routine-plus/
├── apps/
│   ├── api/        # Backend (Node.js + Express)
│   └── web/        # Frontend (HTML + CSS + JS)
├── .env.example
└── README.md
```

O projeto segue o padrão **monorepo**, mantendo frontend e backend no mesmo repositório, mas totalmente separados em pastas.

---

## 4. Tecnologias Utilizadas

### **Backend**

* Node.js
* Express.js
* MongoDB Driver
* Node-Fetch
* Dotenv
* CORS

### **Frontend**

* HTML5
* CSS3
* JavaScript Vanilla

### **Infraestrutura**

* **MongoDB Atlas** (banco de dados na nuvem)
* **Render** (deploy do backend)
* **OpenWeather API** (dados climáticos atualizados)

---

## 5. Explicação das APIs e Serviços Utilizados

### **MongoDB Atlas — Banco de Dados em Nuvem**

O **MongoDB Atlas** é responsável por armazenar todas as tarefas com segurança e persistência total.
Ele oferece:

* Armazenamento em nuvem
* Alta disponibilidade
* Gerenciamento automático
* Backup e escalabilidade

Toda operação CRUD é salva diretamente no cluster Atlas, mantendo os dados disponíveis mesmo que o backend reinicie.

---

### **OpenWeather API — Clima em Tempo Real**

A OpenWeather fornece os dados climáticos usados pelo sistema.

Ela permite:

* Obter clima atual por cidade
* Obter previsão do tempo
* Detectar risco de chuva
* Alimentar o sistema de alertas para tarefas ao ar livre

O backend processa essas informações e envia apenas o necessário para o frontend.

---

### **Render — Hospedagem do Backend**

A aplicação utiliza o Render para hospedar o servidor Express em produção.

Ele é responsável por:

* Hospedar a API publicamente
* Rodar o Node.js 24/7
* Realizar deploy automático a cada atualização do GitHub
* Manter conexão estável com o MongoDB Atlas

Isso permite que o frontend funcione de qualquer lugar.

---

### **URL da API em Produção**

O backend está disponível publicamente em:

```
https://routine-plus.onrender.com
```

Essa URL é usada pelo frontend para consumir:

* Endpoints de tarefas
* Endpoints de clima
* Funções auxiliares da API

Também permite testes externos via Postman, Insomnia ou navegador.

---

## 6. Instalação e Execução Local

### 6.1. Pré-requisitos

* Node.js instalado
* Conta no MongoDB Atlas
* Chave da OpenWeather API

### 6.2. Backend (apps/api)

```bash
cd apps/api
npm install
```

Crie o arquivo `.env` baseado em `.env.example`:

```
PORT=3000
MONGO_URI=SuaStringDeConexaoAqui
OPENWEATHER_API_KEY=SuaChaveAqui
```

Inicie o servidor:

```bash
npm run dev
```

### 6.3. Frontend (apps/web)

Abra o arquivo:

```
apps/web/index.html
```

Como é estático, funciona direto no navegador.

---

## 7. Documentação da API

### **Tarefas**

| Método | Rota             | Descrição               |
| ------ | ---------------- | ----------------------- |
| GET    | `/api/tasks`     | Lista tarefas pendentes |
| POST   | `/api/tasks`     | Cria nova tarefa        |
| PATCH  | `/api/tasks/:id` | Conclui uma tarefa      |
| DELETE | `/api/tasks/:id` | Apaga uma tarefa        |

---

### **Clima**

| Método | Rota                    | Parâmetros | Descrição          |
| ------ | ----------------------- | ---------- | ------------------ |
| GET    | `/api/weather`          | `city`     | Clima atual        |
| GET    | `/api/weather/forecast` | `city`     | Previsão detalhada |

---

## 8. Prints da Aplicação

Inclua aqui imagens do funcionamento da sua aplicação.

Exemplos:

* Tela inicial
* Sidebar filtrável
* Tela de tarefas
* Alertas climáticos

---

## 9. Contribuição

Para contribuições:

1. Fork o repositório
2. Crie uma branch
3. Envie seu PR com descrição clara

---

## 10. Licença

Este projeto está licenciado sob os termos da **MIT License**.
Para mais detalhes, consulte o arquivo `LICENSE`.

