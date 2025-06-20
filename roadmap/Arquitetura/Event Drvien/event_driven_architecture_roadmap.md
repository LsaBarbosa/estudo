# Roadmap de Estudos – Event-Driven Architecture (EDA)

## Índice

- [1. Fundamentos da Event-Driven Architecture](#1-fundamentos-da-event-driven-architecture)
- [2. Padrões de Comunicação em EDA](#2-padrões-de-comunicação-em-eda)
- [3. Tecnologias e Ferramentas para EDA](#3-tecnologias-e-ferramentas-para-eda)
- [4. Modelagem de Eventos](#4-modelagem-de-eventos)
- [5. Implementando uma Solução Event-Driven](#5-implementando-uma-solução-event-driven)
- [6. Monitoramento, Logging e Resiliência](#6-monitoramento-logging-e-resiliência)
- [7. Estudos Avançados](#7-estudos-avançados)

## 1. Fundamentos da Event-Driven Architecture

### 1.1. O que é EDA?
- Estilo arquitetural baseado em emissão, consumo e reação a eventos.
- Comunicação assíncrona entre componentes.

### 1.2. Componentes Principais
- **Event Producers**
  - Componentes responsáveis por gerar e publicar eventos para o sistema

  - Responsabilidade Princípal
    - Detectar mudanças de estado
    - Cria eventos + metadados como: timeStamp, Id de correlação,etc

  - Boas práticas
    - Garantir que o evento se versionado e bem definido
    - Não incluir lógica
    - Ser IDEMPOTENTE (Garante que ao consumir a mesma msg mais de uma vez, produza paenas um unico resultado)
      
- **Event Consumers**
  -  Componentes que recebem os eventos produzidos.

  -  Responsabilidades Principais
    - Executa eventos de interesse nos canais apropriados.
    - Processa o evento de froma assíncrona.
    - Tratar falhas e implementar estratégias de:  retry, dead-letter queues,etc

  -  Boas práticas  
    - Utilizar mecanismo de Dead letter queue para tratar eventos que falham repetidamente.
    - Manter o consumidor desacoplado da origem do evento  
    - Garantir processamento de idempotencia
      
- **Event Channels (Brokers)**
  - Intermediario responsável por transportar o evento do produtor ao consumidor
    - São como um buffer assíncrono e garantem a entrega confiável dos eventos.

  - Exemplo:
    - Kafka, RabitMq, AWS SNS/SQS, Google Pub/Sub
          
  - Responsabilidade Principais
    - Receber evento dos produtores
    - Roteá-los para consumidores apropriados.
    - Garantir caracteristicas: durabilidade, persistencia, ordenação, resiliência.

  - Modos de entrega: Pub/Sub e Queue(fila)
```text
| **Componente**         | **Responsável por**                                | **Exemplos de Tecnologias**    |
| ---------------------- | -------------------------------------------------- | ------------------------------ |
| Event Producer         | Emitir o evento                                    | Microservices, Backend APIs    |
| Event Consumer         | Processar o evento                                 | Workers, Lambda, Microservices |
| Event Channel (Broker) | Transporte, armazenamento e roteamento dos eventos | Kafka, RabbitMQ, SQS/SNS       |

``` 
### 1.3. Benefícios da EDA
- Escalabilidade
  - Capacidade de aumentar/diminuir recursos de forma dinâmica para entender a variação na carga de trabalho
  - Como EDA Fornerce isso:
    - Processamento assíncrono
      - Eventos ficam no broker até serem processados, evitando sobrecarga imediata nos consumidores.
    - Escalabilidade Independente
      - Produtores e Consumidores podem escalar de forma separada
    - Parallel Processing
      - Multiplos cosnumidores podem processar diferentes partições de eventos em paralelo (kafka multiplas partições)  

- Resiliência
  - Capacidade de continuar operando mesmo diante de falhas
  - Como EDA Fornerce isso:
    - Retry e DLQ
      - consumidores podem tentar novamente o processamento em caso de falaha, ou encaminhar para dead letter queue
    - Persistencia de eventos
      - Brokers como kafka  armazenam eventos de forma dutável até o proessamento
    - Desacoplamento Temporal: Produtores não precisam saber se o consumer está disponível ou não no ato da publicação      

- Baixo acoplamento
  - Produtores e consumidores são independentes entre si, sem dependencias diretas de implementação 
  - Como EDA Fornerce isso:
    - Produtores conhecem somente o evento e nao o consumidor
      - Isso permite que a adição ou remoção de consumers sem afetar o produtor 
    - Flexibilidade de evolução
      - Mudanças lógicas de um cosnumidor ou surgimento de um novo requisito não exigem alterações nos producers
    - Suporte a multiplos consumers
      - Um único evento pode ser consumido por diferentes serviços com propósito distintos
```text
| **Benefício**     | **Como a EDA entrega**                                        |
| ----------------- | ------------------------------------------------------------- |
| Escalabilidade    | Processamento paralelo, escalonamento independente            |
| Resiliência       | Retentativas, persistência de mensagens, isolamento de falhas |
| Baixo Acoplamento | Independência entre produtores e consumidores                 |

```
### 1.4. Desafios comuns
- Garantia de entrega
  - AT MOST ONCE (no máximo uma vez): evento pode ser perdido, mas não será processado mais de uma vez.
  - AT LEAST ONCE (pelo menos uma vez): evento pode ser entregue mais de uma vez, mas nunca será perdido
  - EXACTLY ONCE (exatamente uma vez): cada evento será entregue e processado apenas uma vez, sem perdas nem duplicação
 
- Ordering
  - Garantir que os eventos sejam processados na mesma ordem em que foram gerados.
  - Por que é um problema:
    - Em arquiteturas distribuídas e escaláveis, diferentes instâncias de consumidores podem processar eventos fora de ordem.

  - Exemplo de problema:
    - Se os eventos OrderCreated e OrderCancelled forem processados fora de ordem, pode-se faturar um pedido que já foi cancelado.
    - Soluções comuns:
      - Particionamento com chave (Kafka): Garantir ordem dentro de uma partição específica.
      - Uso de sequence numbers: Consumidores podem validar se um evento chegou fora de ordem.
      - Processamento com Ordering Queues: Implementar filas por entidade-chave (ex: por ID de pedido).

  - Limitação:
    - Garantir ordem global (em todos os eventos) pode limitar a escalabilidade.
      
- Duplicate Event Handling
  - Consequências:
    - Processamento duplo
    - Geração de dados incosnsistentes

  - Soluções
    - Idempotência: Garantir que o processamento de um mesmo evento produza sempre o mesmo resultado
    - Duplication Store: Usar um armazenamento(redis) para rastrear ids de eventos já processados
    - Events IDs + Cache: Marcar cada evento com um UUID único e validar antes de processar
  - Exemplo prático:
    - Antes de salvar um pagamento, o consumidor verifica se já existe um registro com o eventId informado.

### 1.5. Exercícios Práticos - Fundamentos
- Criar um diagrama de fluxo de eventos simples.
- Listar 3 cenários reais que se beneficiam de EDA.

## 2. Padrões de Comunicação em EDA

### 2.1. Event Notification
- Apenas notificação, sem payload relevante.
- Características principais:
  - O payload é pequeno, geralmente só contém o tipo do evento e um identificador
  - O consumidor precisa buscar os detalhes adicionais diretamente no produtor (consulta síncrona via API, por exemplo).

- Exemplo
    Evento: UserCreated
    - ```json
    {
          "userId": 123
    }
      ```
    O consumidor, ao receber o evento, faz uma chamada GET para buscar os detalhes do usuário.

- Vantagens:
  Eventos leves.
  Simples de produzir.

- Desvantagens:
  - Consumidores ficam dependentes de consultas síncronas.
  - Pode gerar problemas de performance em casos de muitos consumidores.

### 2.2. Event-Carried State Transfer
- Evento carrega o estado completo da entidade.
- Características principais:
  - O payload inclui todos os dados relevantes da entidade ou da mudança.
  - Reduz a necessidade de chamadas síncronas posteriores.
- ```json
{
  "userId": 123,
  "name": "Lucas",
  "email": "lucas@example.com",
  "createdAt": "2025-06-20T10:00:00Z"
}
    ```
- Vantagens:
  - Evita acoplamento por chamadas síncronas.
  - Melhor performance para sistemas com múltiplos consumidores.

- Desvantagens:
  - Payloads maiores.
  - Risco de divergência de dados caso os eventos não sejam bem versionados.
    
### 2.3. Event Sourcing
- Estado da aplicação reconstruído a partir de eventos, estado da aplicação não é armazenado diretament em bancos tradicionais.

- Como funciona:
  - Cada mudança de estado gera um evento.
  - Exemplo prático:
    - Para uma conta bancária:
      - AccountCreated { balance: 0 }
      - MoneyDeposited { amount: 500 }
      - MoneyWithdrawn { amount: 200 }
      - O estado atual é obtido aplicando todos os eventos, na ordem em que aconteceram.

-  Vantagem
  - Histórico completo de todas as mudanças (Auditoria perfeita)
  - possibilidade de reconstruir o estado de qualquer ponto no tempo
  - Suporte nativo a cenários de replays ou rollback de estado
   
-  Desvantagem
  - Complexidade maior
  - Requer infraestrutra para armazenar e versionar eventos de forma consistente
  - Pode ser custoso reconstruir estados muito longos (exige snapshots periódicos)
```text
| **Padrão**             | **Descrição**                         | **Exemplo**                                       |
| ---------------------- | ------------------------------------- | ------------------------------------------------- |
| Notification           | Só notifica que algo aconteceu        | `UserCreated { userId }`                          |
| Carried State Transfer | carrega o estado completo             | `UserCreated { id, name, email }`                 |
| Sourcing               | reconstruído via sequência de eventos | `AccountCreated`,`MoneyDeposited`,`MoneyWithdrawn`|
```
### 2.4. Exercícios Práticos - Padrões
- Criar um evento simples com Event Notification.
- Criar um exemplo com Event-Carried State Transfer.
- Modelar um fluxo de Event Sourcing.

## 3. Tecnologias e Ferramentas para EDA

### 3.1. Message Brokers
- RabbitMQ, ActiveMQ

### 3.2. Streaming Platforms
- Apache Kafka, AWS Kinesis

### 3.3. Event Mesh e Event Bus
- Solace, NATS

### 3.4. Exercícios Práticos - Ferramentas
- Publicar e consumir eventos usando RabbitMQ.
- Criar um tópico Kafka e testar com Producer/Consumer Java.

## 4. Modelagem de Eventos

### 4.1. Definição de Eventos
- Nomeação clara
- Semântica imutável

### 4.2. Versionamento de Eventos
- Estratégias: Avro Schema Registry, Versioned Event Classes

### 4.3. Garantia de Entrega
- At-least-once, At-most-once, Exactly-once

### 4.4. Exercícios Práticos - Modelagem
- Criar uma estrutura de evento com campos: id, timestamp, type, payload.
- Criar uma segunda versão de um evento com campo adicional.

## 5. Implementando uma Solução Event-Driven

### 5.1. Publicação de Eventos
- Exemplo: Spring Kafka Template.

### 5.2. Consumo de Eventos
- Exemplo: KafkaListener ou RabbitListener.

### 5.3. Processamento Assíncrono
- Thread Pools, Async Executors.

### 5.4. Exercícios Práticos - Implementação
- Criar Producer Spring Boot que publica um evento.
- Criar Consumer Spring Boot que processa o evento e grava no banco.

## 6. Monitoramento, Logging e Resiliência

### 6.1. Dead Letter Queues (DLQ)
- Tratamento de mensagens com falha.

### 6.2. Retry Policies
- Backoff, Number of Retries.

### 6.3. Event Replay
- Reprocessamento de eventos antigos.

### 6.4. Exercícios Práticos - Monitoramento
- Configurar DLQ no RabbitMQ.
- Implementar retry com Spring Retry.
- Fazer replay de eventos em Kafka.

## 7. Estudos Avançados

### 7.1. Event Choreography vs Orchestration
- Diferenças, vantagens e desvantagens.

### 7.2. CQRS com EDA
- Separação de leitura e escrita.

### 7.3. Transações Eventuais
- Consistência eventual entre microserviços.

### 7.4. Recursos Recomendados
- Livro: "Designing Event-Driven Systems" – Ben Stopford.
- Artigo: https://martinfowler.com/articles/201701-event-driven.html
- Curso: Event-Driven Microservices with Spring Boot & Kafka (Udemy)

---

