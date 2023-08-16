 ### Table user

|Champ  | Type | Spécificités |Description |

|id |INT  | PRIMARY KEY, UNSIGNED, NOT NULL, AUTO_INCREMENT| L’identifiant de l'utilisateur
| username | VARCHAR(64) | NOT NULL | pseudo de l'utilisateur |
| password |VARCHAR(64)  |NOT NULL  | mot de passe de l'utilisateur |
| email |VARCHAR(240)  |NOT NULL  | email de l'utilisateur |
| tel |INT  |NOT NULL  | te de l'utilisateur |
| role |LIST_ENUM|NOT NULL ,DEFAULT USER  | role de l'utilisateur  |
| avatar | VARCHAR(128) | NULL,DEFAULT AVATAR | avatar  de l'utilisateur |
|created_at | TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de création |
 |updated_at |TIMESTAMP  | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de dernière modification de user |

 ### Table garden

|Champ  | Type | Spécificités |Description |

|id_garden |INT  | PRIMARY KEY, UNSIGNED, NOT NULL, AUTO_INCREMENT| identifiant du jardin
| title | VARCHAR(64) | NOT NULL | titre du jardin |
| description |VARCHAR(500)  |NOT NULL  | description du jardin|
| address|VARCHAR(240)  |NOT NULL  | adresse du jardin |
| postal code| INT  |NOT NULL  | code postal du jardin |
| town |VARCHAR(64)  |NOT NULL ,DEFAULT USER  | ville du jardin  |
| water | BOOL | NOT NULL,DEFAULT NO | point d'eau du jardin|
|tool | VARCHAR(240) |  NULL| liste des outils disponible sur le jardin |
| shed| BOOL | NOT NULL,DEFAULT NO | presence abri de jardin  |
| picture |LIST_ENUM |NULL  | photos du jardin  |
| state | VARCHAR(128) | NULL,DEFAULT AVATAR | état du jardin |
|surface| LIST_ENUM | NOT NULL | Surface disponible du jardin |
| phone | BOOL | NOT NULL,DEFAULT NO | droits usage du telephone de l'utilisateur |
|created_at | TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de création |
 |updated_at |TIMESTAMP  | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de dernière modification du jardin |
|user_id| INT| FOREIGN KEY,NOT NULL | référence id propriétaire du jardin |

 ### Table favorite ou garden_user

|Champ  | Type | Spécificités |Description |
|user_id| ENTITY| PRIMARY KEY,NOT NULL| L’identifiant de l'utilisateur
|garden_id| ENTITYPRIMARY KEY| NOT NULL| L’identifiant du jardin
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ4MTMyNjI4NCwtMTI3OTQwOTM0Myw2ND
c2MDM5MiwyMTIxOTUwNzg4LC0xMzMzMTU2ODAwLC01MzcyNjc2
NDUsMTA1ODUwNzg2NiwtODMyNTU3MjA1XX0=
-->