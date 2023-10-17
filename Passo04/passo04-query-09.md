# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript



// 9 - Busca todas as task e seus usuarios responsaveis que a data limite ja estorou considerando o mes atual
db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    task: "$tasks.title",
    deadline_date: "$tasks.deadline_date",
    user: "$tasks.user.email"
}
},
{
$match: {
     deadline_date: {$lt: ISODate("2023-08-31T00:00:00Z")}
    }
}])

//Resultado:

[
  {
    "deadline_date": {"$date": "2023-03-15T00:00:00.000Z"},
    "task": "Database Design",
    "user": "maria@projectx.com"
  },
  {
    "deadline_date": {"$date": "2023-05-01T00:00:00.000Z"},
    "task": "Frontend Development",
    "user": "carlos@projectx.com"
  },
  {
    "deadline_date": {"$date": "2023-05-25T00:00:00.000Z"},
    "task": "User Authentication",
    "user": "luisa@taskapp.com"
  },
  {
    "deadline_date": {"$date": "2023-06-15T00:00:00.000Z"},
    "task": "Task List UI",
    "user": "rafael@taskapp.com"
  },
  {
    "deadline_date": {"$date": "2023-03-30T00:00:00.000Z"},
    "task": "Design Homepage",
    "user": "sophia@ecommerce.com"
  },
  {
    "deadline_date": {"$date": "2023-05-01T00:00:00.000Z"},
    "task": "Backend Development",
    "user": "daniel@ecommerce.com"
  },
  {
    "deadline_date": {"$date": "2023-06-20T00:00:00.000Z"},
    "task": "Campaign Strategy",
    "user": "megan@marketing.com"
  },
  {
    "deadline_date": {"$date": "2023-07-15T00:00:00.000Z"},
    "task": "Content Creation",
    "user": "liam@marketing.com"
  },
  {
    "deadline_date": {"$date": "2023-05-25T00:00:00.000Z"},
    "task": "Prototype Testing",
    "user": "olivia@productdev.com"
  },
  {
    "deadline_date": {"$date": "2023-06-15T00:00:00.000Z"},
    "task": "Manufacturing Setup",
    "user": "noah@productdev.com"
  },
  {
    "deadline_date": {"$date": "2023-05-30T00:00:00.000Z"},
    "task": "Wireframing",
    "user": "aiden@appdev.com"
  },
  {
    "deadline_date": {"$date": "2023-07-15T00:00:00.000Z"},
    "task": "Frontend Development",
    "user": "ella@appdev.com"
  },
  {
    "deadline_date": {"$date": "2023-07-20T00:00:00.000Z"},
    "task": "Content Calendar",
    "user": "mia@contentmarketing.com"
  },
  {
    "deadline_date": {"$date": "2023-08-15T00:00:00.000Z"},
    "task": "Content Creation",
    "user": "william@contentmarketing.com"
  },
  {
    "deadline_date": {"$date": "2023-06-20T00:00:00.000Z"},
    "task": "Feature Specification",
    "user": "sophia@accountingsoftware.com"
  },
  {
    "deadline_date": {"$date": "2023-08-15T00:00:00.000Z"},
    "task": "Software Development",
    "user": "daniel@accountingsoftware.com"
  },
  {
    "deadline_date": {"$date": "2023-08-20T00:00:00.000Z"},
    "task": "Product Design",
    "user": "aiden@electronicproduct.com"
  },
  {
    "deadline_date": {"$date": "2023-07-20T00:00:00.000Z"},
    "task": "Platform Architecture",
    "user": "liam@ecommerceplatform.com"
  },
  {
    "deadline_date": {"$date": "2023-08-15T00:00:00.000Z"},
    "task": "Frontend Development",
    "user": "ella@ecommerceplatform.com"
  },
  {
    "deadline_date": {"$date": "2023-08-20T00:00:00.000Z"},
    "task": "Curriculum Planning",
    "user": "ethan@educationapp.com"
  }
]

```








