# **Chapitre 1 : Introduction à PHP**

### **1.1 Installation de PHP**
1. Installer un serveur local comme XAMPP ou MAMP.
2. Créer un fichier PHP et le nommer `index.php`.
3. Tester votre installation en écrivant un simple script PHP :
   ```php
   <?php
   echo "Hello, world!";
   ?>
   ```
4. Ouvrir ce fichier dans le navigateur en accédant à `http://localhost/index.php`.

### **1.2 Syntaxe de base en PHP**

1. **Variables et types de données**
   - Les variables commencent par un `$` suivi du nom de la variable.
   - Types : `string`, `integer`, `float`, `boolean`, `array`, etc.

   Exemple :
   ```php
   <?php
   $nom = "Marie";
   $age = 25;
   $estEtudiant = true;
   ?>
   ```

2. **Commentaires**
   ```php
   // Ceci est un commentaire sur une ligne.
   /* Ceci est un commentaire
      sur plusieurs lignes. */
   ```

---

# **Exercice 1 : Créer un script PHP simple**

### **Objectif :**
Créer un script PHP qui affiche le nom et l'âge d'une personne.

### **Corrigé :**
```php
<?php
$nom = "Jean";
$age = 30;
echo "Nom : " . $nom . "<br>";
echo "Âge : " . $age;
?>
```

---

# **Chapitre 2 : Les structures de contrôle**

### **2.1 Les conditions**

1. **if, else, else if**
   ```php
   <?php
   $note = 15;
   if ($note >= 10) {
       echo "Admis";
   } else {
       echo "Échoué";
   }
   ?>
   ```

2. **Switch**
   ```php
   <?php
   $jour = "lundi";
   switch ($jour) {
       case "lundi":
           echo "C'est le début de la semaine.";
           break;
       case "vendredi":
           echo "C'est bientôt le week-end.";
           break;
       default:
           echo "Jour inconnu.";
   }
   ?>
   ```

---

# **Exercice 2 : Utiliser les structures conditionnelles**

### **Objectif :**
Écrire un script PHP qui affiche si une personne est mineure ou majeure en fonction de son âge.

### **Corrigé :**
```php
<?php
$age = 17;
if ($age >= 18) {
    echo "Vous êtes majeur.";
} else {
    echo "Vous êtes mineur.";
}
?>
```

---

## **Chapitre 3 : Les boucles**

### **3.1 Boucle `for`**
```php
<?php
for ($i = 1; $i <= 10; $i++) {
    echo "Nombre : " . $i . "<br>";
}
?>
```

### **3.2 Boucle `while`**
```php
<?php
$i = 1;
while ($i <= 5) {
    echo "Compteur : " . $i . "<br>";
    $i++;
}
?>
```

---

# **Exercice 3 : Compter avec une boucle**

### **Objectif :**
Créer un script qui affiche les nombres de 1 à 5 en utilisant une boucle `while`.

### **Corrigé :**
```php
<?php
$i = 1;
while ($i <= 5) {
    echo $i . "<br>";
    $i++;
}
?>
```

---

# **Chapitre 4 : Les fonctions**

### **4.1 Définir et appeler une fonction**
```php
<?php
function direBonjour($nom) {
    return "Bonjour, " . $nom . "!";
}
echo direBonjour("Alice");
?>
```

---

# **Exercice 4 : Créer une fonction**

### **Objectif :**
Écrire une fonction qui prend deux nombres et retourne leur somme.

### **Corrigé :**
```php
<?php
function additionner($a, $b) {
    return $a + $b;
}
echo additionner(5, 7);
?>
```

---

# **Chapitre 5 : Les tableaux**

### **5.1 Tableaux simples**
```php
<?php
$fruits = array("Pomme", "Banane", "Orange");
echo $fruits[1]; // Affiche "Banane"
?>
```

### **5.2 Tableaux associatifs**
```php
<?php
$personne = array("nom" => "Paul", "âge" => 32);
echo $personne["nom"]; // Affiche "Paul"
?>
```

---

## **Exercice 5 : Manipuler des tableaux**

### **Objectif :**
Créer un tableau associatif pour stocker le nom, l'âge et la profession d'une personne. Afficher ces informations.

### **Corrigé :**
```php
<?php
$personne = array("nom" => "Jean", "âge" => 45, "profession" => "Professeur");
echo "Nom : " . $personne["nom"] . "<br>";
echo "Âge : " . $personne["âge"] . "<br>";
echo "Profession : " . $personne["profession"];
?>
```

---

# **Chapitre 6 : Gestion des formulaires**

### **6.1 Récupérer les données d'un formulaire**
```php
<form method="POST" action="traitement.php">
    Nom : <input type="text" name="nom">
    <input type="submit" value="Envoyer">
</form>
```

```php
// traitement.php
<?php
$nom = $_POST['nom'];
echo "Bonjour, " . $nom;
?>
```

---

# **Exercice 6 : Créer un formulaire et traiter les données**

### **Objectif :**
Créer un formulaire qui demande le nom et l'âge de l'utilisateur, et affiche ces informations.

### **Corrigé :**
```php
<form method="POST" action="affiche.php">
    Nom : <input type="text" name="nom">
    Âge : <input type="number" name="age">
    <input type="submit" value="Envoyer">
</form>

<!-- affiche.php -->
<?php
$nom = $_POST['nom'];
$age = $_POST['age'];
echo "Nom : " . $nom . "<br>";
echo "Âge : " . $age;
?>
```

---

# **Conclusion**
Ce tutoriel couvre les bases de PHP, allant de la syntaxe simple aux tableaux et formulaires. Chaque chapitre est accompagné d'exercices pour aider vos étudiants à appliquer ce qu'ils ont appris. Vous pouvez maintenant passer à des sujets plus avancés, comme la gestion des fichiers, les sessions, et la connexion à une base de données MySQL.

