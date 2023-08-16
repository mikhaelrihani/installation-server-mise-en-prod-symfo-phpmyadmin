 ### Table utilisateur

|Champ  | Type | Spécificités |Description |

|id_user  |INT  | PRIMARY KEY, UNSIGNED, NOT NULL, AUTO_INCREMENT| L’identifiant de l'utilisateur
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

|id_jardin |INT  | PRIMARY KEY, UNSIGNED, NOT NULL, AUTO_INCREMENT| L’identifiant du jardin
| title | VARCHAR(64) | NOT NULL | titre du jardin |
| texte |VARCHAR(64)  |NOT NULL  | texte du jardin|
| adresse |VARCHAR(240)  |NOT NULL  | adresse du jardin |
| code postal| INT  |NOT NULL  | code postal du jardin |
| ville  |VARCHAR(64)  |NOT NULL ,DEFAULT USER  | role de l'utilisateur  |
| point d'eau | VARCHAR(128) | NULL,DEFAULT AVATAR | point d'eau du jardin|
|outils | TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | outils disponible sur le jardin |
| abri de jardin| INT  |NOT NULL  | abri de jardin  |
| photos |VARCHAR(64)  |DEFAULT USER  | photos du jardin  |
| état du jardin | VARCHAR(128) | NULL,DEFAULT AVATAR | avatar  de l'utilisateur |
|surface| TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de création |
| utilisation telephone | VARCHAR(128) | NULL,DEFAULT AVATAR | avatar  de l'utilisateur |

|crée le | TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de création |
 |mis_a_jour_le |TIMESTAMP  | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de dernière modification de user |
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTA1ODUwNzg2NiwtODMyNTU3MjA1XX0=
-->