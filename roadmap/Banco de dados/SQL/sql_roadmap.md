# Roadmap de Estudos – SQL (Structured Query Language)

## Índice

- [1. Fundamentos de Banco de Dados Relacional](#1-fundamentos-de-banco-de-dados-relacional)
- [2. Consultas Básicas (SELECT)](#2-consultas-básicas-select)
- [3. Operações de Manipulação de Dados (DML)](#3-operações-de-manipulação-de-dados-dml)
- [4. Filtros Avançados e Funções de Agregação](#4-filtros-avançados-e-funções-de-agregação)
- [5. Joins e Relacionamentos](#5-joins-e-relacionamentos)
- [6. Subconsultas e Views](#6-subconsultas-e-views)
- [7. DDL - Definindo Estrutura de Tabelas](#7-ddl---definindo-estrutura-de-tabelas)
- [8. Índices, Normalização e Performance](#8-índices-normalização-e-performance)
- [9. Stored Procedures e Triggers](#9-stored-procedures-e-triggers)
- [10. Transações e Controle de Concorrência](#10-transações-e-controle-de-concorrência)

## 1. Fundamentos de Banco de Dados Relacional

### 1.1. O que é um Banco de Dados Relacional?
- Armazena dados em tabelas com linhas e colunas.

### 1.2. Estrutura de Tabelas, Linhas e Colunas
- Tabela = Entidade.
- Linha = Registro.
- Coluna = Atributo.

### 1.3. Principais SGBDs do Mercado
- MySQL, PostgreSQL, Oracle, SQL Server.

### 1.4. Exercícios Práticos - Fundamentos
- Criar um banco e uma tabela simples (ex: alunos).
- Inserir registros básicos.

## 2. Consultas Básicas (SELECT)

### 2.1. Seleção de Colunas
- `SELECT coluna1, coluna2 FROM tabela;`

### 2.2. Filtros com WHERE
- `SELECT * FROM alunos WHERE idade > 18;`

### 2.3. Ordenação com ORDER BY
- `SELECT nome FROM alunos ORDER BY nome ASC;`

### 2.4. Exercícios Práticos - SELECT
- Listar todos os alunos com idade acima de 20.
- Exibir os nomes em ordem alfabética.

## 3. Operações de Manipulação de Dados (DML)

### 3.1. INSERT
- Inserir novos registros.

### 3.2. UPDATE
- Atualizar registros existentes.

### 3.3. DELETE
- Remover registros.

### 3.4. Exercícios Práticos - DML
- Inserir 5 alunos fictícios.
- Atualizar a idade de um aluno.
- Deletar um aluno específico.

## 4. Filtros Avançados e Funções de Agregação

### 4.1. Operadores Lógicos (AND, OR, NOT)
- Combinar condições no WHERE.

### 4.2. LIKE, IN, BETWEEN
- Filtragem avançada de dados.

### 4.3. Funções: COUNT, SUM, AVG, MIN, MAX
- Agregações de dados.

### 4.4. GROUP BY e HAVING
- Agrupamento de registros.

### 4.5. Exercícios Práticos - Agregação
- Contar número de alunos por idade.
- Listar idades com mais de 2 alunos.

## 5. Joins e Relacionamentos

### 5.1. INNER JOIN
- Junção de tabelas com correspondência.

### 5.2. LEFT JOIN, RIGHT JOIN
- Inclusão de registros não correspondentes.

### 5.3. FULL OUTER JOIN
- Junção completa de ambos os lados.

### 5.4. Exercícios Práticos - Joins
- Criar tabelas `alunos` e `turmas`.
- Fazer join para listar alunos e suas turmas.

## 6. Subconsultas e Views

### 6.1. Subqueries no WHERE e no FROM
- Consultas dentro de consultas.

### 6.2. Common Table Expressions (CTE)
- Consulta temporária nomeada.

### 6.3. Views
- Consultas salvas como tabelas virtuais.

### 6.4. Exercícios Práticos - Subconsultas
- Criar uma View para listar alunos com mais de 3 matérias.
- Fazer subquery que retorna alunos com idade acima da média.

## 7. DDL - Definindo Estrutura de Tabelas

### 7.1. CREATE TABLE
- Criar estrutura de tabela.

### 7.2. ALTER TABLE
- Alterar estrutura existente.

### 7.3. DROP TABLE
- Excluir tabela.

### 7.4. Exercícios Práticos - DDL
- Criar tabela de professores.
- Adicionar nova coluna na tabela alunos.
- Remover a tabela turmas.

## 8. Índices, Normalização e Performance

### 8.1. O que são Índices?
- Melhoram a performance de consultas.

### 8.2. Normal Forms (1NF, 2NF, 3NF)
- Regras de modelagem para evitar redundâncias.

### 8.3. Exercícios Práticos - Performance
- Criar índice na coluna `nome` da tabela alunos.
- Analisar uma tabela e sugerir melhorias de normalização.

## 9. Stored Procedures e Triggers

### 9.1. Stored Procedures
- Blocos de código SQL armazenados no SGBD.

### 9.2. Triggers
- Código executado automaticamente após eventos (INSERT, UPDATE).

### 9.3. Exercícios Práticos - Procedures e Triggers
- Criar uma procedure que insere novo aluno.
- Criar uma trigger que impede exclusão de alunos menores de idade.

## 10. Transações e Controle de Concorrência

### 10.1. BEGIN, COMMIT, ROLLBACK
- Controle de transações.

### 10.2. Isolation Levels
- Controle de concorrência.

### 10.3. Exercícios Práticos - Transações
- Criar uma transação que insere aluno e matrícula.
- Testar rollback em caso de erro.

---

