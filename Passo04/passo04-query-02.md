# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript

// 2 - Busca de todos os projetos e taks que tem o dead_line a partir de janeiro de 2024

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    project: "$name",
    task: "$tasks.title",
    deadline_date: "$tasks.deadline_date"
}
},
{
$match: {
     deadline_date: {$gt: ISODate("2024-01-01T00:00:00Z")}
    }
}])

// Resultado:

[
  {
    "deadline_date": {"$date": "2024-01-15T00:00:00.000Z"},
    "project": "E-Learning Platform Development",
    "task": "Platform Development"
  },
  {
    "deadline_date": {"$date": "2024-01-10T00:00:00.000Z"},
    "project": "Travel App Launch",
    "task": "App Testing"
  },
  {
    "deadline_date": {"$date": "2024-01-15T00:00:00.000Z"},
    "project": "Delivery App Development",
    "task": "App Development"
  },
  {
    "deadline_date": {"$date": "2024-01-15T00:00:00.000Z"},
    "project": "Fitness App Development",
    "task": "App Development"
  }
]


```








