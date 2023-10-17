# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript


// 3 - busca todas os projetos e tasks com prioridade urgente

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    project: "$name",
    task: "$tasks.title",
    priority: "$tasks.priority"
}
},
{
$match: {
     priority: "Urgente"
    }
}])

//Resultado:

[
  {
    "priority": "Urgente",
    "project": "Electronic Product Launch",
    "task": "Product Design"
  },
  {
    "priority": "Urgente",
    "project": "Social Media App Development",
    "task": "Platform Design"
  },
  {
    "priority": "Urgente",
    "project": "Game Development",
    "task": "Game Concept"
  },
  {
    "priority": "Urgente",
    "project": "Travel App Launch",
    "task": "App Testing"
  },
  {
    "priority": "Urgente",
    "project": "Fitness App Development",
    "task": "App Development"
  }
]



```








