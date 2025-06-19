# Roadmap de Estudos – Spring Batch

## Índice

- [1. Fundamentos do Spring Batch](#1-fundamentos-do-spring-batch)
- [2. Estrutura de um Job Batch](#2-estrutura-de-um-job-batch)
- [3. Controle de Execução](#3-controle-de-execução)
- [4. Persistência de Estado](#4-persistência-de-estado)
- [5. Processamento em Lotes](#5-processamento-em-lotes)
- [6. Leituras e Escritas Avançadas](#6-leituras-e-escritas-avançadas)
- [7. Controle de Fluxo e Particionamento](#7-controle-de-fluxo-e-particionamento)
- [8. Monitoramento e Tuning](#8-monitoramento-e-tuning)

## 1. Fundamentos do Spring Batch

### 1.1. O que é Spring Batch?
- Framework para processamento em lote.
- Processamento de grandes volumes de dados.

### 1.2. Casos de Uso
- Migração de dados.
- Processamento de logs.
- Geração de relatórios.

### 1.3. Arquitetura do Spring Batch
- Job Repository, Job Launcher, Job, Step.

### 1.4. Exercícios Práticos - Fundamentos
- Criar projeto Spring Boot com Spring Batch.
- Criar um Job simples que imprime "Hello Batch".

## 2. Estrutura de um Job Batch

### 2.1. Job
- Representa um processo batch completo.

### 2.2. Step
- Unidade de trabalho dentro do Job.

### 2.3. ItemReader, ItemProcessor, ItemWriter
- Leitura, processamento e escrita de dados.

### 2.4. Exercícios Práticos - Estrutura de Job
- Criar um Job com um Step que lê uma lista de Strings, converte para maiúsculo e grava em arquivo.

## 3. Controle de Execução

### 3.1. JobParameters
- Parâmetros passados na execução.

### 3.2. JobExecutionListener
- Hooks antes e depois da execução.

### 3.3. Restartability
- Permite retomar um Job de onde parou.

### 3.4. Exercícios Práticos - Execução
- Criar um Listener que loga início e fim do Job.
- Rodar um Job com parâmetro `run.id` para múltiplas execuções.

## 4. Persistência de Estado

### 4.1. JobRepository
- Guarda estado das execuções.

### 4.2. JobExplorer
- Consulta de status de Jobs executados.

### 4.3. Exercícios Práticos - Persistência
- Configurar persistência do Spring Batch usando banco H2.
- Consultar histórico de execuções.

## 5. Processamento em Lotes

### 5.1. Chunk-Oriented Processing
- Leitura → Processamento → Escrita em chunks.

### 5.2. Tasklet
- Unidade de tarefa simples.

### 5.3. Exercícios Práticos - Processamento
- Criar um Job usando chunk de tamanho 5.
- Criar um Step usando Tasklet que apenas imprime uma mensagem.

## 6. Leituras e Escritas Avançadas

### 6.1. FlatFileItemReader / Writer
- Leitura/Escrita de arquivos CSV.

### 6.2. JdbcPagingItemReader
- Leitura paginada de banco de dados.

### 6.3. MultiResourceItemReader
- Leitura de múltiplos arquivos.

### 6.4. Exercícios Práticos - I/O
- Ler um CSV com clientes e gravar em outro CSV com transformação.
- Ler de banco usando JdbcPagingItemReader.

## 7. Controle de Fluxo e Particionamento

### 7.1. Split, Flow e Decision
- Controle de fluxo condicional entre Steps.

### 7.2. Partitioning
- Divisão de processamento em múltiplas threads.

### 7.3. Exercícios Práticos - Fluxo e Particionamento
- Criar um Job com Split Flow executando dois Steps paralelamente.
- Implementar Partitioning para processamento paralelo de arquivos.

## 8. Monitoramento e Tuning

### 8.1. JobExplorer e JobOperator
- Monitoramento e controle via API.

### 8.2. Performance Tuning
- Ajuste de commit-interval, fetch-size.

### 8.3. Exercícios Práticos - Monitoramento
- Criar um JobOperator para iniciar e parar Jobs via REST Controller.
- Medir tempo de execução com diferentes tamanhos de chunk.

---

