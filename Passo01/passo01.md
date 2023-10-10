# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 01 - Mapeamento 
```json
{
   "name":"Pay4u",  							      // nome do projeto
   "start_date":"01/01/2023", 					//data de inicio do projeto
   "end_date":"01/12/2023",						//data fim do projeto
   "tasks":[									      //Lista de tasks vinculadas ao projeto
      {
         "title":"Implementar tela de login",	//titulo da task
         "description":"Desenvolver a tela de login do sistema pay4to", //descricao da task
         "start_date":"10/11/2023",				//data de inicio da task
         "deadline_date":"15/11/2023",			//data limite para terminar a task
         "dataFim":"",							   //data em que a task foi dada como done
         "priority":"Alta",						//prioridade da task
         "status":"Para fazer",					//status
         "user":{								      //usuario em que a task esta vinculada
            "first_name":"Joao Pedro", 		//primeiro nome
            "last_name":"Cardoso",				//segundo nome
            "email":"joaopedro@exemple.com",	//email
            "cell_phone":"34 991220033", 		//telefone celular
            "skill":"Desenvolvedor BE",		//skill do usuario
            "seniority":"Especialista"			//senioridade do usuario
         }
      }
   ]
}
```
