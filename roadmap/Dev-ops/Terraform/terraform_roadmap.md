# Roadmap de Estudos – Terraform (Infrastructure as Code)

## Índice

- [1. Fundamentos do Terraform](#1-fundamentos-do-terraform)
- [2. Trabalhando com Recursos](#2-trabalhando-com-recursos)
- [3. Gerenciamento de Estado (State Management)](#3-gerenciamento-de-estado-state-management)
- [4. Módulos e Reutilização](#4-módulos-e-reutilização)
- [5. Deploy Automatizado e CI/CD](#5-deploy-automatizado-e-cicd)
- [6. Boas Práticas e Segurança](#6-boas-práticas-e-segurança)
- [7. Estudos Avançados](#7-estudos-avançados)

## 1. Fundamentos do Terraform

### 1.1. O que é Infrastructure as Code (IaC)?
- Gerenciamento de infraestrutura via código declarativo.
- Permite versionamento e repetibilidade.

### 1.2. Conceitos Básicos do Terraform
- Providers
- Resources
- Variables
- Outputs

### 1.3. Instalação e Configuração Inicial
- Download do Terraform CLI.
- Configuração de provider AWS.

### 1.4. Exercícios Práticos - Fundamentos
- Instalar Terraform localmente.
- Criar provider AWS com região `us-east-1`.

## 2. Trabalhando com Recursos

### 2.1. Providers
- AWS, GCP, Azure, etc.

### 2.2. Resources
- Exemplos: `aws_s3_bucket`, `aws_instance`.

### 2.3. Variables e Outputs
- Uso de `variables.tf`.
- Uso de `outputs.tf`.

### 2.4. Exercícios Práticos - Recursos
- Criar um S3 Bucket usando variável para nome.
- Exibir ARN do bucket via output.

## 3. Gerenciamento de Estado (State Management)

### 3.1. Arquivo de Estado Local
- Arquivo `.tfstate` local.

### 3.2. Remote State (S3, GCS, etc)
- Configurar backend S3 com DynamoDB para locking.

### 3.3. State Locking e Lock Prevention
- Evitar alterações simultâneas.

### 3.4. Exercícios Práticos - State
- Criar backend remoto com S3.
- Simular lock com duas execuções paralelas.

## 4. Módulos e Reutilização

### 4.1. O que são Módulos
- Blocos reutilizáveis de infraestrutura.

### 4.2. Criando Módulos Customizados
- Exemplo: módulo para criar VPC.

### 4.3. Uso de Módulos da Terraform Registry
- Exemplo: módulo oficial de VPC AWS.

### 4.4. Exercícios Práticos - Módulos
- Criar um módulo para S3.
- Reutilizar módulo oficial de VPC.

## 5. Deploy Automatizado e CI/CD

### 5.1. Terraform CLI em Pipelines
- Uso de `terraform init`, `plan`, `apply` em pipelines.

### 5.2. Terraform Cloud e Terraform Enterprise
- Workspaces, Remote Runs.

### 5.3. Exercícios Práticos - CI/CD
- Criar pipeline GitLab CI que faça validate + plan.
- Configurar workflow no GitHub Actions.

## 6. Boas Práticas e Segurança

### 6.1. Uso de .tfvars para Secrets
- Separar variáveis sensíveis.

### 6.2. Configuração de Backend Seguro
- Configurar S3 com criptografia.

### 6.3. Sensitive Variables
- Marcar outputs como sensitive.

### 6.4. Exercícios Práticos - Segurança
- Criar arquivo `secrets.tfvars` com variáveis sensíveis.
- Proteger outputs sensíveis.

## 7. Estudos Avançados

### 7.1. Sentinel Policies
- Políticas de aprovação antes de apply.

### 7.2. Drift Detection
- Detectar mudanças manuais no ambiente.

### 7.3. Custom Providers
- Criar um provider customizado.

### 7.4. Exercícios Práticos - Avançado
- Ativar Drift Detection.
- Criar uma policy Sentinel simples para bloquear apply sem aprovação.

---

