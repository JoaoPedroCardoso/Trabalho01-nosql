# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript

// 15 - Todas as tasks que possuem todas as subtask done

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    task: "$tasks.title",
    subtasks: "$tasks.related_to"
}
},
{
$unwind: "$subtasks"
},
{
$project: {
    _id: false,
    subtask: "$subtasks.title",
    status: "$subtasks.status"
}
},
{
$match: {
    status: "Done"
}
}
])
//Resultado:

[
  {
    "status": "Done",
    "subtask": "Arquitecture Design"
  }
]


```








