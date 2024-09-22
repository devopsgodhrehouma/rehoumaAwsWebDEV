# Création d'une application de gestion des employés 

## Étape 1 : Préparation de l'environnement

1. Assurez-vous d'avoir XAMPP installé sur votre ordinateur.
2. Démarrez XAMPP et activez Apache et MySQL.

## Étape 2 : Création de la base de données

1. Ouvrez votre navigateur et allez sur `http://localhost/phpmyadmin`.
2. Cliquez sur l'onglet "SQL" en haut de la page.
3. Copiez le code suivant et collez-le dans la zone de texte :

```sql
CREATE DATABASE IF NOT EXISTS gestion_employes;

USE gestion_employes;

CREATE TABLE IF NOT EXISTS boutique (
    id INT AUTO_INCREMENT PRIMARY KEY,
    libelle VARCHAR(255) NOT NULL
);

CREATE TABLE IF NOT EXISTS employee (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(255) NOT NULL,
    prenom VARCHAR(255) NOT NULL,
    boutique VARCHAR(255) NOT NULL
);

INSERT INTO boutique (libelle) VALUES 
('Zara'),
('H&M'),
('Uniqlo'),
('Mango'),
('Bershka'),
('Pull & Bear'),
('Stradivarius'),
('Massimo Dutti'),
('Gap'),
('Levi\'s');
```

4. Cliquez sur le bouton "Exécuter" en bas de la page.

## Étape 3 : Création du fichier AjoutEmployee.php

1. Ouvrez le Bloc-notes ou un éditeur de texte.
2. Copiez le code suivant et collez-le dans le fichier :

```php
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ajout d'un employé</title>
</head>
<body>
    <h1>Ajout d'un nouvel employé</h1>
    <form action="ValiderAjoutEmployee.php" method="post">
        <label for="nom">Nom :</label>
        <input type="text" id="nom" name="nomF" required><br><br>
        
        <label for="prenom">Prénom :</label>
        <input type="text" id="prenom" name="prenomF" required><br><br>
        
        <fieldset>
            <legend>Boutique :</legend>
            <?php
            $serveur = "localhost";
            $utilisateur = "root";
            $pwd = "";
            $bd = "gestion_employes";

            $conn = new mysqli($serveur, $utilisateur, $pwd, $bd);

            if ($conn->connect_error) {
                die("Connexion échouée : " . $conn->connect_error);
            }

            $query = "SELECT * FROM boutique";
            $result = $conn->query($query);

            if ($result->num_rows > 0) {
                while($row = $result->fetch_assoc()) {
                    echo '<input type="radio" id="' . $row['libelle'] . '" name="boutiqueF" value="' . $row['libelle'] . '" required>';
                    echo '<label for="' . $row['libelle'] . '">' . $row['libelle'] . '</label><br>';
                }
            }

            $conn->close();
            ?>
        </fieldset>
        <br>
        <input type="submit" value="Ajouter">
    </form>
</body>
</html>
```

3. Enregistrez le fichier sous le nom "AjoutEmployee.php" dans le dossier `C:\xampp\htdocs\gestion_employes\`.

## Étape 4 : Création du fichier ValiderAjoutEmployee.php

1. Ouvrez un nouveau fichier dans le Bloc-notes ou votre éditeur de texte.
2. Copiez le code suivant et collez-le dans le fichier :

```php
<?php
$serveur = "localhost";
$utilisateur = "root";
$pwd = "";
$bd = "gestion_employes";

$conn = new mysqli($serveur, $utilisateur, $pwd, $bd);

if ($conn->connect_error) {
    die("Connexion échouée : " . $conn->connect_error);
}

$nomR = $conn->real_escape_string($_POST['nomF']);
$prenomR = $conn->real_escape_string($_POST['prenomF']);
$boutiqueR = $conn->real_escape_string($_POST['boutiqueF']);

$query = "INSERT INTO employee (nom, prenom, boutique) VALUES (?, ?, ?)";
$stmt = $conn->prepare($query);
$stmt->bind_param("sss", $nomR, $prenomR, $boutiqueR);

if ($stmt->execute()) {
    echo "Employé ajouté avec succès.";
    echo "<br><a href='AjoutEmployee.php'>Retour au formulaire</a>";
} else {
    echo "Erreur lors de l'ajout de l'employé : " . $stmt->error;
}

$stmt->close();
$conn->close();
?>
```

3. Enregistrez le fichier sous le nom "ValiderAjoutEmployee.php" dans le même dossier que AjoutEmployee.php.

## Étape 5 : Test de l'application

1. Ouvrez votre navigateur web.
2. Dans la barre d'adresse, tapez : `http://localhost/gestion_employes/AjoutEmployee.php`
3. Vous devriez voir un formulaire pour ajouter un nouvel employé.
4. Remplissez le formulaire avec des informations d'exemple :
   - Nom : Dupont
   - Prénom : Jean
   - Choisissez une boutique en cliquant sur l'un des boutons radio
5. Cliquez sur le bouton "Ajouter".
6. Vous devriez voir un message confirmant que l'employé a été ajouté avec succès.
7. Cliquez sur le lien "Retour au formulaire" pour ajouter un autre employé si vous le souhaitez.



# Table récapitulant les méthodes **built-in** (intégrées) utilisées dans notre code PHP pour la création de l'application de gestion des employés :

| Méthode PHP intégrée      | Description                                                                                       | Exemple d'utilisation                                             |
|---------------------------|---------------------------------------------------------------------------------------------------|-------------------------------------------------------------------|
| **`new mysqli()`**         | Crée une nouvelle connexion à une base de données MySQL en utilisant l'extension MySQLi.           | `$conn = new mysqli($serveur, $utilisateur, $pwd, $bd);`          |
| **`connect_error`**        | Vérifie s'il y a eu une erreur lors de la connexion à la base de données.                         | `if ($conn->connect_error) { ... }`                               |
| **`die()`**                | Arrête l'exécution du script et affiche un message d'erreur si la connexion échoue.               | `die("Connexion échouée : " . $conn->connect_error);`             |
| **`query()`**              | Exécute une requête SQL sur la base de données et retourne un objet MySQLi result.                | `$result = $conn->query($query);`                                 |
| **`num_rows`**             | Renvoie le nombre de lignes affectées ou retournées par une requête SQL.                          | `if ($result->num_rows > 0) { ... }`                              |
| **`fetch_assoc()`**        | Récupère une ligne du résultat sous forme d'un tableau associatif (clé-valeur).                   | `$row = $result->fetch_assoc();`                                  |
| **`real_escape_string()`**  | Échappe les caractères spéciaux dans une chaîne pour les utiliser dans une requête SQL.            | `$nomR = $conn->real_escape_string($_POST['nomF']);`              |
| **`prepare()`**            | Prépare une requête SQL pour l'exécution avec des paramètres (prévention d'injections SQL).       | `$stmt = $conn->prepare($query);`                                 |
| **`bind_param()`**         | Lie des variables aux paramètres de la requête préparée.                                          | `$stmt->bind_param("sss", $nomR, $prenomR, $boutiqueR);`          |
| **`execute()`**            | Exécute la requête SQL préparée.                                                                  | `if ($stmt->execute()) { ... }`                                   |
| **`close()`**              | Ferme la connexion à la base de données ou l'objet MySQLi après utilisation.                      | `$stmt->close(); $conn->close();`                                 |

Cette table résume les méthodes intégrées qui sont utilisées pour interagir avec la base de données MySQL dans le cadre de l'application de gestion des employés.
