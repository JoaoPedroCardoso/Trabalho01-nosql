# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript



// 1 - Busca de todos os projetos que tem a data final ate o final de 2023

db.todolist.find({end_date: {$lt:ISODate("2023-12-31T00:00:00Z")}})

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

// 5 - Busca todas as tasks que estao done.

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    task: "$tasks.title",
    priority: "$tasks.priority",
    status: "$tasks.status"
}
},
{
$match: {
     status: "Done"
    }
}])

// 6 - busca todo as task que foram finalizadas ate o fim de 2023
db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$project: {
    _id: false,
    project: "$name",
    task: "$tasks.title",
    data_fim: "$tasks.data_fim"
}
},
{
$match: {
     data_fim: {$lt: ISODate("2024-01-01T00:00:00Z")}
    }
}, {$sort: {data_fim: -1}}])

// 7 - Busca a quantidade de task e cada status em order decrescente

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$group: {
    _id: "$tasks.status",
    total_tasks: {$sum: 1}
}
}, {$sort: {total_tasks: -1}}])

// 8 - Busca quais sao as skill que cada usuario possui

db.todolist.aggregate([
{
$unwind: "$tasks"
},
{
$group: {
    _id: "$tasks.user.first_name",
    skills: { $push: "$tasks.user.skill" }
}
}])

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



```








