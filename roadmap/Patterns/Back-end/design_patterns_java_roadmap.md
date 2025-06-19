# Roadmap de Estudos – Design Patterns em Java

## Índice

- [1. Introdução aos Design Patterns](#1-introdução-aos-design-patterns)
- [2. Padrões Criacionais](#2-padrões-criacionais)
- [3. Padrões Estruturais](#3-padrões-estruturais)
- [4. Padrões Comportamentais](#4-padrões-comportamentais)
- [5. Integração de Patterns em Projetos Spring](#5-integração-de-patterns-em-projetos-spring)
- [6. Melhores Práticas e Armadilhas Comuns](#6-melhores-práticas-e-armadilhas-comuns)

## 1. Introdução aos Design Patterns

### 1.1. O que são Design Patterns?
- Soluções reutilizáveis para problemas recorrentes de design de software.

### 1.2. Categorias de Design Patterns
- Criacionais
- Estruturais
- Comportamentais

### 1.3. Boas Práticas ao Usar Patterns
- Aplicar apenas quando necessário.
- Priorizar legibilidade e manutenibilidade.

### 1.4. Exercícios Práticos - Introdução
- Identificar padrões usados em um código Java existente.

## 2. Padrões Criacionais

### 2.1. Singleton
- Garante que uma classe tenha apenas uma instância.

### 2.2. Factory Method
- Cria objetos sem expor a lógica de criação.

### 2.3. Abstract Factory
- Produz famílias de objetos relacionados.

### 2.4. Builder
- Constrói objetos complexos passo a passo.

### 2.5. Prototype
- Clona objetos existentes.

### 2.6. Exercícios Práticos - Criacionais
- Implementar Singleton para um Logger.
- Criar uma Factory de veículos.

## 3. Padrões Estruturais

### 3.1. Adapter
- Converte interface de uma classe para outra.

### 3.2. Decorator
- Adiciona funcionalidades sem alterar a classe original.

### 3.3. Facade
- Fornece uma interface simplificada para um subsistema complexo.

### 3.4. Composite
- Trabalha com hierarquias de objetos.

### 3.5. Proxy
- Fornece um substituto ou representante de outro objeto.

### 3.6. Exercícios Práticos - Estruturais
- Criar um Adapter entre duas interfaces.
- Usar Decorator para adicionar funcionalidades a um objeto.

## 4. Padrões Comportamentais

### 4.1. Observer
- Notifica múltiplos objetos sobre alterações de estado.

### 4.2. Strategy
- Define uma família de algoritmos e os torna intercambiáveis.

### 4.3. Template Method
- Define o esqueleto de um algoritmo, deixando alguns passos para subclasses.

### 4.4. Command
- Encapsula uma solicitação como um objeto.

### 4.5. Chain of Responsibility
- Passa a solicitação por uma cadeia de handlers.

### 4.6. State
- Permite que um objeto altere seu comportamento com base no estado interno.

### 4.7. Exercícios Práticos - Comportamentais
- Criar Observer para sistema de notificações.
- Implementar Strategy para cálculo de frete.

## 5. Integração de Patterns em Projetos Spring

### 5.1. Exemplos de uso de Singleton no Spring
- Beans Spring são Singleton por padrão.

### 5.2. Uso de Strategy Pattern com Spring Beans
- Configuração de múltiplas estratégias como Beans.

### 5.3. Exemplo de Factory Method na Configuração de Beans
- Uso de métodos @Bean para criar instâncias.

### 5.4. Exercícios Práticos - Spring e Patterns
- Criar Strategy de validação de usuários.
- Criar Factory Method para criação de Repositories.

## 6. Melhores Práticas e Armadilhas Comuns

### 6.1. Overengineering (quando evitar padrões)
- Não aplicar padrões desnecessários.

### 6.2. Combinando Patterns
- Exemplo: Factory + Singleton.

### 6.3. Exercícios Práticos - Melhores Práticas
- Refatorar código para remover uso exagerado de padrões.
- Identificar casos onde o uso de um padrão melhoraria a manutenção.

---

