# Roadmap de Estudos – Design Patterns para Front-End

## Índice

- [1. Introdução aos Design Patterns no Front-End](#1-introdução-aos-design-patterns-no-front-end)
- [2. Patterns Estruturais no Front-End](#2-patterns-estruturais-no-front-end)
- [3. Patterns Comportamentais no Front-End](#3-patterns-comportamentais-no-front-end)
- [4. Patterns de Arquitetura no Front-End](#4-patterns-de-arquitetura-no-front-end)
- [5. Patterns de Performance e Reatividade](#5-patterns-de-performance-e-reatividade)
- [6. Design Patterns Modernos e Avançados](#6-design-patterns-modernos-e-avançados)

## 1. Introdução aos Design Patterns no Front-End

### 1.1. Por que usar Design Patterns no Front-End?
- Melhor organização e manutenção de código.
- Facilitar testes e reutilização.

### 1.2. Diferenças entre Patterns de Front-End e Back-End
- Foco maior em UI, estado e eventos.

### 1.3. Exercícios Práticos - Introdução
- Revisar código de um projeto React ou Angular e identificar padrões usados.

## 2. Patterns Estruturais no Front-End

### 2.1. Singleton
- Exemplo: Serviço global de autenticação.

### 2.2. Module Pattern (IIFE/ES6 Modules)
- Organização de código JavaScript.

### 2.3. Decorator (exemplo com React HOC ou Angular Decorators)
- Exemplo: Criar um Higher-Order Component (HOC) no React.

### 2.4. Exercícios Práticos - Estruturais
- Criar Singleton para gerenciar tema (dark/light).
- Criar HOC que adiciona logging a um componente React.

## 3. Patterns Comportamentais no Front-End

### 3.1. Observer (RxJS, EventEmitter, PubSub)
- Escutar eventos ou fluxos de dados.

### 3.2. Strategy (Ex: Diferentes Formas de Renderizar uma Tabela)
- Trocar estratégias de renderização.

### 3.3. Command (Ex: Controle de Undo/Redo)
- Exemplo de execução de comandos com histórico.

### 3.4. State (Ex: Redux, NgRx)
- Centralizar estado da aplicação.

### 3.5. Exercícios Práticos - Comportamentais
- Criar Observer para um chat simples com RxJS.
- Implementar Strategy para diferentes ordenações de uma lista.

## 4. Patterns de Arquitetura no Front-End

### 4.1. MVVM (Angular)
- Model-View-ViewModel com Data Binding.

### 4.2. Flux (React + Redux)
- Fluxo unidirecional de dados.

### 4.3. Component-Based Architecture
- Dividir funcionalidades em pequenos componentes reutilizáveis.

### 4.4. Exercícios Práticos - Arquitetura
- Criar projeto Angular com MVVM.
- Criar aplicação React com Redux para gerenciar estado de carrinho de compras.

## 5. Patterns de Performance e Reatividade

### 5.1. Debounce e Throttle
- Controle de frequência de execução de funções.

### 5.2. Lazy Loading de Componentes
- Carregar componentes somente quando necessário.

### 5.3. Memoization (React.memo, PureComponent)
- Evitar renderizações desnecessárias.

### 5.4. Exercícios Práticos - Performance
- Implementar debounce em campo de busca.
- Usar Lazy Loading em rotas Angular ou React.

## 6. Design Patterns Modernos e Avançados

### 6.1. Custom Hooks (React)
- Encapsular lógica reutilizável.

### 6.2. Services e Injection Tokens (Angular)
- Injeção de dependência customizada.

### 6.3. Slot/Slot Props (Vue e React)
- Renderizar conteúdo dinâmico.

### 6.4. Exercícios Práticos - Avançados
- Criar Custom Hook para chamada de API.
- Criar Service Angular para notificação global.

---

