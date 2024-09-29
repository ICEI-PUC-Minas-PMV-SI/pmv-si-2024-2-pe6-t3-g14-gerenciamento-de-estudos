# APIs e Web Services

O projeto consiste na criação de uma API para o cadastro de usuário e a manutenção de suas disciplinas e notas, para isso executamos alguns passos descritos a seguir.

Criação do Projeto Inicial: Nesta fase, estruturamos a aplicação e criamos os modelos principais que representam as entidades do sistema. Adicionamos também as primeiras validações necessárias para garantir a integridade dos dados.

Definição de Relacionamentos e Rotas: Após a criação dos modelos, estabelecemos os relacionamentos entre as entidades e implementamos as rotas da API, que são responsáveis pela comunicação entre o cliente e o servidor.

Configuração e Testes de Banco de Dados: O banco de dados foi configurado em ambiente de teste, permitindo a execução de testes para validar as rotas implementadas. Esses testes garantem que cada funcionalidade da API esteja funcionando conforme o esperado, ajustando o desempenho e a segurança quando necessário.


## Objetivos da API

O objetivo da API é fornecer e permitir aos usuários:

Criar uma conta: A API deve permitir o registro de novos usuários, armazenando suas informações, como nome, email, e credenciais de acesso. Para autenticação.

Cadastrar asdisciplinas cursadas, essas disciplinas serão vinculadas ao usuário, que poderá gerenciar essas informações usando a classe Disciplina e o enum DisciplinasEnum.

O usuário poderá registrar as notas que obteve em cada disciplina, com validações para garantir que os valores inseridos sejam apropriados (como no caso da classe Nota, que restringe os valores entre 0 e 10).

Os principais recursos que a API fornecerá incluem:

Cadastro e autenticação de usuários.

Gerenciamento de disciplinas.

Gerenciamento de notas.

## Arquitetura

A arquitetura das APIs do aplicativo de gerenciamento de tarefas acadêmicas é baseada em uma estrutura RESTful, facilitando a comunicação entre o cliente e o servidor. Aqui estão os principais componentes e suas interações:

API RESTful: Construída com ASP.NET Core.

Modelo de Dados:

Usuario: Contém informações do usuário e suas disciplinas.

Disciplina: Representa as matérias disponíveis.

Nota: Registra as notas dos usuários em suas disciplinas.

DTOs: Objetos usados para transferir dados entre a API e o cliente, garantindo que apenas as informações necessárias sejam enviadas.

Dados: Utiliza Entity Framework Core para gerenciar as interações com o banco de dados.

Autenticação: Implementa camadas de segurança a partir dos pacotes JWTBearer e BCrypt para garantir a segurança do usuário.

Interações

Requisições do Cliente: O cliente faz requisições HTTP para a API para acessar ou modificar dados.

Controle de Dados: Os controladores da API processam as requisições, validam os dados e interagem com o contexto de dados para realizar operações no banco.

Fluxo de Dados: Por exemplo, ao criar uma nota:

O cliente envia uma requisição com os dados da nota.

O controlador valida e cria uma nova nota no banco de dados.

A API retorna uma resposta ao cliente confirmando a operação.

## Modelagem da Aplicação

A modelagem da aplicação para o sistema de gerenciamento de tarefas envolve a estruturação dos dados e suas interações. Aqui estão os principais pontos:

1. Estrutura de Dados
 
A aplicação tem três entidades principais:

- Usuario: Contém informações como nome, email, senha e as disciplinas que o usuário cursa.

- Disciplina: Representa as matérias, vinculadas a um usuário.

- Nota: Registra as notas que os usuários obtêm nas disciplinas.

2. Diagrama de Classes
+-----------------+         +---------------------+      +---------------------+
|     Usuario     |    1    |    Disciplina       |  *   |      Nota           |
| - Id: int       |-------->| - Id: int           |----->| - Id: int           |
| - Nome: string  |         | - Nome: enum        |      | - Valor: float      |
| - Email: string |         | - UsuarioId: int    |      | - DisciplinaId: int |
| - Senha: string |         +---------------------+      | - UsuarioId: int    |
| + Disciplinas:  |         | + Notas:            |      +---------------------+
|   ICollection<Disciplina> |   ICollection<Nota> |
+-----------------+         +---------------------+



Usuario: Atributos como Id, Nome, Email, Senha, e uma lista de Disciplinas.

Disciplina: Atributos como Id, Nome, UsuarioId, e uma lista de Notas.

Nota: Atributos como Id, Valor, DisciplinaId, e UsuarioId.


3. Outras Representações Visuais
   
Diagrama ER (Entidade-Relacionamento): Mostra como as entidades estão conectadas, ajudando a entender o banco de dados.
Exemplo de Diagrama ER:
+-----------------+      +---------------------+      +---------------------+
|     Usuario     |  1  |    Disciplina        |   *  |      Nota           |
|-----------------|----->|---------------------|----->|---------------------|
| - Id: int       |      | - Id: int           |      | - Id: int           |
| - Nome: string  |      | - Nome: enum        |      | - Valor: float      |
| - Email: string |      | - UsuarioId: int    |      | - DisciplinaId: int |
| - Senha: string |      |---------------------|      | - UsuarioId: int    |
|                 |      | + Notas:            |      +---------------------+
|                 |      |   ICollection<Nota> |
+-----------------+      +---------------------+
   
Relações:
Usuario    (1) ---- (N) Disciplina: Um usuário pode ter várias disciplinas.
Disciplina (1) ---- (N) Nota: Uma disciplina pode ter várias notas.

Fluxogramas: Representam o fluxo de processos, como a autenticação do usuário.

Exemplo de Fluxograma:

+-------------------+
|  Iniciar Processo |
+-------------------+
          |
          v
+-------------------+
| Receber Dados     |
| (Nota, Disciplina)|
+-------------------+
          |
          v
+-------------------+
|   Validar Dados   |
+-------------------+
          |
  +-------+--------+
  |                |
 Yes               No---------------
  |                |               |
  v                v               v
+-------------------+    +-----------------------+
| Salvar Nota       |    |     Retornar Erro     |
| no Banco de Dados |    +-----------------------+
+-------------------+
          |
          v
+-------------------+
| Atualizar Usuario  |
| (se necessário)    |
+-------------------+
          |
          v
+-------------------+
| Finalizar Processo |
+-------------------+

Descrição do Fluxo:

- Iniciar Processo: Começa a operação de criação de uma nova nota.
- Receber Dados: Coleta as informações necessárias (nota e disciplina).
- Validar Dados: Verifica se os dados estão corretos.
- Se sim, continua para salvar a nota.
- Se não, retorna um erro.
- Salvar Nota: Armazena a nota no banco de dados.
- Atualizar Usuario: Caso necessário atualiza informações do usuário.
- Finalizar Processo: Conclui a operação.

## Fluxo de Dados

[Diagrama ou descrição do fluxo de dados na aplicação.]
+-------------------+
|   Início do Fluxo |
+-------------------+
          |
          v
+-------------------+
| Receber Dados     |
| (Nota, Disciplina)|
+-------------------+
          |
          v
+-------------------+
| Validar Dados     |
+-------------------+
          |
  +-------+--------+
  |                |
 Sim                Não-------------
  |                |               |
  v                v               v
+-------------------+    +-----------------------+
|   Salvar Nota     |    | Retornar Erro         |
| no Banco de Dados |    +-----------------------+
+-------------------+
          |
          v
+-------------------+
| Atualizar Usuario  |
| (se necessário)    |
+-------------------+
          |
          v
+-------------------+
| Enviar Resposta   |
| (Confirmação ou   |
|  Erro)           |
+-------------------+
          |
          v
+-------------------+
|    Fim do Fluxo   |
+-------------------+


## Requisitos Funcionais

|RF-001| Cadastro de Usuário                     | ALTA |

|RF-002| Cadastro de Disciplina                  | ALTA |

|RF-003| Criptografia de senhas                  | ALTA |

|RF-004| Armazenamento de nota                   | ALTA |

## Requisitos Não Funcionais

|RNF-001| A API deve suportar até 100 usuários simultâneamente   | MÉDIO |

|RNF-002| A API deve ser de fácil manutenção                     | ALTA |

|RNF-003| As senhas dos usuários devem ser armazenadas com algoritmos de criptografia para garantir a segurança. | ALTA |




## Tecnologias Utilizadas

As técnologias utilizadas em nossa API são a linguagem de programação C#, juntamente com o Entity Framework, além de utilizar pacotes como o BCrypt.Net.Next e também o pacote Microsoft.AspNetCore.Authentication.JWTBearer para realizar os processos de encriptação e segurança.

## API Endpoints

[Liste os principais endpoints da API, incluindo as operações disponíveis, os parâmetros esperados e as respostas retornadas.]

### Endpoint 1
- Método: GET
- URL: /endpoint1
- Parâmetros:
  - param1: [descrição]
- Resposta:
  - Sucesso (200 OK)
    ```
    {
      "message": "Success",
      "data": {
        ...
      }
    }
    ```
  - Erro (4XX, 5XX)
    ```
    {
      "message": "Error",
      "error": {
        ...
      }
    }
    ```


## Considerações de Segurança

[Discuta as considerações de segurança relevantes para a aplicação distribuída, como autenticação, autorização, proteção contra ataques, etc.]

Para garantir a segurança da aplicação adotamos diversas medidas de proteção, focadas em autenticação, autorização.

Autenticação:

O sistema utiliza JWT (JSON Web Token), implementado com o pacote JWTBearer, para autenticação segura dos usuários. Ao fazer login, o usuário recebe um token que é utilizado nas solicitações subsequentes para identificar e autenticar o acesso. Esse token é assinado de forma criptografada, garantindo que não possa ser alterado sem a chave de assinatura.

Autorização:

A autorização é tratada por meio de políticas e claims definidas nos tokens JWT. Essas claims indicam o nível de acesso do usuário, garantindo que ele tenha permissões adequadas para acessar recursos específicos.

Criptografia de Senhas:

As senhas dos usuários são armazenadas de forma segura utilizando o pacote BCrypt.Net.Next.

## Implantação

[Instruções para implantar a aplicação distribuída em um ambiente de produção.]

1. Defina os requisitos de hardware e software necessários para implantar a aplicação em um ambiente de produção.
2. Escolha uma plataforma de hospedagem adequada, como um provedor de nuvem ou um servidor dedicado.
3. Configure o ambiente de implantação, incluindo a instalação de dependências e configuração de variáveis de ambiente.
4. Faça o deploy da aplicação no ambiente escolhido, seguindo as instruções específicas da plataforma de hospedagem.
5. Realize testes para garantir que a aplicação esteja funcionando corretamente no ambiente de produção.

## Testes

[Descreva a estratégia de teste, incluindo os tipos de teste a serem realizados (unitários, integração, carga, etc.) e as ferramentas a serem utilizadas.]

1. Crie casos de teste para cobrir todos os requisitos funcionais e não funcionais da aplicação.
2. Implemente testes unitários para testar unidades individuais de código, como funções e classes.
3. Realize testes de integração para verificar a interação correta entre os componentes da aplicação.
4. Execute testes de carga para avaliar o desempenho da aplicação sob carga significativa.
5. Utilize ferramentas de teste adequadas, como frameworks de teste e ferramentas de automação de teste, para agilizar o processo de teste.

# Referências

Inclua todas as referências (livros, artigos, sites, etc) utilizados no desenvolvimento do trabalho.
