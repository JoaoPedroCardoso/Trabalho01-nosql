# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript

// 11 - Busca todas as task que tem um usuario de senioridade Expert vinculado

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    task: "$tasks.title",
    user: "$tasks.user.email",
    seniority: "$tasks.user.seniority"
}
}, {
$match: {
    seniority: "Expert"
}
}])

//Resultado:

[
  {
    "seniority": "Expert",
    "task": "Database Design",
    "user": "maria@projectx.com"
  },
  {
    "seniority": "Expert",
    "task": "Design Homepage",
    "user": "sophia@ecommerce.com"
  },
  {
    "seniority": "Expert",
    "task": "Campaign Strategy",
    "user": "megan@marketing.com"
  },
  {
    "seniority": "Expert",
    "task": "Frontend Development",
    "user": "ella@appdev.com"
  },
  {
    "seniority": "Expert",
    "task": "Content Calendar",
    "user": "mia@contentmarketing.com"
  },
  {
    "seniority": "Expert",
    "task": "Requirements Gathering",
    "user": "ethan@inventorysystem.com"
  },
  {
    "seniority": "Expert",
    "task": "Venue Selection",
    "user": "ella@eventplanning.com"
  },
  {
    "seniority": "Expert",
    "task": "Marketing Strategy",
    "user": "aiden@productlaunch.com"
  },
  {
    "seniority": "Expert",
    "task": "Content Strategy",
    "user": "liam@contentmanagement.com"
  },
  {
    "seniority": "Expert",
    "task": "User Feedback Analysis",
    "user": "liam@customersupport.com"
  },
  {
    "seniority": "Expert",
    "task": "Feature Specification",
    "user": "sophia@accountingsoftware.com"
  },
  {
    "seniority": "Expert",
    "task": "Software Development",
    "user": "daniel@accountingsoftware.com"
  },
  {
    "seniority": "Expert",
    "task": "Product Design",
    "user": "aiden@electronicproduct.com"
  },
  {
    "seniority": "Expert",
    "task": "Platform Architecture",
    "user": "liam@ecommerceplatform.com"
  },
  {
    "seniority": "Expert",
    "task": "Frontend Development",
    "user": "ella@ecommerceplatform.com"
  },
  {
    "seniority": "Expert",
    "task": "Research Objectives",
    "user": "oliver@marketresearch.com"
  },
  {
    "seniority": "Expert",
    "task": "Feature Planning",
    "user": "sophia@healthapp.com"
  },
  {
    "seniority": "Expert",
    "task": "App Development",
    "user": "daniel@healthapp.com"
  },
  {
    "seniority": "Expert",
    "task": "Product Development",
    "user": "oliver@foodproduct.com"
  },
  {
    "seniority": "Expert",
    "task": "Platform Design",
    "user": "liam@socialmediaapp.com"
  }
]

```








