# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript


// 6 - busca todo as task que foram finalizadas ate o fim de 2023
db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    project: "$name",
    task: "$tasks.title",
    data_fim: "$tasks.data_fim"
}
},
{
$match: {
     data_fim: {$lt: ISODate("2024-01-01T00:00:00Z")}
    }
}, {$sort: {data_fim: -1}}])


//Resultado


[
  {
    "data_fim": {"$date": "2023-11-05T00:00:00.000Z"},
    "project": "Product Launch",
    "task": "Product Testing"
  },
  {
    "data_fim": {"$date": "2023-10-20T00:00:00.000Z"},
    "project": "Social Media App Development",
    "task": "Platform Design"
  },
  {
    "data_fim": {"$date": "2023-10-15T00:00:00.000Z"},
    "project": "News Website Development",
    "task": "Content Strategy"
  },
  {
    "data_fim": {"$date": "2023-09-10T00:00:00.000Z"},
    "project": "Market Research",
    "task": "Research Objectives"
  },
  {
    "data_fim": {"$date": "2023-08-15T00:00:00.000Z"},
    "project": "Content Marketing Campaign",
    "task": "Content Creation"
  },
  {
    "data_fim": {"$date": "2023-07-15T00:00:00.000Z"},
    "project": "Content Marketing Campaign",
    "task": "Content Calendar"
  },
  {
    "data_fim": {"$date": "2023-06-15T00:00:00.000Z"},
    "project": "Accounting Software Development",
    "task": "Feature Specification"
  },
  {
    "data_fim": {"$date": "2023-05-15T00:00:00.000Z"},
    "project": "Product Development",
    "task": "Prototype Testing"
  }
]



```








