# PRD - Sistema de Integração Mercado Livre + Bling

## 1. Visão Geral do Projeto

### 1.1 Objetivo
Desenvolver um sistema web simples que permita visualizar produtos de uma planilha de controle e consultar preços do Mercado Livre para comparação com o preço de custo, proporcionando uma visão clara da competitividade dos preços.

### 1.2 Escopo
- **Entrada**: Planilha Excel/Google Sheets com informações de produtos
- **Processamento**: Backend NestJS + Frontend React com consulta à API do Mercado Livre
- **Saída**: Visualização comparativa entre custo da planilha e preços do Mercado Livre
- **Interface**: Página web simples e intuitiva para consulta e comparação de preços
- **Infraestrutura**: Aplicação containerizada com Docker

## 2. Análise da Planilha Atual

### 2.1 Campos Identificados
- **MARCA**: Nome da marca do produto
- **SKU**: Código único do produto
- **CUSTO**: Preço de custo do produto
- **PEN**: Possível campo de estoque pendente
- **IMPOST**: Percentual de impostos
- **VERBA**: Orçamento/verba disponível
- **AUTO**: Status automático (X vermelho = desabilitado)
- **CLASSICO**: Preço de venda clássico
- **COMISSÃO**: Percentual de comissão
- **FRETE**: Valor do frete
- **PROMO**: Valor de promoção
- **MARGEI**: Margem de lucro

### 2.2 Campos Adicionais Necessários
- **EAN**: Código de barras EAN
- **ESTOQUE**: Quantidade em estoque
- **CATEGORIA**: Categoria do produto
- **DESCRIÇÃO**: Descrição detalhada do produto
- **IMAGENS**: URLs das imagens do produto

## 3. Requisitos Funcionais

### 3.1 Gestão de Produtos
- [ ] Importação automática da planilha
- [ ] Visualização dos produtos em tabela
- [ ] Busca simples por SKU ou nome

### 3.2 Integração Mercado Livre
- [ ] Consulta de produtos por SKU/EAN
- [ ] Busca de preços no catálogo do Mercado Livre
- [ ] Comparação entre preço de custo e preços do Mercado Livre

### 3.3 Integração Bling
- [ ] **Não implementado nesta versão**
- [ ] Integração futura para gestão de estoque e vendas

### 3.4 Dashboard Web
- [ ] Visualização de produtos da planilha em tabela
- [ ] Botão de sincronização para consultar preços do Mercado Livre
- [ ] Comparação visual entre custo e preços do Mercado Livre
- [ ] Busca simples por SKU ou nome do produto

## 4. Requisitos Não Funcionais

### 4.1 Performance
- Tempo de resposta < 2 segundos para operações básicas
- Sincronização em lote para grandes volumes
- Cache inteligente para dados frequentemente acessados

### 4.2 Segurança
- Autenticação e autorização robusta
- Criptografia de dados sensíveis
- Logs de auditoria completos
- Backup automático dos dados

### 4.3 Escalabilidade
- Arquitetura modular para fácil expansão
- Suporte a múltiplos usuários simultâneos
- Processamento assíncrono para operações pesadas

### 4.4 Disponibilidade
- Uptime de 99.5%
- Monitoramento contínuo
- Recuperação automática de falhas

## 5. Arquitetura Técnica

### 5.1 Tecnologias
- **Backend**: NestJS com TypeScript
- **Frontend**: React.js com TypeScript
- **UI**: Material-UI
- **Banco de Dados**: SQLite
- **Estado**: React Hooks ou Context API
- **HTTP**: Axios para consultas à API do Mercado Livre
- **Planilha**: Leitura via Excel.js ou similar
- **Containerização**: Docker
- **Deploy**: GitHub Pages

### 5.2 Padrões de Arquitetura
- **Backend**: NestJS com arquitetura modular e decorators
- **Frontend**: Component-Based Architecture com React
- **Custom Hooks**: Lógica de negócio isolada em hooks
- **Service Layer**: Serviços para comunicação com APIs externas
- **Repository Pattern**: Para acesso ao banco de dados
- **State Management**: Gerenciamento de estado com Context API ou Zustand
- **Responsive Design**: Interface adaptável para diferentes dispositivos

### 5.3 Estrutura de Módulos
```
backend/              # Backend NestJS
├── src/
│   ├── products/     # Módulo de produtos
│   ├── mercado-livre/ # Módulo de integração ML
│   ├── common/       # Utilitários e decorators
│   └── main.ts       # Arquivo principal
├── dist/             # Build compilado
└── package.json

frontend/             # Frontend React
├── src/
│   ├── components/   # Componentes React reutilizáveis
│   │   ├── ProductTable/ # Tabela de produtos
│   │   ├── PriceComparison/ # Comparação de preços
│   │   └── SyncButton/   # Botão de sincronização
│   ├── hooks/        # Custom hooks
│   │   ├── useProducts/  # Hook para gestão de produtos
│   │   └── useMercadoLivre/ # Hook para API do ML
│   ├── services/     # Serviços externos
│   │   └── mercadoLivreService/ # Serviço do Mercado Livre
│   ├── types/        # Tipos TypeScript
│   ├── utils/        # Funções utilitárias
│   └── pages/        # Páginas da aplicação
└── package.json

docker/               # Configurações Docker
├── Dockerfile.backend
├── Dockerfile.frontend
└── docker-compose.yml
```

## 6. Cronograma de Desenvolvimento

### 6.1 Fase 1 - Setup e Estrutura (1 semana)
- Setup do ambiente React
- Estrutura base do projeto
- Componentes básicos
- Leitura da planilha

### 6.2 Fase 2 - Integração Mercado Livre (2 semanas)
- Implementação da API do Mercado Livre
- Busca de produtos por SKU/EAN
- Comparação de preços
- Interface de visualização

### 6.3 Fase 3 - Refinamento e Deploy (1 semana)
- Otimizações de interface
- Testes de funcionalidade
- Deploy da aplicação
- Documentação

## 7. Critérios de Aceitação

### 7.1 Funcionalidades
- [ ] Sistema carrega planilha Excel automaticamente
- [ ] Produtos são exibidos em tabela organizada
- [ ] Botão de sincronização consulta preços do Mercado Livre
- [ ] Comparação visual entre custo e preços do ML
- [ ] Interface responsiva e intuitiva

### 7.2 Qualidade
- [ ] Interface responsiva e rápida
- [ ] Tratamento adequado de erros
- [ ] Performance otimizada para consultas
- [ ] Código limpo e bem documentado
- [ ] **Sem testes unitários** - foco na funcionalidade

## 8. Riscos e Mitigações

### 8.1 Riscos Técnicos
- **Risco**: APIs externas instáveis
  - **Mitigação**: Implementar retry logic e circuit breakers

- **Risco**: Volume de dados muito alto
  - **Mitigação**: Processamento em lote e cache inteligente

### 8.2 Riscos de Negócio
- **Risco**: Mudanças nas APIs dos parceiros
  - **Mitigação**: Abstração forte das integrações

- **Risco**: Dependência de planilha externa
  - **Mitigação**: Validação robusta e backup automático

## 9. Métricas de Sucesso

- Redução de 90% no tempo de consulta de preços
- Interface intuitiva com tempo de resposta < 2 segundos
- Comparação visual clara entre custo e preços do mercado
- Sistema funcionando localmente sem dependências externas

## 10. Próximos Passos

1. Setup do ambiente NestJS com TypeScript
2. Configuração do banco SQLite
3. Setup do ambiente React com TypeScript
4. Configuração do Material-UI
5. Implementação da leitura da planilha Excel
6. Desenvolvimento da interface de visualização
7. Integração com API do Mercado Livre
8. Configuração do Docker
9. Deploy no GitHub Pages
