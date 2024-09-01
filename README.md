# API para Gestão de Médicos = MedVoll

Esta é uma API desenvolvida com Java e Spring Boot para gerenciar informações de médicos, incluindo cadastro, atualização, listagem e exclusão. A API permite operações CRUD completas e utiliza um banco de dados relacional para persistência dos dados.

## Tecnologias Utilizadas

- Java 17
- Spring Boot
- JPA (Java Persistence API) com Hibernate
- PostgreSQL
- Maven

## Estrutura do Projeto

O projeto segue uma estrutura organizada por pacotes:

- **api**: Contém a classe principal `ApiApplication` para inicialização do Spring Boot.
- **controller**: Contém o controlador REST `MedicoController` para gerenciar as requisições relacionadas aos médicos.
- **endereco**: Contém classes relacionadas ao endereço dos médicos.
- **medico**: Contém classes e enumerações relacionadas ao domínio de médicos, como entidades, DTOs (Data Transfer Objects) e o repositório.

## Endpoints

### 1. Cadastrar Médico

- **Método**: `POST`
- **URL**: `/medicos`
- **Descrição**: Cadastra um novo médico no sistema.
- **Corpo da Requisição**: JSON contendo os dados do médico.

### 2. Listar Médicos

- **Método**: `GET`
- **URL**: `/medicos`
- **Descrição**: Lista todos os médicos ativos no sistema com paginação.
- **Parâmetros de Query**: `Pageable` (page, size, sort)

### 3. Atualizar Médico

- **Método**: `PUT`
- **URL**: `/medicos`
- **Descrição**: Atualiza as informações de um médico existente.
- **Corpo da Requisição**: JSON contendo os dados atualizados do médico.

### 4. Excluir Médico

- **Método**: `DELETE`
- **URL**: `/medicos/{id}`
- **Descrição**: Exclui (inativa) um médico do sistema com base no ID.

## Validações

- Validações de campos obrigatórios e formatos específicos (e.g., e-mail, CEP, CRM) são realizadas usando as anotações do Jakarta Validation API.

## Modelo de Dados

### Médico (`Medico`)

- **id**: Identificador único do médico (Long)
- **nome**: Nome do médico (String)
- **email**: E-mail do médico (String)
- **crm**: Código de Registro Médico (String)
- **telefone**: Telefone do médico (String)
- **especialidade**: Especialidade médica (Enum: `ORTOPEDIA`, `CARDIOLOGIA`, `GINECOLOGIA`, `DERMATOLOGIA`)
- **endereco**: Dados de endereço do médico (Objeto `Endereco`)
- **ativo**: Indica se o médico está ativo no sistema (Boolean)

### Endereço (`Endereco`)

- **logradouro**: Rua/Avenida (String)
- **bairro**: Bairro (String)
- **cep**: Código Postal (String)
- **numero**: Número da residência (String)
- **complemento**: Complemento (String)
- **cidade**: Cidade (String)
- **uf**: Unidade Federativa (String)

## Como Executar o Projeto

1. Clone o repositório: `git clone <URL_DO_REPOSITORIO>`
2. Navegue até o diretório do projeto: `cd nome-do-projeto`
3. Configure o banco de dados PostgreSQL e ajuste o arquivo `application.properties` com suas credenciais.
4. Execute o comando `mvn spring-boot:run` para iniciar a aplicação.

## Contribuições

Sinta-se à vontade para contribuir com melhorias, correções de bugs ou novas funcionalidades por meio de pull requests.

## Autor

Kaio Vitor - [GitHub](https://github.com/Kaio-0708)
