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
Créez un fichier `AjoutEtudiant.php` avec le contenu de base suivant :
Créez un fichier `ListeEtudiants.php` avec le contenu de base suivant :
Créez un fichier `ValiderAjoutEtudiant.php` avec le contenu de base suivant :

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

Créez un fichier `AjoutEtudiant.php` avec le contenu de base suivant :

```php
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Ajouter un Étudiant</title>
</head>
<body>
    <h1>Ajouter un Nouvel Étudiant</h1>
    <form action="ValiderAjoutEtudiant.php" method="post">
        <label for="nom">Nom :</label>
        <input type="text" id="nom" name="nom" required><br><br>
        
        <label for="age">Âge :</label>
        <input type="number" id="age" name="age" required><br><br>
        
        <label for="programme">Programme :</label>
        <select id="programme" name="programme" required>
            <?php
            // Ajoutez ici le code pour récupérer et afficher les programmes depuis la base de données
            ?>
        </select><br><br>
        
        <input type="submit" value="Ajouter">
    </form>
</body>
</html>
```

## Étape 3 : Création du fichier ValiderAjoutEtudiant.php

Créez un fichier `ValiderAjoutEtudiant.php` avec le contenu de base suivant :

```php
<?php
// Ajoutez ici le code pour la connexion à la base de données

if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $nom = // Récupérez et nettoyez la valeur de $_POST['nom']
    $age = // Récupérez et nettoyez la valeur de $_POST['age']
    $id_programme = // Récupérez et nettoyez la valeur de $_POST['programme']

    // Ajoutez ici le code pour insérer l'étudiant dans la base de données
    
    // Ajoutez ici le code pour gérer les erreurs et afficher un message de succès
}
?>
```

## Étape 4 : Création du fichier ListeEtudiants.php

Créez un fichier `ListeEtudiants.php` avec le contenu de base suivant :

```php
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Liste des Étudiants</title>
</head>
<body>
    <h1>Liste des Étudiants</h1>
    <table border="1">
        <tr>
            <th>Nom</th>
            <th>Âge</th>
            <th>Programme</th>
        </tr>
        <?php
        // Ajoutez ici le code pour récupérer et afficher les étudiants depuis la base de données
        ?>
    </table>
</body>
</html>
```

## Instructions pour les étudiants :

1. Complétez le fichier `create_database.sql` en ajoutant des INSERT INTO pour peupler la table programme.
2. Dans `AjoutEtudiant.php`, ajoutez le code PHP nécessaire pour récupérer les programmes depuis la base de données et les afficher dans le menu déroulant.
3. Complétez `ValiderAjoutEtudiant.php` en ajoutant le code pour :
   - Se connecter à la base de données
   - Récupérer et nettoyer les données du formulaire
   - Insérer l'étudiant dans la base de données
   - Gérer les erreurs et afficher un message de succès
4. Dans `ListeEtudiants.php`, ajoutez le code PHP pour récupérer tous les étudiants de la base de données et les afficher dans le tableau HTML.
5. Assurez-vous d'utiliser PDO pour toutes les opérations de base de données.
6. Testez votre application et fournissez des captures d'écran montrant son fonctionnement.

Expliquez brièvement le rôle de chaque fichier et les principales modifications que vous avez apportées.
