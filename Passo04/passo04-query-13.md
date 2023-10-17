# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript



// 13 - Busca a quantidade de task por projeto

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$group: {
    _id: "$name",
    total_tasks: {$sum: 1}
}
}, {$sort: {total_tasks: -1}}])


//Resultado:

[
  {
    "_id": "Mobile App Development",
    "total_tasks": 2
  },
  {
    "_id": "Fitness App Development",
    "total_tasks": 2
  },
  {
    "_id": "Project X",
    "total_tasks": 2
  },
  {
    "_id": "Customer Support Redesign",
    "total_tasks": 2
  },
  {
    "_id": "Delivery App Development",
    "total_tasks": 2
  },
  {
    "_id": "Travel App Launch",
    "total_tasks": 2
  },
  {
    "_id": "E-commerce Website",
    "total_tasks": 2
  },
  {
    "_id": "Marketing Campaign",
    "total_tasks": 2
  },
  {
    "_id": "Task Management App",
    "total_tasks": 2
  },
  {
    "_id": "Social Media App Development",
    "total_tasks": 2
  },
  {
    "_id": "Game Development",
    "total_tasks": 2
  },
  {
    "_id": "Content Marketing Campaign",
    "total_tasks": 2
  },
  {
    "_id": "Education App Development",
    "total_tasks": 2
  },
  {
    "_id": "Content Management",
    "total_tasks": 2
  },
  {
    "_id": "E-Learning Platform Development",
    "total_tasks": 2
  },
  {
    "_id": "Mental Health App Development",
    "total_tasks": 2
  },
  {
    "_id": "News Website Development",
    "total_tasks": 2
  },
  {
    "_id": "Personal Finance App Development",
    "total_tasks": 2
  },
  {
    "_id": "Accounting Software Development",
    "total_tasks": 2
  },
  {
    "_id": "Research Project",
    "total_tasks": 2
  }
]



```








