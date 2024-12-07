# Front-end Móvel

Aplicativo vem com o objetivo de auxiliar, controlar e facilitar a organização do usuário, com seus estudos e suas notas.
Dessa forma o aplicativo foi desenvolvido com a opção de cadastro de notas e matérias, sendo assim o usuário pode lançar suas notas e acompanhar seu aproveitamento durante o período letivo.

## Tecnologias Utilizadas

No desenvolvimento do Front-end Móvel foram utilizadas as tecnologias React, e para persistência dos dados o Sqlite.

## Arquitetura

A arquitetura do aplicativo de gerenciamento de tarefas acadêmicas mobile é construido com base no React para renderizar a tela, e no Sqlite para persistir os dados

Modelo de Dados:

Usuario: Contém informações do usuário e suas disciplinas.

Disciplina: Representa as matérias disponíveis.

Nota: Registra as notas dos usuários em suas disciplinas.

Dados: Utiliza Sqlite para gerenciar as interações com o banco de dados.


Interações

Requisições do Cliente: O cliente faz requisições para acessar ou modificar dados.

Fluxo de Dados: Por exemplo, ao criar uma nota:

O cliente envia uma requisição com os dados da nota.

O controlador valida e cria uma nova nota no banco de dados.

A API retorna uma resposta ao cliente confirmando a operação.

## Projeto da Interface
[Descreva o projeto da interface móvel da aplicação, incluindo o design visual, layout das páginas, interações do usuário e outros aspectos relevantes.]

### Wireframes
[Inclua os wireframes das páginas principais da interface, mostrando a disposição dos elementos na página.]

### Design Visual
[Descreva o estilo visual da interface, incluindo paleta de cores, tipografia, ícones e outros elementos gráficos.]

### Layout Responsivo

O desenvolvimento do React utilizando responsividade nativa.

### Interações do Usuário

Atravez da aplicação o usuário pode realizar cadastros, através de imputs, realizar consultas e atualizações nos dados.

## Fluxo de Dados
![123456](https://github.com/user-attachments/assets/8a9e2690-fd5f-4c59-997c-b3c6974f45a9)


## Requisitos Funcionais
|RF-001| Cadastro de Usuário | ALTA |

|RF-002| Cadastro de Disciplina | ALTA |

|RF-003| Persistência de dados | ALTA |


Requisitos Não Funcionais
|RNF-001| A aplicação deve suportar até 100 usuários simultâneamente | MÉDIO |

|RNF-002| A aplicação deve ser de fácil manutenção | ALTA |

|RNF-003| A aplicação deve ser responsiva | ALTA |


## Considerações de Segurança

Sendo uma aplicação que funcionará localmente no dispositivo do usuário, visamos a utilização de recursos nativos do dispositivo para segurança.

# Referências

Inclua todas as referências (livros, artigos, sites, etc) utilizados no desenvolvimento do trabalho.
