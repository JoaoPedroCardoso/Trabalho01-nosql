# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 02 - Validação de Dados 

```javascript

// validacao do shcema

db.createCollection("todolist", {
    validator: {
        $jsonSchema: {
            required: [
                "name",
                "start_date",
            ],
            properties: {
                _id: {
                    bsonType: "objectId"
                },
                name: {
                    bsonType: "string",
                    maxLength: 255,
                    description: "Nome do projeto deve ser preenchido e conter no maximo 255 caracteres."
                },
                start_date: {
                    bsonType: "date",
                    description: "Data de inicio do projeto deve ser preenchido com o formato date."
                },
                end_date: {
                   bsonType: "date",
                   description: "Data fim do projeto deve ser do formato date."
                },
                tasks: {
                  bsonType: [ "array" ],
                  items: {
                    bsonType: "object",
                    required: [
                        "title",
                        "deadline_date",
                        "priority",
                        "status"
                    ],
                    properties: {
                        title: {
                            bsonType: "string",
                            maxLength: 255,
                            description: "Titulo da task deve ser preenchido e conter ate 255 caracteres."
                        },
                        description: {
                            maxLength: 1000,
                            bsonType: "string",
                            description: "Descricao da task deve conter ate 1000 caracteres."
                        },
                        start_date: {
                          bsonType: "date",
                          description: "Data de inicio da task deve ser no formato date."
                        },
                        deadline_date: {
                          bsonType: "date",
                          description: "Data maxima para realizacao da task deve ser preenchida e no formato date."
                        },
                        dataFim: {
                          bsonType: "date",
                          description: "Data que a task foi finalizada deve ser no formato date."
                        },
                        priority: {
                          enum: [ "Alta", "Media", "Baixa", "Urgente" ],
                          description: "Prioridade da task deve ser preenchida com um dos valores [ `Alta`, `Media`, `Baixa`, `Urgente` ]"
                        },
                        status: {
                          enum: [ "Todo", "Doing", "Done", "Block" ],
                          description: "Status da task deve ser um dos valores [ `Todo`, `Doing`, `Done`, `Block`]"
                        },
                        user: {
                            bsonType: "object",
                            required: [
                                "first_name",
                                "last_name",
                                "email",
                                "cell_phone"
                            ],
                            properties: {
                                first_name: {
                                    bsonType: "string",
                                    maxLength: 55,
                                    description: "Primeiro nome do usuario deve ser preenchido e conter ate 55 caracteres."
                                },
                                last_name: {
                                    maxLength: 150,
                                    bsonType: "string",
                                    description: "Segundo nome do usuario deve ser preenchido e conter ate 150 caracteres."
                                },
                                email: {
                                  bsonType: "string",
                                  maxLength: 200,
                                  description: "Email do usuario deve ser preenchido e conter ate 200 caracteres."
                                }
                                ,
                                cell_phone: {
                                  bsonType: "string",
                                  maxLength: 32,
                                  description: "naturalness deve ser preenchido e conter ate ate 32 caracteres."
                                },
                                skill: {
                                  bsonType: "string",
                                  maxLength: 50,
                                  description: "Skill do usuario deve ser preenchida e conter ate 50 caracteres."
                                },
                                seniority: {
                                  bsonType: "string",
                                  maxLength: 30,
                                  description: "seniority deve ser preenchida e conter ate 30 caracteres."
                                }
                            }
                        }
                    }
                  }
                }
            }
        }
    }
})


// insercao base para criacao da tabela no banco:

db.todolist.insertOne(
{
   "name":"Pay4u",
   "start_date": ISODate("2023-01-01T00:00:00Z"),
   "end_date": ISODate("2023-12-01T00:00:00Z"),
   "tasks":[
      {
         "title":"Implementar tela de login",
         "description":"Desenvolver a tela de login do sistema pay4to",
         "start_date": ISODate("2023-11-10T00:00:00Z"),
         "deadline_date": ISODate("2023-11-15T00:00:00Z"),
         "priority":"Alta",
         "status":"Todo",
         "user":{
            "first_name":"Joao Pedro",
            "last_name":"Cardoso",
            "email":"joaopedro@exemple.com",
            "cell_phone":"34 991220033",
            "skill":"Desenvolvedor BE",
            "seniority":"Especialista"
         }
      }
   ]
}
);

//busca do dado:

db.todolist.find()

``
