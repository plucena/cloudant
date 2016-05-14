
Evandro Pegorari
-----------------------------

URL do banco: https://4e0f134a-7fa9-4ef3-a4b6-96b3dc7e1630-bluemix.cloudant.com/meudb/
-----------------------------

JSONs
-----------------------------

{
 "class":"sensor",
 "serial": "000124",
 "unidade": "temperatura",
 "valor": 36
}

{
 "class":"sensor",
 "serial": "000121",
 "unidade": "temperatura",
 "valor": 38.6
}

{
 "class":"sensor",
 "serial": "000333",
 "unidade": "temperatura",
 "valor": 40
}

Resultado do post:
-----------------------------

{"ok":true,"id":"defd7fcd1ab0dddad7d2458b725b6306","rev":"1-a94c0dc9cabe484dd5ca78a333901a2d"}
{"ok":true,"id":"4375fbac73844826db929c01946cb3c8","rev":"1-6990e4825774b7b4b2aadab01028024e"}
{"ok":true,"id":"dd02e423ca83273b5f5f5c4927866f29","rev":"1-0f5f0bf746229a9df55f7970fbac8991"}

Query com reduce:
-----------------------------

{
  "_id": "_design/numero-sensores",
  "_rev": "1-b416bf951a3c94cd0ed5874c2252a116",
  "views": {
    "numero-sensores": {
      "reduce": "_count",
      "map": "function (doc) {\n  if(doc.class==\"sensor\")  \n    emit(doc._id, 1);\n}"
    }
  },
  "language": "javascript"
}


Query com lucene:
-- -----------------------------

{
	"selector": {
		"class": "sensor",
		"serial": "000121"
	},
	"fields": [
		"unidade", "valor"
	]
}
