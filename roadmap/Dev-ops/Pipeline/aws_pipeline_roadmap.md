# Roadmap de Estudos – Pipeline de Deploy (Teoria + AWS)

## Índice

- [1. Fundamentos de CI/CD e Pipelines](#1-fundamentos-de-cicd-e-pipelines)
- [2. Ferramentas de Pipeline na AWS](#2-ferramentas-de-pipeline-na-aws)
- [3. Arquitetura de um Pipeline CI/CD na AWS](#3-arquitetura-de-um-pipeline-cicd-na-aws)
- [4. Práticas de Qualidade em Pipelines](#4-práticas-de-qualidade-em-pipelines)
- [5. Gerenciamento de Ambientes](#5-gerenciamento-de-ambientes)
- [6. Monitoramento e Troubleshooting de Pipelines](#6-monitoramento-e-troubleshooting-de-pipelines)

## 1. Fundamentos de CI/CD e Pipelines

### 1.1. O que é CI/CD?
- **CI (Integração Contínua):** Teste e build automático de cada mudança.
- **CD (Entrega/Deploy Contínuo):** Automação do deploy em ambientes.

### 1.2. Fases de um Pipeline
- **Source → Build → Test → Deploy → Approval → Prod Deploy**

### 1.3. Benefícios da Automação de Deploy
- Menos erros manuais.
- Deploys mais rápidos.
- Feedback mais rápido.

### 1.4. Exercícios Práticos - Fundamentos
- Desenhar um fluxo de CI/CD.
- Listar ferramentas CI/CD que já conhece.

## 2. Ferramentas de Pipeline na AWS

### 2.1. AWS CodeCommit
- Repositório Git totalmente gerenciado.

### 2.2. AWS CodeBuild
- Serviço de build e testes.

### 2.3. AWS CodeDeploy
- Automação de deploy em EC2, ECS e Lambda.

### 2.4. AWS CodePipeline
- Orquestração de todo o pipeline.

### 2.5. Exercícios Práticos - Ferramentas AWS
- Criar um repositório no CodeCommit.
- Criar um build simples no CodeBuild.
- Criar um pipeline básico com CodePipeline.

## 3. Arquitetura de um Pipeline CI/CD na AWS

### 3.1. Pipeline End-to-End (CodeCommit → Build → Deploy)
- Exemplo de fluxo:
1. Push no Git.
2. Build automático.
3. Deploy automático.

### 3.2. Deploy em EC2, ECS ou Lambda
- Deploy blue/green com CodeDeploy.

### 3.3. Notificações e Feedback (SNS, CloudWatch)
- Alerta de sucesso/falha.

### 3.4. Exercícios Práticos - Arquitetura
- Criar pipeline para deploy de uma aplicação Spring Boot.
- Configurar notificação SNS para falhas de build.

## 4. Práticas de Qualidade em Pipelines

### 4.1. Testes Automatizados na Pipeline
- Unit tests, Integration tests.

### 4.2. Análise de Código Estática
- SonarQube, Checkstyle.

### 4.3. Scan de Vulnerabilidades
- Snyk, Trivy.

### 4.4. Exercícios Práticos - Qualidade
- Adicionar etapa de teste unitário no CodeBuild.
- Integrar análise SonarQube.

## 5. Gerenciamento de Ambientes

### 5.1. Multi-Stage Pipelines (Dev, QA, Prod)
- Separação clara por estágio.

### 5.2. Aprovações Manuais entre Ambientes
- Gate de aprovação.

### 5.3. Deploy Blue/Green e Canary
- Minimizar risco em produção.

### 5.4. Exercícios Práticos - Ambientes
- Criar pipeline com 3 ambientes.
- Adicionar etapa de aprovação manual.

## 6. Monitoramento e Troubleshooting de Pipelines

### 6.1. Logs de Execução (CloudWatch, CodeBuild Logs)
- Visualizar logs detalhados de cada fase.

### 6.2. Retenção e Histórico de Builds
- Configurar política de retenção de build history.

### 6.3. Falhas Comuns e Como Resolver
- Erros de permissão (IAM).
- Falhas de build.

### 6.4. Exercícios Práticos - Monitoramento
- Criar alarme no CloudWatch para falhas de deploy.
- Configurar retenção de logs para 30 dias.

---

