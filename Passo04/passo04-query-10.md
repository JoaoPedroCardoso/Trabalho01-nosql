# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript


// 10 - Busca todas as tasks que possui alguma task relacionada a ela (subtask)

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    task: "$tasks.title",
    sub_task_title: "$tasks.related_to.title"
}
}, {
$match: {
    sub_task_title: { $exists: true }
}
}])

//Resultado:

[
  {
    "sub_task_title": ["Arquitecture Design"],
    "task": "Backend Development"
  },
  {
    "sub_task_title": ["Data Collection Definition"],
    "task": "Data Collection"
  },
  {
    "sub_task_title": ["Database Design"],
    "task": "Implementar tela de login"
  }
]

```








