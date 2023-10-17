# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 01 - Mapeamento 
```json
{
   "name":"Pay4u", // nome do projeto
   "start_date":"2023-01-01T00:00:00Z",  //data de inicio do projeto
   "end_date":"2023-12-25T00:00:00Z", //data fim do projeto
   "tasks":[   //Lista de tasks vinculadas ao projeto
      {
         "title":"Implementar tela de login",   //titulo da task
         "description":"Desenvolver a tela de login do sistema pay4to", //descricao da task
         "start_date":"2023-11-10T00:00:00Z", //data de inicio da task
         "deadline_date":"2023-11-15T00:00:00Z", //data limite para terminar a task
         "data_fim":"", //data em que a task foi dada como done
         "priority":"Alta", //prioridade da task
         "status":"Todo", //status
         "user":{  //usuario em que a task esta vinculada
            "first_name":"Joao Pedro", //primeiro nome
            "last_name":"Cardoso", //segundo nome
            "email":"joaopedro@exemple.com", //email
            "cell_phone":"34 991220033",  //telefone celular
            "skill":"Desenvolvedor BE", //skill do usuario
            "seniority":"Especialista"  //senioridade do usuario
         },
         "related_to" [] // Lista de task vinculada a task atual (repete o mesmo objeto da tasks)
      }
   ]
}
```
