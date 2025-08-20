# 🚀 Sistema de Consulta de Preços Mercado Livre

Sistema web para visualizar produtos de planilhas e consultar preços no Mercado Livre para comparação com preços de custo.

## 📋 Índice

- [Visão Geral](#visão-geral)
- [Funcionalidades](#funcionalidades)
- [Tecnologias](#tecnologias)
- [Arquitetura](#arquitetura)
- [Pré-requisitos](#pré-requisitos)
- [Instalação](#instalação)
- [Execução](#execução)
- [Desenvolvimento](#desenvolvimento)
- [Deploy](#deploy)
- [Contribuição](#contribuição)

## 🎯 Visão Geral

Este projeto permite:
- **Carregar planilhas Excel** com informações de produtos
- **Visualizar produtos** em tabela organizada
- **Consultar preços** no Mercado Livre via API
- **Comparar visualmente** custo vs preços do mercado
- **Buscar produtos** por SKU ou nome

## ✨ Funcionalidades

### 🔧 Gestão de Produtos
- [x] Importação automática da planilha
- [x] Visualização dos produtos em tabela
- [x] Busca simples por SKU ou nome

### 🔗 Integração Mercado Livre
- [x] Consulta de produtos por SKU/EAN
- [x] Busca de preços no catálogo
- [x] Comparação entre custo e preços

### 🖥️ Dashboard Web
- [x] Interface responsiva com Material-UI
- [x] Botão de sincronização
- [x] Comparação visual de preços

## 🛠️ Tecnologias

### Backend
- **NestJS** - Framework Node.js com TypeScript
- **SQLite** - Banco de dados local
- **TypeORM** - ORM para banco de dados
- **Class-validator** - Validação de dados

### Frontend
- **React 18** com TypeScript
- **Material-UI** - Biblioteca de componentes
- **Axios** - Cliente HTTP
- **Excel.js** - Leitura de planilhas

### Infraestrutura
- **Docker** - Containerização
- **Docker Compose** - Orquestração
- **GitHub Pages** - Deploy estático

## 🏗️ Arquitetura

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │    Backend      │    │   Mercado       │
│   React + MUI   │◄──►│   NestJS        │◄──►│   Livre API     │
│                 │    │   + SQLite      │    │                 │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │
         │                       │
         ▼                       ▼
┌─────────────────┐    ┌─────────────────┐
│   Excel File    │    │   Docker        │
│   Upload        │    │   Container     │
└─────────────────┘    └─────────────────┘
```

### Estrutura do Projeto

```
pedela/
├── backend/                 # Backend NestJS
│   ├── src/
│   │   ├── products/        # Módulo de produtos
│   │   ├── mercado-livre/   # Módulo de integração ML
│   │   ├── common/          # Utilitários e decorators
│   │   ├── app.module.ts    # Módulo principal
│   │   └── main.ts          # Arquivo principal
│   ├── dist/                # Build compilado
│   ├── package.json
│   └── tsconfig.json
│
├── frontend/                # Frontend React
│   ├── src/
│   │   ├── components/      # Componentes React
│   │   │   ├── ProductTable/
│   │   │   ├── PriceComparison/
│   │   │   └── SyncButton/
│   │   ├── hooks/           # Custom hooks
│   │   ├── services/        # Serviços
│   │   ├── types/           # Tipos TypeScript
│   │   ├── utils/           # Utilitários
│   │   └── pages/           # Páginas
│   ├── public/
│   ├── package.json
│   └── tsconfig.json
│
├── docker/                  # Configurações Docker
│   ├── Dockerfile.backend
│   ├── Dockerfile.frontend
│   └── docker-compose.yml
│
├── docs/                    # Documentação
│   ├── PRD.md
│   ├── project_status.md
│   └── tasks.md
│
├── README.md
└── .gitignore
```

## 📋 Pré-requisitos

- **Node.js** 18+ 
- **npm** ou **yarn**
- **Docker** e **Docker Compose**
- **Git**

## 🚀 Instalação

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/pedela.git
cd pedela
```

### 2. Setup do Backend

```bash
cd backend
npm install
```

### 3. Setup do Frontend

```bash
cd frontend
npm install
```

### 4. Configuração do Banco

```bash
cd backend
npm run migration:run
```

## 🏃‍♂️ Execução

### Opção 1: Docker (Recomendado)

```bash
# Na raiz do projeto
docker-compose up -d
```

Acesse:
- **Frontend**: http://localhost:3000
- **Backend**: http://localhost:3001

### Opção 2: Desenvolvimento Local

#### Terminal 1 - Backend
```bash
cd backend
npm run start:dev
```

#### Terminal 2 - Frontend
```bash
cd frontend
npm start
```

## 💻 Desenvolvimento

### Scripts Disponíveis

#### Backend
```bash
cd backend
npm run start          # Produção
npm run start:dev      # Desenvolvimento
npm run build          # Build
npm run test           # Testes
npm run migration:run  # Executar migrações
```

#### Frontend
```bash
cd frontend
npm start              # Desenvolvimento
npm run build          # Build de produção
npm test               # Testes
npm run eject          # Eject (irreversível)
```

### Estrutura de Desenvolvimento

#### Backend (NestJS)
- **Módulos**: Organização por domínio
- **Controllers**: Endpoints da API
- **Services**: Lógica de negócio
- **Entities**: Modelos do banco
- **DTOs**: Validação de entrada

#### Frontend (React)
- **Components**: Reutilizáveis e focados
- **Hooks**: Lógica de estado e efeitos
- **Services**: Comunicação com APIs
- **Types**: Definições TypeScript

## 🐳 Docker

### Build das Imagens

```bash
# Backend
docker build -f docker/Dockerfile.backend -t pedela-backend .

# Frontend
docker build -f docker/Dockerfile.frontend -t pedela-frontend .
```

### Docker Compose

```yaml
version: '3.8'
services:
  backend:
    build:
      context: ./backend
      dockerfile: ../docker/Dockerfile.backend
    ports:
      - "3001:3001"
    volumes:
      - ./backend:/app
      - /app/node_modules
    environment:
      - NODE_ENV=development
      - DATABASE_PATH=/app/database.sqlite

  frontend:
    build:
      context: ./frontend
      dockerfile: ../docker/Dockerfile.frontend
    ports:
      - "3000:3000"
    volumes:
      - ./frontend:/app
      - /app/node_modules
    depends_on:
      - backend
```

## 🚀 Deploy

### GitHub Pages (Frontend)

```bash
cd frontend
npm run build
npm run deploy
```

### Backend (Opcional)

```bash
cd backend
npm run build
# Deploy para Vercel, Heroku, etc.
```

## 📊 Banco de Dados

### SQLite Schema

```sql
-- Tabela de Produtos
CREATE TABLE products (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  sku VARCHAR(100) UNIQUE NOT NULL,
  name VARCHAR(255) NOT NULL,
  brand VARCHAR(100),
  cost DECIMAL(10,2),
  ean VARCHAR(50),
  category VARCHAR(100),
  description TEXT,
  stock INTEGER DEFAULT 0,
  created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
  updated_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

-- Tabela de Preços ML
CREATE TABLE mercado_livre_prices (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  product_id INTEGER,
  ml_id VARCHAR(100),
  title VARCHAR(255),
  price DECIMAL(10,2),
  seller VARCHAR(100),
  condition VARCHAR(50),
  shipping DECIMAL(10,2),
  total_price DECIMAL(10,2),
  created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (product_id) REFERENCES products(id)
);
```

## 🔧 Configuração

### Variáveis de Ambiente

#### Backend (.env)
```env
NODE_ENV=development
PORT=3001
DATABASE_PATH=./database.sqlite
MERCADO_LIVRE_API_URL=https://api.mercadolibre.com
```

#### Frontend (.env)
```env
REACT_APP_API_URL=http://localhost:3001
REACT_APP_MERCADO_LIVRE_API_URL=https://api.mercadolivre.com
```

## 🧪 Testes

### Backend
```bash
cd backend
npm run test              # Testes unitários
npm run test:e2e          # Testes end-to-end
npm run test:cov          # Cobertura de testes
```

### Frontend
```bash
cd frontend
npm test                  # Testes unitários
npm run test:coverage     # Cobertura de testes
```

## 📝 API Endpoints

### Produtos
- `GET /api/products` - Listar produtos
- `GET /api/products/:id` - Buscar produto por ID
- `POST /api/products` - Criar produto
- `PUT /api/products/:id` - Atualizar produto
- `DELETE /api/products/:id` - Deletar produto

### Mercado Livre
- `GET /api/mercado-livre/search?q=:query` - Buscar produtos
- `GET /api/mercado-livre/product/:id` - Detalhes do produto
- `POST /api/mercado-livre/sync` - Sincronizar preços

## 🤝 Contribuição

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 📞 Suporte

- **Issues**: [GitHub Issues](https://github.com/seu-usuario/pedela/issues)
- **Documentação**: [Wiki](https://github.com/seu-usuario/pedela/wiki)
- **Email**: seu-email@exemplo.com

## 🙏 Agradecimentos

- **NestJS** - Framework backend
- **React** - Biblioteca frontend
- **Material-UI** - Componentes UI
- **Mercado Livre** - API de produtos

---

**Desenvolvido com ❤️ para otimizar consultas de preços**
