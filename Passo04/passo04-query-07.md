# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript



// 7 - Busca a quantidade de task e cada status em order decrescente

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$group: {
    _id: "$tasks.status",
    total_tasks: {$sum: 1}
}
}, {$sort: {total_tasks: -1}}])

//Resultado:

[
  {
    "_id": "Todo",
    "total_tasks": 28
  },
  {
    "_id": "Doing",
    "total_tasks": 22
  },
  {
    "_id": "Done",
    "total_tasks": 8
  },
  {
    "_id": "Block",
    "total_tasks": 2
  }
]


```








