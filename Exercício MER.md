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
