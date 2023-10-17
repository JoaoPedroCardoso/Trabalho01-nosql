# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript

// 12 - Busca todos os usuario que possuem o email com @healthapp.com

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    name: "$tasks.user.first_name",
    last_name: "$tasks.user.last_name",
    email: "$tasks.user.email"
}
}, {
$match: {
    email: /@healthapp.com/
}
}])

//Resultado:


[
  {
    "email": "sophia@healthapp.com",
    "last_name": "Clark",
    "name": "Sophia"
  },
  {
    "email": "daniel@healthapp.com",
    "last_name": "Brown",
    "name": "Daniel"
  }
]

```








