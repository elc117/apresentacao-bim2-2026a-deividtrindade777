# Atividade - Java + Javalin

## Nome

Deivid Da Silva Trindade

---

# Objetivo da atividade

A atividade consistia em executar exemplos utilizando Java + Javalin, analisar os códigos fornecidos e identificar recursos de orientação a objetos e Java que eu já conhecia e outros que ainda eram novos para mim.

---

# Parte 1 - Execução do exemplo

O exemplo escolhido foi o `HelloJavalin`.

Para executar o exemplo no Codespaces, utilizei os comandos:

```bash
cd javalin
make hello
```

O comando `make hello` utiliza o `Makefile`, que automatiza a execução do projeto.

O `Makefile` possui comandos prontos para facilitar a compilação e execução dos exemplos, deixando a execução mais organizada.

O `Makefile` chama o Gradle:

```bash
gradle -q runHello
```

O Gradle organiza o projeto, verifica dependências e executa a aplicação Java utilizando o compilador `javac`.

Após isso, o Javalin sobe um servidor local na porta `3000`.

```java
int p = Integer.parseInt(System.getenv().getOrDefault("PORT", "3000"));
Javalin app = Javalin.create().start(p);
```

### Explicação do trecho

```java
Integer.parseInt()
```

Converte um valor `String` para `int`.

```java
System.getenv()
```

Obtém variáveis de ambiente do sistema.

```java
getOrDefault("PORT", "3000")
```

Caso não exista uma variável `PORT`, utiliza a porta `3000`.

```java
Javalin.create().start(p)
```

Cria e inicia o servidor local utilizando a porta definida.

Quando a porta é aberta no navegador, a aplicação retorna:

```java
app.get("/", ctx -> ctx.result("Hello World"));
```

Nesse trecho:

```java
ctx -> ctx.result("Hello World")
```

é utilizado um lambda do Java, semelhante à ideia de funções anônimas vistas em Haskell.

O `ctx.result()` retorna a resposta da rota HTTP no navegador.

Resultado no navegador:

```txt
Hello World
```
No exemplo HelloJavalin, a própria abertura do navegador já realiza uma requisição GET para a rota `/`, retornando a mensagem `"Hello World"`.

---

# Evidência da execução

Exemplo:

```md
![Execução do HelloJavalin](execution/hello-execution.gif)
```

---

# Parte 2 - Análise dos códigos

## Recursos que eu já conhecia

- classes Java
- polimorfismo
- herança
- orientação a objetos
- lógica de backend
- rotas HTTP
- separação de responsabilidade

Alguns desses conceitos eu já conhecia principalmente pelo contato anterior com Python e Django, apesar da estrutura em Java ser mais detalhada.

---

## Recursos que eu ainda não conhecia bem

### Javalin
Framework Java utilizado para criar aplicações web e rotas HTTP.

### Gradle
Ferramenta utilizada para organizar, compilar e executar projetos Java.

### Makefile
Arquivo que automatiza comandos de execução do projeto.

### Lambda do Java
Função anônima utilizada diretamente no código.

```java
ctx -> ctx.result("Hello World")
```

### localhost
Servidor local utilizado para testes da aplicação.

### Interface
Define um contrato que outras classes precisam implementar.

```java
public interface TeamRecommendationStrategy
```

### implements
Indica que uma classe está implementando uma interface.

```java
implements TeamRecommendationStrategy
```

### @Override
Indica que um método está sobrescrevendo um método definido pela interface.

```java
@Override
```

### Métodos static
Métodos chamados diretamente pela classe, sem criar objetos.

```java
Integer.parseInt()
System.getenv()
```

### @load
Recurso utilizado no material da professora para carregar exemplos de código automaticamente.

---

# Código da aula passada

Na aula passada, utilizei a estratégia `RequirementGroupingStrategy`.

```java
public class RequirementGroupingStrategy
        implements TeamRecommendationStrategy
```

Nesse código, consegui entender melhor:
- interface
- implementação
- separação de responsabilidade
- estratégia de recomendação

A lógica percorre trabalhadores e monta uma equipe seguindo requisitos definidos:

```java
if (trabalhador.getCargo() == Cargo.ENGENHEIRO
        && engenheiros < 2)
```

Também utilizei listas:

```java
List<Trabalhador> equipe = new ArrayList<>();
```

---

# Relação com Gradle

Durante o desenvolvimento do projeto da aula passada, tive dificuldades para testar minha lógica porque o projeto ainda dependia de algumas configurações e dependências do Gradle.

Depois que essas dependências foram organizadas corretamente, consegui executar e testar minha parte do código normalmente.

Essa atividade ajudou a entender melhor o papel do Gradle na execução de projetos Java.

---

# O que eu entendi

O que eu mais consegui entender durante a atividade foi:

- como o Javalin sobe um servidor local
- como uma rota HTTP responde no navegador
- como o Gradle ajuda na execução do projeto
- como interfaces e estratégias funcionam em Java
- como funções lambda podem ser utilizadas em Java

---

# Referências

- Documentação do Javalin
- Material da aula
- Repositório disponibilizado pela professora