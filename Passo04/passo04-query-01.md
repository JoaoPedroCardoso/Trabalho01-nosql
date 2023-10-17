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


// Resultado:

[
  {
    "_id": {"$oid": "652efde41e361043f72684db"},
    "end_date": {"$date": "2023-10-30T00:00:00.000Z"},
    "name": "Project X",
    "start_date": {"$date": "2023-02-15T00:00:00.000Z"},
    "tasks": [
      {
        "title": "Database Design",
        "description": "Create the database schema for Project X",
        "start_date": {"$date": "2023-03-01T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-03-15T00:00:00.000Z"},
        "priority": "Alta",
        "status": "Doing",
        "user": {
          "first_name": "Maria",
          "last_name": "Silva",
          "email": "maria@projectx.com",
          "cell_phone": "55 123456789",
          "skill": "Database Architect",
          "seniority": "Expert"
        }
      },
      {
        "title": "Frontend Development",
        "description": "Create the user interface for Project X",
        "start_date": {"$date": "2023-04-01T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-05-01T00:00:00.000Z"},
        "priority": "Media",
        "status": "Todo",
        "user": {
          "first_name": "Carlos",
          "last_name": "Gonzalez",
          "email": "carlos@projectx.com",
          "cell_phone": "55 987654321",
          "skill": "Frontend Developer",
          "seniority": "Intermediate"
        }
      }
    ]
  },
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
        "priority": "Baixa",
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
  },
  {
    "_id": {"$oid": "652efde41e361043f72684de"},
    "end_date": {"$date": "2023-08-31T00:00:00.000Z"},
    "name": "Marketing Campaign",
    "start_date": {"$date": "2023-06-01T00:00:00.000Z"},
    "tasks": [
      {
        "title": "Campaign Strategy",
        "description": "Plan the marketing campaign strategy",
        "start_date": {"$date": "2023-06-10T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-06-20T00:00:00.000Z"},
        "priority": "Alta",
        "status": "Doing",
        "user": {
          "first_name": "Megan",
          "last_name": "Davis",
          "email": "megan@marketing.com",
          "cell_phone": "123-456-7890",
          "skill": "Marketing Manager",
          "seniority": "Expert"
        }
      },
      {
        "title": "Content Creation",
        "description": "Create engaging content for the campaign",
        "start_date": {"$date": "2023-07-01T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-07-15T00:00:00.000Z"},
        "priority": "Media",
        "status": "Todo",
        "user": {
          "first_name": "Liam",
          "last_name": "Johnson",
          "email": "liam@marketing.com",
          "cell_phone": "123-789-4560",
          "skill": "Content Writer",
          "seniority": "Intermediate"
        }
      }
    ]
  },
  {
    "_id": {"$oid": "652efde41e361043f72684df"},
    "end_date": {"$date": "2023-11-30T00:00:00.000Z"},
    "name": "Product Development",
    "start_date": {"$date": "2023-04-15T00:00:00.000Z"},
    "tasks": [
      {
        "title": "Prototype Testing",
        "description": "Test the product prototype with user feedback",
        "start_date": {"$date": "2023-05-10T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-05-25T00:00:00.000Z"},
        "data_fim": {"$date": "2023-05-15T00:00:00.000Z"},
        "priority": "Media",
        "status": "Done",
        "user": {
          "first_name": "Olivia",
          "last_name": "Martinez",
          "email": "olivia@productdev.com",
          "cell_phone": "111-222-3333",
          "skill": "Product Manager",
          "seniority": "Senior"
        }
      },
      {
        "title": "Manufacturing Setup",
        "description": "Prepare the manufacturing process for the product",
        "start_date": {"$date": "2023-06-01T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-06-15T00:00:00.000Z"},
        "priority": "Baixa",
        "status": "Todo",
        "user": {
          "first_name": "Noah",
          "last_name": "Garcia",
          "email": "noah@productdev.com",
          "cell_phone": "111-333-4444",
          "skill": "Manufacturing Specialist",
          "seniority": "Intermediate"
        }
      }
    ]
  },
  {
    "_id": {"$oid": "652efde41e361043f72684e1"},
    "end_date": {"$date": "2023-09-30T00:00:00.000Z"},
    "name": "Content Marketing Campaign",
    "start_date": {"$date": "2023-07-01T00:00:00.000Z"},
    "tasks": [
      {
        "title": "Content Calendar",
        "description": "Create a content calendar for the campaign",
        "start_date": {"$date": "2023-07-10T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-07-20T00:00:00.000Z"},
        "data_fim": {"$date": "2023-07-15T00:00:00.000Z"},
        "priority": "Media",
        "status": "Done",
        "user": {
          "first_name": "Mia",
          "last_name": "Johnson",
          "email": "mia@contentmarketing.com",
          "cell_phone": "123-456-7890",
          "skill": "Content Manager",
          "seniority": "Expert"
        }
      },
      {
        "title": "Content Creation",
        "description": "Write blog posts and social media content",
        "start_date": {"$date": "2023-08-01T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-08-15T00:00:00.000Z"},
        "data_fim": {"$date": "2023-08-15T00:00:00.000Z"},
        "priority": "Baixa",
        "status": "Done",
        "user": {
          "first_name": "William",
          "last_name": "Miller",
          "email": "william@contentmarketing.com",
          "cell_phone": "123-789-4560",
          "skill": "Content Writer",
          "seniority": "Intermediate"
        }
      }
    ]
  },
  {
    "_id": {"$oid": "652efde41e361043f72684e2"},
    "end_date": {"$date": "2023-11-30T00:00:00.000Z"},
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
  },
  {
    "_id": {"$oid": "652efde41e361043f72684e6"},
    "end_date": {"$date": "2023-12-15T00:00:00.000Z"},
    "name": "Content Management",
    "start_date": {"$date": "2023-11-01T00:00:00.000Z"},
    "tasks": [
      {
        "title": "Content Strategy",
        "description": "Develop a content strategy for the platform",
        "start_date": {"$date": "2023-11-10T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-11-20T00:00:00.000Z"},
        "priority": "Alta",
        "status": "Doing",
        "user": {
          "first_name": "Liam",
          "last_name": "Smith",
          "email": "liam@contentmanagement.com",
          "cell_phone": "555-111-2222",
          "skill": "Content Strategist",
          "seniority": "Expert"
        }
      },
      {
        "title": "Content Creation",
        "description": "Produce and publish Alta-quality content",
        "start_date": {"$date": "2023-11-25T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-12-10T00:00:00.000Z"},
        "priority": "Media",
        "status": "Todo",
        "user": {
          "first_name": "Ava",
          "last_name": "Johnson",
          "email": "ava@contentmanagement.com",
          "cell_phone": "555-222-3333",
          "skill": "Content Creator",
          "seniority": "Intermediate"
        }
      }
    ]
  },
  {
    "_id": {"$oid": "652efde41e361043f72684eb"},
    "end_date": {"$date": "2023-11-30T00:00:00.000Z"},
    "name": "Market Research",
    "start_date": {"$date": "2023-08-15T00:00:00.000Z"},
    "tasks": [
      {
        "title": "Research Objectives",
        "description": "Define the objectives and scope of the market research",
        "start_date": {"$date": "2023-08-30T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-09-15T00:00:00.000Z"},
        "data_fim": {"$date": "2023-09-10T00:00:00.000Z"},
        "priority": "Alta",
        "status": "Done",
        "user": {
          "first_name": "Oliver",
          "last_name": "Martinez",
          "email": "oliver@marketresearch.com",
          "cell_phone": "555-111-2222",
          "skill": "Market Researcher",
          "seniority": "Expert"
        }
      },
      {
        "title": "Data Collection",
        "description": "Collect and analyze market data and trends",
        "start_date": {"$date": "2023-09-20T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-10-15T00:00:00.000Z"},
        "priority": "Media",
        "status": "Todo",
        "user": {
          "first_name": "Aria",
          "last_name": "Johnson",
          "email": "aria@marketresearch.com",
          "cell_phone": "555-333-4444",
          "skill": "Data Analyst",
          "seniority": "Intermediate"
        }
      }
    ]
  },
  {
    "_id": {"$oid": "652eff531e361043f72684fa"},
    "end_date": {"$date": "2023-12-01T00:00:00.000Z"},
    "name": "Pay4u",
    "start_date": {"$date": "2023-01-01T00:00:00.000Z"},
    "tasks": [
      {
        "title": "Implementar tela de login",
        "description": "Desenvolver a tela de login do sistema pay4to",
        "start_date": {"$date": "2023-11-10T00:00:00.000Z"},
        "deadline_date": {"$date": "2023-11-15T00:00:00.000Z"},
        "priority": "Alta",
        "status": "Todo",
        "user": {
          "first_name": "Joao Pedro",
          "last_name": "Cardoso",
          "email": "joaopedro@exemple.com",
          "cell_phone": "34 991220033",
          "skill": "Desenvolvedor BE",
          "seniority": "Especialista"
        },
        "related_to": [
          {
            "title": "Database Design",
            "description": "Create the database schema for Project X",
            "start_date": {"$date": "2023-03-01T00:00:00.000Z"},
            "deadline_date": {"$date": "2023-03-15T00:00:00.000Z"},
            "priority": "Alta",
            "status": "Doing",
            "user": {
              "first_name": "Maria",
              "last_name": "Silva",
              "email": "maria@projectx.com",
              "cell_phone": "55 123456789",
              "skill": "Database Architect",
              "seniority": "Expert"
            }
          }
        ]
      }
    ]
  }
]



```








