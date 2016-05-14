# Cloudant

1. Edite a permissão anonima para leitura/escrita/admin

# Criando alguns documentos

POST https://d7a497fa-eec2-4ca7-809d-c8215a3c12cc-bluemix.cloudant.com/meubd

    {
    "class": "produto",
    "nome": "Tecido Florido Verao 2016",
    "tipo": "Tecido",
    "descricao": "Cool stuff",
    "unidade": "metro",
    "valorUnidade": 10,
    "codigoDeBarras": "3554436325667223"
    }
    

    {
    "class": "fornecedor"
    "cnpj": "010203",
    "nome": "china tecidos reciclaveis",
    "email": "?@?.com",
    "telefone": "000099932",
    "prazoEntregaDias": 100,
    "endereco_Pais": "China",
    "endereco_Estado": "-",
    "endereco_Cidade": "Beijing",
    "endereco_Logradouro": "???????? 42",
    "endereco_CEP": "08378472",
    "ativo": true
    }

Resposta: {"ok":true,"id":"7e0e6c9618b8535bc4649ea3c44771ba","rev":"1-366f71878c88e404738cc0ea3b7eec16"}

Acesse o documento

GET https://d7a497fa-eec2-4ca7-809d-c8215a3c12cc-bluemix.cloudant.com/meubd/7e0e6c9618b8535bc4649ea3c44771ba


# Criando Queries (Views) Listar todos os documentos

    "views": {
    "todos_fornecedores": {
      "map": "function (doc) 
                if(doc.class=="fornrcedor")  
                emit(doc._id, doc);
                }"
    },
    "todos_produtos": {
      "map": "function (doc) {
      if(doc.class=="produto\")
      emit(doc._id, doc);
      }"
      }
      
Acessando as Views 

https://d7a497fa-eec2-4ca7-809d-c8215a3c12cc-bluemix.cloudant.com/meubd/_design/q/_view/todos_produtos?limit=100&reduce=false

https://d7a497fa-eec2-4ca7-809d-c8215a3c12cc-bluemix.cloudant.com/meubd/_design/q/_view/todos_fornecedores?limit=100&reduce=false

#Listando um documento específico


# Lucene Queries

Index all Fields 

POST https://d7a497fa-eec2-4ca7-809d-c8215a3c12cc-bluemix.cloudant.com/meubd/_index

    {
     "type": "text",
     "index": {}
    }


SELECT nome, tipo, descricao FROM produto WHERE codigoDeBarras="3554436325667223"

POST  https://d7a497fa-eec2-4ca7-809d-c8215a3c12cc-bluemix.cloudant.com/meubd/_find


    {
    "selector": {
    "class": "produto",
    "codigoDeBarras": "3554436325667223"
    },
     "fields": [
        "nome", "tipo", "descricao"
    ]
    }
    
