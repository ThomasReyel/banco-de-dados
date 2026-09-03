## Questão 1
SGBD ou sistema de gerenciamento de banco de dados é um software utilizado para gerir e armazenar base de dados de uma forma mais
organizada. Algumas das vantagens dos SGBDs em relação a um sistema de arquivo padrão são: atomicidade, operações
atômicas são mais difíceis de se executar em um sistema padrão de arquivo; Questões de segurança, os SGBD previnem acessos indevidos
ao banco de dados; previne criação de dados repetidos e padronizam o tipo do arquivo que guarda a base de dados.

## Questão 2

```mermaid
erDiagram
    CAMPEONATO {
        int codigo
        string nome
        date data_inicio
        date data_final
    }
    
    EQUIPE {
        int codigo
        string nome
    }
    
    JOGADOR {
        int codigo
        string nome
        string apelido
        string posicao
    }
    
    CT {
        int codigo
        string nome
        string funcao
    }
    
    PARTIDA {
        int codigo
        string estadio
        date data
        string endereco
    }
    
    ESCALACAO {
        int id
        int código_equipe
        int código_partida
        int código_jogador
        int numero_camisa
        string situacao
        string status
    }
    
    GOL {
        int id
        int numero_gols
        string autor
    }

CAMPEONATO ||--o{ PARTIDA : Possui

CAMPEONATO ||--|{ EQUIPE : Participam

PARTIDA }o--|{ EQUIPE : Disputam

EQUIPE ||--|{ JOGADOR: Possui

EQUIPE ||--|{ CT: Possui

ESCALACAO }|--|| PARTIDA: Contém

JOGADOR ||--|{ ESCALACAO: Contém

EQUIPE ||--|{ ESCALACAO: Contém

PARTIDA ||--|{ GOL: Possui

GOL ||--|{ ESCALACAO: Contém
```

## Questão 3


```mermaid
erDiagram
  UFRN {
  
  }

  CENTRO {}

  DEPARTAMENTO {}

  DOCENTE {}

  COMPONENTE_CURRICULAR {}

  CURSO {}

  ESTRUTURA_CURRICULAR {}

  ALUNO {}

  DISCIPLINA {}

  MATRICULA {}

  TURMA {}

  CENTRO ||--|{ CURSO : tem
  CENTRO ||--|{ DEPARTAMENTOS : tem
  ALUNO }|--|| CURSO : matriculado
  CURSO ||--|{ COMPONENTE_CURRICULAR : tem
  DEPARTAMENTO ||--|{ COMPONENTE_CURRICULAR : responsável
  DOCENTE }|--|{ TURMA : ensina
  TURMA }|--|{ ALUNO : tem
  DISCIPLINA ||--|{ TURMA : tem
  TURMA ||--|{ ALUNO : monitor
  ALUNO }|--|| DEPARTAMENTO : tem
  
```

## Questão 4

```mermaid
erDiagram

    VEÍCULO {

      string marca
      string placa
      string cor
      date ano
      float quilometragem
      float locação
      string categoria
  }

    CLIENTE {

      string cpf
      string cnh
      string nome
      string endereço
      string telefone
      int idade
}

    ALUGUEL {

      string cliente
      string veículo
      date data
      string hora
}

    LISTA {

      int qnt_veículos
      float horas
      float valor_total_aluguéis
      int qnt_multas
}

    TÉCNICO {

      string numero_cadastro
      string cpf
      string nome
}

ALUGUEL }|--|| VEÍCULO: tem
ALUGUEL }|--|| CLIENTE: faz
LISTA ||--|| CLIENTE: tem
TÉCNICO }|--|{ VEÍCULO: revisa
```

## Questão 5


```mermaid
erDiagram

CLIENTE {

    string cpf
    string nome
    string telefone
    string endereço
}

PRODUTO {

    string nome
    string tipo
    string preço
    string quantidade
    float preço
    int quantidade
}

COMPRA {

    string cliente
    date data
    float valor_total
    string produtos
}

FUNCIONARIOS {

    string nome
    string telefone
    string endereço
    float salário
    string função
    string cpf
}

FORNECEDOR {

    string nome
    string cnpj
    string telefone
    string endereço
}

CLIENTE ||--|{ COMPRA: tem
PRODUTO }|--|{ COMPRA: possui

```
## Questão 6

```mermaid
erDiagram

DEPARTAMENTO {

    string nome
    int número
}

PROJETO {

    string nome
    int número
    date período
}

FUNCIONÁRIO {
    int id
}

PESQUISADOR {

    string nome
    string endereço
    string sexo
    date data_nascimento
    float salário
    string área
}

SECRETÁRIO {

    string nome
    string endereço
    string sexo
    date data_nascimento
    float salário
    string grau_escolaridade

}

LIMPEZA {

    string nome
    string endereço
    string sexo
    date data_nascimento
    float salário
    string jornada_trabalho
}

DEPENDENTE {

    string nome
    string endereço
    string sexo
    string grau_parentesco
}

DEPARTAMENTO ||--|{ PROJETO: controla
FUNCIONÁRIO ||--|| LIMPEZA: "pode ser"
FUNCIONÁRIO ||--|| PESQUISADOR: "pode ser"
FUNCIONÁRIO ||--|| SECRETÁRIO: "pode ser"
FUNCIONÁRIO }|--|| DEPARTAMENTO: pertence
PESQUISADOR }|--|{ PROJETO: trabalha
FUNCIONÁRIO ||--|{ DEPENDENTE: possui
```
