Marcelo Rizzardo Lima

Diego Roso Da Silva

### 1. Requests to add sample data:

  POST: https://a52b0bbb-d32c-4423-8d9b-240e08d9cfe1-bluemix.cloudant.com/meudb
  
    {
        "userId": 1,
        "role": "admin",
        "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
        "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto",
        "salary": 10000
    }
    

    {
        "userId": 2,
        "role": "writer",
        "title": "qui est esse",
        "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla",
        "salary": 1000
    }
    
    
    {
        "userId": 3,
        "role": "writer",
        "title": "qui est esse",
        "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla",
        "salary": 100
    }
    
  
    {
        "userId": 4,
        "role": "reader",
        "title": "ea molestias quasi exercitationem repellat qui ipsa sit aut",
        "body": "et iusto sed quo iure\nvoluptatem occaecati omnis eligendi aut ad\nvoluptatem doloribus vel accusantium quis pariatur\nmolestiae porro eius odio et labore et velit aut",
        "salary": 10
    }
    
### 2. Query with map reduce to sum salaries:

GET: `https://a52b0bbb-d32c-4423-8d9b-240e08d9cfe1-bluemix.cloudant.com/grupo2/_design/roles/_view/list_writers?limit=20&reduce=false`

```
function (doc) {
  if(doc.role=="writer")  
    emit(doc._id, doc.salary);
}
```

### 3. Lucene Queries

#### 3.1. Lucene Query to index all data

    {
        "type": "text",
        "index": {}
    }
