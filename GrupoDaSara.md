// Sara Fabiane Cocco
// Adriano de Souza
// Bruno Serva
// Edson Lana
// Thiago Cardeal
// Egon Agostin
// Julio Cesar Campos

// JSON
{
  "_id": "b97f3cc78a85ea5a7c2ef8f08d8c64a9",
  "_rev": "1-4d577ce3df80f3a260a68e531fac59a3",
  "class": "aluno",
  "cod_turma": "BI24",
  "cod_aluno": 3,
  "nota": 8
}

{
  "_id": "8102853be2c435dad4835690e11bf104",
  "_rev": "3-9cf2589a1b54618d9bb0f871f7da70f8",
  "class": "aluno",
  "cod_turma": "BI24",
  "cod_aluno": 1,
  "nota": 10
}

{
  "_id": "785bc69b886599dec9d64edf61f0f488",
  "_rev": "1-91d92b3266b25d407f56b5e5d1b0a622",
  "class": "aluno",
  "cod_turma": "BI24",
  "cod_aluno": 2,
  "nota": 9
}

// Query
"alunos": {
  "map": "function (doc) {
    if (doc.cod_turma == "BI24")
    emit(doc._id, doc.nota);
    }",
  "reduce": "_sum"
}

// Lucene
{
"selector": {
"class": "aluno",
"cod_turma": "BI24"
},
 "fields": [
    "class","cod_turma","cod_aluno","nota"
]
}


