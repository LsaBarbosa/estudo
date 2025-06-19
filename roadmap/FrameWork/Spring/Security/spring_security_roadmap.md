# Roadmap de Estudos – Spring Security

## Índice

- [1. Fundamentos de Segurança](#1-fundamentos-de-segurança)
- [2. Configuração Básica do Spring Security](#2-configuração-básica-do-spring-security)
- [3. Autenticação Customizada](#3-autenticação-customizada)
- [4. Autorização e Controle de Acesso](#4-autorização-e-controle-de-acesso)
- [5. JWT com Spring Security](#5-jwt-com-spring-security)
- [6. Proteções Adicionais](#6-proteções-adicionais)
- [7. OAuth2 e Social Login](#7-oauth2-e-social-login)
- [8. Testes de Segurança](#8-testes-de-segurança)

## 1. Fundamentos de Segurança

### 1.1. O que é Autenticação e Autorização?

- **Autenticação:** Verificar quem é o usuário.
- **Autorização:** Verificar o que o usuário pode acessar.

### 1.2. Principais ameaças (CSRF, XSS, etc)

- Cross Site Request Forgery.
- Cross Site Scripting.
- Brute Force Attacks.

### 1.3. O papel do Spring Security

- Framework de segurança para aplicações Spring.
- Controle de autenticação, autorização, e proteção contra ameaças.

### 1.4. Exercícios Práticos - Fundamentos

- Criar um projeto Spring Boot com Spring Security Starter.
- Testar o login padrão gerado automaticamente.

## 2. Configuração Básica do Spring Security

### 2.1. Dependências Maven/Gradle

- `spring-boot-starter-security`

### 2.2. Spring Security Default Login Page

- Login gerado automaticamente pelo Spring Security.

### 2.3. application.properties básico

- Desativar CSRF (para fins de teste):

```properties
spring.security.user.name=admin
spring.security.user.password=123456
```

### 2.4. Exercícios Práticos - Configuração Básica

- Customizar usuário e senha no application.properties.
- Criar um endpoint `/hello` protegido por login.

## 3. Autenticação Customizada

### 3.1. UserDetails e UserDetailsService

- Criação de usuários customizados.
- Implementação de `UserDetailsService`.

### 3.2. PasswordEncoder

- Uso de BCryptPasswordEncoder.

### 3.3. Autenticação em Banco de Dados

- Uso de JPA para carregar usuários.

### 3.4. Exercícios Práticos - Autenticação

- Implementar um `UserDetailsService` que busca usuários do banco MySQL.
- Criptografar senhas com BCrypt.

## 4. Autorização e Controle de Acesso

### 4.1. Roles e Authorities

- Controle baseado em papéis.

### 4.2. Configuração de URL-based Security

- Exemplo de configuração:

```java
http.authorizeRequests()
    .antMatchers("/admin/**").hasRole("ADMIN")
    .antMatchers("/user/**").hasAnyRole("USER", "ADMIN")
    .anyRequest().authenticated();
```

### 4.3. @PreAuthorize e @Secured

- Uso de anotações para proteger métodos.

### 4.4. Exercícios Práticos - Autorização

- Criar endpoints `/admin` e `/user` com roles diferentes.
- Adicionar `@PreAuthorize` em um método de serviço.

## 5. JWT com Spring Security

### 5.1. O que é JWT?

- JSON Web Token.
- Token stateless para autenticação.

### 5.2. Implementação de Filtro JWT

- Filtro customizado que valida o JWT em cada requisição.

### 5.3. Token Provider e Authentication Filter

- Classe para criar e validar tokens.

### 5.4. Exercícios Práticos - JWT

- Criar um endpoint `/auth/login` que gera JWT.
- Criar filtro que valida JWT nas requisições protegidas.

## 6. Proteções Adicionais

### 6.1. CSRF Protection

- Habilitar e entender quando desativar.

### 6.2. CORS Configuration

- Configurar CORS globalmente ou por endpoint.

### 6.3. Rate Limiting (Spring + Bucket4j)

- Evitar ataques de força bruta.

### 6.4. Exercícios Práticos - Proteções

- Configurar CORS para um domínio específico.
- Adicionar proteção CSRF.
- Implementar rate limiting com Bucket4j.

## 7. OAuth2 e Social Login

### 7.1. Spring Security OAuth2 Client

- Login via Google, Facebook, etc.

### 7.2. Login com Google/Facebook

- Configurar clientId e clientSecret.

### 7.3. Exercícios Práticos - OAuth2

- Habilitar login com Google.
- Criar pagina customizada de login social.

## 8. Testes de Segurança

### 8.1. Spring Security Test

- Uso de `@WithMockUser`.

### 8.2. Testando autenticação e autorização

- Testes unitários de endpoints protegidos.

### 8.3. Exercícios Práticos - Testes

- Criar teste que valida acesso negado sem login.
- Testar acesso permitido para role correta.

---

