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

[Liste os principais requisitos funcionais da aplicação.]

## Requisitos Não Funcionais

[Liste os principais requisitos não funcionais da aplicação, como desempenho, segurança, escalabilidade, etc.]


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
