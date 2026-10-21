## Questão 1
Funcionário(<ins>Matrícula</ins>, Nome, DataNasc,Nacionalidade,Sexo, EstCivil, RG, CIC, DataAdmissão)

Telefone(**idFunc**, telefone)

Endereço(**idFunc**,id, CEP, Rua, Bairro, cidade, numero)

CargoOcupado(**idFunc**, id, Cargo, DtInicio, DtFim)

Dependentes(**idFunc**,<ins>id</ins>, Nome, DtNascimento)

## Questão 2
Cliente(codigo, nome)

Telefone(**cod_cli**, id, telefone)

Endereço(id,**cod_cli**,rua, numero,cidade,estado,cep)

## Questão 3
Pedido(idPedido,Data,**codProduto**,qtde)

Produto(codProduto,**codCategoria**, nomeProduto, valorUnitário)

Categoria(codCategoria,NomeCategoria)
