#Integrante
Nome: Adriano Daronco
RE: 139.523.528-70
id: ahdaronc

#Criando Documentos
https://04b1e599-9b5a-44f9-8e97-b9ce159f9c03-bluemix.cloudant.com/meudb/4375fbac73844826db929c0194878f04
{
"class": "produto",
"nome": "Tecido BRANCO Verao 2016",
"tipo": "Tecido",
"descricao": "Cool stuff",
"unidade": "metro",
"valorUnidade": 12,
"codigoDeBarras": "3554436325667223"
}

https://04b1e599-9b5a-44f9-8e97-b9ce159f9c03-bluemix.cloudant.com/meudb/dd02e423ca83273b5f5f5c4927a1c66b
{
"class": "produto",
"nome": "Tecido AZUL Verao 2016",
"tipo": "Tecido",
"descricao": "Cool stuff",
"unidade": "metro",
"valorUnidade": 15,
"codigoDeBarras": "3554436325447223"
}

https://04b1e599-9b5a-44f9-8e97-b9ce159f9c03-bluemix.cloudant.com/meudb/d58d5bc793bc6b29a42d1f6f3d7694ed
{
"class": "fornecedor"
"cnpj": "040406",
"nome": "Americana tecidos",
"email": "?@?.com",
"telefone": "000099932",
"prazoEntregaDias": 100,
"endereco_Pais": "Brasil",
"endereco_Estado": "-",
"endereco_Cidade": "Americana",
"endereco_Logradouro": "Rua da Boiada 666",
"endereco_CEP": "123456789",
"ativo": true
}

#Criando Views
function (doc) {
   if(doc.codigoDeBarras && doc.class=="produto" && doc.nome=="Tecido BRANCO Verao 2016")   
   result= "Tipo: " + doc.tipo + " - Descr: " + doc.descricao;
   emit(doc.codigoDeBarras, result);
}

#Lucine Query
Post Lucine Query:
https://04b1e599-9b5a-44f9-8e97-b9ce159f9c03-bluemix.cloudant.com/meudb/_find

Query:
{
"selector": {
"class": "fornecedor",
"nome": "Americana tecidos"
},
 "fields": [
    "nome", "class", "ativo"
]
}

Result Lucine Query:
{"docs":[
{"nome":"Americana tecidos","class":"fornecedor","ativo":true}
],
"bookmark": "g2wAAAABaANkAChkYmNvcmVAZGIyLmJtLWRhbC1zdGFuZGFyZDIuY2xvdWRhbnQubmV0bAAAAAJuBAAAAADAbgQA____32poAkY__81TAAAAAGECag"}

