# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript


// 14 - Todas as tasks que possuem subtasks e seus user da task e subtask

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    task: "$tasks.title",
    user_task: "$tasks.user.email",
    sub_task_user: "$tasks.related_to.user.email"
}
},
{
$match: {
    sub_task_user: { $exists: true }
}
}])

//Resultado:

[
  {
    "sub_task_user": ["daniel@ecommerce.com"],
    "task": "Backend Development",
    "user_task": "daniel@ecommerce.com"
  },
  {
    "sub_task_user": ["james@researchproject.com"],
    "task": "Data Collection",
    "user_task": "james@researchproject.com"
  },
  {
    "sub_task_user": ["maria@projectx.com"],
    "task": "Implementar tela de login",
    "user_task": "joaopedro@exemple.com"
  }
]


```








