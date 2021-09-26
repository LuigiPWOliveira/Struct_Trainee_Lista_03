Table professores as T{
  id int [pk, not null]
  nome varchar [not null]
  cpf varchar [not null, unique]
  rg varchar [not null, unique]
  idSexo int [not null, ref: > sexos.id]
  email varchar [not null]
  dataNascimento date [not null]
}

Table sexos{
  id int [pk]
  nome varchar [not null]
}

Table linguagens_professores as TL{
  id int [pk, not null]
  idProfessor int [ref: > T.id]
  idLinguagem int [ref: > PL.id]
}

Table linguagens_programacao as PL{
  id int [pk]
  linguagem varchar [not null]
}

ref: T.id < S.idProfessor

Table alunos as S{
  id int [pk, not null]
  idProfessor int [not null]
  nome varchar [not null]
  cpf varchar [not null, unique]
  rg varchar [not null, unique]
  dataNascimento date [not null]
  idEndereco int [not null, ref: > enderecos.id]
  idCidade int  [not null, ref: > cidades.id]
  idEstadoResidencia int [not null, ref: > estados.id]
}

Table cidades{
  id int [pk]
  nome varchar [not null]
}

Table estados{
  id int [pk]
  nome varchar [not null]
}

Table enderecos{
  id int [pk]
  nome varchar [not null]
}
