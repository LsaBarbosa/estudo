# Roadmap de Estudos – Testes de Front-End com JavaScript

## Índice

- [1. Introdução aos Testes de Front-End](#1-introdução-aos-testes-de-front-end)
- [2. Testes Unitários com Jest](#2-testes-unitários-com-jest)
- [3. Testes de Componentes (React, Angular, Vue)](#3-testes-de-componentes-react-angular-vue)
- [4. Testes de Integração](#4-testes-de-integração)
- [5. Testes End-to-End (E2E)](#5-testes-end-to-end-e2e)
- [6. Testes de Performance Front-End](#6-testes-de-performance-front-end)
- [7. Test Coverage e Relatórios](#7-test-coverage-e-relatórios)
- [8. Testes Automatizados em CI/CD](#8-testes-automatizados-em-cicd)

## 1. Introdução aos Testes de Front-End

### 1.1. Por que testar aplicações front-end?
- Garantir que componentes, APIs e interações funcionem corretamente.

### 1.2. Tipos de Testes para Front-End
- Unitários, Integração, E2E, Performance.

### 1.3. Pirâmide de Testes Front-End
- Mais testes unitários e menos E2E.

### 1.4. Exercícios Práticos - Introdução
- Mapear os tipos de testes para um projeto front-end real.

## 2. Testes Unitários com Jest

### 2.1. Estrutura de um Teste com Jest
- Funções como describe(), test(), expect().

### 2.2. Mocking de Funções e Módulos
- Uso de jest.fn(), jest.mock().

### 2.3. Test Coverage com Jest
- Geração de relatórios de cobertura.

### 2.4. Exercícios Práticos - Jest
- Testar função de cálculo de desconto.
- Mockar dependência externa.

## 3. Testes de Componentes (React, Angular, Vue)

### 3.1. Testing Library (React Testing Library, Angular Testing Library)
- Testes focados em comportamento de usuário.

### 3.2. Shallow Rendering vs Full Rendering
- Diferenças entre tipos de renderização de componente.

### 3.3. Mock de Props e Services
- Simular serviços ou propriedades.

### 3.4. Exercícios Práticos - Componentes
- Testar exibição condicional em um componente React.
- Testar input/output de componente Angular.

## 4. Testes de Integração

### 4.1. Testando Integração entre Componentes
- Garantir comunicação entre múltiplos componentes.

### 4.2. Mock de API com MSW (Mock Service Worker)
- Simular respostas de APIs.

### 4.3. Exercícios Práticos - Integração
- Testar página que consome API e exibe lista.
- Simular erro de API e validar tratamento.

## 5. Testes End-to-End (E2E)

### 5.1. Cypress
- Testes de navegação e fluxo de usuário.

### 5.2. Playwright
- Alternativa moderna ao Cypress.

### 5.3. Exercícios Práticos - E2E
- Criar teste Cypress para fluxo de login.
- Validar fluxo de cadastro de usuário.

## 6. Testes de Performance Front-End

### 6.1. Lighthouse
- Métricas de performance web.

### 6.2. Web Vitals
- FCP, LCP, CLS, etc.

### 6.3. Exercícios Práticos - Performance
- Rodar análise de performance com Lighthouse.
- Melhorar pontuação de um site simples.

## 7. Test Coverage e Relatórios

### 7.1. Cobertura de Código com Istanbul (nyc)
- Relatórios de cobertura detalhados.

### 7.2. Relatórios HTML e CLI
- Visualização gráfica.

### 7.3. Exercícios Práticos - Coverage
- Configurar nyc para um projeto Node.js front-end.
- Gerar relatório de cobertura.

## 8. Testes Automatizados em CI/CD

### 8.1. Rodando Testes no GitHub Actions
- Integração contínua.

### 8.2. Cypress no CI/CD
- Execução de testes E2E na pipeline.

### 8.3. Exercícios Práticos - CI/CD
- Criar pipeline simples que executa Jest e Cypress.
- Gerar badge de cobertura de código.

---

