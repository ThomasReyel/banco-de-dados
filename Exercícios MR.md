### Tabela de modelo relacional dos exercícios de modelo entidade-relacionamento da questão 4
- Veiculo(int id PK;string marca; string placa;string cor;date ano; float quilometragem; float locação;string categoria)
- Cliente(int id PK; string cnh;string nome;string endereço; string telefone; int idade)
- Aluguel(int id PK;int id_veiculo FK; int id_cliente FK; string veículo; datetime data)
- Tecnico(int id PK;string numero_cadastro; string cpf;string nome)
- Lista(int id PK; int id_cliente FK int qnt_veículos; float horas; float valor_total_aluguéis; int qnt_multas)
- Tecnico_veiculo(int id PK;int id_tecnico FK; int id_veiculo FK)

### Tabela de modelo relacional dos exercícios de modelo entidade-relacionamento da questão 5

- Cliente(int id PK; string cpf;string nome;string telefone;string endereço)
- Produto(int id PK;int id_fornecedor FK ;string nome; string tipo;string preço;string quantidade;float preço;int quantidade)
- Compra(int id PK;int id_cliente FK; int id_funcionario FK; string cliente; date data; float valor_total; string produtos)
- Funcionario(int id PK;string nome;string telefone;string endereço;float salário;string função;string cpf)
- Fornecedor(int id PK;string nome;string cnpj; string telefone;string endereço)
