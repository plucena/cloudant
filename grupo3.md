Grupo

Leandro Tubini Bezerra
Marcos Giovani do Prado
Rafael Alberto da Cruz
David Pullz
Fernando Assis de Souza
Victor Renato Guillardi Junior


Criar alguns documentos:
post https://f3e6ec85-a338-40cb-8f1f-a3046b1018b4-bluemix.cloudant.com/meubd/
{
 "class":"estoque",
 "cod_prod": "2sdfad",
 "cod_fabricante": 2234234,
 "total": 1000
}

{
 "class":"estoque",
 "cod_prod": "  2232",
 "cod_fabricante": 222,
 "total": 100
}

{
 "class":"estoque",
 "cod_prod": "  "4432",
 "cod_fabricante": 2344,
 "total": 134242
}

Criar Map/Reduce
{
   "_id" : "_design/totalestoque",
  "views": {
"totalestoque": {
  "map": "function (doc) {if(doc.class==\"estoque\") emit(doc._id, doc.total);}",
  "reduce": "_sum"
}
}
}

Visualizando 
https://f3e6ec85-a338-40cb-8f1f-a3046b1018b4-bluemix.cloudant.com/meubd/_design/totalestoque/_view/totalestoque?limit=20&reduce=false


Post https://f3e6ec85-a338-40cb-8f1f-a3046b1018b4-bluemix.cloudant.com/meubd/_index
{
 "type": "text",
 "index": {}
}

Post https://f3e6ec85-a338-40cb-8f1f-a3046b1018b4-bluemix.cloudant.com/meubd/_find
{
"selector": {
"class": "estoque",
  "cod_prod": "2sdfad"
},
 "fields": [
    "cod_fabricante", "total", "class"
]
}
