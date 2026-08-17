# banco-de-dados

## Conceitos
### O que é?
Conjunto de dados relacionados armazenados em um dispositivo. Esse dispositivo é independente do sistema que fornece as informações. O sistema que se conecta no BD precisa poder realizar as operações do CRUD

### ACID
Atomicidade

Consistência

Isolamento

Durabilidade

...
## Sitemas de Arquivos
- Problemas
  - Arquivos diferentes em formatos diferentes programas diferentes não conseguiam rodar.
  - Inconsistência e redundância de dados (Não possui ferramentas de controle)
  - Não havia uma padronização
  - Atomicidade (várias operações ao mesmo tempo, é muito difícil de se garantir em sistemas de arquivos)
  - Não consegue atualizar tudo ao mesmo tempo
  - Interação de atualizações concorrentes pode gerar inconsistência de dados
  - Problemas de segurança (não pode garantir que pessoas vejam somente o que as compete)
 
## SGBD (Sistema Gerente de Banco de Dados)
O objetivo de um SGBD é Proporcionar um ambiente para a recuperação e armazenamento das informações do banco de dados.
Sistemas de BD são projetados para gerir grandes volumes de informações. Possivelmente da ordem de petabytes ou mais.

### Visão de dados
- Um SGBD é uma coleção de arquivos e programas inter-relacionados
- Proporciona uma visão abstrata dos dados:
  - Oculta do usuário detalhes sobre a forma de armazenamento e de manutenção
### Níveis de Abstração
- Físico: Descreve como de fato os dados estão armazenados fisicamente na máquina.
- Lógico: Descreve quais os dados que estão armazenados no banco e os inter-relacionamentos entre eles. É uma abstração para administradores do banco de dados que precisam decidir quais informações deve pertencer ao banco. Dessa forma não sendo necessário conhecer os trâmites do nível físico. (Esse é o nível do programador)
- Visão: Mais alto nível de abstração. Descreve apenas parte do banco de dados. É o que o cliente verá


### Instâncias e Esquemas
- O conjunto de informações em um BD, em um dado momento, é chamado instância (E uma fotografia, meio que um objeto mas é o daquele momento e somente quando ele estiver no contexto de estar conectado no banco)
- O projeto geral do BD é chamado esquema (Meio que a classe de poo)

### Modelo de dado
Um conjunto de ferramentas conceituais usadas para a descrição de dados, relacionamentos entre dados semântica de dados e regras de consistência. Ou seja é a forma como descrevemos o dado suas relações e regras. Possuem 3 tipos:

- Modelos lógicos com base em objetos;
Usado na descrição dos dados no nível lógico e de visões.
  - Modelo entidade relacionamento (Mer)
Nesse modelo existem as entidades, objetos ou partes envolvidas no negócio (Exemplo: um carro ou uma venda); Também existem os relacionamentos, que são a forma e a quantidade na qual os objetos se relacionam.

  - Modero Orientado a Objetos - OO
Se  fundamenta nos preceitos de OO com objetos, Encapsulamento, herança e etc.
    
- Modelos lógicos com base em registros;
Esses modelos são voltados para o entendimento dos registros dos dados, o BD é estruturado por meio de registros fixos
- Modelos físicos.
Como a informação é gravada fisicamente na máquina.


## Modelo Entidade-Relacionamento
- Entidade: É um objeto que existe e é parte do negócio seja ele um objeto real ou abstrato (ex: carro ou venda). Uma entidade é um conjunto de atributos
- Atributos: São características comuns a instâncias das entidades. São divididas em 2 tipos
  - Simples: É atômico (ex: Idade: numérico; Nome: cadeia de caracteres).
  - Composto: Contém sub-atributos que compõem o atributo (ex: Endereço: (rua, número, bairro, cidade)).
- Relacionamento: são a forma e a quantidade na qual as entidades se relacionam entre si.
