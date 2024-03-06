# Separation-of-Concerns - Soc 

## Acoplamento e Coesão

A aplicação da separação dos Conceitos/Responsabilidades envolve dois processos: 

- Reduzir o acoplamento
- Aumentar a coesão
#### Aplicando principio DRY
### Acoplamento: (–)
Acoplamento é o nível de dependencia/conhecimento que pode existir entre os componentes do sistema;
Quanto maior o acomplamento entre os componentes do sistema maior será dependencia entre eles, e mais dificl será manter, reusar e estender o sistema

### Coesão: (+)
Coesão é o nível de integridade interna dos componentes do sistema;
Quanto maior a coesão entre os componentes mais definidos são suas responsabilidades sendo mais difícil desmembrar o componente em outros componentes

```Portanto quanto menor o acoplamento e mais alta a coesão de um componente ou módulo do sistema mais fácil será de reusar, estender e  manter```


------------------------------------


```Módulos de alto nível são classes da camada de negócio que encapsulam uma lógica mais complexa```</br>

```Módulos de baixo nível são classes da camada de infraestrutura que implementa operações básicas como acesso a dados, ao disco, protocolos de rede, etc. ``` </br>

```As abstrações seriam interfaces ou classes abstratas que não possuem implementação``` </br>

```Assim as classes da camada de negócio não devem depedner das classes da camada de infraestrutura mas ambas devem depender de interfaces ou classes abstratas```
# Dependency Inversion(DI) ou inversão da dependencia
#### Aplicando principio DIP 
> Não confundir o princípio de Inversão da dependência com o padrão de projeto da Injeção da Dependencia
- A direção da dependencia em uma aplicação deverá ser na direção da abstração e não nos detalhes de implementação

- Módulos de alto nivel não devem depender de modulos de baixo nivel. ambos devem depender de uma abstração

- Abstrações não devem depender de detalhes. Detalhes que devem depender de abstrações

Resumo
- DIP - principio </br>
- DI - padrão de projeto </br>
- IoC - forma de aplicar a inversão da dependencia </br>
- Container IoC - Container de injeção de dependencia - framework que permite fazer a injeção de dependencia de forma automatica nos componentes

