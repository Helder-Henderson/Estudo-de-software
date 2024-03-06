# Projects-Patterns
## Repository Pattern

- Faz a mediação entre o domínio e as camadas de mapeamento de dados, agindo como uma coleção de objetos de domínio em memória

- Um repositorio é essencialmente uma coleção de objetos de domínio em memória, e , com base nisso o padrão Repository permite desacoplar o modelo de dominio do código de acesso a dados.

- Ao utilizar o padrão Repository você pode realizar a persistencia e a separação de interesses em seu código de acesso a dados visto que ele encapsula alógica necessária para persisitr os objetos do seu domínio na sua fonte de dados

#### Implementação e tipos de repositório 

Podemos começar defininndo uma interface que atuará como a nossa fachada de acesso aos dados e a seguir definir a implementação na classe concreta

- Pode-se implementar os seguintes tipos de repositório : 

-- Repositorio Generico <br>
-- Repositorio Especifico

- E podemos realizar uma implementação sincrona ou assincrona (Task, async/await):

-- Criar uma interface ou classe abstrata e definir o contrato com os métodos do repositório<br>
-- Criar a classe concreta que implementa a interface

![image](https://user-images.githubusercontent.com/59569208/181938374-bbe79257-0bef-4005-87d3-2a3dc1c8ca0f.png)


##### Benefícios 

Minimiza a lógica de consultas na sua aplicação evitando consultas esparramadas pelo seu código 

Encapsula a lógica das consultas em um repositório

Desacopla a sua aplicação dos frameworks de persistência como o EF Core

Facilita a realização de testes de unidade em sua aplicação (Repositório fake)

Centraliza a lógica de acesso a dados facilitando a manutenção

-------------------------------

## Patterns MVC 
``` Não confundir com arquitetura em 3 camadas ```

Fornece uma maneira de separar a funcionalidades e responsabilidades envolvidas com a manutenção e apresentação dos dados de uma aplicação usando 3 componentes: 

- O model : Representa os dados a serem tratados e não inclui detalhes de implementação 
- A view : Representa o componente de interface com o usuário (UI) e esta vinculado ao Model
- O Controller - Fornece um mecanismo para o usuário interagir com o sistema definindo como a interface do usuário vai reagir a ação do usuário. É responsável por trocar e interpretar mensagens entre a View e o Model.

### Permitidos 

Os usuarios podem interagir com uma View <br>
Views podem interagir com Controllers <br>
Controllers podem interagir com Views <br>
Controllers podem se comunicar com outros Controllers <br>
Controllers podem se comunicar com o Model

### Não permitidos

Os usuários não podem interagir diretamente com o Model <br>
Views não podem interagir diretamente com outras Views <br>
Views não podem interagir diretamente com o Model <br>
Models não podem interagir com outros Models

![image](https://user-images.githubusercontent.com/59569208/181946265-2edc5f0d-e0ca-4344-b4e4-41d68a57662d.png)

#### Beneficios

- A View e o Model são desacoplados ou dissociados. Isso significa que voce pode ter muitas Views associadas com um determinado model 

- A dissociação View-Controller permite que voce altere a forma como uma aplicação responde a entrada do usuario sem alterar o modo de exibição, permitindo que a interface do usuário (a view) seja alterada sem alterar a maneira como o aplicativo responde a entrada do usuário.

- A sepração das responsabilidades permite que diferentes membros da equipe possam se concentrar em uma parte da aplicação que melhor se alinha com suas respectivas habilidades

- Como o padrão MVC Gerencia múltiplos visualizadores usando o mesmo modelo, é facil manter, testar e atualizar mais de um sistema

![image](https://user-images.githubusercontent.com/59569208/181969657-0a08f9d8-055d-4586-8dba-07eedf917fc5.png)

----------------------------

## CQRS Pattern 

Command Query Responsibility Segregation, é utilizado para aplicar modelos diferentes para operações de leitura e gravação.

- Alterações de dados são realizados via Commands.<br>
``` Commands representa tudo o que altera o estado de uma entidade (insert,update,delete)```<br>

- leitura de dados são realizados via Queries.<br>
``` Queries não alteram o estado da entidade (select) ```

![image](https://user-images.githubusercontent.com/59569208/181982368-e8414e9b-baef-4d74-b21b-f52dcccd2c48.png)

![image](https://user-images.githubusercontent.com/59569208/181984177-e6ea09f2-3ddc-41ee-8c56-ae8d3c91d814.png)

#### Beneficios 

- Escala independente: O CQRS permite que as cargas de trabalho de leitura e gravação sejam escalonadas independentemente o que pode resultar em menos contenções de bloqueio.

- Esquemas de dados otimizados: O lado de leitura pode usar um esquema otimizado para consultas enquanto o lado de gravação usa um esquema otimizado para atualizações .

- Segurança: È mais facil garantir que apenas as entidades de domínio corretas estejam executando gravações nos dados.

- Separação de responsabilidades: A segregação dos lados de leitura e gravação pode resultar em modelos mais flexível e faceis de manter. A maior parte da lógica de negócios complexa entra no modelo de gravação. O modelo de leitura pode ser relativamente simples;

- Consultas mais simples: Ao armazenar uma visualização no banco de dados de leitura, o aplicativo pode evitar junções(joins) complexas durante a consulta tornando as consultas mais simples.
