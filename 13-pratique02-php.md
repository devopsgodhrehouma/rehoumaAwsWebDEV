# **Chapitre 1 : Configuration d'une base de données MySQL**

### **1.1 Installer MySQL**
1. **Installer un serveur local :**
   - Si vous utilisez XAMPP ou MAMP, MySQL est déjà inclus.
   - Assurez-vous que le serveur MySQL est démarré dans votre interface XAMPP/MAMP.

2. **Accéder à phpMyAdmin :**
   - Ouvrez votre navigateur et allez à l'adresse `http://localhost/phpmyadmin`.
   - Vous verrez l'interface phpMyAdmin, qui vous permet de gérer vos bases de données MySQL graphiquement.

---

# **Chapitre 2 : Créer une base de données et une table**

### **2.1 Créer une base de données**

1. Dans phpMyAdmin, cliquez sur l'onglet **Bases de données**.
2. Saisissez le nom de la base de données, par exemple `etudiants_db`, puis cliquez sur **Créer**.

### **2.2 Créer une table**

1. Une fois la base de données créée, sélectionnez-la dans le menu de gauche.
2. Cliquez sur **Nouvelle table**.
3. Donnez un nom à la table, par exemple `etudiants`, et définissez le nombre de colonnes (par exemple 3).
4. Remplissez les colonnes comme suit :
   - **id** : INT, A_I (Auto Increment), PRIMARY
   - **nom** : VARCHAR(100)
   - **age** : INT(11)

Cliquez sur **Sauvegarder** pour créer la table.

---

# **Chapitre 3 : Connecter PHP à la base de données**

### **3.1 Écrire un script de connexion**

Dans votre projet PHP, créez un fichier appelé `config.php` qui contiendra la connexion à la base de données :

```php
<?php
$host = "localhost";  // Hôte (ici localhost pour un serveur local)
$dbname = "etudiants_db";  // Nom de la base de données
$username = "root";  // Nom d'utilisateur (par défaut, "root" sur XAMPP/MAMP)
$password = "";  // Mot de passe (laissez vide pour XAMPP/MAMP)

try {
    // Connexion à la base de données
    $conn = new PDO("mysql:host=$host;dbname=$dbname", $username, $password);
    $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    echo "Connexion réussie à la base de données!";
} catch (PDOException $e) {
    echo "Erreur de connexion : " . $e->getMessage();
}
?>
```

### **3.2 Tester la connexion**

1. Créez un fichier `index.php` et incluez le fichier de connexion :
   ```php
   <?php
   include 'config.php';
   ?>
   ```
2. Ouvrez le fichier dans votre navigateur en allant sur `http://localhost/index.php`.
3. Si tout est correct, vous verrez le message : _"Connexion réussie à la base de données!"_.

---

# **Chapitre 4 : Ajouter des données à la base**

### **4.1 Créer un formulaire pour ajouter des étudiants**

Créez un fichier `ajouter_etudiant.php` contenant un formulaire simple pour ajouter un étudiant :

```php
<form method="POST" action="inserer_etudiant.php">
    Nom : <input type="text" name="nom"><br>
    Âge : <input type="number" name="age"><br>
    <input type="submit" value="Ajouter">
</form>
```

### **4.2 Insérer les données dans la base**

Créez un fichier `inserer_etudiant.php` pour traiter les données du formulaire et insérer un étudiant dans la base de données :

```php
<?php
include 'config.php';

if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $nom = $_POST['nom'];
    $age = $_POST['age'];

    try {
        // Préparer la requête SQL
        $sql = "INSERT INTO etudiants (nom, age) VALUES (:nom, :age)";
        $stmt = $conn->prepare($sql);

        // Lier les valeurs aux paramètres
        $stmt->bindParam(':nom', $nom);
        $stmt->bindParam(':age', $age);

        // Exécuter la requête
        $stmt->execute();
        echo "Étudiant ajouté avec succès!";
    } catch (PDOException $e) {
        echo "Erreur : " . $e->getMessage();
    }
}
?>
```

---

# **Chapitre 5 : Afficher les données de la base**

### **5.1 Récupérer et afficher les étudiants**

Créez un fichier `afficher_etudiants.php` qui affiche la liste des étudiants dans la base de données :

```php
<?php
include 'config.php';

try {
    // Requête pour récupérer tous les étudiants
    $sql = "SELECT * FROM etudiants";
    $stmt = $conn->prepare($sql);
    $stmt->execute();

    // Afficher les résultats
    $resultats = $stmt->fetchAll(PDO::FETCH_ASSOC);

    if ($resultats) {
        foreach ($resultats as $etudiant) {
            echo "ID: " . $etudiant['id'] . " - Nom: " . $etudiant['nom'] . " - Âge: " . $etudiant['age'] . "<br>";
        }
    } else {
        echo "Aucun étudiant trouvé.";
    }
} catch (PDOException $e) {
    echo "Erreur : " . $e->getMessage();
}
?>
```

### **5.2 Tester l’affichage**

1. Ajoutez quelques étudiants via le formulaire `ajouter_etudiant.php`.
2. Ouvrez le fichier `afficher_etudiants.php` dans votre navigateur pour voir la liste des étudiants ajoutés.

---

# **Chapitre 6 : Exercice final**

### **Objectif :**
Vos étudiants doivent créer un mini-système de gestion des étudiants où ils peuvent :
- Ajouter un étudiant.
- Voir la liste des étudiants.
- Supprimer un étudiant (en ajoutant une fonction de suppression).

### **Corrigé pour la suppression :**

1. **Modifier le fichier `afficher_etudiants.php` pour ajouter un bouton de suppression :**
   ```php
   foreach ($resultats as $etudiant) {
       echo "ID: " . $etudiant['id'] . " - Nom: " . $etudiant['nom'] . " - Âge: " . $etudiant['age'];
       echo " <a href='supprimer_etudiant.php?id=" . $etudiant['id'] . "'>Supprimer</a><br>";
   }
   ```

2. **Créer le fichier `supprimer_etudiant.php` pour traiter la suppression :**
   ```php
   <?php
   include 'config.php';

   $id = $_GET['id'];

   try {
       $sql = "DELETE FROM etudiants WHERE id = :id";
       $stmt = $conn->prepare($sql);
       $stmt->bindParam(':id', $id);
       $stmt->execute();
       echo "Étudiant supprimé avec succès!";
   } catch (PDOException $e) {
       echo "Erreur : " . $e->getMessage();
   }

   // Redirection après suppression
   header("Location: afficher_etudiants.php");
   ?>
   ```

---

## **Conclusion**

Cette pratique montre comment configurer et utiliser une base de données avec PHP pour des débutants. Les étapes sont détaillées pour garantir que vos étudiants comprennent comment :
- Créer une base de données.
- Ajouter et afficher des données.
- Gérer des opérations comme l’insertion et la suppression.

