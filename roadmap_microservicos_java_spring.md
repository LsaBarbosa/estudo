# Roadmap Completo de Microserviços com Java & Spring

- [1. Introdução a Microserviços](#1-introdução-a-microserviços)
- [2. Design de Microserviços](#2-design-de-microserviços)
- [3. Stack Java para Microserviços](#3-stack-java-para-microserviços)
- [4. Comunicação entre Microserviços](#4-comunicação-entre-microserviços)
- [5. Descoberta e Registro de Serviços](#5-descoberta-e-registro-de-serviços)
- [6. Configuração Centralizada](#6-configuração-centralizada)
- [7. Resiliência e Observabilidade](#7-resiliência-e-observabilidade)
- [8. Segurança em Microserviços](#8-segurança-em-microserviços)
- [9. Testes e Qualidade](#9-testes-e-qualidade)
- [10. Deploy, Escalabilidade e DevOps](#10-deploy-escalabilidade-e-devops)
- [11. Evolução, Versionamento e Documentação de APIs](#11-evolução-versionamento-e-documentação-de-apis)
- [12. Estratégias de Dados em Microserviços](#12-estratégias-de-dados-em-microserviços)
- [13. Padrões Avançados e Desafios Reais](#13-padrões-avançados-e-desafios-reais)

---

## 1. Introdução a Microserviços

### 1.1. O que são microserviços?

- 1.1.1. Definição e motivação
    - Estilo arquitetural em que uma aplicação é composta por pequenos serviços
    - Serviços cada um com uma responsabilidade específica, implantado,desenvolvido e escalado de forma independente
- 1.1.2. Vantagens e desvantagens
    *
        + Escalabilidade Independente (api produto pode ter mais pods pois recebe mais tráfego)
    *
        + Resiliência (se um MS cair o sistema pode continuar funcionando)
    *
        + Deploy independente, Autonomia de times, Tecnologia adequada ao sistema

    +
        - Complexidade de integração.
- 1.1.3. Exemplo
    - [Usuário]
      |
      [API Gateway]
      / | \   \
      [Cadastro][Produtos][Carrinho][Pagamento][Entrega]

### 1.2. Arquitetura monolítica vs microserviços

- 1.2.1. Características do monólito
    - Todos os módulos, camadas e funcionalidades estão agrupados em um único artefato(jar,war,exe)
    - Deploy centralizado,Código compartilhado, esalabilidade limitada, dependencia e acoplamento
- 1.2.2. Características de microserviços
    - Múltiplos serviços independentes: Cada funcionalidade principal vira um serviço próprio, com deploy e ciclo de
      vida independentes.
    - Deploys independentes: Pode atualizar, escalar ou reiniciar apenas um serviço.
    - Bancos de dados separados: Cada serviço pode (e idealmente deve) ter seu próprio banco, evitando acoplamento de
      dados.
    - Tecnologias variadas: Cada serviço pode usar a linguagem, framework ou banco que faz mais sentido para sua
      necessidade.
    - Comunicação por API (HTTP, mensageria): Os serviços trocam informações por meio de APIs REST ou mensagens (Kafka,
      RabbitMQ).
    - Escalabilidade específica: Só escalar o que precisa (por exemplo, apenas o serviço de checkout numa Black Friday).

---

## 2. Design de Microserviços

### 2.1. Princípios de design

- 2.1.1. Independência e autonomia
- 2.1.2. Bounded Context (DDD)
    - Um conceito de DDD que define os limites de significado e responsabilidade para um modelo de domínio.
    - Cada MS deve representar um "Bounded Context" (Contexto de negocio bem definido e independente)
        - evita conflito de nomenclatura e regra de negocio em áreas diferentes
        - Cada serviço tem sua linguagem Ubíqua e lógica própia
        - O mesmo termo pode ter significado diferentes em cada contexto
        - Ex: Serviço de “Usuários” define “User”, “Role”, “Auth”.
        - Ex: Serviço de “Pedidos” define “Order”, “OrderItem”, “Shipping”.
- 2.1.3. Comunicação desacoplada
    - Reduz a dependencia forte entre serviços
    - Permite evoluir contratos, ersionar apis e mudar internals sem quebrar os outros
    - Dois tipos de comunicação: Síncrona e assíncrona
        - Síncrona: Rest(HTTP,gRPC,etc)
            - Ex: Api de produto busca todos os produtos do banco
        - Assíncrona: Filas/mensagem (RabbitMQ,Kafka)
            - Ex: Api de pagamentos envia uma msg a fila sinalizando que foi pago, outros serviços reagem.

### 2.3. Identidade e resiliência

- 2.3.1. Idempotência
    - Operação idempotente quando pode ser executada multiplas vzes com mesmo efeito que uma única execução.
    - Falhas de rede pode causar reenvio da msg, o cliente não sabe se a msg for processada
        - Se não houver idempotencia haverá efeitos colaterais, duplicação de pedidom multiplos pagamentos

```java
@PostMapping("/pagamentos")
public ResponseEntity<Pagamento> criar(@RequestBody Pagamento pagamento, 
    @RequestHeader("Idempotency-Key") String idempotencyKey) {
    if (pagamentoService.existeComIdempotencyKey(idempotencyKey)) {
        // Já processado: devolve o mesmo resultado
        return ResponseEntity.status(HttpStatus.OK)
            .body(pagamentoService.buscarPorIdempotencyKey(idempotencyKey));
    }
    // Processa o pagamento e salva idempotencyKey
    Pagamento novo = pagamentoService.processar(pagamento, idempotencyKey);
    return ResponseEntity.status(HttpStatus.CREATED).body(novo);
}
```

- 2.3.2. Retry e circuit breaker
  - RETRY: Tenta executar novamente uma operação após uma falha temporária
    - Ex
```java
@Service
public class ClienteExternoService {
    @Retry(name = "buscar-produto", fallbackMethod = "produtoFallback")
    public Produto buscarProduto(Long id) {
        // Chamada HTTP a outro serviço
        return webClient.get()
            .uri("/produtos/{id}", id)
            .retrieve()
            .bodyToMono(Produto.class)
            .block();
    }

    public Produto produtoFallback(Long id, Exception ex) {
        // Resposta alternativa (padrão, cache, etc)
        return new Produto(id, "Desconhecido", 0.0);
    }
}
```
```yml
resilience4j.retry:
  instances:
    buscar-produto:
      max-attempts: 3
      wait-duration: 2s

```
---

---

## 3. Stack Java para Microserviços
### 3.1. Spring Boot
- 3.1.1. Inicialização rápida
- 3.1.2. Configuração com `application.yml/properties`
### 3.2. Spring Web / WebFlux
- 3.2.1. RESTful APIs com `@RestController`
- 3.2.2. APIs reativas com WebFlux
### 3.3. Spring Data
- 3.3.1. JPA e bancos relacionais
- 3.3.2. MongoDB e bancos NoSQL
### 3.4. Outros frameworks importantes
- 3.4.1. MapStruct / ModelMapper (DTO mapping)
- 3.4.2. Lombok (boilerplate)

---

## 4. Comunicação entre Microserviços
### 4.1. Síncrona (HTTP/REST)
- 4.1.1. Feign Client
- 4.1.2. RestTemplate e WebClient
- 4.1.3. Boas práticas para requisições HTTP
### 4.2. Assíncrona (mensageria)
- 4.2.1. RabbitMQ
- 4.2.2. Kafka
- 4.2.3. Event-Driven Architecture
### 4.3. API Gateway
- 4.3.1. Spring Cloud Gateway
- 4.3.2. Zuul (legado)
- 4.3.3. Autenticação no Gateway

---

## 5. Descoberta e Registro de Serviços
### 5.1. Service Registry
- 5.1.1. Eureka (Spring Cloud Netflix)
- 5.1.2. Consul / Zookeeper
### 5.2. Service Discovery Client
- 5.2.1. Load Balancer integrado
- 5.2.2. Circuit Breaker integrado

---

## 6. Configuração Centralizada
### 6.1. Spring Cloud Config
- 6.1.1. Servidor de configuração
- 6.1.2. Refresh automático (`@RefreshScope`)
### 6.2. Vault (Segredos e credenciais)
- 6.2.1. Integração com Spring

---

## 7. Resiliência e Observabilidade
### 7.1. Resiliência
- 7.1.1. Retry e fallback (`@Retryable`, Resilience4j)
- 7.1.2. Circuit Breaker (`@CircuitBreaker`)
- 7.1.3. Timeout e Bulkhead
### 7.2. Observabilidade
- 7.2.1. Logs estruturados (ELK)
- 7.2.2. Tracing distribuído (Zipkin, Sleuth, OpenTelemetry)
- 7.2.3. Métricas (Prometheus, Actuator)

---

## 8. Segurança em Microserviços
### 8.1. Autenticação e Autorização
- 8.1.1. OAuth2/JWT (Spring Security)
- 8.1.2. Centralização da autenticação (SSO)
### 8.2. Segurança de transporte
- 8.2.1. HTTPS, TLS e certificados
### 8.3. Segurança entre serviços
- 8.3.1. RBAC
- 8.3.2. Policies

---

## 9. Testes e Qualidade
### 9.1. Testes unitários (JUnit, Mockito)
- 9.1.1. Testes de controller e serviço
### 9.2. Testes de integração
- 9.2.1. Testes com banco de dados real (`@DataJpaTest`)
- 9.2.2. Testes com containers (Testcontainers)
### 9.3. Testes de contrato
- 9.3.1. Pact
- 9.3.2. Spring Cloud Contract

---

## 10. Deploy, Escalabilidade e DevOps
### 10.1. Docker e Containerização
- 10.1.1. Dockerfile para microserviços Java
- 10.1.2. Docker Compose para ambiente local
### 10.2. Orquestração com Kubernetes
- 10.2.1. Manifests básicos (Deployment, Service)
- 10.2.2. ConfigMaps e Secrets
- 10.2.3. Autoescalonamento (HPA)
### 10.3. CI/CD para microserviços
- 10.3.1. Pipelines multi-serviço
- 10.3.2. Estratégias de deploy (Blue-Green, Canary)

---

## 11. Evolução, Versionamento e Documentação de APIs
### 11.1. Versionamento de endpoints
- 11.1.1. Versionamento via URI, Header, Content-Type
### 11.2. Documentação automática
- 11.2.1. OpenAPI/Swagger
- 11.2.2. Springdoc

---

## 12. Estratégias de Dados em Microserviços
### 12.1. Banco de dados por serviço
- 12.1.1. Modelagem descentralizada
- 12.1.2. Sincronização eventual
### 12.2. Padrão Saga
- 12.2.1. Orquestrado (choreography vs orchestration)
### 12.3. CQRS e Event Sourcing
- 12.3.1. Query vs Command
- 12.3.2. Implementações práticas

---

## 13. Padrões Avançados e Desafios Reais
### 13.1. Padrão Strangler Fig (migração monólito→micro)
### 13.2. API Composition, Backend for Frontend (BFF)
### 13.3. Dealing with distributed transactions

---

