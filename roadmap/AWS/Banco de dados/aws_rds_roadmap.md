# Roadmap de Estudos – AWS RDS (Relational Database Service)

## Índice

- [1. Fundamentos do AWS RDS](#1-fundamentos-do-aws-rds)
- [2. Criação e Configuração de Instâncias](#2-criação-e-configuração-de-instâncias)
- [3. Segurança e Controle de Acesso](#3-segurança-e-controle-de-acesso)
- [4. Backup, Restore e Snapshots](#4-backup-restore-e-snapshots)
- [5. Alta Disponibilidade e Replicação](#5-alta-disponibilidade-e-replicação)
- [6. Monitoramento e Performance Tuning](#6-monitoramento-e-performance-tuning)
- [7. Manutenção e Atualizações](#7-manutenção-e-atualizações)

## 1. Fundamentos do AWS RDS

### 1.1. O que é o RDS?
- Serviço gerenciado de banco de dados relacional na AWS.
- Gerencia provisionamento, patching, backup e failover.

### 1.2. Tipos de Banco Suportados
- MySQL
- PostgreSQL
- MariaDB
- Oracle
- SQL Server
- Aurora

### 1.3. Casos de Uso Reais
- Aplicações web com persistência.
- Sistemas de BI com leitura intensiva.

### 1.4. Exercícios Práticos - Fundamentos
- Criar uma instância RDS MySQL.
- Conectar-se via MySQL Workbench.

## 2. Criação e Configuração de Instâncias

### 2.1. Opções de Engine
- Escolher engine conforme necessidade de aplicação.

### 2.2. Storage Types (GP2, IO1, etc)
- GP2: uso geral.
- IO1: IOPS provisionado.

### 2.3. Network (VPC, Subnet Groups, Security Groups)
- Configurar Subnet Group para múltiplas zonas de disponibilidade.
- Configurar Security Group para acesso restrito.

### 2.4. Exercícios Práticos - Instâncias
- Criar instância com storage tipo IO1.
- Configurar VPC e Subnet Group.

## 3. Segurança e Controle de Acesso

### 3.1. Encryption (at rest, in transit)
- Ativar criptografia com KMS.

### 3.2. IAM Authentication
- Autenticação via tokens IAM.

### 3.3. Security Groups e Firewalls
- Limitar acesso por IP.

### 3.4. Exercícios Práticos - Segurança
- Criar política de IAM para permitir acesso ao RDS.
- Configurar SSL connection.

## 4. Backup, Restore e Snapshots

### 4.1. Automated Backups
- Backup contínuo com retenção configurável.

### 4.2. Manual Snapshots
- Snapshots manuais para restauração futura.

### 4.3. PITR (Point-in-Time Recovery)
- Restaurar a instância para um momento específico.

### 4.4. Exercícios Práticos - Backup
- Criar snapshot manual.
- Realizar recuperação de ponto no tempo.

## 5. Alta Disponibilidade e Replicação

### 5.1. Multi-AZ Deployments
- Réplica síncrona para failover automático.

### 5.2. Read Replicas
- Réplicas assíncronas para leitura escalável.

### 5.3. Failover automático
- Detecção e troca automática de instâncias.

### 5.4. Exercícios Práticos - Alta Disponibilidade
- Habilitar Multi-AZ em uma instância.
- Criar Read Replica.

## 6. Monitoramento e Performance Tuning

### 6.1. CloudWatch Metrics para RDS
- Monitorar CPU, memória, conexões.

### 6.2. Enhanced Monitoring
- Monitoramento em nível de sistema operacional.

### 6.3. Performance Insights
- Identificar queries mais custosas.

### 6.4. Exercícios Práticos - Monitoramento
- Criar alarmes de CPU via CloudWatch.
- Ativar Performance Insights e analisar queries.

## 7. Manutenção e Atualizações

### 7.1. Maintenance Windows
- Definir períodos para manutenção automática.

### 7.2. Patch Management
- Atualizar engine para versão mais recente.

### 7.3. Upgrades de Engine
- Major/minor upgrades planejados.

### 7.4. Exercícios Práticos - Manutenção
- Agendar janela de manutenção.
- Realizar upgrade de versão MySQL de 5.7 para 8.0.

---

