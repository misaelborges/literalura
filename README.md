# Projeto LiterAlura

O **LiterAlura** é uma aplicação desenvolvida em Java com Spring Boot, que explora dados literários. Ele permite gerenciar informações sobre autores e livros, além de consumir dados externos da API Gutendex para enriquecer seu banco de dados.

## Funcionalidades

### Autor
- **Cadastrar autores** com informações como nome, ano de nascimento e, se aplicável, ano de falecimento.
- **Relacionar autores aos livros** em que colaboraram.
- Listar autores e os livros associados.
- Filtrar autores vivos em um determinado ano.

### Livro
- **Gerenciar informações de livros**, como título, idioma e quantidade de downloads.
- Relacionar livros a autores.
- Listar livros por idioma ou autor.
- Exibir os 10 livros mais baixados.

### API Gutendex
- Consumir informações de livros e autores diretamente da API Gutendex para complementar os dados existentes.

## Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3**
- **JPA/Hibernate** para persistência de dados
- **MySQL** como banco de dados relacional
- **Jakarta Persistence** para mapeamento das entidades
- **HttpClient** para consumo de APIs externas
- **Jackson** para manipulação de dados JSON

## Estrutura do Projeto

### Pacote `model`
Contém as classes que representam as entidades principais da aplicação:
- **Autor**: Entidade JPA que representa os autores.
- **Livro**: Entidade JPA que representa os livros.
- **DadosAutor**, **DadosLivro** e **DadosGutendex**: Classes auxiliares para manipulação de dados consumidos pela API Gutendex.

### Pacote `repositories`
Define as interfaces para acesso ao banco de dados:
- **AutorRepository**: Operações relacionadas aos autores.
- **LivroRepository**: Operações relacionadas aos livros.

### Pacote `service`
Contém a lógica de negócios:
- **AutorService**: Serviços para gerenciar autores.
- **LivroService**: Serviços para gerenciar livros.
- **ConsumoApi**: Responsável por consumir a API Gutendex.
- **ConverterDados**: Serviço para conversão de dados JSON em objetos Java.

### Classe `LiteraluraApplication`

Classe principal da aplicação, contendo o método `main` que inicializa o Spring Boot. Ela também implementa `CommandLineRunner`, permitindo a execução do método `run` logo após a inicialização, onde é exibido o menu principal através da classe `Principal`.

## Pré-requisitos

Certifique-se de ter as seguintes ferramentas instaladas:
- **Java 17**
- **Maven**
- **MySQL**

## Como Executar

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/literalura.git
   cd literalura
   ```

2. Configure o banco de dados no arquivo `application.properties`.

3. Execute o projeto com o Maven:
   ```bash
   mvn spring-boot:run
   ```

4. Acesse a aplicação pelo navegador ou através de um cliente REST.

## Próximos Passos

- Implementar testes unitários para os serviços e repositórios.
- Criar uma interface front-end para interação com a aplicação.
- Expandir as funcionalidades com filtros e relatórios.

---

Este projeto foi desenvolvido como parte dos estudos na plataforma Alura. Sinta-se à vontade para contribuir ou abrir issues no repositório!
