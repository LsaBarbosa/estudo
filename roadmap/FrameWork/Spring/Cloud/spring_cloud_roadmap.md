# Roadmap de Estudos – Spring Cloud

## Índice

- [1. Fundamentos do Spring Cloud](#1-fundamentos-do-spring-cloud)
- [2. Service Discovery](#2-service-discovery)
- [3. API Gateway](#3-api-gateway)
- [4. Load Balancing com Spring Cloud LoadBalancer](#4-load-balancing-com-spring-cloud-loadbalancer)
- [5. Circuit Breaker e Resiliência](#5-circuit-breaker-e-resiliência)
- [6. Configuração Centralizada com Spring Cloud Config](#6-configuração-centralizada-com-spring-cloud-config)
- [7. Monitoramento com Spring Cloud Sleuth e Zipkin](#7-monitoramento-com-spring-cloud-sleuth-e-zipkin)
- [8. Comunicação entre Microserviços](#8-comunicação-entre-microserviços)

## 1. Fundamentos do Spring Cloud

### 1.1. O que é Spring Cloud?
- Framework que facilita o desenvolvimento de aplicações distribuídas com Spring Boot.

### 1.2. Casos de Uso
- Microserviços.
- Sistemas distribuídos.

### 1.3. Módulos Principais do Spring Cloud
- Eureka, Config Server, Gateway, LoadBalancer, Sleuth, Zipkin, etc.

### 1.4. Exercícios Práticos - Fundamentos
- Criar um projeto Spring Boot com dependências Spring Cloud.
- Configurar versionamento de dependências usando Spring Cloud BOM.

## 2. Service Discovery

### 2.1. Spring Cloud Netflix Eureka
- Registro e descoberta de serviços.

### 2.2. Spring Cloud Consul
- Alternativa baseada em Consul.

### 2.3. Exercícios Práticos - Service Discovery
- Subir um Eureka Server.
- Registrar dois microserviços no Eureka.

## 3. API Gateway

### 3.1. Spring Cloud Gateway
- Roteamento de requisições.
- Filtros pré e pós processamento.

### 3.2. Roteamento e Filtros
- Exemplo de filtros: Logging, Auth, Rate Limiting.

### 3.3. Exercícios Práticos - API Gateway
- Criar um Spring Cloud Gateway.
- Configurar rota para um microserviço.

## 4. Load Balancing com Spring Cloud LoadBalancer

### 4.1. Configuração de Load Balancer
- Load balancing entre instâncias de serviços.

### 4.2. Ribbon vs LoadBalancer
- Ribbon está deprecated.
- Uso de `@LoadBalanced` com RestTemplate ou WebClient.

### 4.3. Exercícios Práticos - Load Balancing
- Criar duas instâncias do mesmo microserviço.
- Testar distribuição de chamadas.

## 5. Circuit Breaker e Resiliência

### 5.1. Spring Cloud CircuitBreaker (Resilience4j)
- Prevenção de falhas em cascata.

### 5.2. Retry e Timeout
- Configurar retries e timeouts personalizados.

### 5.3. Exercícios Práticos - Resiliência
- Adicionar Circuit Breaker em um cliente REST.
- Configurar Retry com Resilience4j.

## 6. Configuração Centralizada com Spring Cloud Config

### 6.1. Spring Cloud Config Server
- Servidor central de configuração.

### 6.2. Spring Cloud Config Client
- Serviços consumindo configuração centralizada.

### 6.3. Exercícios Práticos - Config Server
- Criar um Config Server.
- Configurar um microserviço para buscar configurações.

## 7. Monitoramento com Spring Cloud Sleuth e Zipkin

### 7.1. Distributed Tracing com Sleuth
- Adiciona traceId e spanId em logs.

### 7.2. Visualização com Zipkin
- Exibição gráfica de traces.

### 7.3. Exercícios Práticos - Monitoramento
- Configurar Sleuth em dois serviços.
- Subir Zipkin e visualizar os traces.

## 8. Comunicação entre Microserviços

### 8.1. OpenFeign
- Cliente declarativo HTTP.

### 8.2. RestTemplate e WebClient
- Comunicação tradicional HTTP.

### 8.3. Exercícios Práticos - Comunicação
- Criar um cliente Feign para buscar dados de outro serviço.
- Implementar comunicação via WebClient com LoadBalancer.

---

