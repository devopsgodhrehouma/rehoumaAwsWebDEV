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

# Complétez l'annexe 2 
- Développez un mini-projet de gestion des étudiants en utilisant les tables fournies (etudiants et programme). 
- Complétez l'annexe 2 . Il contient du code pour vous aider. Il suffit de suivre le même style ci-haut !
- Créez un fichier `AjoutEtudiant.php`
- Créez un fichier `ValiderAjoutEtudiant.php`
- Fournissez le code source de tous les fichiers PHP créés et des captures d'écran montrant le fonctionnement de votre application.


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

# Annexe 2 - la partie 10%


# Projet de Gestion des Étudiants (10%)

## Étape 1 : Création de la base de données

Créez un fichier `create_database.sql` avec le contenu suivant :

```sql
CREATE DATABASE IF NOT EXISTS gestion_etudiants;

USE gestion_etudiants;

CREATE TABLE programme (
    id_programme INT(11) PRIMARY KEY AUTO_INCREMENT,
    code VARCHAR(10) NOT NULL,
    intitule VARCHAR(100) NOT NULL
);

CREATE TABLE etudiants (
    id INT(11) PRIMARY KEY AUTO_INCREMENT,
    nom VARCHAR(100) NOT NULL,
    age INT(11) NOT NULL,
    id_programme INT(11),
    FOREIGN KEY (id_programme) REFERENCES programme(id_programme)
);

-- Ajoutez ici des INSERT INTO pour peupler la table programme
```

## Étape 2 : Création du fichier AjoutEtudiant.php

```php
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Ajout d'un Étudiant</title>
</head>
<body>
    <h1>Ajout d'un nouvel étudiant</h1>
    <form action="ValiderAjoutEtudiant.php" method="post">
        <label for="nom">Nom :</label>
        <input type="text" id="nom" name="nomF" required><br><br>
        
        <label for="age">Âge :</label>
        <input type="number" id="age" name="ageF" required><br><br>
        
        <fieldset>
            <legend>Programme :</legend>
            <?php
            // Ajoutez ici le code pour se connecter à la base de données
            // et afficher les programmes sous forme de boutons radio
            ?>
        </fieldset>
        <br>
        <input type="submit" value="Ajouter">
    </form>
</body>
</html>
```

## Étape 3 : Création du fichier ValiderAjoutEtudiant.php

```php
<?php
// Ajoutez ici le code pour la connexion à la base de données

// Récupération et nettoyage des données du formulaire
$nomR = // Nettoyez et récupérez le nom
$ageR = // Nettoyez et récupérez l'âge
$programmeR = // Nettoyez et récupérez l'id du programme

// Préparation et exécution de la requête d'insertion
// Utilisez une requête préparée pour insérer les données dans la table etudiants

// Gestion des erreurs et affichage du message de confirmation
if (/* l'insertion a réussi */) {
    echo "Étudiant ajouté avec succès.";
    echo "<br><a href='AjoutEtudiant.php'>Retour au formulaire</a>";
} else {
    echo "Erreur lors de l'ajout de l'étudiant : " . /* message d'erreur */;
}

// Fermeture de la connexion
?>
```

## Instructions pour les étudiants :

1. Complétez le fichier `create_database.sql` en ajoutant des INSERT INTO pour peupler la table programme.
2. Dans `AjoutEtudiant.php`, ajoutez le code PHP nécessaire pour :
   - Se connecter à la base de données
   - Récupérer les programmes depuis la base de données
   - Afficher les programmes sous forme de boutons radio
3. Complétez `ValiderAjoutEtudiant.php` en ajoutant le code pour :
   - Se connecter à la base de données
   - Récupérer et nettoyer les données du formulaire
   - Préparer et exécuter la requête d'insertion
   - Gérer les erreurs et afficher un message de succès
4. Assurez-vous d'utiliser des requêtes préparées pour toutes les opérations d'insertion dans la base de données.
5. Testez votre application et fournissez des captures d'écran montrant son fonctionnement.

Expliquez brièvement le rôle de chaque fichier et les principales modifications que vous avez apportées.
