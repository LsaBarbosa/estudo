# Roadmap de Estudos – AWS Lambda

## Índice

- [1. Fundamentos do AWS Lambda](#1-fundamentos-do-aws-lambda)

  - [1.1. O que é Serverless?](#11-o-que-é-serverless)
  - [1.2. Conceito do AWS Lambda](#12-conceito-do-aws-lambda)
  - [1.3. Casos de Uso Reais](#13-casos-de-uso-reais)
  - [1.4. Exercícios Práticos - Fundamentos](#14-exercícios-práticos---fundamentos)

- [2. Desenvolvimento de Funções Lambda](#2-desenvolvimento-de-funções-lambda)

  - [2.1. Linguagens Suportadas](#21-linguagens-suportadas)
  - [2.2. Estrutura de um Handler Lambda](#22-estrutura-de-um-handler-lambda)
  - [2.3. Testando localmente (AWS SAM CLI)](#23-testando-localmente-aws-sam-cli)
  - [2.4. Empacotamento de Dependências](#24-empacotamento-de-dependências)
  - [2.5. Exercícios Práticos - Desenvolvimento](#25-exercícios-práticos---desenvolvimento)

- [3. Triggers e Eventos](#3-triggers-e-eventos)

  - [3.1. Integração com API Gateway](#31-integração-com-api-gateway)
  - [3.2. Integração com S3](#32-integração-com-s3)
  - [3.3. Integração com DynamoDB](#33-integração-com-dynamodb)
  - [3.4. CloudWatch Events e EventBridge](#34-cloudwatch-events-e-eventbridge)
  - [3.5. Exercícios Práticos - Eventos](#35-exercícios-práticos---eventos)

- [4. Deployment e Automação](#4-deployment-e-automação)

  - [4.1. Deploy via AWS CLI](#41-deploy-via-aws-cli)
  - [4.2. Deploy via Terraform](#42-deploy-via-terraform)
  - [4.3. Deploy via AWS SAM](#43-deploy-via-aws-sam)
  - [4.4. Exercícios Práticos - Deployment](#44-exercícios-práticos---deployment)

- [5. Monitoramento e Logging](#5-monitoramento-e-logging)

  - [5.1. CloudWatch Logs](#51-cloudwatch-logs)
  - [5.2. X-Ray (Tracing)](#52-x-ray-tracing)
  - [5.3. Métricas de Performance](#53-métricas-de-performance)
  - [5.4. Exercícios Práticos - Monitoramento](#54-exercícios-práticos---monitoramento)

- [6. Melhores Práticas e Otimizações](#6-melhores-práticas-e-otimizações)

  - [6.1. Configuração de Timeout e Memória](#61-configuração-de-timeout-e-memória)
  - [6.2. Cold Start: Como minimizar](#62-cold-start-como-minimizar)
  - [6.3. Versionamento e Aliases](#63-versionamento-e-aliases)
  - [6.4. Exercícios Práticos - Otimização](#64-exercícios-práticos---otimização)

---

## 1. Fundamentos do AWS Lambda

### 1.1. O que é Serverless?

- Modelo de computação sem servidor gerenciado.
- Escalabilidade automática.
- Custo baseado em execução (pay-per-use).

### 1.2. Conceito do AWS Lambda

- Serviço que executa funções em resposta a eventos.
- Suporte a múltiplas linguagens.

### 1.3. Casos de Uso Reais

- Processamento de uploads S3.
- Backend para APIs REST.
- Processamento de streams DynamoDB.

### 1.4. Exercícios Práticos - Fundamentos

- Criar uma Lambda "Hello World" via Console.
- Retornar um JSON simples.

---

## 2. Desenvolvimento de Funções Lambda

### 2.1. Linguagens Suportadas

- Node.js, Python, Java, Go, .NET Core, Ruby.

### 2.2. Estrutura de um Handler Lambda

**Exemplo Node.js:**

```javascript
exports.handler = async (event) => {
  console.log("Evento recebido:", event);
  return { statusCode: 200, body: "Hello Lambda!" };
};
```

### 2.3. Testando localmente (AWS SAM CLI)

```bash
sam init
sam build
sam local invoke
```

### 2.4. Empacotamento de Dependências

**Python:**

```bash
pip install requests -t .
zip -r function.zip .
```

### 2.5. Exercícios Práticos - Desenvolvimento

- Criar Lambda Node.js com parâmetro de entrada.
- Criar Lambda Python que consome API externa.

---

## 3. Triggers e Eventos

### 3.1. Integração com API Gateway

- Criar endpoint REST chamando uma Lambda.

### 3.2. Integração com S3

- Executar Lambda após upload em bucket.

### 3.3. Integração com DynamoDB

- Trigger em eventos de inserção.

### 3.4. CloudWatch Events e EventBridge

- Disparar Lambda via cron ou evento customizado.

### 3.5. Exercícios Práticos - Eventos

- Criar Lambda para uploads S3.
- Criar Lambda para API Gateway GET.
- Criar Lambda para inserir log após alteração no DynamoDB.

---

## 4. Deployment e Automação

### 4.1. Deploy via AWS CLI

```bash
aws lambda create-function --function-name HelloWorld --runtime nodejs14.x --role arn:aws:iam::account-id:role/lambda-role --handler index.handler --zip-file fileb://function.zip
```

### 4.2. Deploy via Terraform

**Exemplo:**

```hcl
resource "aws_lambda_function" "example" {
  function_name = "hello_lambda"
  filename      = "lambda.zip"
  handler       = "index.handler"
  runtime       = "nodejs14.x"
  role          = aws_iam_role.lambda_exec.arn
}
```

### 4.3. Deploy via AWS SAM

```bash
sam build
sam deploy --guided
```

### 4.4. Exercícios Práticos - Deployment

- Deploy manual com AWS CLI.
- Deploy com Terraform incluindo IAM Role.
- Deploy usando AWS SAM.

---

## 5. Monitoramento e Logging

### 5.1. CloudWatch Logs

- Ver logs de execução com:

```bash
aws logs filter-log-events --log-group-name /aws/lambda/HelloWorld
```

### 5.2. X-Ray (Tracing)

- Ativar tracing na Lambda.
- Analisar o fluxo de execução no X-Ray.

### 5.3. Métricas de Performance

- Métricas padrão (invocações, duração, erros).

### 5.4. Exercícios Práticos - Monitoramento

- Gerar erro intencional e visualizar no CloudWatch.
- Ativar X-Ray e revisar traces de execução.

---

## 6. Melhores Práticas e Otimizações

### 6.1. Configuração de Timeout e Memória

- Ajustar recursos de acordo com workload.

### 6.2. Cold Start: Como minimizar

- Usar provisioned concurrency.
- Reduzir dependências.

### 6.3. Versionamento e Aliases

- Criar múltiplas versões da Lambda.
- Criar Aliases (dev, prod).

### 6.4. Exercícios Práticos - Otimização

- Criar duas versões da mesma Lambda.
- Criar alias apontando para a nova versão.
- Configurar provisioned concurrency.

---

