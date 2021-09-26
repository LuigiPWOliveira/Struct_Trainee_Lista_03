
Table players as P{
  id int [pk]
  name varchar [not null]
  dataNascimento date [not null]
  idSexo int [not null, ref: > sexes.id]
  idRegiao int [not null, ref: > regions.id]
}

Table sexes{
  id int [pk]
  name varchar [not null]
}

Table regions{
  id int [pk]
  nome varchar
}

Table playable_Games as GP{
  id int [pk]
  idJogadores int [ref: > P.id]
  idJogosJogados int [ref: > G.id]
}

Table games as G{
  id int [pk]
  tempoJogo float [not null]
  idPublisher int [not null, ref: > publishers.id]
  idDesenvolvedoras int [not null, ref: > developers.id]
  idPlataforma int [not null]
  idGenero int [not null, ref: > genres.id]
  idSoundtrack int [not null]
}

Table publishers{
  id int [pk]
  name varchar [not null]
  anoFundacao date [not null]
}

Table developers{
  id int [pk]
  name varchar [not null]
  anoFundacao date [not null]
}

Table playable_Plataforms{
  id int [pk]
  idJogo int [not null, ref: > G.idPlataforma]
  idPlataforma int [not null, ref: > plataforms.id]
}

Table plataforms{
  id int [pk]
  name varchar
}

Table genres{
  id int [pk]
  nome varchar [not null]
}

Table soundtracks{
  id int [pk]
  idJogos int [not null, ref: > G.idSoundtrack]
  idMusicas int [not null, ref: > songs.id]
}

Table composers{
  id int [pk]
  nome varchar [not null]
  dataNascimento date [not null]
  idSexo int [not null, ref: > sexes.id]
  idRegiao int [not null, ref: > regions.id]
}

Table songs{
  id int [pk]
  name varchar
  idCompositor int [not null, ref: > composers.id]
}
