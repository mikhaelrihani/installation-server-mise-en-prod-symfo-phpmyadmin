
### Table user

  

| Champ | Type | Spécificités | Description |

  

|id_user | INT | PRIMARY KEY, UNSIGNED, NOT NULL, AUTO_INCREMENT| identifiant utilisateur |

| username | VARCHAR(64) | NOT NULL | pseudo utilisateur |

| password |VARCHAR(64) |NOT NULL | mot de passe utilisateur |

| email |VARCHAR(240) |NOT NULL | email de utilisateur |

| phone |INT |NOT NULL | telephone utilisateur |

| role |LIST_ENUM|NOT NULL ,DEFAULT USER | role utilisateur |

| avatar | VARCHAR(128) | NULL,DEFAULT AVATAR | avatar utilisateur |

|created_at | TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de création |

|updated_at |TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de dernière modification de user |

  

### Table garden

  

|Champ | Type | Spécificités |Description |

  

|id_garden |INT | PRIMARY KEY, UNSIGNED, NOT NULL, AUTO_INCREMENT| identifiant jardin|

| title | VARCHAR(64) | NOT NULL | titre du jardin |

| description |VARCHAR(500) |NOT NULL | description jardin|

| address| VARCHAR(240) |NOT NULL | adresse du jardin |

| postal code| INT |NOT NULL | code postal du jardin |

| town |VARCHAR(64) |NOT NULL ,DEFAULT USER | ville jardin |

| water | BOOL | NOT NULL,DEFAULT  NO | point eau du jardin|

|tool | VARCHAR(240) | NULL| liste des outils disponible sur le jardin |

| shed| BOOL | NOT NULL,DEFAULT  NO | presence abri de jardin |

| picture |LIST_ENUM |NULL | photos du jardin |

| state | VARCHAR(128) | NULL,DEFAULT AVATAR | état du jardin |

|surface| LIST_ENUM | NOT NULL | Surface disponible du jardin |

| phone | BOOL | NOT NULL,DEFAULT  NO | droits usage du telephone utilisateur |

|created_at | TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de création |

|updated_at |TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de dernière modification du jardin |

|user_id| INT| FOREIGN KEY,NOT NULL | référence id propriétaire du jardin |

  

### Table favorite ou garden_user

  

|Champ | Type | Spécificités |Description |

|user_id| ENTITY| PRIMARY KEY,NOT NULL| identifiant utilisateur|

|garden_id| ENTITYPRIMARY KEY| NOT NULL| identifiant du jardin|
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg2MDQ4NzQzMCwxNjM4Mjc2MjM4LDcwOD
cxODY5MiwtMTI3OTQwOTM0Myw2NDc2MDM5MiwyMTIxOTUwNzg4
LC0xMzMzMTU2ODAwLC01MzcyNjc2NDUsMTA1ODUwNzg2NiwtOD
MyNTU3MjA1XX0=
-->