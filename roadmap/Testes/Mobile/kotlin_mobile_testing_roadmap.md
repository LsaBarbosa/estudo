# Roadmap de Estudos – Testes Mobile com Kotlin (Android)

## Índice

- [1. Introdução aos Testes Mobile](#1-introdução-aos-testes-mobile)
- [2. Testes Unitários com JUnit e Kotlin](#2-testes-unitários-com-junit-e-kotlin)
- [3. Testes com Mockito no Android](#3-testes-com-mockito-no-android)
- [4. Testes de Instrumentação (UI Tests)](#4-testes-de-instrumentação-ui-tests)
- [5. Testes de Integração com Room, Retrofit e ViewModel](#5-testes-de-integração-com-room-retrofit-e-viewmodel)
- [6. Testes com Coroutines e Flow](#6-testes-com-coroutines-e-flow)
- [7. Testes de UI com Jetpack Compose](#7-testes-de-ui-com-jetpack-compose)
- [8. Testes End-to-End com Firebase Test Lab](#8-testes-end-to-end-com-firebase-test-lab)
- [9. Relatórios de Testes e Cobertura](#9-relatórios-de-testes-e-cobertura)
- [10. Testes Automatizados em CI/CD para Android](#10-testes-automatizados-em-cicd-para-android)

## 1. Introdução aos Testes Mobile

### 1.1. Importância dos Testes em Aplicações Android
- Garantia de qualidade e redução de bugs.

### 1.2. Tipos de Testes no Android
- Unitário, Instrumentação (UI), Integração, E2E.

### 1.3. Estrutura de Testes no Android Studio
- Diretórios: `src/test` e `src/androidTest`.

### 1.4. Exercícios Práticos - Introdução
- Criar projeto Android com pastas de teste configuradas.

## 2. Testes Unitários com JUnit e Kotlin

### 2.1. Estrutura de um Teste Unitário
- Uso de @Test, @Before.

### 2.2. Uso de Assertions
- assertEquals, assertTrue, assertThrows.

### 2.3. Testes de Classes Utilitárias
- Testar métodos de classes helpers.

### 2.4. Exercícios Práticos - Unitários
- Criar teste unitário para uma classe de validação.

## 3. Testes com Mockito no Android

### 3.1. Criando Mocks e Stubs
- Uso de `mock()` e `when().thenReturn()`.

### 3.2. Verificando Interações
- Uso de `verify()`.

### 3.3. Exercícios Práticos - Mockito
- Testar ViewModel com dependências mockadas.

## 4. Testes de Instrumentação (UI Tests)

### 4.1. Espresso
- Testes de interação com Views.

### 4.2. UI Automator
- Testes de navegação entre aplicativos.

### 4.3. Exercícios Práticos - Instrumentação
- Criar teste Espresso para um botão.
- Verificar transição entre telas.

## 5. Testes de Integração com Room, Retrofit e ViewModel

### 5.1. Testes de DAOs com Room
- Testar inserções e consultas.

### 5.2. Testando ViewModels com LiveData
- Testar lógica de ViewModel com LiveData.

### 5.3. Mock de Requisições Retrofit
- Simular respostas de APIs.

### 5.4. Exercícios Práticos - Integração
- Testar consulta em DAO.
- Testar transformação de LiveData.

## 6. Testes com Coroutines e Flow

### 6.1. TestCoroutineDispatcher
- Controlar coroutines nos testes.

### 6.2. Testing Flow Collections
- Testar emissores de Flow.

### 6.3. Exercícios Práticos - Coroutines
- Testar função com delay usando coroutines.

## 7. Testes de UI com Jetpack Compose

### 7.1. Compose Testing Library
- Ferramentas para teste de Compose.

### 7.2. Testando Layouts e Interações
- Localizar e interagir com componentes Compose.

### 7.3. Exercícios Práticos - Compose
- Testar clique em botão Compose.
- Validar exibição de texto.

## 8. Testes End-to-End com Firebase Test Lab

### 8.1. Configuração de Test Runs no Firebase
- Upload de APKs de teste.

### 8.2. Testes em Dispositivos Reais na Nuvem
- Execução de testes em múltiplos devices.

### 8.3. Exercícios Práticos - E2E
- Rodar teste Espresso no Firebase Test Lab.

## 9. Relatórios de Testes e Cobertura

### 9.1. Jacoco para Android
- Geração de relatório de cobertura.

### 9.2. Relatórios HTML e Sonarqube
- Visualização e análise de cobertura.

### 9.3. Exercícios Práticos - Coverage
- Gerar relatório Jacoco de um módulo.

## 10. Testes Automatizados em CI/CD para Android

### 10.1. Testes no GitHub Actions
- Rodar testes unitários e instrumentados.

### 10.2. Testes no GitLab CI
- Configuração de jobs para testes Android.

### 10.3. Exercícios Práticos - CI/CD
- Criar pipeline que executa testes e gera relatório de cobertura.

---

