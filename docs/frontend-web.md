# Front-end Web

O projeto envolve o desenvolvimento do front-end para garantir uma interface amigável e eficiente para os usuários interagirem com a API.

Integração com a API: Implementamos a comunicação com a API através de chamadas HTTP, garantindo que as interações, como salvar ou editar disciplinas e notas, sejam realizadas de maneira rápida e eficiente, utilizando funções como fetch API. 

Validações e Feedback ao Usuário: No front-end,desenvolvemos mensagens que informam ao usuário e retornam informações relevantes.

Design e Responsividade: O front end conta com a responsividade nativa do bootstrap.

## Tecnologias Utilizadas

Utilizamos no projeto as tecnologias como Html, para melhorar visualmente o Bootstrap, Css para ajustes finos de estilização e para manipulação de dados utilizamos o Javascript.

## Arquitetura

A arquitetura da aplicação web do aplicativo de gerenciamento de tarefas acadêmicas é baseada em uma estrutura de Fetch API, facilitando a comunicação entre o cliente e o serviço. Aqui estão os principais componentes e suas interações:

Fetch API : Construída com base nos Controllers do Back End

Modelo de Dados:

Usuario: Contém informações do usuário e suas disciplinas.

Disciplina: Representa as matérias disponíveis.

Nota: Registra as notas dos usuários em suas disciplinas.

Autenticação: Implementa camadas de segurança a partir dos pacotes JWTBearer e BCrypt para garantir a segurança do usuário.

Interações

Requisições do Cliente: O cliente faz requisições HTTP para a API para acessar ou modificar dados.

Controle de Dados: Os controladores da API processam as requisições, validam os dados e interagem com o contexto de dados para realizar operações no banco.

Fluxo de Dados: Por exemplo, ao criar uma nota:

O cliente envia uma requisição com os dados da nota.

O controlador valida e cria uma nova nota no banco de dados.

A API retorna uma resposta ao cliente confirmando a operação.

## Projeto da Interface Web
[Descreva o projeto da interface Web da aplicação, incluindo o design visual, layout das páginas, interações do usuário e outros aspectos relevantes.]

A interface web consiste em uma página que será construida dinamicamente com base nas interações do usuário, como exemplo: 

Na página inicial teremos na lateral esquerda a lista de disciplinas do usuário.

Ao topo do barra de navegação temos um ícone de usuário que permite o login e o logout.

Ao centro da página temos a lista de tarefas e os espaço destinado para geração do gráfico geral do rendimento do usuário.

Em páginas de cadastro temos a abertura de modais, com as informações desejadas, como na página de cadastro de disciplinas, notas e tarefas.

Além disso temos a página que exibe o rendimento do aluno em uma disciplina específica, contendo uma tabela com as notas cadastradas e um gráfico comparando as notas cadastradas durante o período.

### Wireframes

![desktop1](https://github.com/user-attachments/assets/afeecc2e-8dae-4822-857d-3bd35e0fb40c)
![desktop2](https://github.com/user-attachments/assets/ab68be52-b63c-484d-83ff-52923a0e9a94)
![desktop3](https://github.com/user-attachments/assets/ff311498-3c88-4766-9056-65886b0af36a)
![desktop4](https://github.com/user-attachments/assets/1da768ea-6d77-4bb0-88cd-fae1875af35c)
![desktop5](https://github.com/user-attachments/assets/e3692b71-963b-42ac-8c4a-5fa4c79668be)
![desktop6](https://github.com/user-attachments/assets/746c579b-21ef-409d-91d1-3e7f6516463a)



### Design Visual

Para o design visual optamos por utilizar a biblioteca de estilos do bootstrap, assim utilizando como padrão sua tipografia, paleta de cores, ícones entre outros elementos gráficos, além de utilizarmos a biblioteca chars js para criação de gráficos dinamicamente.

### Layout Responsivo

Utiliza a responsividade nativa do bootstrap, sendo assim o controle da responsividade é feito a partir das classes col, row, d-flex e container.

### Interações do Usuário

Durante a utilização do sistema de gerenciamento de estudos o usuário vai ter as seguintes interações:

Cadastro de disciplinas

Cadastro de notas

Cadastro de tarefas

Durante esses cadastros o usuário irá preencherá um formulário em um modal que será exibido dinamicamente na tela.

A transição da página login para a página principal do sistema.
## Fluxo de Dados

Durante a interação do usuário com o sistema o fluxo de dados segue por meio das requisições HTTP em funções de Fetch API seguindo o padrão dos verbos GET, POST, PUT e DELETE na interação com o Back End e posteriormente o banco de dados.

## Requisitos Funcionais

|RF-001| Cadastro de Usuário | ALTA |

|RF-002| Cadastro de Disciplina | ALTA |

|RF-003| Cadastro de Tarefas | ALTA |

|RF-004| Cadastro de Notas | ALTA |

|RF-005| Apagar Usuários | ALTA |

|RF-006| Apagar disciplinas | ALTA |

|RF-007| Apagar Tarefas | ALTA |

|RF-008| Apagar Notas | ALTA |

## Requisitos Não Funcionais

[Liste os principais requisitos não funcionais da aplicação, como desempenho, segurança, escalabilidade, etc.]

Requisitos Não Funcionais
|RNF-001| A interface web deve suportar até 100 usuários simultâneamente | MÉDIO |

|RNF-002| A interface deve ser de fácil manutenção | ALTA |

|RNF-003| O layout deve ser responsivo | ALTA |

|RNF-004| O layout deve ser intuitivo | ALTA |


## Considerações de Segurança

[Discuta as considerações de segurança relevantes para a aplicação distribuída, como autenticação, autorização, proteção contra ataques, etc.]


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
