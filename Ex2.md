Table users as U{
  id int [pk]
  nome varchar [not null]
  email varchar [not null, unique]
  senha varchar [not null, unique]
  cpf varchar [not null,unique]
  numSeguidores int [ref: < U.id]
  idEndereco int [not null, ref: > adresses.id]
  interesses varchar [ref: < I.nome]
}

Table adresses{
  id int [pk]
  nome varchar [not null]
}

Table interests as I{
  nome varchar [unique]
}

Table Posts as P{
  id int [pk]
  descricao varchar
  pessoaMarcada varchar
}

Table marked_Posts{
  id int [pk]
  marcado int [ref: > U.id]
  marcacoes int [ref: > P.id] 
}
