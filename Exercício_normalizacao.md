## Questão 1
Funcionário(<ins>Matrícula</ins>, Nome, DataNasc,Nacionalidade,Sexo, EstCivil, RG, CIC, DataAdmissão)

Telefone(**idFunc**, <ins>telefone</ins>)

Endereço(**idFunc**,<ins>id</ins>, CEP, Rua, Bairro, cidade, numero)

CargoOcupado(**idFunc**, <ins>id</ins>, Cargo, DtInicio, DtFim)

Dependentes(**idFunc**,<ins>id</ins>, Nome, DtNascimento)

## Questão 2
Cliente(<ins>codigo</ins>, nome)

Telefone(**cod_cli**, <ins>id</ins>, telefone)

Endereço(<ins>id</ins>,**cod_cli**,rua, numero,cidade,estado,cep)

## Questão 3
Pedido(<ins>idPedido</ins>,Data,**codProduto**,qtde)

Produto(<ins>codProduto</ins>,**codCategoria**, nomeProduto, valorUnitário)

Categoria(<ins>codCategoria</ins>,NomeCategoria)

## Questão 4

Pacientes(<ins>numPaciente</ins>, Nome, DataNasc, sexo, RG, Est.Civil, Convênio)
Telefone(**numPaciente**, <ins>telefone</ins>)

Endereço(**numPaciente**,<ins>id</ins>, CEP, Rua, Bairro, cidade, numero)

Consultas(<ins>numConsulta</ins>,**numPaciente**, data, CRM, diganóstico)

Consulta_Exames(**numConsultas**,**numExames**)

Exames(<ins>numExames</ins>, exame, data)
