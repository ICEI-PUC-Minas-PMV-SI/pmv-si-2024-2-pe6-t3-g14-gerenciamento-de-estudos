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

   ![diagrama de classe](https://github.com/user-attachments/assets/034d21db-fd67-4d86-81c2-52aa3a8617c8)



Usuario: Atributos como Id, Nome, Email, Senha, e uma lista de Disciplinas.

Disciplina: Atributos como Id, Nome, UsuarioId, e uma lista de Notas.

Nota: Atributos como Id, Valor, DisciplinaId, e UsuarioId.


3. Outras Representações Visuais
   
Diagrama ER (Entidade-Relacionamento): Mostra como as entidades estão conectadas, ajudando a entender o banco de dados.
Exemplo de Diagrama ER:

Relações:
Usuario    (1) ---- (N) Disciplina: Um usuário pode ter várias disciplinas.
Disciplina (1) ---- (N) Nota: Uma disciplina pode ter várias notas.
![EntidadeR](https://github.com/user-attachments/assets/bf2481b4-cab6-4902-aefd-19b542d59d5a)

Fluxogramas: Representam o fluxo de processos, como a autenticação do usuário.

Exemplo de Fluxograma:

![fluxogram2](https://github.com/user-attachments/assets/799bd56f-06cf-4b0d-80a8-8d20cc6b29f1)

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

![fluxodd1](https://github.com/user-attachments/assets/d0ef602d-e619-4afc-8e4b-87800a94909a)


![fluxodd2](https://github.com/user-attachments/assets/2a5fb5fd-8b2d-4eb7-abb8-5b08a7090416)


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

### Endpoint 1
- Método: GET
- URL: /Usuarios/{id}
- Parâmetros:

   {
   "id":
  }

   Resposta:
  
   Sucesso (200 OK)
   {
   "nome": "Luiz",
  "email": "luiz@hotmail.com",
   "id": 2
  -  }
  - Erro (404)
  - {
  -"type": "https://tools.ietf.org/html/rfc9110#section-15.5.5",
  -"title": "Not Found",
  -"status": 404,
  -"traceId": "00-97e1c82a67c072d0521f02683e7c523c-e0dbc3410a2e44a9-00"

}

### Endpoint 2
- Método: POST
- URL: /Notas/{id}
- Parâmetros:
 {
  "valor": 9.5,
  "disciplinaId": 1,
  "usuarioId": 1
}

- Resposta:
- Sucesso (201)
- {
  "message": "Nota criada com sucesso.",
  "data": {
    "id": 1,
    "valor": 9.5,
    "disciplinaId": 1,
    "usuarioId": 1
  }
}

### Endpoint 3
- Método: DELETE
- URL: /Notas/{id}
- Parâmetros:
  {
   "id":
  }
- Resposta:(404)
- {
  "message": "Error",
  "error": {
    "details": "Nota não encontrada."
  }
}

  

## Considerações de Segurança

Para garantir a segurança da aplicação adotamos diversas medidas de proteção, focadas em autenticação, autorização.

Autenticação:

O sistema utiliza JWT (JSON Web Token), implementado com o pacote JWTBearer, para autenticação segura dos usuários. Ao fazer login, o usuário recebe um token que é utilizado nas solicitações subsequentes para identificar e autenticar o acesso. Esse token é assinado de forma criptografada, garantindo que não possa ser alterado sem a chave de assinatura.

Autorização:

A autorização é tratada por meio de políticas e claims definidas nos tokens JWT. Essas claims indicam o nível de acesso do usuário, garantindo que ele tenha permissões adequadas para acessar recursos específicos.

Criptografia de Senhas:

As senhas dos usuários são armazenadas de forma segura utilizando o pacote BCrypt.Net.Next.

## Implantação

Instruções para Implantação

Requisitos:

Hardware:

CPU: 2 núcleos.
RAM: 4 GB.
Armazenamento: 20 GB.

Software:

Sistema Operacional: Windows ou Linux.
Banco de Dados: MySQL ou SQL Server.
.NET Core instalado.

Escolha da Hospedagem:

Plataformas como AWS ou Azure.

Configuração do Ambiente:

Instale dependências (.NET Core, banco de dados).
Configure variáveis de ambiente (como strings de conexão).

Deploy da Aplicação:

Use ferramentas como Docker ou CI/CD para fazer o upload do código.

Testes:

Teste a aplicação para garantir que tudo funciona.
Verifique o desempenho e monitore logs.

## Testes

Testes Unitários:

Objetivo: Verificar se unidades individuais de código (funções, métodos, classes) funcionam corretamente.
Ferramentas: xUnit ou NUnit para .NET.

Caso de Teste: Criação de Usuário

ID do Caso de Teste: TC001

Objetivo: Verificar se um usuário pode ser criado com sucesso com dados válidos.

Pré-condições:

O serviço da API deve estar em execução.
O banco de dados deve estar acessível.

Dados de Entrada:
{
  "nome": "João Silva",
  "email": "joao@example.com",
  "senha": "senhaSegura123"
}

Passos:

Enviar uma requisição POST para a API /api/usuarios com os dados de entrada acima.
Resultado Esperado:

A resposta deve ser um status 201 Created.
O corpo da resposta deve conter os detalhes do usuário criado, incluindo um ID gerado.
Pós-condições:

O usuário deve ser inserido no banco de dados e deve ser possível recuperá-lo usando sua ID.
Testes de Integração:

Objetivo: Validar a interação entre diferentes componentes da aplicação, como a comunicação entre a API e o banco de dados.
Ferramentas: Postman para testes de API.

Testes de Performance:

Objetivo: Medir o tempo de resposta e o desempenho geral da aplicação em diferentes cenários.

Testes de Segurança:

Objetivo: Identificar vulnerabilidades e garantir que a aplicação esteja protegida contra ataques comuns.


Implementação:

Criação de Casos de Teste: Desenvolver casos de teste para cada funcionalidade, cobrindo tanto requisitos funcionais quanto não funcionais.
Execução de Testes: Automatizar a execução dos testes sempre que novas alterações forem feitas no código, usando ferramentas de CI/CD como Jenkins ou GitHub Actions.
Relatórios:

Gerar relatórios de testes para documentar resultados, identificar falhas e acompanhar a qualidade do software ao longo do tempo.


# Referências

Referências

Stack Overflow: Plataforma de perguntas e respostas onde diversos problemas de programação e desenvolvimento de software foram discutidos e solucionados.
Link: stackoverflow.com

ChatGPT: Modelo de linguagem da OpenAI utilizado para auxiliar na geração de textos e resolução de dúvidas técnicas.
Link: openai.com/chatgpt

Biblioteca do .NET: Documentação oficial que fornece informações sobre as funcionalidades e classes disponíveis na plataforma .NET.
Link: .NET Documentation

Balta.io: Plataforma de cursos online que oferece conteúdos voltados para desenvolvimento de software, incluindo temas relacionados a .NET e tecnologias web.
Link: balta.io

Udemy: Plataforma de aprendizado online com diversos cursos sobre programação e desenvolvimento de aplicações.
Link: udemy.com
