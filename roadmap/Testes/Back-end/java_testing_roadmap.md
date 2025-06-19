# Roadmap de Estudos – Testes com Java

## Índice

- [1. Introdução aos Testes de Software](#1-introdução-aos-testes-de-software)
- [2. Testes Unitários com JUnit](#2-testes-unitários-com-junit)
- [3. Mockito - Mocks e Stubs](#3-mockito---mocks-e-stubs)
- [4. Testes de Integração com Spring Boot Test](#4-testes-de-integração-com-spring-boot-test)
- [5. Testes de Repositórios e Banco de Dados](#5-testes-de-repositórios-e-banco-de-dados)
- [6. Testes de API REST (MockMvc, WebTestClient)](#6-testes-de-api-rest-mockmvc-webtestclient)
- [7. Testes de Performance e Carga](#7-testes-de-performance-e-carga)
- [8. Testes com Banco de Mensageria (Ex: Kafka)](#8-testes-com-banco-de-mensageria-ex-kafka)
- [9. Test Coverage e Relatórios](#9-test-coverage-e-relatórios)
- [10. Testes End-to-End com RestAssured ou Postman/Newman](#10-testes-end-to-end-com-restassured-ou-postmannewman)

## 1. Introdução aos Testes de Software

### 1.1. Por que testar?
- Garantir qualidade e estabilidade.

### 1.2. Tipos de Testes
- Unitário, Integração, API, E2E.

### 1.3. Pirâmide de Testes
- Distribuição de esforço em testes.

### 1.4. Exercícios Práticos - Introdução
- Criar checklist de cobertura de testes para um projeto Java.

## 2. Testes Unitários com JUnit

### 2.1. Estrutura de um Teste JUnit
- Anotações: @Test, @BeforeEach, @AfterEach.

### 2.2. Assertions
- assertEquals, assertTrue, assertThrows.

### 2.3. Teste de Exceções
- Como testar exceções esperadas.

### 2.4. Exercícios Práticos - JUnit
- Escrever testes unitários para classe Calculadora.
- Testar exceções personalizadas.

## 3. Mockito - Mocks e Stubs

### 3.1. O que é Mockito?
- Biblioteca para criar objetos mockados.

### 3.2. Criando Mocks e Definindo Comportamento
- Uso de when(), thenReturn().

### 3.3. Verificando Interações (verify)
- Garantir chamadas de métodos.

### 3.4. Exercícios Práticos - Mockito
- Criar mock de um serviço de autenticação.
- Verificar interações entre classes.

## 4. Testes de Integração com Spring Boot Test

### 4.1. @SpringBootTest
- Testes com contexto completo.

### 4.2. Testcontainers (bancos reais nos testes)
- Criar ambientes de teste com containers.

### 4.3. Exercícios Práticos - Integração
- Testar um serviço com banco real usando Testcontainers.
- Criar teste de contexto Spring Boot.

## 5. Testes de Repositórios e Banco de Dados

### 5.1. Testes com H2 e @DataJpaTest
- Testes rápidos com banco em memória.

### 5.2. Flyway e Liquibase para Testes
- Aplicar migrações antes dos testes.

### 5.3. Exercícios Práticos - Repositórios
- Testar métodos de um repository JPA.
- Criar teste com banco H2.

## 6. Testes de API REST (MockMvc, WebTestClient)

### 6.1. Testando Controllers com MockMvc
- Testes de endpoints REST.

### 6.2. Testando APIs reativas com WebTestClient
- Para aplicações com WebFlux.

### 6.3. Exercícios Práticos - API REST
- Criar teste GET e POST para endpoint de usuários.
- Testar API reativa com WebTestClient.

## 7. Testes de Performance e Carga

### 7.1. JMeter
- Ferramenta para carga.

### 7.2. Gatling
- Testes de stress para APIs Java.

### 7.3. Exercícios Práticos - Performance
- Criar script de carga JMeter.
- Executar teste de stress com Gatling.

## 8. Testes com Banco de Mensageria (Ex: Kafka)

### 8.1. Embedded Kafka
- Criar um broker Kafka embutido para testes.

### 8.2. Testes de Produção e Consumo de Mensagens
- Testar envio e recebimento de mensagens.

### 8.3. Exercícios Práticos - Kafka
- Criar teste de um KafkaListener.
- Testar envio com KafkaTemplate.

## 9. Test Coverage e Relatórios

### 9.1. Jacoco
- Gerar relatórios de cobertura de código.

### 9.2. Cobertura de Código no Maven e Gradle
- Plugins para análise.

### 9.3. Exercícios Práticos - Cobertura
- Gerar cobertura de um projeto Java.
- Analisar áreas não cobertas.

## 10. Testes End-to-End com RestAssured ou Postman/Newman

### 10.1. RestAssured
- Testes de API com Java.

### 10.2. Postman e Newman CLI
- Execução de coleções automatizadas.

### 10.3. Exercícios Práticos - E2E
- Criar teste E2E com RestAssured.
- Exportar coleção Postman e executar via Newman.

---

