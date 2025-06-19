# Roadmap de Estudos – Clean Architecture

## Índice

- [1. Fundamentos da Clean Architecture](#1-fundamentos-da-clean-architecture)
  - [1.1. O que é Clean Architecture?](#11-o-que-é-clean-architecture)
  - [1.2. Princípios SOLID](#12-princípios-solid)
  - [1.3. Separação de Camadas](#13-separação-de-camadas)
  - [1.4. Dependência Direcionada para o Centro](#14-dependência-direcionada-para-o-centro)
  - [1.5. Exercícios Práticos - Fundamentos](#15-exercícios-práticos---fundamentos)

- [2. Estrutura de Projeto com Clean Architecture](#2-estrutura-de-projeto-com-clean-architecture)
  - [2.1. Camada de Entidades (Domain)](#21-camada-de-entidades-domain)
  - [2.2. Camada de Casos de Uso (Use Cases)](#22-camada-de-casos-de-uso-use-cases)
  - [2.3. Camada de Interfaces Adapters](#23-camada-de-interfaces-adapters)
  - [2.4. Camada de Frameworks & Drivers](#24-camada-de-frameworks--drivers)
  - [2.5. Exercícios Práticos - Estrutura de Projeto](#25-exercícios-práticos---estrutura-de-projeto)

- [3. Implementação de um Projeto Exemplo](#3-implementação-de-um-projeto-exemplo)
  - [3.1. Definindo o Domínio](#31-definindo-o-domínio)
  - [3.2. Criando os Casos de Uso](#32-criando-os-casos-de-uso)
  - [3.3. Criando Controllers, Presenters e Gateways](#33-criando-controllers-presenters-e-gateways)
  - [3.4. Implementando a Infraestrutura](#34-implementando-a-infraestrutura)
  - [3.5. Exercícios Práticos - Projeto Exemplo](#35-exercícios-práticos---projeto-exemplo)

- [4. Testes em Clean Architecture](#4-testes-em-clean-architecture)
  - [4.1. Testes de Unidade de Casos de Uso](#41-testes-de-unidade-de-casos-de-uso)
  - [4.2. Testes de Integração](#42-testes-de-integração)
  - [4.3. Testes End-to-End](#43-testes-end-to-end)
  - [4.4. Exercícios Práticos - Testes](#44-exercícios-práticos---testes)

- [5. Boas Práticas e Anti-patterns](#5-boas-práticas-e-anti-patterns)
  - [5.1. Injeção de Dependência](#51-injeção-de-dependência)
  - [5.2. Separação de Responsabilidades](#52-separação-de-responsabilidades)
  - [5.3. Evitando Regras de Negócio no Controller](#53-evitando-regras-de-negócio-no-controller)
  - [5.4. Exercícios Práticos - Boas Práticas](#54-exercícios-práticos---boas-práticas)

- [6. Recursos e Estudos Avançados](#6-recursos-e-estudos-avançados)
  - [6.1. Livros Recomendados](#61-livros-recomendados)
  - [6.2. Exemplos de Repositórios no GitHub](#62-exemplos-de-repositórios-no-github)
  - [6.3. Palestras e Vídeos](#63-palestras-e-vídeos)

---

## 1. Fundamentos da Clean Architecture

### 1.1. O que é Clean Architecture?
- Arquitetura centrada no domínio.
- Independente de frameworks, UI, bancos ou dispositivos.
- Permite fácil manutenção, testes e mudanças.

### 1.2. Princípios SOLID
- **S:** Single Responsibility Principle
- **O:** Open/Closed Principle
- **L:** Liskov Substitution Principle
- **I:** Interface Segregation Principle
- **D:** Dependency Inversion Principle

### 1.3. Separação de Camadas
- Entidades (Domínio)
- Casos de Uso
- Interface Adapters
- Frameworks & Drivers

### 1.4. Dependência Direcionada para o Centro
- Fluxo de dependência sempre de fora para dentro.
- As camadas internas **não conhecem** as camadas externas.

### 1.5. Exercícios Práticos - Fundamentos
- Desenhar um diagrama de uma Clean Architecture.
- Refatorar uma aplicação simples separando Domain e Infrastructure.

---

## 2. Estrutura de Projeto com Clean Architecture

### 2.1. Camada de Entidades (Domain)
- Contém as regras de negócio.
- Exemplo: classe `Order`, `User`.

### 2.2. Camada de Casos de Uso (Use Cases)
- Contém lógica de aplicação.
- Exemplo: `CreateOrderUseCase`, `GetUserUseCase`.

### 2.3. Camada de Interfaces Adapters
- Controllers, Gateways e Presenters.
- Exemplo: `OrderController`, `UserRepositoryAdapter`.

### 2.4. Camada de Frameworks & Drivers
- Integrações com banco de dados, web, mensageria.
- Exemplo: `OrderJpaRepository`, `KafkaEventPublisher`.

### 2.5. Exercícios Práticos - Estrutura de Projeto
- Criar um projeto Maven com pastas: `domain`, `application`, `adapters`, `infrastructure`.
- Criar um modelo simples de domínio e um caso de uso.

---

## 3. Implementação de um Projeto Exemplo

### 3.1. Definindo o Domínio
- Criar classes de entidade: `Product`, `OrderItem`, `Order`.

### 3.2. Criando os Casos de Uso
- Exemplo: `PlaceOrderUseCase` com validações de negócio.

### 3.3. Criando Controllers, Presenters e Gateways
- Exemplo de Controller Spring Boot chamando o Use Case.

### 3.4. Implementando a Infraestrutura
- Criar repositórios JPA.
- Configurar Controller REST.

### 3.5. Exercícios Práticos - Projeto Exemplo
- Implementar endpoint REST `/order` que use a Clean Architecture completa.
- Fazer persistência usando Spring Data.

---

## 4. Testes em Clean Architecture

### 4.1. Testes de Unidade de Casos de Uso
- Testar regra de negócio pura.
- Exemplo: Teste de validação de pedido com estoque insuficiente.

### 4.2. Testes de Integração
- Testar conexão entre Use Case e Repository.

### 4.3. Testes End-to-End
- Simular chamadas HTTP completas via TestRestTemplate ou MockMvc.

### 4.4. Exercícios Práticos - Testes
- Criar testes unitários para 2 casos de uso.
- Criar teste de integração usando banco H2.
- Fazer um teste end-to-end completo.

---

## 5. Boas Práticas e Anti-patterns

### 5.1. Injeção de Dependência
- Usar Spring IoC para instanciar Use Cases e Repositories.

### 5.2. Separação de Responsabilidades
- Não colocar lógica de negócio em Controllers.
- Cada camada com sua responsabilidade clara.

### 5.3. Evitando Regras de Negócio no Controller
- Controllers só fazem parsing de request, chamam o Use Case e retornam a resposta.

### 5.4. Exercícios Práticos - Boas Práticas
- Refatorar uma API REST existente para mover lógica de negócios para a camada de Use Case.
- Criar interfaces para cada gateway e implementar na infraestrutura.

---

## 6. Recursos e Estudos Avançados

### 6.1. Livros Recomendados
- **Clean Architecture** – Robert C. Martin (Uncle Bob)
- **Domain-Driven Design** – Eric Evans

### 6.2. Exemplos de Repositórios no GitHub
- `https://github.com/ard333/clean-architecture-example`
- `https://github.com/jmnarloch/clean-architecture-example`

### 6.3. Palestras e Vídeos
- "Clean Architecture em Java" – Canal DevDojo
- "Domain-Centric Hexagonal Architecture" – Venkat Subramaniam

---

