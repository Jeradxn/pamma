# Tarefas do Projeto - Consulta de Preços Mercado Livre

## 📋 Backlog de Tarefas

### 🏗️ Fase 1 - Setup e Estrutura (Semana 1)

#### Setup do Ambiente
- [ ] **TASK-001**: Configurar ambiente de desenvolvimento NestJS
  - **Descrição**: Instalar Node.js, npm/yarn, criar projeto NestJS com TypeScript
  - **Estimativa**: 2 horas
  - **Responsável**: [A definir]
  - **Dependências**: Nenhuma

- [ ] **TASK-002**: Configurar ambiente de desenvolvimento React
  - **Descrição**: Criar projeto React com TypeScript
  - **Estimativa**: 1 hora
  - **Responsável**: [A definir]
  - **Dependências**: TASK-001

- [ ] **TASK-003**: Configurar estrutura do projeto
  - **Descrição**: Criar estrutura de pastas para backend NestJS e frontend React
  - **Estimativa**: 2 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-001

- [ ] **TASK-004**: Configurar banco de dados SQLite
  - **Descrição**: Configurar TypeORM e banco SQLite
  - **Estimativa**: 2 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-001

- [ ] **TASK-005**: Configurar bibliotecas de UI
  - **Descrição**: Instalar e configurar Material-UI
  - **Estimativa**: 1 hora
  - **Responsável**: [A definir]
  - **Dependências**: TASK-002

- [ ] **TASK-006**: Configurar biblioteca para leitura de Excel
  - **Descrição**: Instalar Excel.js ou similar para leitura de planilhas
  - **Estimativa**: 1 hora
  - **Responsável**: [A definir]
  - **Dependências**: TASK-002

#### Componentes Base
- [ ] **TASK-007**: Criar tipos TypeScript
  - **Descrição**: Definir interfaces para Product, PriceComparison, etc.
  - **Estimativa**: 2 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-003

- [ ] **TASK-008**: Implementar componente ProductTable
  - **Descrição**: Tabela para exibir produtos da planilha
  - **Estimativa**: 4 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-007

- [ ] **TASK-009**: Implementar componente SyncButton
  - **Descrição**: Botão para sincronizar com Mercado Livre
  - **Estimativa**: 2 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-008

- [ ] **TASK-010**: Implementar componente PriceComparison
  - **Descrição**: Exibição comparativa entre custo e preços do ML
  - **Estimativa**: 4 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-008

#### Leitura da Planilha
- [ ] **TASK-011**: Implementar leitura de arquivo Excel
  - **Descrição**: Upload e leitura de planilha Excel
  - **Estimativa**: 4 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-006

- [ ] **TASK-012**: Implementar mapeamento de campos
  - **Descrição**: Mapear colunas da planilha para tipos do sistema
  - **Estimativa**: 3 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-011

### 🔧 Fase 2 - Integração Mercado Livre (Semanas 2-3)

#### API Mercado Livre
- [ ] **TASK-011**: Estudar API do Mercado Livre
  - **Descrição**: Documentação, endpoints, autenticação
  - **Estimativa**: 4 horas
  - **Responsável**: [A definir]
  - **Dependências**: Nenhuma

- [ ] **TASK-012**: Implementar serviço de consulta
  - **Descrição**: Serviço para buscar produtos no Mercado Livre
  - **Estimativa**: 6 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-011

- [ ] **TASK-013**: Implementar busca por SKU/EAN
  - **Descrição**: Busca de produtos específicos no ML
  - **Estimativa**: 8 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-012

- [ ] **TASK-014**: Implementar comparação de preços
  - **Descrição**: Lógica para comparar custo com preços do ML
  - **Estimativa**: 6 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-013

#### Interface de Usuário
- [ ] **TASK-015**: Implementar busca simples
  - **Descrição**: Busca por SKU ou nome do produto
  - **Estimativa**: 4 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-008



- [ ] **TASK-016**: Implementar responsividade
  - **Descrição**: Interface adaptável para mobile e desktop
  - **Estimativa**: 6 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-015

### 🚀 Fase 3 - Refinamento e Deploy (Semana 4)

#### Otimizações
- [ ] **TASK-017**: Otimizar interface e performance
  - **Descrição**: Melhorias na interface e otimizações de renderização
  - **Estimativa**: 6 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-016

- [ ] **TASK-019**: Otimizar performance
  - **Descrição**: Otimizações de renderização e consultas
  - **Estimativa**: 4 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-018

- [ ] **TASK-020**: Implementar tratamento de erros
  - **Descrição**: Tratamento robusto de erros da API
  - **Estimativa**: 4 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-019

#### Deploy e Documentação
- [ ] **TASK-021**: Preparar para deploy
  - **Descrição**: Build de produção e configurações
  - **Estimativa**: 2 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-020

- [ ] **TASK-022**: Deploy da aplicação
  - **Descrição**: Deploy em GitHub Pages, Netlify ou similar
  - **Estimativa**: 2 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-021

- [ ] **TASK-023**: Documentar funcionalidades
  - **Descrição**: README e guia de uso
  - **Estimativa**: 2 horas
  - **Responsável**: [A definir]
  - **Dependências**: TASK-022



## 📊 Resumo de Estimativas

| Fase | Tarefas | Horas Estimadas | Semanas |
|------|---------|-----------------|---------|
| Fase 1 - Setup e Estrutura | 12 | 24h | 1 |
| Fase 2 - Integração Mercado Livre | 7 | 40h | 2 |
| Fase 3 - Refinamento e Deploy | 6 | 20h | 1 |
| **Total** | **25** | **84h** | **4** |

## 🎯 Critérios de Definição de Pronto (DoD)

### Para cada tarefa:
- [ ] Código implementado e funcionando
- [ ] Testes unitários implementados e passando
- [ ] Código revisado por outro desenvolvedor
- [ ] Documentação atualizada
- [ ] Integração testada (quando aplicável)

### Para cada fase:
- [ ] Todas as tarefas da fase concluídas
- [ ] Testes de integração passando
- [ ] Performance dentro dos SLAs
- [ ] Documentação da fase concluída
- [ ] Aprovação do Product Owner

## 🔄 Processo de Atualização

Este arquivo deve ser atualizado:
- Semanalmente com o progresso das tarefas
- Quando uma tarefa for iniciada (mover para "Em Andamento")
- Quando uma tarefa for concluída (mover para "Concluídas")
- Quando novos problemas forem identificados
- Quando decisões técnicas forem tomadas
