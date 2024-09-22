# Création d'une application de gestion des employés v2 avec PDO

## Étape 1 : Création du dossier

1. Créez un nouveau dossier nommé "gestion_employes_v2" dans le répertoire `C:\xampp\htdocs\`.

## Étape 2 : Création du fichier AjoutEmployee.php

1. Dans le dossier "gestion_employes_v2", créez un nouveau fichier nommé "AjoutEmployee.php".
2. Copiez et collez le code suivant dans ce fichier :

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
            $serveur = 'localhost';
            $utilisateur = 'root';
            $pwd = '';
            $bd = 'gestion_employes';

            try {
                $conn = new PDO("mysql:host=" . $serveur . ";dbname=" . $bd, $utilisateur, $pwd);
                $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

                $query = "SELECT * FROM boutique";
                $stmt = $conn->query($query);

                if ($stmt->rowCount() > 0) {
                    while($row = $stmt->fetch(PDO::FETCH_ASSOC)) {
                        echo '<input type="radio" id="' . $row['libelle'] . '" name="boutiqueF" value="' . $row['libelle'] . '" required>';
                        echo '<label for="' . $row['libelle'] . '">' . $row['libelle'] . '</label><br>';
                    }
                }
            } catch (PDOException $e) {
                die("Erreur de connexion : " . $e->getMessage());
            }

            $conn = null;
            ?>
        </fieldset>
        <br>
        <input type="submit" value="Ajouter">
    </form>
</body>
</html>
```

## Étape 3 : Création du fichier ValiderAjoutEmployee.php

1. Dans le même dossier, créez un nouveau fichier nommé "ValiderAjoutEmployee.php".
2. Copiez et collez le code suivant dans ce fichier :

```php
<?php
$serveur = 'localhost';
$utilisateur = 'root';
$pwd = '';
$bd = 'gestion_employes';

try {
    $conn = new PDO("mysql:host=" . $serveur . ";dbname=" . $bd, $utilisateur, $pwd);
    $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

    $nomR = filter_input(INPUT_POST, 'nomF', FILTER_SANITIZE_STRING);
    $prenomR = filter_input(INPUT_POST, 'prenomF', FILTER_SANITIZE_STRING);
    $boutiqueR = filter_input(INPUT_POST, 'boutiqueF', FILTER_SANITIZE_STRING);

    $query = "INSERT INTO employee (nom, prenom, boutique) VALUES (:nom, :prenom, :boutique)";
    $stmt = $conn->prepare($query);
    $stmt->bindParam(':nom', $nomR);
    $stmt->bindParam(':prenom', $prenomR);
    $stmt->bindParam(':boutique', $boutiqueR);

    if ($stmt->execute()) {
        echo "Employé ajouté avec succès.";
        echo "<br><a href='AjoutEmployee.php'>Retour au formulaire</a>";
    } else {
        echo "Erreur lors de l'ajout de l'employé.";
    }
} catch (PDOException $e) {
    die("Erreur : " . $e->getMessage());
}

$conn = null;
?>
```

## Étape 4 : Test de l'application

1. Assurez-vous que XAMPP est en cours d'exécution (Apache et MySQL).
2. Ouvrez votre navigateur et accédez à `http://localhost/gestion_employes_v2/AjoutEmployee.php`.
3. Remplissez le formulaire avec les informations d'un employé.
4. Cliquez sur "Ajouter" pour soumettre le formulaire.
5. Vérifiez que l'employé a été ajouté avec succès.

- Cette version utilise PDO pour une meilleure sécurité et une gestion plus moderne des connexions à la base de données. 
- Elle inclut également une meilleure gestion des erreurs et un nettoyage des entrées utilisateur.
