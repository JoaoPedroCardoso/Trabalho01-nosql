# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 6: Indexação e Otimização

```javascript


// Criando index para busca de tasks pelo status:
//antes do index:
db.todolist.find({'tasks.status': "Done"}).explain("executionStats")
[
  {
    "command": {
      "find": "todolist",
      "filter": {
        "tasks.status": "Done"
      },
      "$db": "trabalho01"
    },
    "executionStats": {
      "executionSuccess": true,
      "nReturned": 7,
      "executionTimeMillis": 36,
      "totalKeysExamined": 0,
      "totalDocsExamined": 31,
      "executionStages": {
        "stage": "COLLSCAN",
        "filter": {
          "tasks.status": {
            "$eq": "Done"
          }
        },
        "nReturned": 7,
        "executionTimeMillisEstimate": 0,
        "works": 33,
        "advanced": 7,
        "needTime": 25,
        "needYield": 0,
        "saveState": 0,
        "restoreState": 0,
        "isEOF": 1,
        "direction": "forward",
        "docsExamined": 31
      }
    },
    "explainVersion": "1",
    "ok": 1,
    "queryPlanner": {
      "namespace": "trabalho01.todolist",
      "indexFilterSet": false,
      "parsedQuery": {
        "tasks.status": {
          "$eq": "Done"
        }
      },
      "queryHash": "78B5AD89",
      "planCacheKey": "78B5AD89",
      "maxIndexedOrSolutionsReached": false,
      "maxIndexedAndSolutionsReached": false,
      "maxScansToExplodeReached": false,
      "winningPlan": {
        "stage": "COLLSCAN",
        "filter": {
          "tasks.status": {
            "$eq": "Done"
          }
        },
        "direction": "forward"
      },
      "rejectedPlans": []
    },
    "serverInfo": {
      "host": "joaopmac.local",
      "port": 27017,
      "version": "6.0.6",
      "gitVersion": "26b4851a412cc8b9b4a18cdb6cd0f9f642e06aa7"
    },
    "serverParameters": {
      "internalQueryFacetBufferSizeBytes": 104857600,
      "internalQueryFacetMaxOutputDocSizeBytes": 104857600,
      "internalLookupStageIntermediateDocumentMaxSizeBytes": 104857600,
      "internalDocumentSourceGroupMaxMemoryBytes": 104857600,
      "internalQueryMaxBlockingSortMemoryUsageBytes": 104857600,
      "internalQueryProhibitBlockingMergeOnMongoS": 0,
      "internalQueryMaxAddToSetBytes": 104857600,
      "internalDocumentSourceSetWindowFieldsMaxMemoryBytes": 104857600
    }
  }
]
//Criacao do index:
db.todolist.createIndex({"tasks.status": 1})

//depois do index:
db.todolist.find({'tasks.status': "Done"}).explain("executionStats")

[
  {
    "command": {
      "find": "todolist",
      "filter": {
        "tasks.status": "Done"
      },
      "$db": "trabalho01"
    },
    "executionStats": {
      "executionSuccess": true,
      "nReturned": 7,
      "executionTimeMillis": 5,
      "totalKeysExamined": 7,
      "totalDocsExamined": 7,
      "executionStages": {
        "stage": "FETCH",
        "nReturned": 7,
        "executionTimeMillisEstimate": 4,
        "works": 8,
        "advanced": 7,
        "needTime": 0,
        "needYield": 0,
        "saveState": 0,
        "restoreState": 0,
        "isEOF": 1,
        "docsExamined": 7,
        "alreadyHasObj": 0,
        "inputStage": {
          "stage": "IXSCAN",
          "nReturned": 7,
          "executionTimeMillisEstimate": 4,
          "works": 8,
          "advanced": 7,
          "needTime": 0,
          "needYield": 0,
          "saveState": 0,
          "restoreState": 0,
          "isEOF": 1,
          "keyPattern": {
            "tasks.status": 1
          },
          "indexName": "tasks.status_1",
          "isMultiKey": true,
          "multiKeyPaths": {
            "tasks.status": ["tasks"]
          },
          "isUnique": false,
          "isSparse": false,
          "isPartial": false,
          "indexVersion": 2,
          "direction": "forward",
          "indexBounds": {
            "tasks.status": ["[\"Done\", \"Done\"]"]
          },
          "keysExamined": 7,
          "seeks": 1,
          "dupsTested": 7,
          "dupsDropped": 0
        }
      }
    },
    "explainVersion": "1",
    "ok": 1,
    "queryPlanner": {
      "namespace": "trabalho01.todolist",
      "indexFilterSet": false,
      "parsedQuery": {
        "tasks.status": {
          "$eq": "Done"
        }
      },
      "queryHash": "78B5AD89",
      "planCacheKey": "287C4CA4",
      "maxIndexedOrSolutionsReached": false,
      "maxIndexedAndSolutionsReached": false,
      "maxScansToExplodeReached": false,
      "winningPlan": {
        "stage": "FETCH",
        "inputStage": {
          "stage": "IXSCAN",
          "keyPattern": {
            "tasks.status": 1
          },
          "indexName": "tasks.status_1",
          "isMultiKey": true,
          "multiKeyPaths": {
            "tasks.status": ["tasks"]
          },
          "isUnique": false,
          "isSparse": false,
          "isPartial": false,
          "indexVersion": 2,
          "direction": "forward",
          "indexBounds": {
            "tasks.status": ["[\"Done\", \"Done\"]"]
          }
        }
      },
      "rejectedPlans": []
    },
    "serverInfo": {
      "host": "joaopmac.local",
      "port": 27017,
      "version": "6.0.6",
      "gitVersion": "26b4851a412cc8b9b4a18cdb6cd0f9f642e06aa7"
    },
    "serverParameters": {
      "internalQueryFacetBufferSizeBytes": 104857600,
      "internalQueryFacetMaxOutputDocSizeBytes": 104857600,
      "internalLookupStageIntermediateDocumentMaxSizeBytes": 104857600,
      "internalDocumentSourceGroupMaxMemoryBytes": 104857600,
      "internalQueryMaxBlockingSortMemoryUsageBytes": 104857600,
      "internalQueryProhibitBlockingMergeOnMongoS": 0,
      "internalQueryMaxAddToSetBytes": 104857600,
      "internalDocumentSourceSetWindowFieldsMaxMemoryBytes": 104857600
    }
  }
]

// Criando index para busca de tasks por emails de usuarios
//antes do index:
db.todolist.find({'tasks.user.email': "/.com/"}).explain("executionStats")
[
  {
    "command": {
      "find": "todolist",
      "filter": {
        "tasks.user.email": "/.com/"
      },
      "$db": "trabalho01"
    },
    "executionStats": {
      "executionSuccess": true,
      "nReturned": 0,
      "executionTimeMillis": 11,
      "totalKeysExamined": 0,
      "totalDocsExamined": 31,
      "executionStages": {
        "stage": "COLLSCAN",
        "filter": {
          "tasks.user.email": {
            "$eq": "/.com/"
          }
        },
        "nReturned": 0,
        "executionTimeMillisEstimate": 0,
        "works": 33,
        "advanced": 0,
        "needTime": 32,
        "needYield": 0,
        "saveState": 0,
        "restoreState": 0,
        "isEOF": 1,
        "direction": "forward",
        "docsExamined": 31
      }
    },
    "explainVersion": "1",
    "ok": 1,
    "queryPlanner": {
      "namespace": "trabalho01.todolist",
      "indexFilterSet": false,
      "parsedQuery": {
        "tasks.user.email": {
          "$eq": "/.com/"
        }
      },
      "queryHash": "EFA37A7F",
      "planCacheKey": "EFA37A7F",
      "maxIndexedOrSolutionsReached": false,
      "maxIndexedAndSolutionsReached": false,
      "maxScansToExplodeReached": false,
      "winningPlan": {
        "stage": "COLLSCAN",
        "filter": {
          "tasks.user.email": {
            "$eq": "/.com/"
          }
        },
        "direction": "forward"
      },
      "rejectedPlans": []
    },
    "serverInfo": {
      "host": "joaopmac.local",
      "port": 27017,
      "version": "6.0.6",
      "gitVersion": "26b4851a412cc8b9b4a18cdb6cd0f9f642e06aa7"
    },
    "serverParameters": {
      "internalQueryFacetBufferSizeBytes": 104857600,
      "internalQueryFacetMaxOutputDocSizeBytes": 104857600,
      "internalLookupStageIntermediateDocumentMaxSizeBytes": 104857600,
      "internalDocumentSourceGroupMaxMemoryBytes": 104857600,
      "internalQueryMaxBlockingSortMemoryUsageBytes": 104857600,
      "internalQueryProhibitBlockingMergeOnMongoS": 0,
      "internalQueryMaxAddToSetBytes": 104857600,
      "internalDocumentSourceSetWindowFieldsMaxMemoryBytes": 104857600
    }
  }
]

//Criacao do index:
db.todolist.createIndex({"tasks.user.email": 1})

//depois do index:
db.todolist.find({'tasks.user.email': "/.com/"}).explain("executionStats")

[
  {
    "command": {
      "find": "todolist",
      "filter": {
        "tasks.user.email": "/.com/"
      },
      "$db": "trabalho01"
    },
    "executionStats": {
      "executionSuccess": true,
      "nReturned": 0,
      "executionTimeMillis": 5,
      "totalKeysExamined": 0,
      "totalDocsExamined": 0,
      "executionStages": {
        "stage": "FETCH",
        "nReturned": 0,
        "executionTimeMillisEstimate": 0,
        "works": 1,
        "advanced": 0,
        "needTime": 0,
        "needYield": 0,
        "saveState": 0,
        "restoreState": 0,
        "isEOF": 1,
        "docsExamined": 0,
        "alreadyHasObj": 0,
        "inputStage": {
          "stage": "IXSCAN",
          "nReturned": 0,
          "executionTimeMillisEstimate": 0,
          "works": 1,
          "advanced": 0,
          "needTime": 0,
          "needYield": 0,
          "saveState": 0,
          "restoreState": 0,
          "isEOF": 1,
          "keyPattern": {
            "tasks.user.email": 1
          },
          "indexName": "tasks.user.email_1",
          "isMultiKey": true,
          "multiKeyPaths": {
            "tasks.user.email": ["tasks"]
          },
          "isUnique": false,
          "isSparse": false,
          "isPartial": false,
          "indexVersion": 2,
          "direction": "forward",
          "indexBounds": {
            "tasks.user.email": ["[\"/.com/\", \"/.com/\"]"]
          },
          "keysExamined": 0,
          "seeks": 1,
          "dupsTested": 0,
          "dupsDropped": 0
        }
      }
    },
    "explainVersion": "1",
    "ok": 1,
    "queryPlanner": {
      "namespace": "trabalho01.todolist",
      "indexFilterSet": false,
      "parsedQuery": {
        "tasks.user.email": {
          "$eq": "/.com/"
        }
      },
      "queryHash": "EFA37A7F",
      "planCacheKey": "E9C05065",
      "maxIndexedOrSolutionsReached": false,
      "maxIndexedAndSolutionsReached": false,
      "maxScansToExplodeReached": false,
      "winningPlan": {
        "stage": "FETCH",
        "inputStage": {
          "stage": "IXSCAN",
          "keyPattern": {
            "tasks.user.email": 1
          },
          "indexName": "tasks.user.email_1",
          "isMultiKey": true,
          "multiKeyPaths": {
            "tasks.user.email": ["tasks"]
          },
          "isUnique": false,
          "isSparse": false,
          "isPartial": false,
          "indexVersion": 2,
          "direction": "forward",
          "indexBounds": {
            "tasks.user.email": ["[\"/.com/\", \"/.com/\"]"]
          }
        }
      },
      "rejectedPlans": []
    },
    "serverInfo": {
      "host": "joaopmac.local",
      "port": 27017,
      "version": "6.0.6",
      "gitVersion": "26b4851a412cc8b9b4a18cdb6cd0f9f642e06aa7"
    },
    "serverParameters": {
      "internalQueryFacetBufferSizeBytes": 104857600,
      "internalQueryFacetMaxOutputDocSizeBytes": 104857600,
      "internalLookupStageIntermediateDocumentMaxSizeBytes": 104857600,
      "internalDocumentSourceGroupMaxMemoryBytes": 104857600,
      "internalQueryMaxBlockingSortMemoryUsageBytes": 104857600,
      "internalQueryProhibitBlockingMergeOnMongoS": 0,
      "internalQueryMaxAddToSetBytes": 104857600,
      "internalDocumentSourceSetWindowFieldsMaxMemoryBytes": 104857600
    }
  }
]

// Criando index para busca de tasks por usuarios com seniority
//antes do index:
db.todolist.find({'tasks.user.seniority': "Expert"}).explain("executionStats")
[
  {
    "command": {
      "find": "todolist",
      "filter": {
        "tasks.user.seniority": "Expert"
      },
      "$db": "trabalho01"
    },
    "executionStats": {
      "executionSuccess": true,
      "nReturned": 26,
      "executionTimeMillis": 4,
      "totalKeysExamined": 0,
      "totalDocsExamined": 31,
      "executionStages": {
        "stage": "COLLSCAN",
        "filter": {
          "tasks.user.seniority": {
            "$eq": "Expert"
          }
        },
        "nReturned": 26,
        "executionTimeMillisEstimate": 0,
        "works": 33,
        "advanced": 26,
        "needTime": 6,
        "needYield": 0,
        "saveState": 0,
        "restoreState": 0,
        "isEOF": 1,
        "direction": "forward",
        "docsExamined": 31
      }
    },
    "explainVersion": "1",
    "ok": 1,
    "queryPlanner": {
      "namespace": "trabalho01.todolist",
      "indexFilterSet": false,
      "parsedQuery": {
        "tasks.user.seniority": {
          "$eq": "Expert"
        }
      },
      "queryHash": "0B3129C9",
      "planCacheKey": "0B3129C9",
      "maxIndexedOrSolutionsReached": false,
      "maxIndexedAndSolutionsReached": false,
      "maxScansToExplodeReached": false,
      "winningPlan": {
        "stage": "COLLSCAN",
        "filter": {
          "tasks.user.seniority": {
            "$eq": "Expert"
          }
        },
        "direction": "forward"
      },
      "rejectedPlans": []
    },
    "serverInfo": {
      "host": "joaopmac.local",
      "port": 27017,
      "version": "6.0.6",
      "gitVersion": "26b4851a412cc8b9b4a18cdb6cd0f9f642e06aa7"
    },
    "serverParameters": {
      "internalQueryFacetBufferSizeBytes": 104857600,
      "internalQueryFacetMaxOutputDocSizeBytes": 104857600,
      "internalLookupStageIntermediateDocumentMaxSizeBytes": 104857600,
      "internalDocumentSourceGroupMaxMemoryBytes": 104857600,
      "internalQueryMaxBlockingSortMemoryUsageBytes": 104857600,
      "internalQueryProhibitBlockingMergeOnMongoS": 0,
      "internalQueryMaxAddToSetBytes": 104857600,
      "internalDocumentSourceSetWindowFieldsMaxMemoryBytes": 104857600
    }
  }
]

//Criacao do index:
db.todolist.createIndex({"tasks.user.seniority": 1})

//depois do index:
db.todolist.find({'tasks.user.seniority': "Expert"}).explain("executionStats")

[
  {
    "command": {
      "find": "todolist",
      "filter": {
        "tasks.user.seniority": "Expert"
      },
      "$db": "trabalho01"
    },
    "executionStats": {
      "executionSuccess": true,
      "nReturned": 26,
      "executionTimeMillis": 2,
      "totalKeysExamined": 26,
      "totalDocsExamined": 26,
      "executionStages": {
        "stage": "FETCH",
        "nReturned": 26,
        "executionTimeMillisEstimate": 0,
        "works": 27,
        "advanced": 26,
        "needTime": 0,
        "needYield": 0,
        "saveState": 0,
        "restoreState": 0,
        "isEOF": 1,
        "docsExamined": 26,
        "alreadyHasObj": 0,
        "inputStage": {
          "stage": "IXSCAN",
          "nReturned": 26,
          "executionTimeMillisEstimate": 0,
          "works": 27,
          "advanced": 26,
          "needTime": 0,
          "needYield": 0,
          "saveState": 0,
          "restoreState": 0,
          "isEOF": 1,
          "keyPattern": {
            "tasks.user.seniority": 1
          },
          "indexName": "tasks.user.seniority_1",
          "isMultiKey": true,
          "multiKeyPaths": {
            "tasks.user.seniority": ["tasks"]
          },
          "isUnique": false,
          "isSparse": false,
          "isPartial": false,
          "indexVersion": 2,
          "direction": "forward",
          "indexBounds": {
            "tasks.user.seniority": ["[\"Expert\", \"Expert\"]"]
          },
          "keysExamined": 26,
          "seeks": 1,
          "dupsTested": 26,
          "dupsDropped": 0
        }
      }
    },
    "explainVersion": "1",
    "ok": 1,
    "queryPlanner": {
      "namespace": "trabalho01.todolist",
      "indexFilterSet": false,
      "parsedQuery": {
        "tasks.user.seniority": {
          "$eq": "Expert"
        }
      },
      "queryHash": "0B3129C9",
      "planCacheKey": "EDF75BE9",
      "maxIndexedOrSolutionsReached": false,
      "maxIndexedAndSolutionsReached": false,
      "maxScansToExplodeReached": false,
      "winningPlan": {
        "stage": "FETCH",
        "inputStage": {
          "stage": "IXSCAN",
          "keyPattern": {
            "tasks.user.seniority": 1
          },
          "indexName": "tasks.user.seniority_1",
          "isMultiKey": true,
          "multiKeyPaths": {
            "tasks.user.seniority": ["tasks"]
          },
          "isUnique": false,
          "isSparse": false,
          "isPartial": false,
          "indexVersion": 2,
          "direction": "forward",
          "indexBounds": {
            "tasks.user.seniority": ["[\"Expert\", \"Expert\"]"]
          }
        }
      },
      "rejectedPlans": []
    },
    "serverInfo": {
      "host": "joaopmac.local",
      "port": 27017,
      "version": "6.0.6",
      "gitVersion": "26b4851a412cc8b9b4a18cdb6cd0f9f642e06aa7"
    },
    "serverParameters": {
      "internalQueryFacetBufferSizeBytes": 104857600,
      "internalQueryFacetMaxOutputDocSizeBytes": 104857600,
      "internalLookupStageIntermediateDocumentMaxSizeBytes": 104857600,
      "internalDocumentSourceGroupMaxMemoryBytes": 104857600,
      "internalQueryMaxBlockingSortMemoryUsageBytes": 104857600,
      "internalQueryProhibitBlockingMergeOnMongoS": 0,
      "internalQueryMaxAddToSetBytes": 104857600,
      "internalDocumentSourceSetWindowFieldsMaxMemoryBytes": 104857600
    }
  }
]


``
