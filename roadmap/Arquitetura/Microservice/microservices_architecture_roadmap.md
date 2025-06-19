# Roadmap de Estudos – Arquitetura de Microserviços

## Índice

- [1. Fundamentos de Microserviços](#1-fundamentos-de-microserviços)
- [2. Design de Microserviços](#2-design-de-microserviços)
- [3. Padrões de Comunicação](#3-padrões-de-comunicação)
- [4. Resiliência e Tolerância a Falhas](#4-resiliência-e-tolerância-a-falhas)
- [5. Observabilidade e Monitoramento](#5-observabilidade-e-monitoramento)
- [6. Deploy, Escalabilidade e Orquestração](#6-deploy-escalabilidade-e-orquestração)
- [7. Segurança em Microserviços](#7-segurança-em-microserviços)

## 1. Fundamentos de Microserviços

### 1.1. O que são Microserviços?
- Arquitetura baseada em pequenos serviços independentes.
- Cada serviço é implantável e escalável separadamente.

### 1.2. Monolito vs Microserviços
- Monolito: uma única aplicação.
- Microserviços: diversos serviços pequenos interconectados.

### 1.3. Benefícios e Desafios
- Benefícios: escalabilidade, deploy independente.
- Desafios: complexidade, comunicação, consistência.

### 1.4. Exercícios Práticos - Fundamentos
- Listar vantagens e desvantagens de migrar um monolito para microserviços.
- Desenhar o diagrama de uma arquitetura microservices simples.

## 2. Design de Microserviços

### 2.1. Definição de Bounded Contexts
- Inspirado no DDD.
- Cada serviço representa um contexto de negócio isolado.

### 2.2. Comunicação entre Microserviços
- API REST, gRPC, Mensageria.

### 2.3. Persistência e Banco de Dados por Serviço
- Database per Service Pattern.
- Evitar esquemas compartilhados.

### 2.4. Exercícios Práticos - Design
- Identificar Bounded Contexts para um sistema de e-commerce.
- Criar dois serviços com bancos separados.

## 3. Padrões de Comunicação

### 3.1. Síncrono (REST, gRPC)
- Requisição/Resposta.

### 3.2. Assíncrono (Mensageria - Kafka, RabbitMQ)
- Comunicação desacoplada via eventos.

### 3.3. Event-Driven
- Arquitetura orientada a eventos.

### 3.4. Exercícios Práticos - Comunicação
- Criar dois microserviços que se comunicam via REST.
- Implementar uma fila RabbitMQ entre dois serviços.

## 4. Resiliência e Tolerância a Falhas

### 4.1. Circuit Breaker
- Evitar propagação de falhas.
- Exemplo: Resilience4j.

### 4.2. Retry e Timeout
- Repetição automática em caso de falha.

### 4.3. Fallback e Degradability
- Fornecer resposta alternativa em caso de falha.

### 4.4. Exercícios Práticos - Resiliência
- Adicionar Circuit Breaker em um Consumer REST.
- Configurar Retry com Spring Retry.

## 5. Observabilidade e Monitoramento

### 5.1. Logs Centralizados
- Uso de ELK Stack ou Loki + Grafana.

### 5.2. Tracing Distribuído
- Ferramentas: Jaeger, Zipkin.

### 5.3. Health Checks
- Exposição de `/actuator/health`.

### 5.4. Exercícios Práticos - Monitoramento
- Criar um dashboard no Grafana.
- Integrar Spring Boot com Micrometer + Prometheus.

## 6. Deploy, Escalabilidade e Orquestração

### 6.1. Docker e Containers
- Containerização de serviços.

### 6.2. Kubernetes
- Orquestração de containers.
- Deployments, Services, ConfigMaps.

### 6.3. Service Discovery e Load Balancing
- Exemplo: Spring Cloud Eureka, Consul.

### 6.4. Exercícios Práticos - Deploy
- Criar Dockerfile para dois serviços.
- Subir serviços no Kubernetes local (minikube).

## 7. Segurança em Microserviços

### 7.1. Autenticação e Autorização
- OAuth2, JWT.

### 7.2. API Gateway e JWT
- Exemplo: Spring Cloud Gateway + OAuth2 Resource Server.

### 7.3. Rate Limiting
- Controle de tráfego por IP ou API Key.

### 7.4. Exercícios Práticos - Segurança
- Implementar autenticação com JWT.
- Configurar API Gateway com Rate Limiting.

---

