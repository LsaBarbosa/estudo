# Roadmap de Estudos – Arquitetura Hexagonal (Ports and Adapters)

## Índice

- [1. Fundamentos da Arquitetura Hexagonal](#1-fundamentos-da-arquitetura-hexagonal)
  - [1.1. O que é Arquitetura Hexagonal?](#11-o-que-é-arquitetura-hexagonal)
  - [1.2. Problemas que ela resolve](#12-problemas-que-ela-resolve)
  - [1.3. Conceito de Ports e Adapters](#13-conceito-de-ports-e-adapters)
  - [1.4. Exercícios Práticos - Fundamentos](#14-exercícios-práticos---fundamentos)

- [2. Estrutura de Projeto com Hexagonal](#2-estrutura-de-projeto-com-hexagonal)
  - [2.1. Camada de Domínio](#21-camada-de-domínio)
  - [2.2. Camada de Application (Use Cases)](#22-camada-de-application-use-cases)
  - [2.3. Ports: Entradas e Saídas](#23-ports-entradas-e-saídas)
  - [2.4. Adapters: Primary e Secondary](#24-adapters-primary-e-secondary)
  - [2.5. Exercícios Práticos - Estrutura](#25-exercícios-práticos---estrutura)

- [3. Implementação de um Projeto Exemplo](#3-implementação-de-um-projeto-exemplo)
  - [3.1. Criando Entidades e Regras de Negócio](#31-criando-entidades-e-regras-de-negócio)
  - [3.2. Criando Ports de Entrada](#32-criando-ports-de-entrada)
  - [3.3. Criando Ports de Saída](#33-criando-ports-de-saída)
  - [3.4. Implementando Adapters](#34-implementando-adapters)
  - [3.5. Exercícios Práticos - Projeto Exemplo](#35-exercícios-práticos---projeto-exemplo)

- [4. Testes com Arquitetura Hexagonal](#4-testes-com-arquitetura-hexagonal)
  - [4.1. Testes de Casos de Uso](#41-testes-de-casos-de-uso)
  - [4.2. Testes de Adapters](#42-testes-de-adapters)
  - [4.3. Testes de Integração com Mocks](#43-testes-de-integração-com-mocks)
  - [4.4. Exercícios Práticos - Testes](#44-exercícios-práticos---testes)

- [5. Boas Práticas e Anti-patterns](#5-boas-práticas-e-anti-patterns)
  - [5.1. Evitando Lógica de Negócio em Adapters](#51-evitando-lógica-de-negócio-em-adapters)
  - [5.2. Isolamento de Dependências](#52-isolamento-de-dependências)
  - [5.3. Separação clara entre Ports e Adapters](#53-separação-clara-entre-ports-e-adapters)
  - [5.4. Exercícios Práticos - Boas Práticas](#54-exercícios-práticos---boas-práticas)

- [6. Recursos de Estudo](#6-recursos-de-estudo)
  - [6.1. Livros e Artigos](#61-livros-e-artigos)
  - [6.2. Exemplos no GitHub](#62-exemplos-no-github)
  - [6.3. Vídeos e Palestras](#63-vídeos-e-palestras)

---

## 1. Fundamentos da Arquitetura Hexagonal

### 1.1. O que é Arquitetura Hexagonal?
- Padrão arquitetural focado em isolar o domínio da aplicação de suas dependências externas.
- Também chamada de **Ports and Adapters**.

### 1.2. Problemas que ela resolve
- Alta acoplamento com frameworks.
- Baixa testabilidade.
- Dificuldade em trocar tecnologia (ex: banco, APIs).

### 1.3. Conceito de Ports e Adapters
- **Ports:** Interfaces que descrevem o comportamento necessário.
- **Adapters:** Implementações concretas (REST Controllers, Repositórios, etc).

### 1.4. Exercícios Práticos - Fundamentos
- Fazer um desenho mostrando a separação entre Ports e Adapters.
- Refletir: qual parte do seu código atual é domínio? Qual é Adapter?

---

## 2. Estrutura de Projeto com Hexagonal

### 2.1. Camada de Domínio
- Entidades e lógica de negócio pura.

### 2.2. Camada de Application (Use Cases)
- Casos de uso que orquestram o fluxo.

### 2.3. Ports: Entradas e Saídas
- Ports de entrada: Interfaces chamadas por Controllers.
- Ports de saída: Interfaces de dependências externas.

### 2.4. Adapters: Primary e Secondary
- **Primary Adapters:** Ex: Controllers REST, CLI.
- **Secondary Adapters:** Ex: JPA Repository, HTTP Clients.

### 2.5. Exercícios Práticos - Estrutura
- Criar um projeto com pacotes:
  - `domain`
  - `application`
  - `adapters.inbound`
  - `adapters.outbound`

---

## 3. Implementação de um Projeto Exemplo

### 3.1. Criando Entidades e Regras de Negócio
- Exemplo: Entidade `Product` com métodos de validação.

### 3.2. Criando Ports de Entrada
- Interface `CreateProductUseCase` com método `create(ProductRequest)`.

### 3.3. Criando Ports de Saída
- Interface `ProductRepositoryPort` com métodos `save()`, `findById()`, etc.

### 3.4. Implementando Adapters
- REST Controller chamando o Use Case.
- Repository JPA implementando `ProductRepositoryPort`.

### 3.5. Exercícios Práticos - Projeto Exemplo
- Criar caso de uso para cadastrar Produto.
- Implementar Controller REST `/products`.
- Persistir Produto usando JPA.

---

## 4. Testes com Arquitetura Hexagonal

### 4.1. Testes de Casos de Uso
- Testar apenas a lógica da classe de Application.

### 4.2. Testes de Adapters
- Testar Controllers com Mock de UseCase.
- Testar Repository com banco H2.

### 4.3. Testes de Integração com Mocks
- Mockar ports de saída para testar Use Cases isolados.

### 4.4. Exercícios Práticos - Testes
- Criar teste unitário para o UseCase `CreateProductUseCase`.
- Criar teste de integração usando TestRestTemplate ou MockMvc.

---

## 5. Boas Práticas e Anti-patterns

### 5.1. Evitando Lógica de Negócio em Adapters
- Toda lógica de negócio deve estar no domínio ou Use Case.

### 5.2. Isolamento de Dependências
- Usar interfaces (Ports) para depender apenas de abstrações.

### 5.3. Separação clara entre Ports e Adapters
- Nunca injetar Adapter dentro de Use Case, sempre o Port.

### 5.4. Exercícios Práticos - Boas Práticas
- Refatorar uma API REST existente para usar Ports and Adapters.
- Criar interfaces para as dependências externas.

---

## 6. Recursos de Estudo

### 6.1. Livros e Artigos
- **"Clean Architecture"** – Uncle Bob
- **"Domain-Driven Design"** – Eric Evans
- **Artigo:** https://alistair.cockburn.us/hexagonal-architecture/

### 6.2. Exemplos no GitHub
- https://github.com/thombergs/code-examples/tree/main/hexagonal-architecture

### 6.3. Vídeos e Palestras
- "Hexagonal Architecture - Venkat Subramaniam"
- "Hexagonal Architecture with Spring Boot" – Amigoscode

---

