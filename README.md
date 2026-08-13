# banco-de-dados

## Conceitos
### O que é?
Conjunto de dados armazenados com contexto.

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
 
## SGBD
### Visão de dados
- Um SGBD é uma coleção de arquivos e progrmas inter-relacionados
- Proporciona uma visão abstrata dos dados:
  - Oculta do usuário detalhes sobre a forma de armazenamento e de manutenção
### Níveis de Abstração
- Físico
- Lógico
- Visão

### Instâncias e Esquemas
- O conjunto de informações em um BD, em um dado momento, é chamado instância (E uma fotografia)
- O projeto geral do BD é chamado esquema

### Modelo de dado
