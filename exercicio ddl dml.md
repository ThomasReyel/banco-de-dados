## 1)

```sql
CREATE DATABASE db_banco
  CHARACTER SET utf8mb4
  COLLATE utf8mb4_unicode_ci;
```
O character set define quais serão os símbolos permitidos no banco, nesse caso estou permitindo todos os caracteres do utf8mb4. 
Já o Collate serve para determinar como o banco compara textos (WHERE, JOIN) e os ordena (ORDER BY).

## 2)

```sql
CREATE TABLE banco (
  codigo int PRIMARY KEY,
  nome CHAR
); 

CREATE TABLE cliente (
  cpf char PRIMARY KEY,
  nome CHAR,
  sexo CHAR,
 endereco CHAR
); 

CREATE TABLE agencia (
  numeroAgen int NOT NULL,
  endereco CHAR,
  cod_banco int NOT NULL,
  FOREIGN KEY (cod_banco) REFERENCES banco (codigo)
  ON UPDATE CASCADE
  ON DELETE RESTRICT,
  CONSTRAINT pk_agencia PRIMARY KEY (numeroAgen, cod_banco)
); 

CREATE TABLE conta (
  numero int NOT NULL,
  conta int NOT NULL,
  saldo FLOAT,
  tipo CHAR,
  cod_banco int NOT NULL,
  num_agencia int NOT NULL,
  FOREIGN KEY (cod_banco) REFERENCES banco (codigo),
  FOREIGN KEY (num_agencia) REFERENCES agencia (numeroAgen),
  CONSTRAINT pk_conta PRIMARY KEY (numero,conta)
); 

CREATE TABLE historico (
  cpf char NOT NULL,
  num_conta int NOT NULL,
  data_inicio DATE,
  FOREIGN KEY (cpf) REFERENCES cliente (cpf)
    ON DELETE RESTRICT,
  FOREIGN KEY (num_conta) REFERENCES conta (numero)
    ON UPDATE CASCADE
    ON DELETE RESTRICT,
  CONSTRAINT pk_historico PRIMARY KEY (cpf,num_conta)
); 


CREATE TABLE telefone (
  cpf CHAR NOT NULL,
  telefone CHAR NOT NULL,
  FOREIGN KEY (cpf) REFERENCES cliente (cpf)
  ON UPDATE CASCADE
  ON DELETE RESTRICT,
  CONSTRAINT pk_telefone PRIMARY KEY (cpf,telefone)
); 
```

## 3)

```sql
ALTER TABLE cliente
ADD Email varchar(255);

```
