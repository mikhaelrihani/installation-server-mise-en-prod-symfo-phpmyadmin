 ### Table utilisateur

|Champ  | Type | Spécificités |Description |

|id |INT  | PRIMARY KEY, UNSIGNED, NOT NULL, AUTO_INCREMENT| L’identifiant de l'utilisateur
| username | VARCHAR(64) | NOT NULL | pseudo de l'utilisateur |
| password |VARCHAR(64)  |NOT NULL  | mot de passe de l'utilisateur |
| email |VARCHAR(240)  |NOT NULL  | email de l'utilisateur |
| tel |INT  |NOT NULL  | te de l'utilisateur |
| role |VARCHAR(64)  |NOT NULL ,DEFAULT USER  | role de l'utilisateur  |
| avatar | VARCHAR(128) | NULL,DEFAULT AVATAR | avatar  de l'utilisateur |
|crée le | TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de création |
 |mis_a_jour_le |TIMESTAMP  | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de dernière modification de user |

 ### Table jardin

|Champ  | Type | Spécificités |Description |

|id |INT  | PRIMARY KEY, UNSIGNED, NOT NULL, AUTO_INCREMENT| L’identifiant du jardin
| title | VARCHAR(64) | NOT NULL | titre du jardin |
| texte |VARCHAR(500)  |NOT NULL  | description du jardin|
| adresse |VARCHAR(240)  |NOT NULL  | location du jardin |
| code postal| INT  |NOT NULL  | code postal du jardin |
| ville  |VARCHAR(64)  |NOT NULL ,DEFAULT USER  | code postal du jardin  |
| point d'eau | BOOL | NOT NULL,DEFAULT NO | point d'eau du jardin|
|outils | VARCHAR(240) |  NULL| liste des outils disponible sur le jardin |
| abri de jardin| BOOL | NOT NULL,DEFAULT NO | presence abri de jardin  |
| photos |LIST_ENUM |NULL  | photos du jardin  |
| état du jardin | VARCHAR(128) | NULL,DEFAULT AVATAR | état du jardin |
|surface| LIST_ENUM | NOT NULL | Surface disponible du jardin |
| utilisation telephone | BOOL | NOT NULL,DEFAULT NO | avatar  de l'utilisateur |
|crée le | TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de création |
|mis_a_jour_le |TIMESTAMP  | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de dernière modification du jardin |
|user_id| INT| FOREIGN KEY,NOT NULL | référence id propriétaire du jardin |

 ### Table PIVOT FAVORIS ou jardin_user

|Champ  | Type | Spécificités |Description |
|USER_ID| ENTITY| PRIMARY KEY,NOT NULL| L’identifiant de l'utilisateur
|Jardin_ID| ENTITYPRIMARY KEY| NOT NULL| L’identifiant du jardin
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkyMTg4MTg3NSwtMTI3OTQwOTM0Myw2ND
c2MDM5MiwyMTIxOTUwNzg4LC0xMzMzMTU2ODAwLC01MzcyNjc2
NDUsMTA1ODUwNzg2NiwtODMyNTU3MjA1XX0=
-->