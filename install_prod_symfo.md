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

|id_jardin |INT  | PRIMARY KEY, UNSIGNED, NOT NULL, AUTO_INCREMENT| L’identifiant de l'utilisateur
| title | VARCHAR(64) | NOT NULL | pseudo de l'utilisateur |
| texte |VARCHAR(64)  |NOT NULL  | mot de passe de l'utilisateur |
| adresse |VARCHAR(240)  |NOT NULL  | email de l'utilisateur |
| code postal|INT  |NOT NULL  | te de l'utilisateur |
| ville  |VARCHAR(64)  |NOT NULL ,DEFAULT USER  | role de l'utilisateur  |
| point d'eau | VARCHAR(128) | NULL,DEFAULT AVATAR | avatar  de l'utilisateur |
|outils | TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de création |
| abri de jardin|INT  |NOT NULL  | te de l'utilisateur |
| photos |VARCHAR(64)  |NOT NULL ,DEFAULT USER  | role de l'utilisateur  |
| etat du jardin | VARCHAR(128) | NULL,DEFAULT AVATAR | avatar  de l'utilisateur |
|surface| TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de création |
| etat du jardin | VARCHAR(128) | NULL,DEFAULT AVATAR | avatar  de l'utilisateur |

|crée le | TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de création |
 |mis_a_jour_le |TIMESTAMP  | NOT NULL, DEFAULT CURRENT_TIMESTAMP | La date de dernière modification de user |
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAxNTAzMjg1MywtODMyNTU3MjA1XX0=
-->