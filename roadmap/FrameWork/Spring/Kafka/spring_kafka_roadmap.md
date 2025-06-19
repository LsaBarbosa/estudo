# Roadmap de Estudos – Spring Kafka

## Índice

- [1. Fundamentos do Apache Kafka](#1-fundamentos-do-apache-kafka)
- [2. Integração com Spring Boot](#2-integração-com-spring-boot)
- [3. Produzindo Mensagens com Spring Kafka](#3-produzindo-mensagens-com-spring-kafka)
- [4. Consumindo Mensagens com Spring Kafka](#4-consumindo-mensagens-com-spring-kafka)
- [5. Configurações Avançadas](#5-configurações-avançadas)
- [6. Retry, Dead Letter Topics e Error Handling](#6-retry-dead-letter-topics-e-error-handling)
- [7. Monitoramento e Tuning](#7-monitoramento-e-tuning)
- [8. Testes com Spring Kafka](#8-testes-com-spring-kafka)

## 1. Fundamentos do Apache Kafka

### 1.1. O que é Kafka?
- Plataforma de mensageria distribuída.
- Alta performance e escalabilidade.

### 1.2. Conceitos principais: Producer, Consumer, Broker, Topic
- Producer: quem envia.
- Consumer: quem consome.
- Broker: servidor Kafka.
- Topic: canal lógico.

### 1.3. Casos de uso de Kafka
- Event sourcing.
- Streaming de dados.

### 1.4. Exercícios Práticos - Fundamentos Kafka
- Subir Kafka local usando Docker.
- Criar um tópico chamado `test-topic`.

## 2. Integração com Spring Boot

### 2.1. Dependências Maven/Gradle
- `spring-kafka`

### 2.2. application.properties básico para Kafka
- Configurar `spring.kafka.bootstrap-servers`.

### 2.3. Exercícios Práticos - Integração
- Criar projeto Spring Boot com Spring Kafka.
- Configurar o `bootstrap-servers` para localhost.

## 3. Produzindo Mensagens com Spring Kafka

### 3.1. KafkaTemplate
- Classe para enviar mensagens.

### 3.2. Serialização de objetos
- Configurar `JsonSerializer`.

### 3.3. Exercícios Práticos - Produção
- Criar Producer REST que envia mensagens JSON para Kafka.
- Enviar uma lista de mensagens em batch.

## 4. Consumindo Mensagens com Spring Kafka

### 4.1. @KafkaListener
- Anotação para métodos consumidores.

### 4.2. Deserialização
- Uso de `JsonDeserializer`.

### 4.3. Processamento assíncrono
- Cada Consumer rodando em Thread separada.

### 4.4. Exercícios Práticos - Consumo
- Criar Consumer que recebe objetos JSON.
- Testar consumo com múltiplas partições.

## 5. Configurações Avançadas

### 5.1. Consumer Groups
- Escalabilidade horizontal de consumidores.

### 5.2. Particionamento e Paralelismo
- Configurar `num.partitions` e `concurrency` no listener.

### 5.3. Acknowledgments Manuais
- Controle manual de commits de offset.

### 5.4. Exercícios Práticos - Configurações
- Criar dois consumers no mesmo group.
- Implementar acknowledgment manual.

## 6. Retry, Dead Letter Topics e Error Handling

### 6.1. RetryTemplate
- Tentativas de reprocessamento em caso de falha.

### 6.2. Dead Letter Publishing Recoverer (DLT)
- Redirecionamento de mensagens com erro para tópico de falha.

### 6.3. ErrorHandler
- Tratamento centralizado de erros.

### 6.4. Exercícios Práticos - Resiliência
- Criar ErrorHandler customizado.
- Configurar DLT para mensagens inválidas.

## 7. Monitoramento e Tuning

### 7.1. Kafka Metrics com Actuator
- Expor métricas de Kafka no Spring Boot.

### 7.2. Lag Monitoring
- Monitorar lag de consumidores.

### 7.3. Exercícios Práticos - Monitoramento
- Expor métricas Kafka via Actuator.
- Criar alerta de lag alto.

## 8. Testes com Spring Kafka

### 8.1. Embedded Kafka
- Uso de broker Kafka embutido para testes.

### 8.2. Testes Unitários com KafkaTemplate
- Mock de KafkaTemplate.

### 8.3. Exercícios Práticos - Testes
- Criar teste de integração com Embedded Kafka.
- Testar envio e recebimento de uma mensagem.

---

