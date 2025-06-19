# Roadmap de Estudos – Event-Driven Architecture (EDA)

## Índice

- [1. Fundamentos da Event-Driven Architecture](#1-fundamentos-da-event-driven-architecture)
- [2. Padrões de Comunicação em EDA](#2-padrões-de-comunicação-em-eda)
- [3. Tecnologias e Ferramentas para EDA](#3-tecnologias-e-ferramentas-para-eda)
- [4. Modelagem de Eventos](#4-modelagem-de-eventos)
- [5. Implementando uma Solução Event-Driven](#5-implementando-uma-solução-event-driven)
- [6. Monitoramento, Logging e Resiliência](#6-monitoramento-logging-e-resiliência)
- [7. Estudos Avançados](#7-estudos-avançados)

## 1. Fundamentos da Event-Driven Architecture

### 1.1. O que é EDA?
- Estilo arquitetural baseado em emissão, consumo e reação a eventos.
- Comunicação assíncrona entre componentes.

### 1.2. Componentes Principais
- **Event Producers**
- **Event Consumers**
- **Event Channels (Brokers)**

### 1.3. Benefícios da EDA
- Escalabilidade
- Resiliência
- Baixo acoplamento

### 1.4. Desafios comuns
- Garantia de entrega
- Ordering
- Duplicate Event Handling

### 1.5. Exercícios Práticos - Fundamentos
- Criar um diagrama de fluxo de eventos simples.
- Listar 3 cenários reais que se beneficiam de EDA.

## 2. Padrões de Comunicação em EDA

### 2.1. Event Notification
- Apenas notificação, sem payload relevante.

### 2.2. Event-Carried State Transfer
- Evento carrega o estado completo da entidade.

### 2.3. Event Sourcing
- Estado da aplicação reconstruído a partir de eventos.

### 2.4. Exercícios Práticos - Padrões
- Criar um evento simples com Event Notification.
- Criar um exemplo com Event-Carried State Transfer.
- Modelar um fluxo de Event Sourcing.

## 3. Tecnologias e Ferramentas para EDA

### 3.1. Message Brokers
- RabbitMQ, ActiveMQ

### 3.2. Streaming Platforms
- Apache Kafka, AWS Kinesis

### 3.3. Event Mesh e Event Bus
- Solace, NATS

### 3.4. Exercícios Práticos - Ferramentas
- Publicar e consumir eventos usando RabbitMQ.
- Criar um tópico Kafka e testar com Producer/Consumer Java.

## 4. Modelagem de Eventos

### 4.1. Definição de Eventos
- Nomeação clara
- Semântica imutável

### 4.2. Versionamento de Eventos
- Estratégias: Avro Schema Registry, Versioned Event Classes

### 4.3. Garantia de Entrega
- At-least-once, At-most-once, Exactly-once

### 4.4. Exercícios Práticos - Modelagem
- Criar uma estrutura de evento com campos: id, timestamp, type, payload.
- Criar uma segunda versão de um evento com campo adicional.

## 5. Implementando uma Solução Event-Driven

### 5.1. Publicação de Eventos
- Exemplo: Spring Kafka Template.

### 5.2. Consumo de Eventos
- Exemplo: KafkaListener ou RabbitListener.

### 5.3. Processamento Assíncrono
- Thread Pools, Async Executors.

### 5.4. Exercícios Práticos - Implementação
- Criar Producer Spring Boot que publica um evento.
- Criar Consumer Spring Boot que processa o evento e grava no banco.

## 6. Monitoramento, Logging e Resiliência

### 6.1. Dead Letter Queues (DLQ)
- Tratamento de mensagens com falha.

### 6.2. Retry Policies
- Backoff, Number of Retries.

### 6.3. Event Replay
- Reprocessamento de eventos antigos.

### 6.4. Exercícios Práticos - Monitoramento
- Configurar DLQ no RabbitMQ.
- Implementar retry com Spring Retry.
- Fazer replay de eventos em Kafka.

## 7. Estudos Avançados

### 7.1. Event Choreography vs Orchestration
- Diferenças, vantagens e desvantagens.

### 7.2. CQRS com EDA
- Separação de leitura e escrita.

### 7.3. Transações Eventuais
- Consistência eventual entre microserviços.

### 7.4. Recursos Recomendados
- Livro: "Designing Event-Driven Systems" – Ben Stopford.
- Artigo: https://martinfowler.com/articles/201701-event-driven.html
- Curso: Event-Driven Microservices with Spring Boot & Kafka (Udemy)

---

