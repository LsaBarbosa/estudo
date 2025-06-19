# Roadmap de Estudos – Apache Kafka

## Índice

- [1. Fundamentos do Apache Kafka](#1-fundamentos-do-apache-kafka)
  - [1.1. O que é o Apache Kafka?](#11-o-que-é-o-apache-kafka)
  - [1.2. Arquitetura Básica do Kafka](#12-arquitetura-básica-do-kafka)
  - [1.3. Casos de Uso Reais](#13-casos-de-uso-reais)
  - [1.4. Exercícios Práticos - Fundamentos](#14-exercícios-práticos---fundamentos)

- [2. Produção e Consumo de Mensagens](#2-produção-e-consumo-de-mensagens)
  - [2.1. Criando Producers](#21-criando-producers)
  - [2.2. Criando Consumers](#22-criando-consumers)
  - [2.3. Serialização e Deserialização](#23-serialização-e-deserialização)
  - [2.4. Partições e Offsets](#24-partições-e-offsets)
  - [2.5. Exercícios Práticos - Produção e Consumo](#25-exercícios-práticos---produção-e-consumo)

- [3. Administração e Operação de Clusters Kafka](#3-administração-e-operação-de-clusters-kafka)
  - [3.1. Gerenciamento de Tópicos](#31-gerenciamento-de-tópicos)
  - [3.2. Retenção de Mensagens](#32-retenção-de-mensagens)
  - [3.3. Controle de Replicação](#33-controle-de-replicação)
  - [3.4. Configuração de Brokers](#34-configuração-de-brokers)
  - [3.5. Exercícios Práticos - Administração](#35-exercícios-práticos---administração)

- [4. Integração com Aplicações](#4-integração-com-aplicações)
  - [4.1. Kafka com Spring Boot](#41-kafka-com-spring-boot)
  - [4.2. Kafka Connect](#42-kafka-connect)
  - [4.3. Kafka Streams](#43-kafka-streams)
  - [4.4. Exercícios Práticos - Integração](#44-exercícios-práticos---integração)

- [5. Monitoramento e Performance](#5-monitoramento-e-performance)
  - [5.1. Monitoramento com JMX e Prometheus](#51-monitoramento-com-jmx-e-prometheus)
  - [5.2. Ferramentas: Confluent Control Center, Grafana](#52-ferramentas-confluent-control-center-grafana)
  - [5.3. Ajustes de Performance](#53-ajustes-de-performance)
  - [5.4. Exercícios Práticos - Monitoramento](#54-exercícios-práticos---monitoramento)

- [6. Preparação para Certificação - Confluent Certified Developer/Admin](#6-preparação-para-certificação---confluent-certified-developeradmin)
  - [6.1. Overview das Certificações](#61-overview-das-certificações)
  - [6.2. Conteúdo mais cobrado](#62-conteúdo-mais-cobrado)
  - [6.3. Recursos de Estudo](#63-recursos-de-estudo)

---

## Exercícios Práticos - Fundamentos
- Instalar Kafka local com Docker.
- Criar um tópico chamado "events".
- Produzir e consumir mensagens via CLI (`kafka-console-producer.sh` / `kafka-console-consumer.sh`).

## Exercícios Práticos - Produção e Consumo
- Criar um Producer Java que envie mensagens JSON.
- Criar um Consumer Java que filtre mensagens por chave.
- Consumir mensagens de um offset específico.
- Criar um Consumer Group com dois consumers concorrentes.

## Exercícios Práticos - Administração
- Criar tópico com 5 partições e replication factor 3.
- Alterar tempo de retenção de um tópico para 30 minutos.
- Excluir um tópico manualmente.
- Verificar o ISR (In-Sync Replicas) de um tópico.

## Exercícios Práticos - Integração
- Criar um Producer/Consumer usando Spring Boot com Spring Kafka.
- Criar um Source Connector com Kafka Connect para ler dados de um banco MySQL.
- Desenvolver uma aplicação Kafka Streams para fazer agregações por chave.

## Exercícios Práticos - Monitoramento
- Configurar Prometheus para coletar métricas JMX do Kafka Broker.
- Criar um dashboard no Grafana com lag de consumer.
- Simular alto throughput e medir o impacto.
- Criar um alerta de Consumer Lag usando Prometheus AlertManager.

## Exercícios Práticos - Certificação
- Simular produção e consumo em diferentes grupos.
- Fazer troubleshooting de um cluster com broker offline.
- Criar tópicos com configurações avançadas (compression.type, cleanup.policy).
- Resolver problemas de serialization/deserialization com Avro.

---

