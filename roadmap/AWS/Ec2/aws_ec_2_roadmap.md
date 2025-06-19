# Roadmap de Estudos – Amazon EC2 (Máquinas Virtuais na AWS)

## Índice

- [1. Fundamentos do Amazon EC2](#1-fundamentos-do-amazon-ec2)
- [2. Lançamento e Configuração de Instâncias EC2](#2-lançamento-e-configuração-de-instâncias-ec2)
- [3. Segurança e Controle de Acesso](#3-segurança-e-controle-de-acesso)
- [4. Elastic IP e Configuração de Rede](#4-elastic-ip-e-configuração-de-rede)
- [5. Armazenamento para EC2](#5-armazenamento-para-ec2)
- [6. Auto Scaling e Load Balancer](#6-auto-scaling-e-load-balancer)
- [7. Monitoramento e Logs](#7-monitoramento-e-logs)
- [8. Backup e Recuperação](#8-backup-e-recuperação)
- [9. Gerenciamento de Custo para EC2](#9-gerenciamento-de-custo-para-ec2)
- [10. Melhores Práticas com EC2](#10-melhores-práticas-com-ec2)

## 1. Fundamentos do Amazon EC2

### 1.1. O que é EC2?
- Serviço de máquinas virtuais escaláveis na AWS.

### 1.2. Casos de Uso
- Hospedagem de sites, bancos de dados, aplicações backend.

### 1.3. Tipos de Instâncias
- General Purpose, Compute Optimized, Memory Optimized, etc.

### 1.4. Exercícios Práticos - Fundamentos
- Criar uma instância EC2 usando a AWS Console.

## 2. Lançamento e Configuração de Instâncias EC2

### 2.1. Escolha de AMI (Amazon Machine Image)
- Imagens Linux, Windows e customizadas.

### 2.2. Tipos de Instâncias e Tamanhos
- t2.micro, m5.large, etc.

### 2.3. Key Pairs e SSH Access
- Geração de par de chaves para login seguro.

### 2.4. Exercícios Práticos - Instâncias
- Conectar via SSH.
- Alterar tipo da instância.

## 3. Segurança e Controle de Acesso

### 3.1. Security Groups
- Controle de portas e tráfego.

### 3.2. Network ACLs
- Controle de tráfego em nível de subnet.

### 3.3. IAM Roles para EC2
- Concessão de permissões para acessar outros serviços AWS.

### 3.4. Exercícios Práticos - Segurança
- Criar Security Group permitindo apenas porta 22.
- Associar IAM Role a uma instância.

## 4. Elastic IP e Configuração de Rede

### 4.1. Elastic IP
- IP fixo público.

### 4.2. Configuração de VPC e Subnets
- VPC, Subnet, Internet Gateway.

### 4.3. Exercícios Práticos - Rede
- Associar Elastic IP a uma instância.
- Criar VPC customizada.

## 5. Armazenamento para EC2

### 5.1. EBS (Elastic Block Store)
- Discos persistentes.

### 5.2. Instance Store
- Armazenamento temporário local.

### 5.3. Exercícios Práticos - Armazenamento
- Criar volume EBS adicional.
- Fazer snapshot de volume.

## 6. Auto Scaling e Load Balancer

### 6.1. Auto Scaling Groups
- Escalabilidade automática.

### 6.2. Elastic Load Balancer (ELB)
- Distribuição de tráfego entre instâncias.

### 6.3. Exercícios Práticos - Escalabilidade
- Configurar Auto Scaling com mínimo 1 e máximo 3 instâncias.
- Criar Load Balancer e associar instâncias.

## 7. Monitoramento e Logs

### 7.1. Monitoramento com CloudWatch
- Uso de CPU, Disco, Rede.

### 7.2. Logs de Sistema
- CloudWatch Logs.

### 7.3. Exercícios Práticos - Monitoramento
- Criar alarme de CPU alta.
- Habilitar envio de logs para CloudWatch.

## 8. Backup e Recuperação

### 8.1. Snapshots de EBS
- Backup de volumes.

### 8.2. Amazon Machine Image (AMI) Personalizada
- Criação de AMIs customizadas.

### 8.3. Exercícios Práticos - Backup
- Criar snapshot de um volume.
- Criar AMI da instância em produção.

## 9. Gerenciamento de Custo para EC2

### 9.1. EC2 Pricing Model: On-Demand, Reserved, Spot
- Modelos de cobrança.

### 9.2. Monitoramento de Custos com Cost Explorer
- Analisar consumo e gastos.

### 9.3. Exercícios Práticos - Custos
- Simular custo de execução de instâncias.

## 10. Melhores Práticas com EC2

### 10.1. Hardening de Instâncias
- Atualizações de segurança, firewall.

### 10.2. Gerenciamento de Atualizações
- Uso de SSM (Systems Manager).

### 10.3. Exercícios Práticos - Boas Práticas
- Criar checklist de segurança EC2.
- Configurar SSM para execução remota de comandos.

---

