Nomes: Andre Rogério Gonçalves
       Carlos Ito
       Cesar T. Tamaru
       Renato Dias

***************queries       
       {
"class": "funcionario",
"nome": "Joao Pedro",
"cargo": "Coveiro",
"matricula": "002",
"unidade": "Saudade",
"salario": 710.00,
"setor": "operacional"
}

{
"class": "funcionario",
"nome": "Joana Pedro",
"cargo": "Coveiro Senior",
"matricula": "005",
"unidade": "Saudade",
"salario": 1700.00,
"setor": "operacional"
}

{
"class": "funcionario",
"nome": "Benedito da Silva",
"cargo": "Gerente de Cemiterio",
"matricula": "001",
"unidade": "Saudade",
"salario": 7000.00,
"setor": "gerencia"
}

***************REDUCE
function (doc) {  
        if(doc.class=="funcionario")
            emit(doc._id, doc.cargo);
}


***************LUCENE
{
"selector": {
"class": "funcionario",
"matricula": "002"
},
 "fields": [
    "nome", "cargo", "setor"
]
}
       
       
       
