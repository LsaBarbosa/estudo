# Roadmap de Estudos – Monitoramento com AWS

## Índice

- [1. Introdução ao Monitoramento na Nuvem](#1-introdução-ao-monitoramento-na-nuvem)
- [2. Amazon CloudWatch](#2-amazon-cloudwatch)
- [3. AWS CloudTrail](#3-aws-cloudtrail)
- [4. AWS X-Ray (Monitoramento de Tracing e Performance)](#4-aws-x-ray-monitoramento-de-tracing-e-performance)
- [5. Monitoramento de Serviços Gerenciados](#5-monitoramento-de-serviços-gerenciados)
- [6. Integração com Ferramentas de Terceiros](#6-integração-com-ferramentas-de-terceiros)
- [7. Notificações e Automação de Respostas](#7-notificações-e-automação-de-respostas)
- [8. Monitoramento de Custo e Uso](#8-monitoramento-de-custo-e-uso)
- [9. Melhores Práticas de Monitoramento AWS](#9-melhores-práticas-de-monitoramento-aws)

## 1. Introdução ao Monitoramento na Nuvem

### 1.1. Por que monitorar recursos na nuvem?
- Garantir disponibilidade.
- Melhorar desempenho.
- Controlar custos.

### 1.2. Conceitos de Observabilidade: Logs, Métricas e Traces
- Logs: Registro de eventos.
- Métricas: Dados numéricos ao longo do tempo.
- Traces: Fluxo de requisições entre serviços.

### 1.3. Serviços AWS para Monitoramento
- CloudWatch, CloudTrail, X-Ray.

### 1.4. Exercícios Práticos - Introdução
- Criar um diagrama de arquitetura com serviços de monitoramento.

## 2. Amazon CloudWatch

### 2.1. Métricas com CloudWatch Metrics
- Monitorar CPU, memória, uso de disco.

### 2.2. Logs com CloudWatch Logs
- Capturar logs de aplicações e serviços.

### 2.3. Alarmes com CloudWatch Alarms
- Criar alertas com base em métricas.

### 2.4. Dashboards com CloudWatch Dashboards
- Visualizar dados em tempo real.

### 2.5. Exercícios Práticos - CloudWatch
- Criar um alarme para EC2 com uso alto de CPU.
- Configurar dashboard customizado.

## 3. AWS CloudTrail

### 3.1. Registro de Eventos da Conta AWS
- Captura de ações da API AWS.

### 3.2. Auditoria de Atividades de Usuário
- Monitorar acessos e alterações.

### 3.3. Exercícios Práticos - CloudTrail
- Ativar CloudTrail.
- Consultar histórico de criação de recursos.

## 4. AWS X-Ray (Monitoramento de Tracing e Performance)

### 4.1. Distributed Tracing
- Visualizar fluxo de requisições entre serviços.

### 4.2. Análise de Performance de Aplicações
- Identificar gargalos em microsserviços.

### 4.3. Exercícios Práticos - X-Ray
- Integrar aplicação Spring Boot com AWS X-Ray.
- Visualizar mapa de serviços no console AWS.

## 5. Monitoramento de Serviços Gerenciados

### 5.1. Monitoramento de EC2
- Monitorar instâncias com CloudWatch.

### 5.2. Monitoramento de RDS
- Métricas de banco de dados.

### 5.3. Monitoramento de Lambda
- Logs e métricas por invocação.

### 5.4. Exercícios Práticos - Serviços Gerenciados
- Criar alarme de latência de Lambda.
- Analisar métricas de RDS.

## 6. Integração com Ferramentas de Terceiros

### 6.1. Exportação de Logs para Elasticsearch/OpenSearch
- Analisar logs com Kibana.

### 6.2. Integração com Datadog, Grafana ou Prometheus
- Exportar métricas via CloudWatch Metrics Exporter.

### 6.3. Exercícios Práticos - Integrações
- Exportar logs de CloudWatch para OpenSearch.
- Criar painel Grafana com métricas AWS.

## 7. Notificações e Automação de Respostas

### 7.1. SNS - Simple Notification Service
- Envio de alertas por e-mail ou SMS.

### 7.2. Lambda Trigger via Alarme
- Reações automáticas a eventos.

### 7.3. Exercícios Práticos - Notificações
- Criar SNS Topic e assinar um e-mail.
- Disparar Lambda em caso de CPU alta.

## 8. Monitoramento de Custo e Uso

### 8.1. AWS Cost Explorer
- Visualizar e analisar custos.

### 8.2. Budgets e Alertas de Custo
- Criar limites de gasto.

### 8.3. Exercícios Práticos - Custo
- Configurar Budget para controlar gastos mensais.

## 9. Melhores Práticas de Monitoramento AWS

### 9.1. Monitoramento Proativo
- Criar alertas antes de falhas acontecerem.

### 9.2. Centralização de Logs
- Uso de um único bucket S3 para logs.

### 9.3. Exercícios Práticos - Boas Práticas
- Implementar centralização de logs.
- Criar uma política de retenção de logs.

---

