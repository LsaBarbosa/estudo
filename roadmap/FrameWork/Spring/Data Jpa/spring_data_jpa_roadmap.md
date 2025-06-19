# Roadmap de Estudos – Spring Boot + Spring Data JPA

## Índice

- [1. Fundamentos do Spring Data JPA](#1-fundamentos-do-spring-data-jpa)
- [2. Configuração do Projeto Spring Boot com JPA](#2-configuração-do-projeto-spring-boot-com-jpa)
- [3. Entidades e Mapeamentos JPA](#3-entidades-e-mapeamentos-jpa)
- [4. Repositórios Spring Data](#4-repositórios-spring-data)
- [5. Paginação, Ordenação e Projeções](#5-paginação-ordenação-e-projeções)
- [6. Transações e Performance](#6-transações-e-performance)
- [7. Boas Práticas com Spring Data JPA](#7-boas-práticas-com-spring-data-jpa)

## 1. Fundamentos do Spring Data JPA

### 1.1. O que é JPA?

- Java Persistence API.
- Mapeamento objeto-relacional (ORM).

### 1.2. O que é Spring Data JPA?

- Abstração da JPA.
- Reduz boilerplate de DAOs.

### 1.3. Conceito de ORM (Object-Relational Mapping)

- Conversão automática entre objetos Java e registros de banco.

### 1.4. Exercícios Práticos - Fundamentos

- Criar projeto Spring Boot com dependência Spring Data JPA.
- Configurar banco H2.

## 2. Configuração do Projeto Spring Boot com JPA

### 2.1. Dependências Maven/Gradle

- Spring Boot Starter Data JPA.
- Driver de banco (H2, MySQL, etc).

### 2.2. Configuração de Banco de Dados

- application.properties ou application.yml.

### 2.3. application.properties / application.yml

- Exemplo:

```properties
spring.datasource.url=jdbc:h2:mem:testdb
spring.jpa.show-sql=true
spring.jpa.hibernate.ddl-auto=update
```

### 2.4. Exercícios Práticos - Configuração

- Configurar conexão com MySQL.
- Alterar strategy para `spring.jpa.hibernate.ddl-auto=create-drop`.

## 3. Entidades e Mapeamentos JPA

### 3.1. Anotações Básicas: @Entity, @Id, @GeneratedValue

- Exemplo de entidade `Customer`.

### 3.2. Relacionamentos: @OneToMany, @ManyToOne, @ManyToMany

- Exemplo de relacionamento entre `Customer` e `Order`.

### 3.3. Embedded e Embeddable

- Uso de objetos embutidos dentro da entidade.

### 3.4. Exercícios Práticos - Entidades

- Criar entidade `Product` com relacionamento com `Category`.
- Implementar um relacionamento ManyToMany.

## 4. Repositórios Spring Data

### 4.1. JpaRepository e CrudRepository

- Métodos padrão: `findAll`, `save`, `deleteById`.

### 4.2. Derived Queries

- Exemplo: `findByNameContaining`, `findByStatusAndCategory`.

### 4.3. @Query (JPQL e Native Query)

- Exemplo com `@Query("SELECT c FROM Customer c WHERE c.name LIKE %:name%")`

### 4.4. Exercícios Práticos - Repositórios

- Criar `ProductRepository` com métodos derivados.
- Criar método com JPQL usando `@Query`.

## 5. Paginação, Ordenação e Projeções

### 5.1. Pageable e Sort

- Uso de `Pageable`, `Page`, `Sort`.

### 5.2. Projections (DTOs customizados)

- Interface-based Projection.
- Class-based Projection.

### 5.3. Specification e Criteria API

- Exemplo de filtro dinâmico com Specification.

### 5.4. Exercícios Práticos - Paginação

- Criar endpoint paginado `/products?page=0&size=10`.
- Criar Projections para exibir somente `name` e `price`.

## 6. Transações e Performance

### 6.1. @Transactional

- Anotação para controle de transações.

### 6.2. FetchType LAZY vs EAGER

- Controle de carregamento de relacionamentos.

### 6.3. Cache com Spring Cache e Hibernate 2nd Level Cache

- Configurar EhCache ou Caffeine.

### 6.4. Exercícios Práticos - Performance

- Adicionar @Transactional em um serviço.
- Alterar FetchType de um relacionamento e medir impacto.
- Habilitar cache de segundo nível.

## 7. Boas Práticas com Spring Data JPA

### 7.1. Evitando N+1 Problem

- Uso de Fetch Join ou EntityGraph.

### 7.2. Uso correto de Projections e DTOs

- Evitar carregar entidades completas sem necessidade.

### 7.3. Estratégias de Batch Inserts e Updates

- Uso de `spring.jpa.properties.hibernate.jdbc.batch_size`.

### 7.4. Exercícios Práticos - Boas Práticas

- Identificar e corrigir um problema de N+1.
- Refatorar repositórios para usar Projections.

---

