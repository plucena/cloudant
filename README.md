# cloudant

1. Edite a permissão para leitura/escrita

# Criando alguns documentos

POST https://d7a497fa-eec2-4ca7-809d-c8215a3c12cc-bluemix.cloudant.com/meubanco

    {
    "class": "produto",
    "nome": "Tecido Florido Verao 2016",
    "tipo": "Tecido",
    "descricao": "Cool stuff",
    "unidade": "metro",
    "valorUnidade": 10,
    "codigoDeBarras": "3554436325667223"
    }

Resposta: {"ok":true,"id":"7e0e6c9618b8535bc4649ea3c44771ba","rev":"1-366f71878c88e404738cc0ea3b7eec16"}

Acesse o documento

GET https://d7a497fa-eec2-4ca7-809d-c8215a3c12cc-bluemix.cloudant.com/meubanco/7e0e6c9618b8535bc4649ea3c44771ba

