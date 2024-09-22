# Gestion des Employés et des Étudiants avec PHP et MySQL (100%)

# Section 1 : Mise en pratique - Gestion des Employés (36%)

### Partie 1 : Projet MySQLi (18%)
1. Créez un dossier nommé "gestion_employes_mysqli" dans votre répertoire htdocs.
2. Copiez-collez le code fourni pour AjoutEmployee.php et ValiderAjoutEmployee.php utilisant MySQLi dans ce dossier (voir partie1.md).
3. Configurez correctement la base de données.
4. Testez l'application en ajoutant un nouvel employé.
5. Envoyez un screenshot du formulaire rempli et un autre du message de confirmation après l'ajout.

### Partie 2 : Projet PDO (18%)
1. Créez un dossier nommé "gestion_employes_pdo" dans votre répertoire htdocs.
2. Copiez-collez le code fourni pour AjoutEmployee.php et ValiderAjoutEmployee.php utilisant PDO dans ce dossier  (voir partie2.md).
3. Configurez correctement la base de données.
4. Testez l'application en ajoutant un nouvel employé.
5. Envoyez un screenshot du formulaire rempli et un autre du message de confirmation après l'ajout.

# Section 2 : Compréhension des mécanismes (54%)

### Partie 1 : MySQLi (27%)

1. (3%) Qu'est-ce que MySQLi et pourquoi est-il utilisé en PHP ?
2. (3%) Énumérez et expliquez les paramètres nécessaires pour établir une connexion MySQLi.
3. (3%) Écrivez une ligne de code PHP pour établir une connexion MySQLi à une base de données.
4. (3%) Expliquez la différence entre mysql_* et mysqli_*. Pourquoi devriez-vous utiliser mysqli_* ?
5. (3%) Comment préparez-vous une requête d'insertion avec MySQLi ? Donnez un exemple de code.
6. (3%) Quelle est la différence entre query() et prepare() en MySQLi ? Dans quels cas utiliseriez-vous l'un plutôt que l'autre ?
7. (3%) Comment récupérez-vous les résultats d'une requête SELECT avec MySQLi ? Fournissez un exemple de code.
8. (3%) Expliquez le rôle du fichier AjoutEmployee.php dans le projet MySQLi. Que fait-il et comment interagit-il avec la base de données ?
9. (3%) Comment gérez-vous les erreurs avec MySQLi ? Donnez un exemple de code.

### Partie 2 : PDO (27%)

1. (3%) Qu'est-ce que PDO et quels sont ses avantages par rapport à MySQLi ?
2. (3%) Énumérez et expliquez les paramètres nécessaires pour établir une connexion PDO.
3. (3%) Écrivez une ligne de code PHP pour établir une connexion PDO à une base de données MySQL.
4. (3%) Comment préparez-vous et exécutez-vous une requête d'insertion avec PDO ? Donnez un exemple de code.
5. (3%) Expliquez ce qu'est une requête préparée et pourquoi elle est importante pour la sécurité.
6. (3%) Comment récupérez-vous les résultats d'une requête SELECT avec PDO ? Fournissez un exemple de code.
7. (3%) Quelle est la différence entre bindParam() et bindValue() en PDO ? Quand utiliseriez-vous l'un plutôt que l'autre ?
8. (3%) Expliquez le rôle du fichier ValiderAjoutEmployee.php dans le projet PDO. Que fait-il et comment interagit-il avec la base de données ?
9. (3%) Comment gérez-vous les exceptions avec PDO ? Donnez un exemple de code.

# Section 3 : Projet de Gestion des Étudiants (10%)

Développez un mini-projet de gestion des étudiants en utilisant les tables fournies (etudiants et programme). Votre projet doit inclure :

1. (2%) Un script SQL pour créer les tables dans la base de données.
2. (6%) 
4. (2%) Utilisation de PDO ou mysqli pour toutes les opérations de base de données.

Fournissez le code source de tous les fichiers PHP créés et des captures d'écran montrant le fonctionnement de votre application.


# ANNEXE : Relation entre les tables:

### **Structure de la Base de Données pour la Gestion des Étudiants et de leurs Programmes d'Études**

#### Diagramme ASCII des Tables :

```
+--------------------------------+     +-------------------------------+
|           etudiants            |     |           programme           |
+--------------------------------+     +-------------------------------+
| id           | INT(11)         |<-+  | id_programme | INT(11)        |
| nom          | VARCHAR(100)    |  |  | code         | VARCHAR(10)    |
| age          | INT(11)         |  |  | intitule     | VARCHAR(100)   |
| id_programme | INT(11)         |--+  +-------------------------------+
+--------------------------------+
```

#### Description des Tables :

- **Table `etudiants`** :
  - **id** : Clé primaire, identifiant unique pour chaque étudiant.
  - **nom** : Nom de l'étudiant.
  - **age** : Âge de l'étudiant.
  - **id_programme** : Clé étrangère qui fait référence à `id_programme` dans la table `programme`.

- **Table `programme`** :
  - **id_programme** : Clé primaire, identifiant unique pour chaque programme.
  - **code** : Code abrégé du programme, par exemple `LEA.E3`.
  - **intitule** : Titre complet du programme, tel que "SPÉCIALISTE EN INTELLIGENCE ARTIFICIELLE".

#### Relations entre les Tables :

- **Relation Many-to-One** : 
  - Plusieurs étudiants peuvent être inscrits dans un même programme. La clé étrangère `id_programme` dans la table `etudiants` permet de relier chaque étudiant à son programme d'études spécifique.

