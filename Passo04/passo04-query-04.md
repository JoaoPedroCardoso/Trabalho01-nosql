# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript


// 4 - Busca de todas as tasks com o usuario "Sophia"

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    task: "$tasks.title",
    user: "$tasks.user.first_name"
}
},
{
$match: {
     user: "Sophia"
    }
}])

// Resultado

[
  {
    "task": "Design Homepage",
    "user": "Sophia"
  },
  {
    "task": "Feature Specification",
    "user": "Sophia"
  },
  {
    "task": "Feature Planning",
    "user": "Sophia"
  },
  {
    "task": "Survey Design",
    "user": "Sophia"
  },
  {
    "task": "Feature Development",
    "user": "Sophia"
  },
  {
    "task": "App Testing",
    "user": "Sophia"
  },
  {
    "task": "App Development",
    "user": "Sophia"
  }
]


```








