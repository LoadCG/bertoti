# Engenharia de Software I

## 📖 Descrição

Este repositório concentra todas as atividades desenvolvidas durante a disciplina **Engenharia de Software I**.  
Cada atividade será organizada em seções próprias, contendo o enunciado (quando necessário), a execução e eventuais reflexões complementares.

---

# 📝 Atividade 1 — Comentários e Trade-offs

### Objetivo
- Ler dois trechos do livro *Software Engineering at Google* e fazer comentários reflexivos sobre cada um.  
- Explicar três exemplos reais ou hipotéticos de **trade-offs** no contexto de engenharia de software.

---

## 📚 Exercício 1) — Comentários sobre *Software Engineering at Google*

### Texto 1 — Percepção da Engenharia de Software

O trecho aborda uma realidade desconfortável: a sociedade tende a considerar outras engenharias mais importantes, pois seus resultados são mais visíveis e tangíveis no mundo real.

> **Reflexão:** Isso cria a expectativa de que a engenharia de software adote métodos tão rigorosos quanto outras áreas, como a engenharia aeronáutica.

Muitas vezes, o engenheiro de software é visto como menos responsável que, por exemplo, um engenheiro de aeronaves.  
Essa visão é equivocada — existem softwares que controlam sistemas críticos e cuidam diretamente de vidas humanas.

---

## 📚 Exercício 2) — Comentários sobre *Software Engineering at Google*

### Texto 2 — *Programming Over Time*

O trecho reforça a importância de escrever código **escalável** e que permita **evoluir continuamente** ao longo do tempo.  
A meta é que o software não seja apenas funcional no presente, mas que mantenha a capacidade de crescer e se adaptar a novas demandas.

Concordo plenamente com essa visão.  
Acredito que, se empresas de grande porte — como o próprio **Google**, citado explicitamente no texto e no título do livro — adotassem e disseminassem padrões mais rigorosos de engenharia de software, treinando programadores no mundo todo para segui-los, poderíamos alcançar avanços significativos na qualidade e na longevidade dos sistemas.

> **Reflexão:** Escalar código não é apenas uma questão técnica, mas também cultural: exige disciplina, padrões claros e compromisso coletivo.

---

## ⚖ Exercício 3) — Três exemplos de *trade-offs* em Engenharia de Software

Um **trade-off** é uma decisão que implica abrir mão de algo para ganhar outra coisa em troca.  
Em engenharia de software, eles aparecem frequentemente quando equilibramos critérios como desempenho, custo, prazo e qualidade.

### 1. Desempenho vs. Manutenibilidade
- **Situação:** Otimizar um algoritmo para rodar extremamente rápido.
- **Ganho:** Melhor tempo de execução e menor consumo de recursos em produção.
- **Perda:** Código mais complexo, difícil de entender e de manter no futuro.  
  → Muitas vezes, é mais viável manter um código levemente mais lento, mas legível e fácil de corrigir.

---

### 2. Velocidade de Entrega vs. Qualidade do Código
- **Situação:** Lançar rapidamente uma nova funcionalidade para atender a uma demanda do cliente.
- **Ganho:** Vantagem competitiva e satisfação imediata do cliente.
- **Perda:** Possível aumento da dívida técnica, exigindo refatorações futuras e gerando riscos de bugs.  
  → O equilíbrio depende do impacto da entrega e do custo da refatoração posterior.

---

### 3. Escalabilidade vs. Custo Inicial
- **Situação:** Projetar um sistema para suportar milhões de usuários desde o início.
- **Ganho:** Infraestrutura preparada para grandes picos de demanda.
- **Perda:** Investimento inicial elevado em servidores, banco de dados e arquitetura complexa que pode não ser necessária no curto prazo.  
  → Em alguns casos, é melhor começar simples e evoluir conforme o crescimento real do produto.

---

# 📝 Atividade 2 — Modelo de Classes e Testes Automatizados

### Objetivo
- Criar um **modelo de classes** simples em Java para um sistema de cadastro de **Usuários** e **Endereços**.
- Implementar o código Java para as classes `Usuario` e `Endereco`, com a respectiva associação.
- Criar testes automatizados utilizando **JUnit** para validar o funcionamento das classes e do relacionamento entre elas.

---

## 📚 Exercício 4) — Diagrama de Classes

O sistema envolve duas entidades principais: **Usuário** e **Endereço**. O relacionamento entre elas é de **1:N**, ou seja, um **Usuário** pode ter vários **Endereços**.

### Diagrama de Classes

```text

+-----------------+       +----------------------+
|     Usuario     |       |       Endereco       |
+-----------------+       +----------------------+
| - idUsuario: int|<>---->| - idEndereco: int    |
| - nome: String  |       | - logradouro: String |
| - email: String |       | - numero: String     |
+-----------------+       | - bairro: String     |
                          | - usuario: Usuario   |
                          +----------------------+
```

---

## 📚 Exercício 5) — Códigos das Classes em Java

### Classe `Usuario.java`

```java
public class Usuario {
    private int idUsuario;
    private String nome;
    private String email;

    // Construtores
    public Usuario(int idUsuario, String nome, String email) {
        this.idUsuario = idUsuario;
        this.nome = nome;
        this.email = email;
    }

    // Getters e Setters
    public int getIdUsuario() {
        return idUsuario;
    }

    public void setIdUsuario(int idUsuario) {
        this.idUsuario = idUsuario;
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }
}
```

### Classe `Endereco.java`

```java
public class Endereco {
    private int idEndereco;
    private String logradouro;
    private String numero;
    private String bairro;
    private Usuario usuario;  // Relacionamento com a classe Usuario

    // Construtores
    public Endereco(int idEndereco, String logradouro, String numero, String bairro, Usuario usuario) {
        this.idEndereco = idEndereco;
        this.logradouro = logradouro;
        this.numero = numero;
        this.bairro = bairro;
        this.usuario = usuario;
    }

    // Getters e Setters
    public int getIdEndereco() {
        return idEndereco;
    }

    public void setIdEndereco(int idEndereco) {
        this.idEndereco = idEndereco;
    }

    public String getLogradouro() {
        return logradouro;
    }

    public void setLogradouro(String logradouro) {
        this.logradouro = logradouro;
    }

    public String getNumero() {
        return numero;
    }

    public void setNumero(String numero) {
        this.numero = numero;
    }

    public String getBairro() {
        return bairro;
    }

    public void setBairro(String bairro) {
        this.bairro = bairro;
    }

    public Usuario getUsuario() {
        return usuario;
    }

    public void setUsuario(Usuario usuario) {
        this.usuario = usuario;
    }
}
```
## 📚 Exercício 6) — Códigos dos Testes Automatizados em Java

### Classe de Teste `UsuarioEnderecoTest.java`

```java
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

public class UsuarioEnderecoTest {

    private Usuario usuario;
    private Endereco endereco;

    @BeforeEach
    public void setUp() {
        usuario = new Usuario(1, "João", "joao@example.com");
        endereco = new Endereco(1, "Rua A", "123", "Centro", usuario);
    }

    @Test
    public void testUsuarioEndereco() {
        // Teste de associação: Verificando se o Endereço está corretamente associado ao Usuário
        assertNotNull(endereco.getUsuario());
        assertEquals("João", endereco.getUsuario().getNome());
        assertEquals(1, endereco.getUsuario().getIdUsuario());
        assertEquals("Rua A", endereco.getLogradouro());
        assertEquals("Centro", endereco.getBairro());
    }

    @Test
    public void testUsuarioNome() {
        // Teste para verificar o nome do usuário
        assertEquals("João", usuario.getNome());
    }

    @Test
    public void testEnderecoBairro() {
        // Teste para verificar o bairro do endereço
        assertEquals("Centro", endereco.getBairro());
    }
}
```

---
# 📝 Atividade 3 — Modelo de Classes e Testes Automatizados (Livro e Categoria)

### Objetivo
- Criar um **modelo de classes** em Java para um sistema de cadastro de **Livros** e suas **Categorias**.
- Implementar o código Java para as classes `Livro` e `Categoria`, com a respectiva associação entre elas.
- Criar **testes automatizados utilizando JUnit** para validar o funcionamento das classes e da associação.

---

## 📚 Exercício 7) — Diagrama de Classes

O sistema envolve duas entidades principais: **Livro** e **Categoria**. O relacionamento entre elas é de **1:N**, ou seja, uma **Categoria** pode conter vários **Livros**.

### Diagrama de Classes

```text
+----------------+       +--------------------------+
|   Categoria    |       |          Livro           |
+----------------+       +--------------------------+
| - id: int      |<----->| - id: int                |
| - nome: String |       | - titulo: String         |
+----------------+       | - autor: String          |
                         | - isbn: String           |
                         | - categoria: Categoria   |
                         +--------------------------+
```

--- 

## 📚 Exercício 8) — Códigos das Classes em Java

### Classe `Categoria.java`

```java
public class Categoria {
    private int id;
    private String nome;

    // Construtor
    public Categoria(int id, String nome) {
        this.id = id;
        this.nome = nome;
    }

    // Getters e Setters
    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }
}
```

### Classe `Livro.java`

```java
public class Livro {
    private int id;
    private String titulo;
    private String autor;
    private String isbn;
    private Categoria categoria;  // Associação

    // Construtor
    public Livro(int id, String titulo, String autor, String isbn, Categoria categoria) {
        this.id = id;
        this.titulo = titulo;
        this.autor = autor;
        this.isbn = isbn;
        this.categoria = categoria;
    }

    // Getters e Setters
    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getTitulo() {
        return titulo;
    }

    public void setTitulo(String titulo) {
        this.titulo = titulo;
    }

    public String getAutor() {
        return autor;
    }

    public void setAutor(String autor) {
        this.autor = autor;
    }

    public String getIsbn() {
        return isbn;
    }

    public void setIsbn(String isbn) {
        this.isbn = isbn;
    }

    public Categoria getCategoria() {
        return categoria;
    }

    public void setCategoria(Categoria categoria) {
        this.categoria = categoria;
    }
}
```

### Classe `LivroCategoriaTest.java`
---

## 📚 Exercício 9) — Códigos dos Testes Automatizados em Java

### Classe de teste `LivroCategoriaTest.java`

```java
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;

public class LivroCategoriaTest {

    private Categoria categoria;
    private Livro livro;

    @BeforeEach
    public void setUp() {
        categoria = new Categoria(1, "Ficção Científica");
        livro = new Livro(1, "Duna", "Frank Herbert", "978-0441172719", categoria);
    }

    @Test
    public void testLivroCategoriaAssociacao() {
        assertNotNull(livro.getCategoria());
        assertEquals("Ficção Científica", livro.getCategoria().getNome());
    }

    @Test
    public void testLivroTituloAutor() {
        assertEquals("Duna", livro.getTitulo());
        assertEquals("Frank Herbert", livro.getAutor());
    }

    @Test
    public void testCategoriaNome() {
        assertEquals("Ficção Científica", categoria.getNome());
    }
}
```

---
