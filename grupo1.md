## Nome dos Integrantes:
- Gabriella Nunes Miranda
- Juliana Matias Machado
- Katsumi Arackawa Junior

## 1. Insert com 3 Jasons:

POST: https://17d9d72b-8de6-4626-9f9f-4f79be099505-bluemix.cloudant.com/novodb/_all_docs

    {
      "_id": "00998c0108bf1461dd77907acb7e6ee4",
      "_rev": "1-6da6c6de2a8a53017fcaffb8ba16c535",
      "class": "sapato",
      "nome": "Bota Inverno 2016",
      "tipo": "bota",
      "descricao": "Calçados de inverno",
      "unidade": "1",
      "valorUnidade": 150,
      "codigoDeBarras": "456456456456"
    }

    {
      "_id": "a42f6ec229a08cc97e64c0c17682e587",
      "_rev": "1-969f0cf112ce39fc133439fa2edaff80",
      "class": "roupa",
      "nome": "Vestido florido Coleção Verão 2016",
      "tipo": "vestido",
      "descricao": "Roupas de verão",
      "unidade": "1",
      "valorUnidade": 50,
      "codigoDeBarras": "123123123123"
    }

    {
      "_id": "a42f6ec229a08cc97e64c0c1769f2bf8",
      "_rev": "1-e8b4917af56d8de685da5a8aa37d85c6",
      "class": "roupa",
      "nome": "Calça jeans Coleção Inverno 2016",
      "tipo": "vestido",
      "descricao": "Roupas de inverno",
      "unidade": "1",
      "valorUnidade": 79,
      "codigoDeBarras": "789789789789"
    }

## 2. Query com Reduce:

URL: https://17d9d72b-8de6-4626-9f9f-4f79be099505-bluemix.cloudant.com/novodb/_design/totaldevendas/_view/totalroupa?limit=20&reduce=true&group_level=0

    "total_roupas": {
        "map": "function (doc) {  
                    if(doc.class=="roupa")
                        emit(doc._id, doc.valorUnidade);
                }",
        "reduce": "_sum"
    }

## 3. Query com Lucene:

POST: https://17d9d72b-8de6-4626-9f9f-4f79be099505-bluemix.cloudant.com/novodb/_index

        {
            "type": "text",
            "index": {}
        }
        


URL: https://17d9d72b-8de6-4626-9f9f-4f79be099505-bluemix.cloudant.com/novodb/_find

        {
        "selector": {
            "class": "sapato",
            "codigoDeBarras": "456456456456"
        },
        "fields": [
                "nome", "tipo", "descricao"
                ]
        }



