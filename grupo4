# Nomes
Márcio Vinícius Barbosa
Felipe Bonzanini
Lucas Gouveia Bacelar
José Henrique Borges
Marcos Nogueira Bortoluci
Danilo da Silva Barbosa

# Insert

POST https://ff51ad8b-8cf3-40ed-a879-a679995a18af-bluemix.cloudant.com/meubd

    {
    "class": "carro",
    "nome": "Uno",
    "marca": "Fiat",
    "cor": "Preto",
    "chassi": "1"
    }
    

    {
    "class": "carro",
    "nome": "Palio",
    "marca": "Fiat",
    "cor": "Branco",
    "chassi": "2"
    }
	
	{
    "class": "carro",
    "nome": "Mobi",
    "marca": "Fiat",
    "cor": "Azul",
    "chassi": "3"
    }


# Reduce

"totalcarrospormarca": {
      "map": "function (doc) {  
            if(doc.class=="carro")
                emit(doc._id, doc.marca);
                }",
      "reduce": "_count"
    }


# Lucene 

    {
     "type": "text",
     "index": {}
    }

    {
    "selector": {
    "class": "carro",
    "chassi": "2"
    },
     "fields": [
        "nome", "marca", "cor"
    ]
    }
    
