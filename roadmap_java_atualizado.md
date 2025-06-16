# Roadmap Completo de Java
1. [Reflection e Manipulação Dinâmica](#9-reflection-e-manipulação-dinâmica)
2. [APIs e Ferramentas do Java](#10-apis-e-ferramentas-do-java)
3. [Testes Automatizados](#11-testes-automatizados)
4. [Desenvolvimento Web com Java](#12-desenvolvimento-web-com-java)
5. [Integração com Banco de Dados](#13-integração-com-banco-de-dados)
6. [Boas Práticas e Arquitetura](#14-boas-práticas-e-arquitetura)
7. [Ferramentas e DevOps](#15-ferramentas-e-devops)
8. [Java Avançado e Temas Modernos](#16-java-avançado-e-temas-modernos)
9. [Segurança em Java](#17-segurança-em-java)
10. [Atualizações Java (17 a 21)](#18-atualizações-java-17-a-21)
11. [Referências](#19-referências)
12. Boas Práticas e Arquitetura](#12-boas-práticas-e-arquitetura)
13. Ferramentas e DevOps](#13-ferramentas-e-devops)
14. Java Avançado e Temas Modernos](#14-java-avançado-e-temas-modernos)
15. Segurança em Java](#15-segurança-em-java)
16. Atualizações Java (17 a 21)](#16-atualizações-java-17-a-21)
17. Referências](#17-referências)

---

## 1. Introdução

A linguagem Java é uma das mais utilizadas no mundo para o desenvolvimento de aplicações robustas, escaláveis e multiplataforma. Este roadmap foi criado para guiar desenvolvedores do nível pleno ao sênior, trazendo uma jornada completa, didática e moderna. Cada capítulo traz exemplos práticos e sugestões visuais para facilitar o entendimento.

---

## 2. Fundamentos da Linguagem Java

### 2.1. Sintaxe Básica

#### 2.1.1. Estrutura de um Programa Java

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Olá, mundo!");
    }
}
```

#### 2.1.2. Tipos Primitivos

- **byte, short, int, long**
- **float, double**
- **char**
- **boolean**

#### 2.1.3. Variáveis e Operadores

```java
int x = 10, y = 5;
int soma = x + y;
int mult = x * y;
boolean maior = x > y;
```

#### 2.1.4. Controle de Fluxo

```java
if (idade >= 18) {
    System.out.println("Maior de idade");
} else {
    System.out.println("Menor de idade");
}

switch (mes) {
    case 1:
        System.out.println("Janeiro");
        break;
    default:
        System.out.println("Outro mês");
}
```

#### 2.1.5. Laços de Repetição

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}

int j = 0;
while (j < 10) {
    System.out.println(j);
    j++;
}
```

### 2.2. Orientação a Objetos

#### 2.2.1. Classes e Objetos

```java
public class Pessoa {
    String nome;
    int idade;
}
Pessoa p = new Pessoa();
p.nome = "Maria";
p.idade = 20;
```

#### 2.2.2. Encapsulamento

```java
public class Conta {
    private double saldo;
    public double getSaldo() { return saldo; }
    public void depositar(double valor) { saldo += valor; }
}
```

#### 2.2.3. Herança

```java
public class Animal {
    public void som() {
        System.out.println("Animal faz um som");
    }
}
public class Cachorro extends Animal {
    @Override
    public void som() {
        System.out.println("Au Au!");
    }
}
```

#### 2.2.4. Polimorfismo

```java
Animal a = new Cachorro();
a.som(); // "Au Au!"
```

#### 2.2.5. Abstração

```java
public abstract class Veiculo {
    public abstract void mover();
}
public class Carro extends Veiculo {
    @Override
    public void mover() { System.out.println("Carro andando"); }
}
```

#### 2.2.6. Modificadores de acesso

- **public, protected, private, package-private**

#### 2.2.7. `this` e `super`

```java
public class Pessoa {
    private String nome;
    public Pessoa(String nome) { this.nome = nome; }
}
public class Estudante extends Pessoa {
    public Estudante(String nome) { super(nome); }
}
```

#### 2.2.8. Sobrecarga e Sobrescrita de Métodos

---

## 3. Estruturas de Dados e Coleções

### 3.1. Arrays

#### 3.1.1. Declaração, inicialização e uso

```java
int[] numeros = {1, 2, 3, 4, 5};
System.out.println(numeros[0]); // 1
```

#### 3.1.2. Arrays multidimensionais

```java
int[][] matriz = new int[2][3];
matriz[0][0] = 1;
matriz[0][1] = 2;
```

### 3.2. Coleções do Java (`java.util`)

#### 3.2.1. Listas (`ArrayList`, `LinkedList`)

```java
List<String> nomes = new ArrayList<>();
nomes.add("Ana");
nomes.add("Bia");
System.out.println(nomes.get(0)); // "Ana"
```

#### 3.2.2. Sets (`HashSet`, `TreeSet`, `LinkedHashSet`)

```java
Set<Integer> numeros = new HashSet<>();
numeros.add(10);
numeros.add(20);
numeros.add(10); // não será adicionado (Set não aceita duplicados)
```

#### 3.2.3. Maps (`HashMap`, `TreeMap`, `LinkedHashMap`)

```java
Map<String, Integer> mapa = new HashMap<>();
mapa.put("idade", 30);
System.out.println(mapa.get("idade")); // 30
```

#### 3.2.4. Filas e Pilhas (`Queue`, `Deque`, `Stack`)

```java
Queue<String> fila = new LinkedList<>();
fila.add("Primeiro");
fila.add("Segundo");
System.out.println(fila.poll()); // "Primeiro"
```

```java
Deque<Integer> pilha = new ArrayDeque<>();
pilha.push(1);
pilha.push(2);
System.out.println(pilha.pop()); // 2
```

### 3.3. Generics

#### 3.3.1. Introdução a Generics

```java
List<String> lista = new ArrayList<>();
```

#### 3.3.2. Wildcards (`?`, `? extends`, `? super`)

```java
public void imprimeLista(List<?> lista) {
    for (Object obj : lista) System.out.println(obj);
}
```

#### 3.3.3. Type Erasure

---

## 4. Tratamento de Exceções

### 4.1. Exceções (`try`, `catch`, `finally`)

#### 4.1.1. Tipos de exceções

- **Checked** (obrigatório tratar)
- **Unchecked** (RuntimeException)

```java
try {
    int resultado = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Erro: " + e.getMessage());
} finally {
    System.out.println("Sempre executa!");
}
```

#### 4.1.2. Criação de exceções personalizadas

```java
public class SaldoInsuficienteException extends Exception {
    public SaldoInsuficienteException(String mensagem) {
        super(mensagem);
    }
}
```

### 4.2. Boas práticas em tratamento de erros

#### 4.2.1. Stacktrace

```java
try {
    // código
} catch (Exception e) {
    e.printStackTrace();
}
```

#### 4.2.2. Relação entre exceções e design de código

---

## 5. Fundamentos do Java Moderno

### 5.1. Lambdas e Functional Interfaces

#### 5.1.1. Sintaxe de Expressões Lambda

```java
List<String> lista = Arrays.asList("a", "b", "c");
lista.forEach(elemento -> System.out.println(elemento));
```

#### 5.1.2. Interfaces funcionais

```java
Predicate<String> comecaComA = s -> s.startsWith("A");
Function<String, Integer> tamanho = s -> s.length();
Consumer<String> imprime = System.out::println;
Supplier<Double> randomico = () -> Math.random();
```

#### 5.1.3. Method references

```java
lista.forEach(System.out::println);
```

### 5.2. Streams API

#### 5.2.1. Criação de Streams

```java
Stream<String> stream = lista.stream();
```

#### 5.2.2. Operações intermediárias e terminais

```java
List<String> filtrados = lista.stream()
    .filter(s -> s.startsWith("A"))
    .map(String::toUpperCase)
    .collect(Collectors.toList());
```

#### 5.2.3. Parallel Streams

```java
lista.parallelStream().forEach(System.out::println);
```

### 5.3. Optionals

```java
Optional<String> opt = Optional.ofNullable(buscaNome());
opt.ifPresent(System.out::println);
String nome = opt.orElse("Padrão");
```

---

## 6. Manipulação de Arquivos e I/O

### 6.1. Java I/O (`java.io`)

#### 6.1.1. Streams de byte e caractere

```java
FileInputStream fis = new FileInputStream("arquivo.txt");
int b = fis.read();
fis.close();
```

#### 6.1.2. Leitura e escrita de arquivos

```java
BufferedReader br = new BufferedReader(new FileReader("arquivo.txt"));
String linha = br.readLine();
br.close();
```

### 6.2. Java NIO (`java.nio`)

#### 6.2.1. Paths, Files, Channels, Buffers

```java
Path path = Paths.get("arquivo.txt");
List<String> linhas = Files.readAllLines(path);
```

#### 6.2.2. Leitura e escrita assíncrona

```java
AsynchronousFileChannel channel = AsynchronousFileChannel.open(path, StandardOpenOption.READ);
```

---

## 7. Programação Concorrente e Paralela

### 7.1. Threads

#### 7.1.1. Criação e gerenciamento de threads

```java
Thread t = new Thread(() -> System.out.println("Executando em thread"));
t.start();
```

### 7.2. Sincronização

#### 7.2.1. `synchronized`, `volatile`

```java
synchronized(obj) { /* código crítico */ }
```

#### 7.2.2. Locks

```java
Lock lock = new ReentrantLock();
lock.lock();
try {
    // código
} finally {
    lock.unlock();
}
```

### 7.3. Concurrency Utilities

#### 7.3.1. Executor Framework

```java
ExecutorService executor = Executors.newFixedThreadPool(2);
executor.submit(() -> System.out.println("Task executada"));
```

#### 7.3.2. Futures e Callables

```java
Future<Integer> futuro = executor.submit(() -> 2 + 2);
System.out.println(futuro.get());
```

#### 7.3.3. Parallel Streams

#### 7.3.4. `CompletableFuture` e programação reativa básica

```java
CompletableFuture.supplyAsync(() -> "resultado")
    .thenAccept(System.out::println);
```

---

## 8. APIs e Ferramentas do Java

### 8.1. API de Datas (`java.time`)

#### 8.1.1. `LocalDate`, `LocalTime`, `LocalDateTime`

```java
LocalDate hoje = LocalDate.now();
LocalDateTime agora = LocalDateTime.now();
```

#### 8.1.2. `ZonedDateTime` e fusos horários

```java
ZonedDateTime zdt = ZonedDateTime.now(ZoneId.of("America/Sao_Paulo"));
```

#### 8.1.3. Manipulação e formatação de datas

```java
DateTimeFormatter formato = DateTimeFormatter.ofPattern("dd/MM/yyyy");
System.out.println(hoje.format(formato));
```

### 8.2. Anotações

#### 8.2.1. Uso de anotações padrão

```java
@Override
public String toString() { return "..." ; }
```

#### 8.2.2. Criação de anotações customizadas

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
public @interface MinhaAnotacao {
    String valor();
}
```

### 8.3. Reflection

#### 8.3.1. Inspeção de classes e objetos

```java
Class<?> clazz = objeto.getClass();
Method[] metodos = clazz.getDeclaredMethods();
```

#### 8.3.2. Manipulação dinâmica

```java
Method metodo = clazz.getMethod("metodoNome");
metodo.invoke(objeto);
```

---

# 9. Reflection e Manipulação Dinâmica

## 9.1. Reflection: Acesso e manipulação de metadados

### 9.1.1. Inspecionando classes e membros

```java
Class<?> clazz = Class.forName("com.exemplo.Usuario");
for (Field f : clazz.getDeclaredFields()) {
    System.out.println("Campo: " + f.getName());
}
```

### 9.1.2. Instanciando objetos dinamicamente

```java
Constructor<?> ctor = clazz.getConstructor(String.class);
Object usuario = ctor.newInstance("João");
```

### 9.1.3. Invocando métodos em runtime

```java
Method metodo = clazz.getMethod("setNome", String.class);
metodo.invoke(usuario, "Maria");
```

### 9.1.4. Usos avançados

- Injeção de dependência (ex: Spring Framework)
- Serialização customizada
- Plugins/carregamento dinâmico de classes

## 9.2. Limitações e cuidados

- Reflection é poderosa, mas pode ser lenta e perigosa (bypassa encapsulamento).
- Pode ser restringida por políticas de segurança.
- Utilize apenas quando necessário.

---

# 10. APIs e Ferramentas do Java

## 10.1. API de Datas (java.time)

### 10.1.1. LocalDate, LocalTime, LocalDateTime

```java
LocalDate hoje = LocalDate.now();
LocalDateTime agora = LocalDateTime.now();
```

### 10.1.2. ZonedDateTime e fusos horários

```java
ZonedDateTime zdt = ZonedDateTime.now(ZoneId.of("America/Sao_Paulo"));
```

### 10.1.3. Manipulação e formatação de datas

```java
DateTimeFormatter formato = DateTimeFormatter.ofPattern("dd/MM/yyyy");
System.out.println(hoje.format(formato));
```

## 10.2. Anotações

### 10.2.1. Uso de anotações padrão

```java
@Override
public String toString() { return "..." ; }
```

### 10.2.2. Criação de anotações customizadas

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
public @interface MinhaAnotacao {
    String valor();
}
```

## 10.3. Reflection (exemplos avançados)

- Exemplo de inspeção dinâmica já apresentado acima.

---

# 11. Testes Automatizados

## 11.1. Testes Unitários

### 11.1.1. JUnit (4, 5)

```java
@Test
void somaTest() {
    assertEquals(4, 2 + 2);
}
```

### 11.1.2. Estrutura de um teste

- Arrange, Act, Assert

### 11.1.3. Assertivas

- assertEquals, assertTrue, assertFalse, etc.

## 11.2. Testes de Integração

### 11.2.1. Teste com banco de dados

```java
@DataJpaTest
class CategoriaRepositoryTest { ... }
```

### 11.2.2. Testes de API

```java
MockMvc mockMvc = MockMvcBuilders.standaloneSetup(controller).build();
```

## 11.3. Mocking

### 11.3.1. Mockito

```java
@Mock
Servico servico;

when(servico.metodo()).thenReturn(valorEsperado);
```

### 11.3.2. Testes de comportamento vs estado

- Comportamento: verifica se método foi chamado
- Estado: verifica resultado final

---

# 12. Desenvolvimento Web com Java

## 12.1. Servlets e JSP

### 12.1.1. Ciclo de vida de um Servlet

- Init → Service → Destroy

### 12.1.2. JSP e JSTL

- JSP para views, JSTL para lógica em página.

## 12.2. Spring Framework

### 12.2.1. Inversão de Controle (IoC)

### 12.2.2. Injeção de Dependências (DI)

```java
@Component
public class MeuComponente {}

@Autowired
private MeuComponente meuComponente;
```

### 12.2.3. Spring Boot

- @SpringBootApplication
- application.properties
- Uso de starters

## 12.3. APIs RESTful

### 12.3.1. Controllers REST

```java
@RestController
@RequestMapping("/api")
public class MeuController {
    @GetMapping("/hello")
    public String hello() { return "Olá"; }
}
```

### 12.3.2. Validações

```java
@PostMapping
public ResponseEntity criar(@Valid @RequestBody MeuDTO dto) { ... }
```

### 12.3.3. Documentação de API

- Swagger/OpenAPI

---

# 13. Integração com Banco de Dados

## 13.1. JDBC

### 13.1.1. Conexão e execução de queries

```java
Connection conn = DriverManager.getConnection(url, user, pass);
PreparedStatement stmt = conn.prepareStatement("SELECT * FROM tabela");
ResultSet rs = stmt.executeQuery();
```

### 13.1.2. Manipulação de ResultSet

```java
while (rs.next()) {
    System.out.println(rs.getString("nome"));
}
```

## 13.2. JPA/Hibernate

### 13.2.1. Entidades e mapeamento

```java
@Entity
@Table(name = "clientes")
public class Cliente { ... }
```

### 13.2.2. Relacionamentos

```java
@OneToMany(mappedBy = "cliente")
private List<Pedido> pedidos;
```

### 13.2.3. JPQL e Criteria API

```java
@Query("SELECT c FROM Cliente c WHERE c.nome = :nome")
List<Cliente> buscarPorNome(@Param("nome") String nome);
```

### 13.2.4. Versionamento e transações

```java
@Version
private Integer version;
```

@Transactional

---

# 14. Boas Práticas e Arquitetura

## 14.1. Clean Code

### 14.1.1. Nomeação de variáveis e métodos

### 14.1.2. Funções pequenas e coesas

### 14.1.3. Princípios SOLID

- Single Responsibility, Open/Closed, Liskov, Interface Segregation, Dependency Inversion

## 14.2. Design Patterns

### 14.2.1. Singleton

```java
public class Logger {
    private static final Logger INSTANCE = new Logger();
    private Logger() {}
    public static Logger getInstance() { return INSTANCE; }
}
```

### 14.2.2. Adapter

### 14.2.3. Observer

## 14.3. Arquitetura de Projetos Java

### 14.3.1. Camadas

- Controller → Service → Repository

### 14.3.2. Hexagonal / Ports and Adapters

### 14.3.3. Microserviços

---

# 15. Ferramentas e DevOps

## 15.1. Gerenciadores de Dependências

### 15.1.1. Maven

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter</artifactId>
</dependency>
```

### 15.1.2. Gradle

```groovy
implementation 'org.springframework.boot:spring-boot-starter'
```

## 15.2. Ferramentas de Build e CI

- Jenkins, GitHub Actions, GitLab CI

## 15.3. Docker e Containerização

```dockerfile
FROM openjdk:21-jdk
COPY target/app.jar app.jar
ENTRYPOINT ["java", "-jar", "app.jar"]
```

---

# 16. Java Avançado e Temas Modernos

## 16.1. Modularity (module-info.java)

```java
module com.exemplo.minhamodulo {
    requires java.sql;
    exports com.exemplo.servicos;
}
```

## 16.2. JVM Internals

### 16.2.1. Garbage Collection (GC)

### 16.2.2. Tuning de JVM

### 16.2.3. Profiling e análise de performance

- VisualVM, JProfiler

## 16.3. Programação Reativa

### 16.3.1. Reactive Streams

### 16.3.2. Spring WebFlux / Project Reactor

```java
@GetMapping("/users")
public Flux<User> getUsers() {
    return userService.findAll();
}
```

## 16.4. GraalVM, Native Images

---

# 17. Segurança em Java

## 17.1. Autenticação e Autorização

### 17.1.1. Spring Security

### 17.1.2. OAuth2 / JWT

## 17.2. Boas práticas de segurança

### 17.2.1. SQL Injection, XSS

### 17.2.2. Hashing de senhas

```java
String hash = BCrypt.hashpw("senha", BCrypt.gensalt());
```

---

# 18. Atualizações Java (17 a 21)

## 18.1. Java 17 (LTS)

### 18.1.1. Sealed Classes

```java
public sealed class Animal permits Cachorro, Gato {}
public final class Cachorro extends Animal {}
public final class Gato extends Animal {}
```

### 18.1.2. Pattern Matching para instanceof

```java
if (obj instanceof String s) {
    System.out.println(s.toUpperCase());
}
```

### 18.1.3. Switch Expressions

```java
String result = switch (dia) {
    case MONDAY, FRIDAY -> "Trabalho";
    case SATURDAY, SUNDAY -> "Descanso";
    default -> "Outro";
};
```

### 18.1.4. Remoção do Applet e APIs antigas

## 18.2. Java 18

### 18.2.1. UTF-8 padrão

### 18.2.2. Simple Web Server

### 18.2.3. Pattern Matching em Switch (preview)

## 18.3. Java 19

### 18.3.1. Virtual Threads (preview)

```java
Thread.startVirtualThread(() -> System.out.println("Thread virtual"));
```

### 18.3.2. Pattern Matching for Switch

## 18.4. Java 20

### 18.4.1. Scoped Values (Incubating)

### 18.4.2. Structured Concurrency (Incubating)

### 18.4.3. Pattern Matching e Records aprimorados

## 18.5. Java 21 (LTS)

### 18.5.1. Virtual Threads (final)

### 18.5.2. Pattern Matching for switch (final)

### 18.5.3. String Templates (preview)

### 18.5.4. Sequenced Collections

### 18.5.5. Record Patterns (final)

### 18.5.6. Depreciação e remoção de APIs antigas

---
