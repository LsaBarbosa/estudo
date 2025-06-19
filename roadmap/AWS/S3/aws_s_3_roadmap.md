# Roadmap de Estudos – Amazon S3 (AWS Simple Storage Service)

## Índice

- [1. Fundamentos do Amazon S3](#1-fundamentos-do-amazon-s3)
- [2. Operações Básicas com S3](#2-operações-básicas-com-s3)
- [3. Segurança e Controle de Acesso](#3-segurança-e-controle-de-acesso)
- [4. Versionamento e Recuperação](#4-versionamento-e-recuperação)
- [5. Storage Classes e Custo](#5-storage-classes-e-custo)
- [6. Logging e Monitoramento](#6-logging-e-monitoramento)
- [7. Gerenciamento de Ciclo de Vida (Lifecycle Rules)](#7-gerenciamento-de-ciclo-de-vida-lifecycle-rules)
- [8. Integração com Aplicações](#8-integração-com-aplicações)
- [9. Static Website Hosting com S3](#9-static-website-hosting-com-s3)
- [10. Melhores Práticas e Custo](#10-melhores-práticas-e-custo)

## 1. Fundamentos do Amazon S3

### 1.1. O que é o Amazon S3?
- Serviço de armazenamento de objetos.

### 1.2. Conceitos principais: Bucket, Object, Key
- Bucket: Container de objetos.
- Object: Arquivo armazenado.
- Key: Nome único do objeto dentro do bucket.

### 1.3. Casos de uso comuns
- Backup, Arquivos estáticos, Big Data.

### 1.4. Exercícios Práticos - Fundamentos
- Criar um Bucket S3.
- Fazer upload de um arquivo.

## 2. Operações Básicas com S3

### 2.1. Criar e configurar Buckets
- Definir região, versionamento, bloqueio de acesso público.

### 2.2. Upload e Download de Objetos
- Via Console ou AWS CLI.

### 2.3. Permissões básicas e políticas de Bucket
- Controle de acesso ao bucket.

### 2.4. Exercícios Práticos - Operações Básicas
- Fazer download de arquivo usando CLI.
- Criar política para permitir leitura pública.

## 3. Segurança e Controle de Acesso

### 3.1. Bucket Policies
- Controle centralizado de permissões.

### 3.2. IAM Policies para S3
- Controle baseado em usuários e roles.

### 3.3. ACLs (Access Control Lists)
- Controle de permissões em nível de objeto.

### 3.4. Exercícios Práticos - Segurança
- Criar IAM Policy com acesso restrito a um bucket.
- Aplicar ACL de leitura pública.

## 4. Versionamento e Recuperação

### 4.1. Habilitando Versionamento
- Manter múltiplas versões de um objeto.

### 4.2. Recuperação de Arquivos Apagados
- Restaurar versões antigas.

### 4.3. Exercícios Práticos - Versionamento
- Ativar versionamento.
- Recuperar versão anterior de um arquivo.

## 5. Storage Classes e Custo

### 5.1. Standard, Intelligent-Tiering, Glacier e Deep Archive
- Diferentes níveis de custo e acesso.

### 5.2. Transição Automática entre Storage Classes
- Regras de ciclo de vida.

### 5.3. Exercícios Práticos - Storage Classes
- Mover objeto para Glacier.
- Configurar Intelligent Tiering.

## 6. Logging e Monitoramento

### 6.1. Server Access Logging
- Registro de acessos ao bucket.

### 6.2. Integração com CloudWatch
- Monitorar eventos e erros.

### 6.3. Exercícios Práticos - Monitoramento
- Ativar logging de acesso.
- Criar alarme de upload excessivo.

## 7. Gerenciamento de Ciclo de Vida (Lifecycle Rules)

### 7.1. Regras de Expiração de Objetos
- Deletar objetos após X dias.

### 7.2. Transições de Storage Class
- Migrar objetos entre classes automaticamente.

### 7.3. Exercícios Práticos - Lifecycle
- Criar regra que move objetos para Glacier após 30 dias.

## 8. Integração com Aplicações

### 8.1. Upload programático com SDK Java ou Node.js
- Upload de arquivos via código.

### 8.2. Geração de URLs Pré-assinadas
- URLs temporárias para acesso seguro.

### 8.3. Exercícios Práticos - Integração
- Criar endpoint para upload.
- Gerar URL pré-assinada para download.

## 9. Static Website Hosting com S3

### 9.1. Configuração para servir HTML estático
- Habilitar static hosting.

### 9.2. Configuração de CORS
- Permitir requisições de outros domínios.

### 9.3. Exercícios Práticos - Static Hosting
- Hospedar site simples em S3.
- Configurar CORS para API externa.

## 10. Melhores Práticas e Custo

### 10.1. Otimização de Custos no S3
- Escolher storage class correta.

### 10.2. Segurança com Least Privilege
- Conceder apenas as permissões necessárias.

### 10.3. Exercícios Práticos - Boas Práticas
- Auditar permissões de buckets.
- Configurar bucket para logs de acesso.

---

