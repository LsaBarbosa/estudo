# Roadmap de Estudos – Amazon DynamoDB

## 1. Fundamentos do DynamoDB

### 1.1. O que é o DynamoDB?
- Serviço NoSQL totalmente gerenciado pela AWS.
- Alta disponibilidade, escalabilidade automática e baixa latência.
- Armazena dados em formato chave-valor e documentos.

### 1.2. Conceitos de Tabela, Item e Atributo
- **Tabela:** Contêiner de dados (exemplo: "Customers").
- **Item:** Cada linha de dados (exemplo: cliente individual).
- **Atributo:** Campos do item (exemplo: `id`, `nome`, `email`).

### 1.3. Tipos de Chave (Partition Key / Sort Key)
- **Partition Key:** Identificador principal para distribuir os dados.
- **Sort Key:** (Opcional) Permite múltiplos itens com a mesma Partition Key.

### 1.4. Capacidades de Leitura e Escrita (RCU/WCU)
- **RCU:** Unidades de capacidade de leitura.
- **WCU:** Unidades de capacidade de escrita.
- Modos: **On-Demand** ou **Provisioned**.

### 1.5. Exercícios Práticos - Fundamentos
- Criar uma tabela "Orders" com Partition Key `orderId`.
- Inserir um item usando AWS CLI.
- Consultar o item com o `GetItem`.

---

## 2. Modelagem de Dados no DynamoDB

### 2.1. Modelagem baseada em acesso
- Pensar nas consultas antes de modelar.
- Otimizar a estrutura de chave conforme os padrões de acesso.

### 2.2. Indexes: GSI e LSI
- **GSI (Global Secondary Index):** Pode ter Partition e Sort Keys diferentes da tabela principal.
- **LSI (Local Secondary Index):** Mantém a Partition Key, muda apenas a Sort Key.

### 2.3. One-to-Many e Many-to-Many
- Modelagem com Composite Keys.
- Uso de atributos de tipo (`entityType`) em Single Table Design.

### 2.4. Patterns: Single Table Design
- Agrupar múltiplos tipos de entidade numa única tabela.
- Exemplo: tabela contendo `User`, `Order` e `Product`.

### 2.5. Exercícios Práticos - Modelagem
- Modelar um cenário com clientes e pedidos (One-to-Many).
- Criar um GSI para buscar pedidos por status.
- Implementar Single Table Design para `User`, `Order`, `Product`.

---

## 3. Operações CRUD com DynamoDB

### 3.1. PutItem, GetItem, UpdateItem, DeleteItem
- Criar item com **PutItem**.
- Buscar com **GetItem**.
- Alterar atributo com **UpdateItem**.
- Excluir com **DeleteItem**.

### 3.2. Query vs Scan
- **Query:** Filtra por Partition Key (mais eficiente).
- **Scan:** Varre toda a tabela (mais custoso).

### 3.3. Batch Operations
- **BatchGetItem:** Buscar múltiplos itens de uma vez.
- **BatchWriteItem:** Inserir ou excluir múltiplos itens.

### 3.4. Exercícios Práticos - CRUD
- Criar um item de `Customer` via Java AWS SDK.
- Realizar update para adicionar novo atributo.
- Realizar um Query por Partition Key.
- Fazer um Scan em toda a tabela.

---

## 4. Performance e Tuning

### 4.1. Provisioned vs On-Demand Capacity
- **On-Demand:** Ajuste automático.
- **Provisioned:** Controle manual de throughput.

### 4.2. Throttling e Retry
- Como detectar erros de throughput.
- Implementar política de Retry Exponencial.

### 4.3. DAX (DynamoDB Accelerator)
- Cache em memória para leitura rápida.
- Reduz latência.

### 4.4. Exercícios Práticos - Performance
- Alterar tabela de On-Demand para Provisioned.
- Simular Throttling com alto volume de requisições.
- Testar consulta com e sem DAX (se disponível).

---

## 5. Integração com Aplicações

### 5.1. DynamoDB com AWS SDK for Java
- Usar classes como `DynamoDbClient`, `PutItemRequest`, `QueryRequest`.

### 5.2. DynamoDB com Spring Data DynamoDB
- Anotar entidades com `@DynamoDBTable`.
- Criar repositórios Spring.

### 5.3. Streams e Lambda Triggers
- Configurar Streams para capturar alterações.
- Criar uma Lambda para processar eventos de inserção.

### 5.4. Exercícios Práticos - Integração
- Criar CRUD completo com Spring Boot.
- Configurar Stream + Lambda para logar inserts.
- Realizar consulta por GSI em código Java.

---

## 6. Segurança e Backup

### 6.1. Controle de Acesso com IAM
- Criar política para permitir somente leitura.
- Aplicar a um usuário específico.

### 6.2. Backup & Restore
- Criar um Backup Manual.
- Restaurar uma tabela a partir de um backup.

### 6.3. Point-in-Time Recovery (PITR)
- Ativar PITR para uma tabela.
- Restaurar um estado anterior.

### 6.4. Exercícios Práticos - Segurança
- Criar uma política de IAM de leitura restrita.
- Fazer um backup manual e restaurar.
- Ativar e testar PITR.

---

## 7. Monitoramento e Troubleshooting

### 7.1. CloudWatch Metrics para DynamoDB
- Monitorar: `ConsumedReadCapacityUnits`, `ThrottledRequests`, etc.

### 7.2. DynamoDB Streams Monitoring
- Verificar fluxo de eventos em Streams.
- Monitorar falhas de entrega para Lambda.

### 7.3. Exercícios Práticos - Monitoramento
- Criar alarmes no CloudWatch para alto consumo de RCU.
- Monitorar Streams com Lambda.
- Criar um dashboard simples de uso.

---

## 8. Preparação para Certificação AWS

### 8.1. Exames onde DynamoDB é cobrado
- AWS Certified Developer – Associate
- AWS Certified Solutions Architect – Associate
- AWS Certified Database – Specialty

### 8.2. Tópicos mais frequentes em provas
- Modelagem de chave.
- Performance e escalabilidade.
- Consistency Models.
- Streams e Triggers.

### 8.3. Exercícios Práticos - Certificação
- Fazer questões de simulados AWS sobre DynamoDB.
- Configurar uma Single Table Design como desafio.
- Criar um fluxo com Streams + Lambda + SQS.

---

