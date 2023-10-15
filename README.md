<div style="background-color: #ff69b4; padding: 10px; text-align: center;">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="Java Icon" width="100" height="100">
</div>

# TodoList Backend

Este é o repositório do backend para o aplicativo TodoList, que gerencia tarefas.

## Funcionalidades

O backend do TodoList oferece as seguintes funcionalidades:

- Registro e autenticação de usuários.
- Criação, listagem e atualização de tarefas.
- Filtros de autenticação baseados em cabeçalhos `Authorization`.
- Manipulação de exceções personalizadas.

## Tecnologias Utilizadas

O backend foi desenvolvido usando as seguintes tecnologias e bibliotecas:

- Java
- Spring Boot
- Banco de Dados H2 
- BCrypt (para hash de senhas)
- Outras dependências do seu projeto

## Configuração

Para configurar o projeto:

1. Clone este repositório.
2. Configure o banco de dados no arquivo `application.properties`.
3. Certifique-se de que o banco de dados esteja configurado e acessível.

## Autenticação

O filtro de autenticação `FilterTaskAuth` verifica a autorização do usuário com base no cabeçalho `Authorization`. As credenciais devem ser fornecidas no formato `Basic <credenciais_codificadas_em_base64>`. A autenticação é validada em relação às informações do banco de dados.

## Manipulador de Exceções

O manipulador de exceções `ExceptionHandlerController` responde a exceções do tipo `HttpMessageNotReadableException` com códigos de resposta 400 (Bad Request) e mensagens de erro específicas.

## Endpoints da API

- `POST /users`: Registro de usuário.
- `POST /users/login`: Autenticação de usuário.
- `POST /tasks`: Criação de tarefas.
- `GET /tasks`: Listagem de tarefas do usuário.
- `PUT /tasks/{id}`: Atualização de tarefas.

## Classes Relacionadas às Tarefas (Tasks)

### `TaskModel`

A classe `TaskModel` representa uma tarefa no sistema e inclui atributos como título, descrição, datas de início e término, prioridade e identificador do usuário associado.

### `TaskController`

O `TaskController` é responsável por gerenciar as operações relacionadas a tarefas, incluindo criação, listagem e atualização.

### `ITaskRepository`

A interface `ITaskRepository` estende `JpaRepository` e fornece métodos para interagir com as tarefas no banco de dados, incluindo a recuperação de tarefas associadas a um usuário específico.

## Uso

- Use o filtro de autenticação para autenticar as solicitações via cabeçalho `Authorization`.
- Utilize os endpoints da API para criar, listar e atualizar tarefas.
- Monitore as respostas do manipulador de exceções para lidar com erros específicos.

Lembre-se de configurar o projeto corretamente e seguir as etapas de configuração mencionadas anteriormente.

