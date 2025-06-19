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

## Exercícios Práticos – Clean Architecture

### 1.5. Exercícios Práticos - Fundamentos
- Desenhar um diagrama da Clean Architecture.
- Escrever um resumo sobre o objetivo de cada camada.
- Refatorar um código monolítico simples aplicando a separação de camadas.

### 2.5. Exercícios Práticos - Estrutura de Projeto
- Criar um projeto Java com pacotes: `domain`, `application`, `adapters`, `infrastructure`.
- Criar uma entidade `Customer` com campos básicos.
- Criar um caso de uso `CreateCustomerUseCase`.
- Criar uma implementação de repositório in-memory.

### 3.5. Exercícios Práticos - Projeto Exemplo
- Implementar o caso de uso **PlaceOrderUseCase** com validação de estoque.
- Criar um Controller REST `/orders` para criação de pedidos.
- Criar um repository com Spring Data JPA.
- Expor um endpoint para buscar pedidos por ID.

### 4.4. Exercícios Práticos - Testes
- Escrever um teste unitário para o **PlaceOrderUseCase**.
- Escrever um teste de integração para a camada de Application com Repository fake.
- Escrever um teste end-to-end simulando uma requisição HTTP real.

### 5.4. Exercícios Práticos - Boas Práticas
- Refatorar um Controller existente que possui lógica de negócios para movê-la para um Use Case.
- Aplicar Injeção de Dependência via Spring Configuration para todos os Use Cases.
- Separar interfaces de leitura e escrita no repositório (Segregação de Interface).

---

