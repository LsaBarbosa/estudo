# Roadmap de Estudos – Angular

## Índice

- [1. Fundamentos do Angular](#1-fundamentos-do-angular)
- [2. Componentes](#2-componentes)
- [3. Diretivas](#3-diretivas)
- [4. Serviços e Injeção de Dependência](#4-serviços-e-injeção-de-dependência)
- [5. Roteamento (Routing)](#5-roteamento-routing)
- [6. Consumo de APIs REST (HttpClient)](#6-consumo-de-apis-rest-httpclient)
- [7. Formulários](#7-formulários)
- [8. Pipes e Formatação de Dados](#8-pipes-e-formatação-de-dados)
- [9. Testes em Angular](#9-testes-em-angular)
- [10. Angular Avançado](#10-angular-avançado)

## 1. Fundamentos do Angular

### 1.1. O que é o Angular?
- Framework front-end baseado em TypeScript.
- Mantido pelo Google.

### 1.2. Estrutura de um Projeto Angular
- Módulos, Componentes, Serviços e Templates.

### 1.3. Ferramentas Essenciais: Node.js, NPM e Angular CLI
- Instalação do Node.js.
- Uso da Angular CLI para criação e gerenciamento de projetos.

### 1.4. Exercícios Práticos - Fundamentos
- Instalar Angular CLI.
- Criar primeiro projeto Angular.

## 2. Componentes

### 2.1. Criação de Componentes
- Comando: `ng generate component`.

### 2.2. Comunicação entre Componentes
- @Input e @Output.

### 2.3. Data Binding (Interpolation, Property, Event e Two-Way)
- Formas de ligação de dados.

### 2.4. Exercícios Práticos - Componentes
- Criar dois componentes e passar dados entre eles.
- Implementar data-binding nos templates.

## 3. Diretivas

### 3.1. Diretivas Estruturais (*ngIf, *ngFor)
- Controle de exibição de elementos.

### 3.2. Diretivas de Atributo (ngClass, ngStyle)
- Manipulação de estilos e classes.

### 3.3. Criando Diretivas Customizadas
- Exemplo de uma diretiva de destaque.

### 3.4. Exercícios Práticos - Diretivas
- Criar lista de itens usando *ngFor.
- Criar diretiva customizada para mudar cor de fundo.

## 4. Serviços e Injeção de Dependência

### 4.1. Criando Serviços
- Comando: `ng generate service`.

### 4.2. Dependency Injection
- Como o Angular injeta dependências.

### 4.3. Singleton vs Scoped Services
- Escopos de serviços.

### 4.4. Exercícios Práticos - Serviços
- Criar um serviço para manipular lista de produtos.
- Injetar serviço em múltiplos componentes.

## 5. Roteamento (Routing)

### 5.1. Configurando Rotas
- Uso de RouterModule.

### 5.2. Roteamento com Parâmetros
- Exemplo com parâmetros de rota.

### 5.3. Guardas de Rotas (Route Guards)
- Controle de acesso por rotas.

### 5.4. Exercícios Práticos - Roteamento
- Criar rotas para dois componentes.
- Proteger rota com Route Guard.

## 6. Consumo de APIs REST (HttpClient)

### 6.1. HttpClientModule
- Configuração no AppModule.

### 6.2. GET, POST, PUT, DELETE
- Métodos básicos de HTTP.

### 6.3. Tratamento de Erros com RxJS
- Uso de catchError.

### 6.4. Exercícios Práticos - API
- Criar serviço que consome API externa.
- Exibir lista de usuários na tela.

## 7. Formulários

### 7.1. Template-driven Forms
- Formulário baseado em templates.

### 7.2. Reactive Forms
- Formulário programático com FormGroup.

### 7.3. Validações Personalizadas
- Criar validações específicas.

### 7.4. Exercícios Práticos - Formulários
- Criar formulário de cadastro com validações.
- Exibir mensagens de erro dinâmicas.

## 8. Pipes e Formatação de Dados

### 8.1. Pipes Padrão (DatePipe, CurrencyPipe)
- Formatação de datas e moedas.

### 8.2. Criando Pipes Customizados
- Exemplo de pipe para transformação de texto.

### 8.3. Exercícios Práticos - Pipes
- Usar CurrencyPipe para mostrar preços.
- Criar pipe que converte texto para maiúsculas.

## 9. Testes em Angular

### 9.1. Testes Unitários com Jasmine/Karma
- Estrutura de teste no Angular CLI.

### 9.2. Testes de Componentes e Serviços
- Testar lógica de serviços.

### 9.3. Exercícios Práticos - Testes
- Escrever teste de um serviço simples.
- Criar teste para verificar exibição de componentes.

## 10. Angular Avançado

### 10.1. Lazy Loading
- Carregamento sob demanda de módulos.

### 10.2. State Management (NgRx)
- Gerenciamento de estado global.

### 10.3. Dynamic Components
- Criação de componentes em tempo de execução.

### 10.4. Exercícios Práticos - Angular Avançado
- Criar módulo com Lazy Loading.
- Configurar NgRx com um exemplo simples.

---

