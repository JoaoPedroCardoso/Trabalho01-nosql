# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

//Criacao de 15 querys

//================================================================================
//                                  QUERIES
//================================================================================




```javascript


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

//Resultado:

[
  {
    "_id": "Ava",
    "skills": ["Researcher", "Content Creator", "UI/UX Designer"]
  },
  {
    "_id": "Sophia",
    "skills": ["UI/UX Designer", "Business Analyst", "Product Manager", "Research Analyst", "App Developer", "Quality Assurance", "App Developer"]
  },
  {
    "_id": "Ethan",
    "skills": ["Business Analyst", "Curriculum Planner", "Content Creator", "App Developer", "Fitness Expert"]
  },
  {
    "_id": "William",
    "skills": ["Content Writer"]
  },
  {
    "_id": "Oliver",
    "skills": ["Market Researcher", "Product Developer", "Quality Assurance"]
  },
  {
    "_id": "Daniel",
    "skills": ["Backend Developer", "Software Developer", "App Developer", "Game Designer", "Quality Assurance"]
  },
  {
    "_id": "Mia",
    "skills": ["Content Manager", "Production Manager", "Game Developer"]
  },
  {
    "_id": "Aiden",
    "skills": ["UX Designer", "Marketing Specialist", "Product Designer"]
  },
  {
    "_id": "Ella",
    "skills": ["Frontend Developer", "Event Planner", "Frontend Developer", "App Developer", "Web Developer", "App Developer", "App Developer"]
  },
  {
    "_id": "Liam",
    "skills": ["Content Writer", "Content Strategist", "User Experience Analyst", "Technical Architect", "UI/UX Designer", "Content Strategist", "Platform Developer", "UI/UX Designer"]
  },
  {
    "_id": "Luisa",
    "skills": ["Backend Developer"]
  },
  {
    "_id": "Carlos",
    "skills": ["Frontend Developer"]
  },
  {
    "_id": "Rafael",
    "skills": ["UI Designer"]
  },
  {
    "_id": "James",
    "skills": ["Data Analyst", "Vendor Manager"]
  },
  {
    "_id": "Megan",
    "skills": ["Marketing Manager"]
  },
  {
    "_id": "Joao Pedro",
    "skills": ["Desenvolvedor BE"]
  },
  {
    "_id": "Olivia",
    "skills": ["Product Manager"]
  },
  {
    "_id": "Aria",
    "skills": ["Database Administrator", "Quality Assurance Specialist", "Data Analyst", "Production Manager", "App Developer"]
  },
  {
    "_id": "Maria",
    "skills": ["Database Architect"]
  },
  {
    "_id": "Noah",
    "skills": ["Manufacturing Specialist"]
  }
]


```








