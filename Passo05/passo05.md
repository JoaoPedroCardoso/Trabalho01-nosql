# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 5: Operações de Update

```javascript

// Operacoes de update


// 1 - alterar o status da task para Done

db.todolist.find({'tasks.title': "Website Development"})
db.todolist.updateOne({tasks: {$elemMatch:{title: "Website Development"}}}, {$set: {'tasks.$.status': "Done"}})

//Resultado:
//trabalho01> db.todolist.updateOne({tasks: {$elemMatch:{title: "Website Development"}}}, {$set: {'tasks.$.status': "Done"}})
  //[2023-10-17 22:03:40] completed in 229 ms
[
  {
    "_id": {"$oid": "652efde41e361043f72684f1"},
    "end_date": {"$date": "2023-12-31T00:00:00.000Z"},
    "name": "News Website Development",
    "start_date": {"$date": "2023-10-01T00:00:00.000Z"},
    "tasks": [
      {
        "title": "Content Strategy",
        "description": "Develop a content strategy for the news website",
        "start_date": {"$date": "2023-10-10T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-10-20T00:00:00.000Z"},
        "data_fim": {"$date": "2023-10-15T00:00:00.000Z"},
        "priority": "Alta",
        "status": "Done",
        "user": {
          "first_name": "Liam",
          "last_name": "Johnson",
          "email": "liam@newswebsite.com",
          "cell_phone": "123-456-7890",
          "skill": "Content Strategist",
          "seniority": "Expert"
        }
      },
      {
        "title": "Website Development",
        "description": "Design and develop the news website",
        "start_date": {"$date": "2023-10-25T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-11-10T00:00:00.000Z"},
        "priority": "Alta",
        "status": "Done",
        "user": {
          "first_name": "Ella",
          "last_name": "Smith",
          "email": "ella@newswebsite.com",
          "cell_phone": "123-789-4560",
          "skill": "Web Developer",
          "seniority": "Expert"
        }
      }
    ]
  }
]


// 2 - alterar o end_date do projeto adicionando mais tempo

db.todolist.find({name: "Research Project"})
db.todolist.updateOne({name: "Research Project"}, {$set: {end_date: ISODate("2024-10-10T00:00:00Z")}})

// Resultado:
//trabalho01> db.todolist.updateOne({name: "Research Project"}, {$set: {end_date: ISODate("2024-10-10T00:00:00Z")}})
//[2023-10-17 21:54:22] completed in 223 ms
[
  {
    "_id": {"$oid": "652efde41e361043f72684e2"},
    "end_date": {"$date": "2024-10-10T00:00:00.000Z"},
    "name": "Research Project",
    "start_date": {"$date": "2023-08-15T00:00:00.000Z"},
    "tasks": [
      {
        "title": "Literature Review",
        "description": "Conduct a review of existing literature in the field",
        "start_date": {"$date": "2023-08-30T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-09-15T00:00:00.000Z"},
        "priority": "Alta",
        "status": "Block",
        "user": {
          "first_name": "Ava",
          "last_name": "Wilson",
          "email": "ava@researchproject.com",
          "cell_phone": "555-111-2222",
          "skill": "Researcher",
          "seniority": "Senior"
        }
      },
      {
        "title": "Data Collection",
        "description": "Gather and analyze research data",
        "start_date": {"$date": "2023-09-20T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-10-15T00:00:00.000Z"},
        "priority": "Media",
        "status": "Todo",
        "user": {
          "first_name": "James",
          "last_name": "Anderson",
          "email": "james@researchproject.com",
          "cell_phone": "555-333-4444",
          "skill": "Data Analyst",
          "seniority": "Intermediate"
        },
        "related_to": [
          {
            "title": "Data Collection Definition",
            "description": "Define all data that should be analyzed",
            "start_date": {"$date": "2023-03-01T00:00:00.000Z"},
            "deadline_date": {"$date": "2023-04-05T00:00:00.000Z"},
            "priority": "Alta",
            "status": "Doing",
            "user": {
              "first_name": "James",
              "last_name": "Anderson",
              "email": "james@researchproject.com",
              "cell_phone": "555-333-4444",
              "skill": "Data Analyst",
              "seniority": "Intermediate"
            }
          }
        ]
      }
    ]
  }
]

// 3 - Alterar o prioridade da task para Urgente
db.todolist.find({'tasks.title': "Task List UI"})
db.todolist.updateOne({tasks: {$elemMatch:{title: "Task List UI"}}}, {$set: {'tasks.$.priority': "Urgente"}})

//Resultado:
//trabalho01> db.todolist.updateOne({tasks: {$elemMatch:{title: "Task List UI"}}}, {$set: {'tasks.$.priority': "Urgente"}})
  //[2023-10-17 22:06:36] completed in 174 ms

[
  {
    "_id": {"$oid": "652efde41e361043f72684dc"},
    "end_date": {"$date": "2023-11-30T00:00:00.000Z"},
    "name": "Task Management App",
    "start_date": {"$date": "2023-04-15T00:00:00.000Z"},
    "tasks": [
      {
        "title": "User Authentication",
        "description": "Implement user authentication for the app",
        "start_date": {"$date": "2023-05-10T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-05-25T00:00:00.000Z"},
        "priority": "Media",
        "status": "Doing",
        "user": {
          "first_name": "Luisa",
          "last_name": "Martinez",
          "email": "luisa@taskapp.com",
          "cell_phone": "44 987123456",
          "skill": "Backend Developer",
          "seniority": "Senior"
        }
      },
      {
        "title": "Task List UI",
        "description": "Design the user interface for the task list",
        "start_date": {"$date": "2023-06-01T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-06-15T00:00:00.000Z"},
        "priority": "Urgente",
        "status": "Todo",
        "user": {
          "first_name": "Rafael",
          "last_name": "Gomez",
          "email": "rafael@taskapp.com",
          "cell_phone": "44 789123456",
          "skill": "UI Designer",
          "seniority": "Intermediate"
        }
      }
    ]
  }
]

// 4 - Alterar o user da task

db.todolist.find({'tasks.title': "Product Development"})
db.todolist.updateOne({tasks: {$elemMatch:{title: "Product Development"}}}, {$set: {'tasks.$.user': {
          "first_name": "Rafael",
          "last_name": "Gomez",
          "email": "rafael@taskapp.com",
          "cell_phone": "44 789123456",
          "skill": "UI Designer",
          "seniority": "Intermediate"
        }}})

//Resultado:
//trabalho01> db.todolist.updateOne({tasks: {$elemMatch:{title: "Product Development"}}}, {$set: {'tasks.$.user': {
  //                      "first_name": "Rafael",
  //                      "last_name": "Gomez",
  //                      "email": "rafael@taskapp.com",
  //                      "cell_phone": "44 789123456",
  //                      "skill": "UI Designer",
  //                      "seniority": "Intermediate"
  //                    }}})
  //[2023-10-17 22:08:54] completed in 213 ms

[
  {
    "_id": {"$oid": "652efde41e361043f72684ed"},
    "end_date": {"$date": "2023-12-31T00:00:00.000Z"},
    "name": "Food Product Launch",
    "start_date": {"$date": "2023-11-01T00:00:00.000Z"},
    "tasks": [
      {
        "title": "Product Development",
        "description": "Develop a new food product and create recipes",
        "start_date": {"$date": "2023-11-10T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-11-20T00:00:00.000Z"},
        "priority": "Alta",
        "status": "Doing",
        "user": {
          "first_name": "Rafael",
          "last_name": "Gomez",
          "email": "rafael@taskapp.com",
          "cell_phone": "44 789123456",
          "skill": "UI Designer",
          "seniority": "Intermediate"
        }
      },
      {
        "title": "Production Setup",
        "description": "Set up the production process for the food product",
        "start_date": {"$date": "2023-11-25T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-12-10T00:00:00.000Z"},
        "priority": "Media",
        "status": "Todo",
        "user": {
          "first_name": "Aria",
          "last_name": "Smith",
          "email": "aria@foodproduct.com",
          "cell_phone": "555-333-4444",
          "skill": "Production Manager",
          "seniority": "Intermediate"
        }
      }
    ]
  }
]

// 5 -  alterar a o related_to adicionando uma task

db.todolist.find({'tasks.title': "Product Development"})
db.todolist.updateOne({tasks: {$elemMatch:{title: "Product Development"}}}, {$set: {'tasks.$.related_to': [{
            "title": "Feature Development",
            "description": "Develop new features for the personal finance app",
            "start_date":  ISODate("2023-10-10T00:00:00Z"),
            "deadline_date": ISODate("2023-10-20T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Ethan",
                "last_name": "Taylor",
                "email": "ethan@financeapp.com",
                "cell_phone": "555-777-8888",
                "skill": "App Developer",
                "seniority": "Expert"
            }
        }]}})

//Resultado:
//trabalho01> db.todolist.updateOne({tasks: {$elemMatch:{title: "Product Development"}}}, {$set: {'tasks.$.related_to': [{
  //                        "title": "Feature Development",
  //                        "description": "Develop new features for the personal finance app",
  //                        "start_date":  ISODate("2023-10-10T00:00:00Z"),
  //                        "deadline_date": ISODate("2023-10-20T00:00:00Z"),
  //                        "priority": "Alta",
  //                        "status": "Doing",
  //                        "user": {
  //                            "first_name": "Ethan",
  //                            "last_name": "Taylor",
  //                            "email": "ethan@financeapp.com",
  //                            "cell_phone": "555-777-8888",
  //                            "skill": "App Developer",
  //                            "seniority": "Expert"
  //                        }
  //                    }]}})
  //[2023-10-17 22:11:24] completed in 222 ms
[
  {
    "_id": {"$oid": "652efde41e361043f72684ed"},
    "end_date": {"$date": "2023-12-31T00:00:00.000Z"},
    "name": "Food Product Launch",
    "start_date": {"$date": "2023-11-01T00:00:00.000Z"},
    "tasks": [
      {
        "title": "Product Development",
        "description": "Develop a new food product and create recipes",
        "start_date": {"$date": "2023-11-10T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-11-20T00:00:00.000Z"},
        "priority": "Alta",
        "status": "Doing",
        "user": {
          "first_name": "Rafael",
          "last_name": "Gomez",
          "email": "rafael@taskapp.com",
          "cell_phone": "44 789123456",
          "skill": "UI Designer",
          "seniority": "Intermediate"
        },
        "related_to": [
          {
            "title": "Feature Development",
            "description": "Develop new features for the personal finance app",
            "start_date": {"$date": "2023-10-10T00:00:00.000Z"},
            "deadline_date": {"$date": "2023-10-20T00:00:00.000Z"},
            "priority": "Alta",
            "status": "Doing",
            "user": {
              "first_name": "Ethan",
              "last_name": "Taylor",
              "email": "ethan@financeapp.com",
              "cell_phone": "555-777-8888",
              "skill": "App Developer",
              "seniority": "Expert"
            }
          }
        ]
      },
      {
        "title": "Production Setup",
        "description": "Set up the production process for the food product",
        "start_date": {"$date": "2023-11-25T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-12-10T00:00:00.000Z"},
        "priority": "Media",
        "status": "Todo",
        "user": {
          "first_name": "Aria",
          "last_name": "Smith",
          "email": "aria@foodproduct.com",
          "cell_phone": "555-333-4444",
          "skill": "Production Manager",
          "seniority": "Intermediate"
        }
      }
    ]
  }
]

``
