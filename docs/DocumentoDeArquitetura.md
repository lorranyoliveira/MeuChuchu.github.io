# Documento de Arquitetura

| Data | Versão | Descrição | Autor |
|--|--|--|--|
| 09/11/2020 | 0.1 | Tópico 3| Daniela Soares |
| 10/11/2020 | 0.2 | Tópico 5| Giovana Dionisio |
| 10/11/2020 | 0.3 | Tópico 2| Hérya Rodrigues |
| 10/11/2020 | 0.4 | Tópico 1| Lorrany Oliveira |
| 11/11/2020 | 0.5 | Tópico 4| Sara Campos |
| 18/11/2020 | 1.0 | Revisão Geral| Daniela Soares e Lorrany Oliveira |
| 25/11/2020 | 1.1 | Revisão| Hérya Rodrigues |




## 1. Introdução

### 1.1 Finalidade

O presente documento tem como finalidade expor uma visão geral sobre a arquitetura usada pelo software MeuChuchu tendo como o intuito uma descrição do sistema que auxilia na compreensão de como o sistema irá se comportar.

### 1.2 Escopo

MeuChuchu é um aplicativo com o objetivo de ajudar feirantes a terem mais visibilidade na exposição de produtos alimentícios oriundos de feiras regionais. Com isso, o atual documento possui informações acerca das decisões tomadas pelo grupo sobre a organização da arquitetura do aplicativo.

### 1.3 Definições, Acrônimos e Abreviações
*API : Application Programming Interface

### 1.4 Referências
* [AIX - Chatbot Python](https://fga-eps-mds.github.io/2019.1-Aix/)
* [HUBCARE ](https://cjjcastro.gitlab.io/2019-1-hubcare-docs/)
* [KalKuli ](https://fga-eps-mds.github.io/2018.2-Kalkuli//)


## 2. Representação da Arquitetura

### 2.1 Diagrama de relações

![Diagrama de Relações](https://i.ibb.co/xqbLHHK/diagrama-rela-es.png)
### 2.1.1 Flask

Flask é um *microframework* para linguagem Python, baseado em Jinja 2, Werkzeug e good intentions. Por padrão, seu núcleo conta apenas com os módulos necessários à criação da aplicação. Assim, é um *microframework* simples, mas extensível e flexível.  Como Flask não possui uma ferramenta padrão para mapeamento objeto-relacional, será usado a extensão Flask-SQLAlchemy juntamente com a biblioteca Psycopg2. Para garantir as boas práticas de padrão de APIs RESTful, será utilizado a extensão Flask-RESTful para a criação de uma API em Flask que seja consistente.

### 2.1.2 React Native

React Native é um *framework open source* para construção de aplicativos nativos para Android e iOS, utilizando JavaScript. Dessa forma, o código da aplicação é escrito em JavaScript, mas renderizado em código nativo. Tendo como proposito manter uma base única de código para distribuição de código multiplataforma. A criação da interface se baseia na JSX, dialeto de JavaScript que procura se assimilar ao HTML, para criação de componentes reutilizáveis.

### 2.1.3 PostgreSQL

PostgreSQL é um sistema de gerenciamento de banco de dados relacional *open source*, com ênfase em extensibilidade e conformidade com SQL.

## 3.Metas e Restrições de Arquitetura

São metas da arquitetura:
* Disponibilizar ao usuário consumidor em potencial uma aplicação para maior identificação com a banca do feirante
* Disponiblizar a aplicação para dispositivos Android
* Disponibilizar interface para usuário feirante

São restrições de arquitetura:
* Conexão com a internet é necessária.
* Dispositivo móvel com Sistema Operacional Android.
* Banco de dados relacional fazendo uso de PostgreSQL.
* Possuir uma API que siga os princípios REST.

# 4. História de usuário

Os dois tipos de usuários possuem acessos similares dentro do aplicativo, sendo que, a diferença essencial é de que o usuário feirante além do login, cadastro, opção de editar perfil, acesso às categorias, à busca e às bancas, terá a  opção de criar/gerenciar sua própria banca. 

| Usário | História |
| --- | --- |
| Usuários consumidor e feirante |	Consumidor/feirante deseja entrar na aplicação |
| Usuários consumidor e feirante |	Consumidor/feirante deseja se cadastrar na aplicação |
|	Usuários consumidor e feirante |	Usuário deseja definir seu tipo de perfil como consumidor ou feirante |
| Usuário feirante |	Feirante deseja cadastrar sua banca na aplicação |
| Usuário feirante | Feirante deseja adicionar/remover produtos da tela da banca | 
| Usuários consumidor e feirante | Consumidor/feirante deseja visualizar a banca, seus produtos e informações de contato |
|	Usuário consumidor |	Consumidor deseja adicionar ou remover suas bancas como favoritas |
|	Usuários consumidor e feirante |	Ambos desejam fazer buscas de bancas pelo nome |


## 5. Visão Lógica
### 5.1 Diagrama de Pacotes
![Front](https://i.ibb.co/k92QktX/Vis-o-L-gica-Front.jpg)  
![Back](https://i.ibb.co/hHBhxBP/Vis-o-L-gica-Back.jpg)


