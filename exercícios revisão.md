1. **Médicos e Hierarquia de Plantão**:
  * O hospital possui médicos cadastrados. Durante os plantões, um médico experiente pode **supervisionar** outros médicos.
  * Um médico supervisor pode orientar vários médicos, mas cada médico supervisionado no plantão responde a no máximo um
  * supervisor (e alguns médicos trabalham de forma autônoma, sem supervisor).
2. **Atendimentos e Prescrições**:

Um médico atende pacientes em consultas. Durante uma consulta, o médico pode gerar uma **prescrição**. Na prescrição,
podem constar vários medicamentos, e para cada medicamento prescrito deve-se registrar a **dosagem** e a **frequência**
(ex: *500mg, de 8 em 8 horas*). O mesmo medicamento pode ser prescrito em diversas consultas.
3. **Internações e Quartos**:
  * Um quarto do hospital possui um número e um andar, e contém vários **leitos** (identificados por letras como 'A', 'B', 'C').
Cada leito pertence obrigatoriamente a um único quarto.
  * Quando um paciente é internado, ele é alocado em um leito. O sistema precisa registrar a **data de entrada** e a
  * **data de alta** do paciente naquele leito específico. Um paciente pode passar por várias internações ao longo do tempo.

---
``` mermaid

erDiagram

MEDICO{
  string nome
  string cim
  
}

QUARTO{
  int numero
  int andar
}

LEITO{
  string identificacao
}


CONSULTA{
  date data
  datetime horario
  
}

PACIENTE{
  string nome
  string cpf
  date dataNascimento
  string numeroProntuario
}

PRESCRICAO{
  date data
}

MEDICAMENTO{
  string nome
  string marca
  boolean generico
}

ITEM_PRESCRICAO{
  string dosagem
  string frequencia
}
INTERNACAO{
  date dataEntrada
  date dataAlta
}

MEDICO}|--o|MEDICO: supervisiona
MEDICO||--|{CONSULTA: atende
PACIENTE||--|{CONSULTA: possui
CONSULTA||--o|PRESCRICAO: passa
PRESCRICAO}o--|{MEDICAMENTO: possui
QUARTO||--|{LEITO: possui
PACIENTE||--|{INTERNACAO: possui
LEITO||--|{INTERNACAO: possui
ITEM_PRESCRICAO}o--||PESCRICAO: possui
```

Medico(id PK) <- regra 1, virou uma relação/tabela
Consulta(id PK, id_medico FK, id_paciente FK) regra de 1:N tando do lado do médico como do paciente
Paciente(id PK) <- regra 1, virou uma relação/tabela
Prescricao(id PK, id_consulta FK) <- regra do 1:1, nesse caso como consulta tem participação total, prescrição vai receber a chave estrangeira que é a chave de consulta 
Quarto(id PK) <- regra 1, virou uma relação/tabela
Leito(id PK, id_quarto FK) <- regra do 1:N o lado N que é o leito vai receber a chave estrangeira do quarto
Medicamento(id PK) <- regra 1, virou uma relação/tabela
Internação(id PK, id_leito FK, id_paciente FK)
Prescricao_Medicamento(id FK,id_medicamento FK, id_Prescricao FK, dosagem, frequencia) <- essa tabela foi criada por conta da regra do N:M e coloquei dosage e a frequência aqui pois fazia sentido já que aqui é o 1 medicamento de 1 prescrição
