# Roadmap de Estudos – NoSQL (Not Only SQL)

## Índice

- [1. Fundamentos de NoSQL](#1-fundamentos-de-nosql)
- [2. Tipos de Bancos NoSQL](#2-tipos-de-bancos-nosql)
- [3. Operações CRUD em NoSQL](#3-operações-crud-em-nosql)
- [4. Modelagem de Dados em NoSQL](#4-modelagem-de-dados-em-nosql)
- [5. Indexação e Performance](#5-indexação-e-performance)
- [6. Consistência, Disponibilidade e Escalabilidade](#6-consistência-disponibilidade-e-escalabilidade)
- [7. Replicação e Alta Disponibilidade](#7-replicação-e-alta-disponibilidade)
- [8. Casos de Uso Reais para NoSQL](#8-casos-de-uso-reais-para-nosql)

## 1. Fundamentos de NoSQL

### 1.1. O que é NoSQL?
- Bancos de dados que não usam SQL tradicional.
- Flexíveis em estrutura de dados.

### 1.2. Características Principais
- Alta escalabilidade.
- Esquema flexível (Schema-less).

### 1.3. Diferenças entre SQL e NoSQL
- SQL: Tabelas e relações.
- NoSQL: Documentos, chave-valor, grafos, colunas.

### 1.4. Exercícios Práticos - Fundamentos
- Instalar MongoDB localmente.
- Criar um banco e uma coleção.

## 2. Tipos de Bancos NoSQL

### 2.1. Document-Oriented (Ex: MongoDB)
- Armazena documentos JSON-like.

### 2.2. Key-Value (Ex: Redis)
- Armazena pares chave-valor.

### 2.3. Column-Oriented (Ex: Cassandra)
- Armazena dados por colunas.

### 2.4. Graph Database (Ex: Neo4j)
- Modelagem de grafos (nós e relacionamentos).

### 2.5. Exercícios Práticos - Tipos
- Inserir documentos no MongoDB.
- Salvar dados chave-valor no Redis.

## 3. Operações CRUD em NoSQL

### 3.1. Create, Read, Update, Delete
- Operações básicas em todos os tipos de NoSQL.

### 3.2. Query Languages: SQL vs NoSQL
- MongoDB: find(), insertOne(), updateOne().
- Redis: SET, GET, DEL.

### 3.3. Exercícios Práticos - CRUD
- Criar, consultar, atualizar e deletar documentos MongoDB.
- Realizar operações SET e GET no Redis.

## 4. Modelagem de Dados em NoSQL

### 4.1. Modelagem Baseada em Documentos
- Exemplo: Uma coleção de pedidos com array de itens.

### 4.2. Denormalização
- Dados repetidos para melhor performance.

### 4.3. Particionamento (Sharding)
- Dividir dados em múltiplos servidores.

### 4.4. Exercícios Práticos - Modelagem
- Modelar um catálogo de produtos no MongoDB.
- Configurar sharding simples.

## 5. Indexação e Performance

### 5.1. Índices em MongoDB
- Criação de índices para acelerar consultas.

### 5.2. TTL Indexes em Redis
- Tempo de expiração automática.

### 5.3. Exercícios Práticos - Indexação
- Criar índice em campo de nome em MongoDB.
- Definir expiração de chave no Redis.

## 6. Consistência, Disponibilidade e Escalabilidade

### 6.1. Teorema CAP
- Trade-off entre Consistência, Disponibilidade e Tolerância à Partição.

### 6.2. Eventual Consistency
- Dados podem levar tempo para se replicar.

### 6.3. Exercícios Práticos - Consistência
- Configurar replica set no MongoDB.
- Simular atraso de replicação.

## 7. Replicação e Alta Disponibilidade

### 7.1. Replica Sets em MongoDB
- Múltiplas cópias de dados.

### 7.2. Cluster Redis com Sentinel
- Failover automático.

### 7.3. Exercícios Práticos - Replicação
- Criar e testar replica set no MongoDB.
- Configurar Sentinel para Redis.

## 8. Casos de Uso Reais para NoSQL

### 8.1. Big Data
- Armazenamento de grandes volumes com Cassandra.

### 8.2. Cache de Alta Performance
- Uso de Redis.

### 8.3. Recomendação e Redes Sociais
- Uso de Neo4j para redes sociais.

### 8.4. Exercícios Práticos - Casos de Uso
- Criar cache com Redis.
- Modelar um grafo de amigos em Neo4j.

---

