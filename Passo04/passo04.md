# Trabalho 01 - MongoDB (To-Do List) - João Pedro
# Passo 04 - Operações de CRUD

```javascript

// Criacao de 30 documentos:


db.todolist.insertMany([
    {
        "name": "Project X",
        "start_date":  ISODate("2023-02-15T00:00:00Z"),
        "end_date": ISODate("2023-10-30T00:00:00Z"),
        "tasks": [
            {
                "title": "Database Design",
                "description": "Create the database schema for Project X",
                "start_date":  ISODate("2023-03-01T00:00:00Z"),
                "deadline_date": ISODate("2023-03-15T00:00:00Z"),
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
                "start_date":  ISODate("2023-04-01T00:00:00Z"),
                "deadline_date": ISODate("2023-05-01T00:00:00Z"),
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
        "name": "Task Management App",
        "start_date":  ISODate("2023-04-15T00:00:00Z"),
        "end_date": ISODate("2023-11-30T00:00:00Z"),
        "tasks": [
            {
                "title": "User Authentication",
                "description": "Implement user authentication for the app",
                "start_date":  ISODate("2023-05-10T00:00:00Z"),
                "deadline_date": ISODate("2023-05-25T00:00:00Z"),
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
                "start_date":  ISODate("2023-06-01T00:00:00Z"),
                "deadline_date": ISODate("2023-06-15T00:00:00Z"),
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
        "name": "E-commerce Website",
        "start_date":  ISODate("2023-03-01T00:00:00Z"),
        "end_date": ISODate("2023-12-31T00:00:00Z"),
        "tasks": [
            {
                "title": "Design Homepage",
                "description": "Create a visually appealing homepage design",
                "start_date":  ISODate("2023-03-15T00:00:00Z"),
                "deadline_date": ISODate("2023-03-30T00:00:00Z"),
                "priority": "Alta",
                "status": "Block",
                "user": {
                    "first_name": "Sophia",
                    "last_name": "Smith",
                    "email": "sophia@ecommerce.com",
                    "cell_phone": "555-555-5555",
                    "skill": "UI/UX Designer",
                    "seniority": "Expert"
                }
            },
            {
                "title": "Backend Development",
                "description": "Set up the backend for the e-commerce website",
                "start_date":  ISODate("2023-04-01T00:00:00Z"),
                "deadline_date": ISODate("2023-05-01T00:00:00Z"),
                "priority": "Alta",
                "status": "Todo",
                "user": {
                    "first_name": "Daniel",
                    "last_name": "Williams",
                    "email": "daniel@ecommerce.com",
                    "cell_phone": "555-123-4567",
                    "skill": "Backend Developer",
                    "seniority": "Senior"
                }
            }
        ]
    },
    {
        "name": "Marketing Campaign",
        "start_date":  ISODate("2023-06-01T00:00:00Z"),
        "end_date": ISODate("2023-08-31T00:00:00Z"),
        "tasks": [
            {
                "title": "Campaign Strategy",
                "description": "Plan the marketing campaign strategy",
                "start_date":  ISODate("2023-06-10T00:00:00Z"),
                "deadline_date": ISODate("2023-06-20T00:00:00Z"),
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
                "start_date":  ISODate("2023-07-01T00:00:00Z"),
                "deadline_date": ISODate("2023-07-15T00:00:00Z"),
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
        "name": "Product Development",
        "start_date":  ISODate("2023-04-15T00:00:00Z"),
        "end_date": ISODate("2023-11-30T00:00:00Z"),
        "tasks": [
            {
                "title": "Prototype Testing",
                "description": "Test the product prototype with user feedback",
                "start_date":  ISODate("2023-05-10T00:00:00Z"),
                "deadline_date": ISODate("2023-05-25T00:00:00Z"),
                                            "data_fim": ISODate("2023-05-15T00:00:00Z"),

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
                "start_date":  ISODate("2023-06-01T00:00:00Z"),
                "deadline_date": ISODate("2023-06-15T00:00:00Z"),
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
        "name": "Mobile App Development",
        "start_date":  ISODate("2023-05-01T00:00:00Z"),
        "end_date": ISODate("2023-12-31T00:00:00Z"),
        "tasks": [
            {
                "title": "Wireframing",
                "description": "Create wireframes for the mobile app",
                "start_date":  ISODate("2023-05-15T00:00:00Z"),
                "deadline_date": ISODate("2023-05-30T00:00:00Z"),
                "priority": "Media",
                "status": "Doing",
                "user": {
                    "first_name": "Aiden",
                    "last_name": "Brown",
                    "email": "aiden@appdev.com",
                    "cell_phone": "555-888-9999",
                    "skill": "UX Designer",
                    "seniority": "Senior"
                }
            },
            {
                "title": "Frontend Development",
                "description": "Develop the frontend for the mobile app",
                "start_date":  ISODate("2023-06-01T00:00:00Z"),
                "deadline_date": ISODate("2023-07-15T00:00:00Z"),
                "priority": "Alta",
                "status": "Todo",
                "user": {
                    "first_name": "Ella",
                    "last_name": "Davis",
                    "email": "ella@appdev.com",
                    "cell_phone": "555-777-6666",
                    "skill": "Frontend Developer",
                    "seniority": "Expert"
                }
            }
        ]
    },
    {
        "name": "Content Marketing Campaign",
        "start_date":  ISODate("2023-07-01T00:00:00Z"),
        "end_date": ISODate("2023-09-30T00:00:00Z"),
        "tasks": [
            {
                "title": "Content Calendar",
                "description": "Create a content calendar for the campaign",
                "start_date":  ISODate("2023-07-10T00:00:00Z"),
                "deadline_date": ISODate("2023-07-20T00:00:00Z"),
                                            "data_fim": ISODate("2023-07-15T00:00:00Z"),

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
                "start_date":  ISODate("2023-08-01T00:00:00Z"),
                "deadline_date": ISODate("2023-08-15T00:00:00Z"),
                                            "data_fim": ISODate("2023-08-15T00:00:00Z"),

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
        "name": "Research Project",
        "start_date":  ISODate("2023-08-15T00:00:00Z"),
        "end_date": ISODate("2023-11-30T00:00:00Z"),
        "tasks": [
            {
                "title": "Literature Review",
                "description": "Conduct a review of existing literature in the field",
                "start_date":  ISODate("2023-08-30T00:00:00Z"),
                "deadline_date": ISODate("2023-09-15T00:00:00Z"),
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
                "start_date":  ISODate("2023-09-20T00:00:00Z"),
                "deadline_date": ISODate("2023-10-15T00:00:00Z"),
                "priority": "Media",
                "status": "Todo",
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
    },
     {
        "name": "Inventory Management System",
        "start_date":  ISODate("2023-09-01T00:00:00Z"),
        "end_date": ISODate("2023-12-31T00:00:00Z"),
        "tasks": [
            {
                "title": "Requirements Gathering",
                "description": "Gather and document system requirements",
                "start_date":  ISODate("2023-09-10T00:00:00Z"),
                "deadline_date": ISODate("2023-09-20T00:00:00Z"),
                "priority": "Alta",
                "status": "Doing",
                "user": {
                    "first_name": "Ethan",
                    "last_name": "Taylor",
                    "email": "ethan@inventorysystem.com",
                    "cell_phone": "555-999-8888",
                    "skill": "Business Analyst",
                    "seniority": "Expert"
                }
            },
            {
                "title": "Database Setup",
                "description": "Set up the database for the inventory system",
                "start_date":  ISODate("2023-09-25T00:00:00Z"),
                "deadline_date": ISODate("2023-10-10T00:00:00Z"),
                "priority": "Media",
                "status": "Todo",
                "user": {
                    "first_name": "Aria",
                    "last_name": "Martin",
                    "email": "aria@inventorysystem.com",
                    "cell_phone": "555-666-7777",
                    "skill": "Database Administrator",
                    "seniority": "Senior"
                }
            }
        ]
    },
    {
        "name": "Event Planning",
        "start_date":  ISODate("2023-09-01T00:00:00Z"),
        "end_date": ISODate("2023-12-31T00:00:00Z"),
        "tasks": [
            {
                "title": "Venue Selection",
                "description": "Select a suitable venue for the event",
                "start_date":  ISODate("2023-09-10T00:00:00Z"),
                "deadline_date": ISODate("2023-09-20T00:00:00Z"),
                "priority": "Alta",
                "status": "Doing",
                "user": {
                    "first_name": "Ella",
                    "last_name": "Smith",
                    "email": "ella@eventplanning.com",
                    "cell_phone": "555-999-8888",
                    "skill": "Event Planner",
                    "seniority": "Expert"
                }
            },
            {
                "title": "Vendor Contracts",
                "description": "Negotiate and sign contracts with event vendors",
                "start_date":  ISODate("2023-09-25T00:00:00Z"),
                "deadline_date": ISODate("2023-10-10T00:00:00Z"),
                "priority": "Media",
                "status": "Todo",
                "user": {
                    "first_name": "James",
                    "last_name": "Wilson",
                    "email": "james@eventplanning.com",
                    "cell_phone": "555-666-7777",
                    "skill": "Vendor Manager",
                    "seniority": "Senior"
                }
            }
        ]
    },  // 10
    {
        "name": "Product Launch",
        "start_date":  ISODate("2023-10-01T00:00:00Z"),
        "end_date": ISODate("2023-12-31T00:00:00Z"),
        "tasks": [
            {
                "title": "Marketing Strategy",
                "description": "Develop a marketing strategy for the product launch",
                "start_date":  ISODate("2023-10-10T00:00:00Z"),
                "deadline_date": ISODate("2023-10-20T00:00:00Z"),
                "priority": "Alta",
                "status": "Doing",
                "user": {
                    "first_name": "Aiden",
                    "last_name": "Brown",
                    "email": "aiden@productlaunch.com",
                    "cell_phone": "123-456-7890",
                    "skill": "Marketing Specialist",
                    "seniority": "Expert"
                }
            },
            {
                "title": "Product Testing",
                "description": "Conduct quality testing of the product",
                "start_date":  ISODate("2023-10-25T00:00:00Z"),
                "deadline_date": ISODate("2023-11-10T00:00:00Z"),
                "data_fim": ISODate("2023-11-05T00:00:00Z"),
                "priority": "Media",
                "status": "Done",
                "user": {
                    "first_name": "Aria",
                    "last_name": "Martin",
                    "email": "aria@productlaunch.com",
                    "cell_phone": "123-789-4560",
                    "skill": "Quality Assurance Specialist",
                    "seniority": "Intermediate"
                }
            }
        ]
    },
    {
        "name": "Content Management",
        "start_date":  ISODate("2023-11-01T00:00:00Z"),
        "end_date": ISODate("2023-12-15T00:00:00Z"),
        "tasks": [
            {
                "title": "Content Strategy",
                "description": "Develop a content strategy for the platform",
                "start_date":  ISODate("2023-11-10T00:00:00Z"),
                "deadline_date": ISODate("2023-11-20T00:00:00Z"),
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
                "start_date":  ISODate("2023-11-25T00:00:00Z"),
                "deadline_date": ISODate("2023-12-10T00:00:00Z"),
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
    "name": "Customer Support Redesign",
    "start_date":  ISODate("2023-10-01T00:00:00Z"),
    "end_date": ISODate("2023-12-31T00:00:00Z"),
    "tasks": [
        {
            "title": "User Feedback Analysis",
            "description": "Analyze user feedback to identify pain points",
            "start_date":  ISODate("2023-10-10T00:00:00Z"),
            "deadline_date": ISODate("2023-10-20T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Liam",
                "last_name": "Smith",
                "email": "liam@customersupport.com",
                "cell_phone": "123-456-7890",
                "skill": "User Experience Analyst",
                "seniority": "Expert"
            }
        },
        {
            "title": "Redesign Implementation",
            "description": "Implement the redesigned customer support system",
            "start_date":  ISODate("2023-10-25T00:00:00Z"),
            "deadline_date": ISODate("2023-11-10T00:00:00Z"),
            "priority": "Media",
            "status": "Todo",
            "user": {
                "first_name": "Ava",
                "last_name": "Johnson",
                "email": "ava@customersupport.com",
                "cell_phone": "123-789-4560",
                "skill": "UI/UX Designer",
                "seniority": "Intermediate"
            }
        }
    ]
},{
    "name": "Accounting Software Development",
    "start_date":  ISODate("2023-06-01T00:00:00Z"),
    "end_date": ISODate("2023-12-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Feature Specification",
            "description": "Specify the features and functionalities of the software",
            "start_date":  ISODate("2023-06-10T00:00:00Z"),
            "deadline_date": ISODate("2023-06-20T00:00:00Z"),
                            "data_fim": ISODate("2023-06-15T00:00:00Z"),

            "priority": "Alta",
            "status": "Done",
            "user": {
                "first_name": "Sophia",
                "last_name": "Martinez",
                "email": "sophia@accountingsoftware.com",
                "cell_phone": "555-777-8888",
                "skill": "Business Analyst",
                "seniority": "Expert"
            }
        },
        {
            "title": "Software Development",
            "description": "Develop the accounting software application",
            "start_date":  ISODate("2023-06-25T00:00:00Z"),
            "deadline_date": ISODate("2023-08-15T00:00:00Z"),
            "priority": "Alta",
            "status": "Todo",
            "user": {
                "first_name": "Daniel",
                "last_name": "Smith",
                "email": "daniel@accountingsoftware.com",
                "cell_phone": "555-123-4567",
                "skill": "Software Developer",
                "seniority": "Expert"
            }
        }
    ]
},
{
    "name": "Electronic Product Launch",
    "start_date":  ISODate("2023-08-01T00:00:00Z"),
    "end_date": ISODate("2023-12-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Product Design",
            "description": "Design the electronic product's hardware and software",
            "start_date":  ISODate("2023-08-10T00:00:00Z"),
            "deadline_date": ISODate("2023-08-20T00:00:00Z"),
            "priority": "Urgente",
            "status": "Doing",
            "user": {
                "first_name": "Aiden",
                "last_name": "Brown",
                "email": "aiden@electronicproduct.com",
                "cell_phone": "555-999-8888",
                "skill": "Product Designer",
                "seniority": "Expert"
            }
        },
        {
            "title": "Production Setup",
            "description": "Prepare the production process for the electronic product",
            "start_date":  ISODate("2023-08-25T00:00:00Z"),
            "deadline_date": ISODate("2023-09-10T00:00:00Z"),
            "priority": "Media",
            "status": "Todo",
            "user": {
                "first_name": "Mia",
                "last_name": "Johnson",
                "email": "mia@electronicproduct.com",
                "cell_phone": "555-666-7777",
                "skill": "Production Manager",
                "seniority": "Senior"
            }
        }
    ]
},
{
    "name": "E-commerce Platform Development",
    "start_date":  ISODate("2023-07-01T00:00:00Z"),
    "end_date": ISODate("2023-12-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Platform Architecture",
            "description": "Define the technical architecture of the e-commerce platform",
            "start_date":  ISODate("2023-07-10T00:00:00Z"),
            "deadline_date": ISODate("2023-07-20T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Liam",
                "last_name": "Garcia",
                "email": "liam@ecommerceplatform.com",
                "cell_phone": "123-456-7890",
                "skill": "Technical Architect",
                "seniority": "Expert"
            }
        },
        {
            "title": "Frontend Development",
            "description": "Develop the frontend of the e-commerce platform",
            "start_date":  ISODate("2023-07-25T00:00:00Z"),
            "deadline_date": ISODate("2023-08-15T00:00:00Z"),
            "priority": "Alta",
            "status": "Todo",
            "user": {
                "first_name": "Ella",
                "last_name": "Smith",
                "email": "ella@ecommerceplatform.com",
                "cell_phone": "123-789-4560",
                "skill": "Frontend Developer",
                "seniority": "Expert"
            }
        }
    ]
},
{
    "name": "Market Research",
    "start_date":  ISODate("2023-08-15T00:00:00Z"),
    "end_date": ISODate("2023-11-30T00:00:00Z"),
    "tasks": [
        {
            "title": "Research Objectives",
            "description": "Define the objectives and scope of the market research",
            "start_date":  ISODate("2023-08-30T00:00:00Z"),
            "deadline_date": ISODate("2023-09-15T00:00:00Z"),
                                        "data_fim": ISODate("2023-09-10T00:00:00Z"),

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
            "start_date":  ISODate("2023-09-20T00:00:00Z"),
            "deadline_date": ISODate("2023-10-15T00:00:00Z"),
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
    "name": "Health App Development",
    "start_date":  ISODate("2023-09-01T00:00:00Z"),
    "end_date": ISODate("2023-12-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Feature Planning",
            "description": "Plan the features and functionalities of the health app",
            "start_date":  ISODate("2023-09-10T00:00:00Z"),
            "deadline_date": ISODate("2023-09-20T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Sophia",
                "last_name": "Clark",
                "email": "sophia@healthapp.com",
                "cell_phone": "555-777-8888",
                "skill": "Product Manager",
                "seniority": "Expert"
            }
        },
        {
            "title": "App Development",
            "description": "Develop the mobile application for the health app",
            "start_date":  ISODate("2023-09-25T00:00:00Z"),
            "deadline_date": ISODate("2023-10-15T00:00:00Z"),
            "priority": "Alta",
            "status": "Todo",
            "user": {
                "first_name": "Daniel",
                "last_name": "Brown",
                "email": "daniel@healthapp.com",
                "cell_phone": "555-123-4567",
                "skill": "App Developer",
                "seniority": "Expert"
            }
        }
    ]
},
{
    "name": "Food Product Launch",
    "start_date":  ISODate("2023-11-01T00:00:00Z"),
    "end_date": ISODate("2023-12-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Product Development",
            "description": "Develop a new food product and create recipes",
            "start_date":  ISODate("2023-11-10T00:00:00Z"),
            "deadline_date": ISODate("2023-11-20T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Oliver",
                "last_name": "Garcia",
                "email": "oliver@foodproduct.com",
                "cell_phone": "555-111-2222",
                "skill": "Product Developer",
                "seniority": "Expert"
            }
        },
        {
            "title": "Production Setup",
            "description": "Set up the production process for the food product",
            "start_date":  ISODate("2023-11-25T00:00:00Z"),
            "deadline_date": ISODate("2023-12-10T00:00:00Z"),
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
},
{
    "name": "Social Media App Development",
    "start_date":  ISODate("2023-10-01T00:00:00Z"),
    "end_date": ISODate("2023-12-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Platform Design",
            "description": "Design the user interface and user experience for the social media app",
            "start_date":  ISODate("2023-10-10T00:00:00Z"),
            "deadline_date": ISODate("2023-10-20T00:00:00Z"),
                                        "data_fim": ISODate("2023-10-20T00:00:00Z"),

            "priority": "Urgente",
            "status": "Done",
            "user": {
                "first_name": "Liam",
                "last_name": "Johnson",
                "email": "liam@socialmediaapp.com",
                "cell_phone": "123-456-7890",
                "skill": "UI/UX Designer",
                "seniority": "Expert"
            }
        },
        {
            "title": "App Development",
            "description": "Develop the mobile application for the social media app",
            "start_date":  ISODate("2023-10-25T00:00:00Z"),
            "deadline_date": ISODate("2023-11-10T00:00:00Z"),
            "priority": "Alta",
            "status": "Todo",
            "user": {
                "first_name": "Ella",
                "last_name": "Martin",
                "email": "ella@socialmediaapp.com",
                "cell_phone": "123-789-4560",
                "skill": "App Developer",
                "seniority": "Expert"
            }
        }
    ]
}, //20
{
    "name": "Consumer Opinion Research",
    "start_date":  ISODate("2023-10-15T00:00:00Z"),
    "end_date": ISODate("2023-12-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Survey Design",
            "description": "Design surveys to gather consumer opinions and feedback",
            "start_date":  ISODate("2023-10-20T00:00:00Z"),
            "deadline_date": ISODate("2023-10-30T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Sophia",
                "last_name": "Miller",
                "email": "sophia@consumerresearch.com",
                "cell_phone": "555-777-8888",
                "skill": "Research Analyst",
                "seniority": "Expert"
            }
        }]
},
{
    "name": "Education App Development",
    "start_date":  ISODate("2023-08-01T00:00:00Z"),
    "end_date": ISODate("2023-12-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Curriculum Planning",
            "description": "Plan the educational curriculum for the app",
            "start_date":  ISODate("2023-08-10T00:00:00Z"),
            "deadline_date": ISODate("2023-08-20T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Ethan",
                "last_name": "Taylor",
                "email": "ethan@educationapp.com",
                "cell_phone": "555-777-8888",
                "skill": "Curriculum Planner",
                "seniority": "Expert"
            }
        },
        {
            "title": "App Development",
            "description": "Develop the mobile application for educational content",
            "start_date":  ISODate("2023-08-25T00:00:00Z"),
            "deadline_date": ISODate("2023-09-15T00:00:00Z"),
            "priority": "Alta",
            "status": "Todo",
            "user": {
                "first_name": "Aria",
                "last_name": "Garcia",
                "email": "aria@educationapp.com",
                "cell_phone": "555-123-4567",
                "skill": "App Developer",
                "seniority": "Expert"
            }
        }
    ]
},
{
    "name": "News Website Development",
    "start_date":  ISODate("2023-10-01T00:00:00Z"),
    "end_date": ISODate("2023-12-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Content Strategy",
            "description": "Develop a content strategy for the news website",
            "start_date":  ISODate("2023-10-10T00:00:00Z"),
            "deadline_date": ISODate("2023-10-20T00:00:00Z"),
                                        "data_fim": ISODate("2023-10-15T00:00:00Z"),

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
            "start_date":  ISODate("2023-10-25T00:00:00Z"),
            "deadline_date": ISODate("2023-11-10T00:00:00Z"),
            "priority": "Alta",
            "status": "Todo",
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
},
{
    "name": "Game Development",
    "start_date":  ISODate("2023-09-01T00:00:00Z"),
    "end_date": ISODate("2023-12-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Game Concept",
            "description": "Define the concept and gameplay for the game",
            "start_date":  ISODate("2023-09-10T00:00:00Z"),
            "deadline_date": ISODate("2023-09-20T00:00:00Z"),
            "priority": "Urgente",
            "status": "Doing",
            "user": {
                "first_name": "Daniel",
                "last_name": "Brown",
                "email": "daniel@gamedevelopment.com",
                "cell_phone": "555-888-9999",
                "skill": "Game Designer",
                "seniority": "Expert"
            }
        },
        {
            "title": "Game Programming",
            "description": "Write the code and develop the game mechanics",
            "start_date":  ISODate("2023-09-25T00:00:00Z"),
            "deadline_date": ISODate("2023-10-15T00:00:00Z"),
            "priority": "Alta",
            "status": "Todo",
            "user": {
                "first_name": "Mia",
                "last_name": "Davis",
                "email": "mia@gamedevelopment.com",
                "cell_phone": "555-123-4567",
                "skill": "Game Developer",

                "seniority": "Expert"}
                }]
 },
 {
    "name": "E-Learning Platform Development",
    "start_date":  ISODate("2023-11-01T00:00:00Z"),
    "end_date": ISODate("2024-03-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Content Creation",
            "description": "Create educational content for the e-learning platform",
            "start_date":  ISODate("2023-11-10T00:00:00Z"),
            "deadline_date": ISODate("2023-11-20T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Ethan",
                "last_name": "Martin",
                "email": "ethan@elearningplatform.com",
                "cell_phone": "555-777-8888",
                "skill": "Content Creator",
                "seniority": "Expert"
            }
        },
        {
            "title": "Platform Development",
            "description": "Develop the e-learning platform and its features",
            "start_date":  ISODate("2023-11-25T00:00:00Z"),
            "deadline_date": ISODate("2024-01-15T00:00:00Z"),
            "priority": "Alta",
            "status": "Todo",
            "user": {
                "first_name": "Liam",
                "last_name": "Garcia",
                "email": "liam@elearningplatform.com",
                "cell_phone": "555-123-4567",
                "skill": "Platform Developer",
                "seniority": "Expert"
            }
        }
    ]
}
,{
    "name": "Travel App Launch",
    "start_date":  ISODate("2023-12-01T00:00:00Z"),
    "end_date": ISODate("2024-02-28T00:00:00Z"),
    "tasks": [
        {
            "title": "Feature Development",
            "description": "Develop new features for the travel app",
            "start_date":  ISODate("2023-12-10T00:00:00Z"),
            "deadline_date": ISODate("2023-12-20T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Sophia",
                "last_name": "Clark",
                "email": "sophia@travelapp.com",
                "cell_phone": "555-999-8888",
                "skill": "App Developer",
                "seniority": "Expert"
            }
        },
        {
            "title": "App Testing",
            "description": "Test the functionality and performance of the travel app",
            "start_date":  ISODate("2023-12-25T00:00:00Z"),
            "deadline_date": ISODate("2024-01-10T00:00:00Z"),
            "priority": "Urgente",
            "status": "Todo",
            "user": {
                "first_name": "Daniel",
                "last_name": "Smith",
                "email": "daniel@travelapp.com",
                "cell_phone": "555-123-4567",
                "skill": "Quality Assurance",
                "seniority": "Expert"
            }
        }
    ]
}
,{
    "name": "Mental Health App Development",
    "start_date":  ISODate("2023-10-15T00:00:00Z"),
    "end_date": ISODate("2024-01-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Therapist Matching",
            "description": "Implement a system for matching users with therapists",
            "start_date":  ISODate("2023-10-20T00:00:00Z"),
            "deadline_date": ISODate("2023-11-05T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Ella",
                "last_name": "Johnson",
                "email": "ella@mentalhealthapp.com",
                "cell_phone": "555-777-8888",
                "skill": "App Developer",
                "seniority": "Expert"
            }
        },
        {
            "title": "App Testing",
            "description": "Conduct testing to ensure the app's reliability and security",
            "start_date":  ISODate("2023-11-10T00:00:00Z"),
            "deadline_date": ISODate("2023-11-25T00:00:00Z"),
            "priority": "Media",
            "status": "Todo",
            "user": {
                "first_name": "Oliver",
                "last_name": "Smith",
                "email": "oliver@mentalhealthapp.com",
                "cell_phone": "555-123-4567",
                "skill": "Quality Assurance",
                "seniority": "Expert"
            }
        }
    ]
}
,{
    "name": "Delivery App Development",
    "start_date":  ISODate("2023-11-01T00:00:00Z"),
    "end_date": ISODate("2024-03-31T00:00:00Z"),
    "tasks": [
        {
            "title": "User Interface Design",
            "description": "Design the user interface for the delivery app",
            "start_date":  ISODate("2023-11-10T00:00:00Z"),
            "deadline_date": ISODate("2023-11-20T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Liam",
                "last_name": "Garcia",
                "email": "liam@deliveryapp.com",
                "cell_phone": "555-999-8888",
                "skill": "UI/UX Designer",
                "seniority": "Expert"
            }
        },
        {
            "title": "App Development",
            "description": "Develop the mobile application for the delivery service",
            "start_date":  ISODate("2023-11-25T00:00:00Z"),
            "deadline_date": ISODate("2024-01-15T00:00:00Z"),
            "priority": "Alta",
            "status": "Todo",
            "user": {
                "first_name": "Ella",
                "last_name": "Smith",
                "email": "ella@deliveryapp.com",
                "cell_phone": "555-123-4567",
                "skill": "App Developer",
                "seniority": "Expert"
            }
        }
    ]
},
{
    "name": "Personal Finance App Development",
    "start_date":  ISODate("2023-10-01T00:00:00Z"),
    "end_date": ISODate("2024-02-29T00:00:00Z"),
    "tasks": [
        {
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
        },
        {
            "title": "App Testing",
            "description": "Conduct testing to ensure the app's functionality and security",
            "start_date":  ISODate("2023-10-25T00:00:00Z"),
            "deadline_date": ISODate("2023-11-10T00:00:00Z"),
            "priority": "Media",
            "status": "Todo",
            "user": {
                "first_name": "Sophia",
                "last_name": "Clark",
                "email": "sophia@financeapp.com",
                "cell_phone": "555-123-4567",
                "skill": "Quality Assurance",
                "seniority": "Expert"
            }
        }
    ]
}
,
{
    "name": "Fitness App Development",
    "start_date":  ISODate("2023-11-01T00:00:00Z"),
    "end_date": ISODate("2024-03-31T00:00:00Z"),
    "tasks": [
        {
            "title": "Workout Program Design",
            "description": "Design effective workout programs for the fitness app",
            "start_date":  ISODate("2023-11-10T00:00:00Z"),
            "deadline_date": ISODate("2023-11-20T00:00:00Z"),
            "priority": "Alta",
            "status": "Doing",
            "user": {
                "first_name": "Ethan",
                "last_name": "Martin",
                "email": "ethan@fitnessapp.com",
                "cell_phone": "555-777-8888",
                "skill": "Fitness Expert",
                "seniority": "Expert"
            }
        },
        {
            "title": "App Development",
            "description": "Develop the mobile application for workout tracking and guidance",
            "start_date":  ISODate("2023-11-25T00:00:00Z"),
            "deadline_date": ISODate("2024-01-15T00:00:00Z"),
            "priority": "Urgente",
            "status": "Todo",
            "user": {
                "first_name": "Sophia",
                "last_name": "Clark",
                "email": "sophia@fitnessapp.com",
                "cell_phone": "555-123-4567",
                "skill": "App Developer",
                "seniority": "Expert"
            }
        }
    ]
}]
)

```


// Queries:




