# Relation entre les tables:

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


----------------------------------------------------
----------------------------------------------------
----------------------------------------------------
----------------------------------------------------


## Schéma ASCII de l'Application

```
gestion_etudiants/
│
├── api/
│   ├── etudiants/
│   │   ├── add.php
│   │   ├── update.php
│   │   ├── delete.php
│   │   ├── get.php
│   │   └── getAll.php
│   │
│   └── programmes/
│       ├── add.php
│       ├── update.php
│       ├── delete.php
│       ├── get.php
│       └── getAll.php
│
├── includes/
│   ├── config.php
│   └── functions.php
│
├── public/
│   ├── css/
│   │   └── style.css
│   │
│   ├── js/
│   │   └── script.js
│   │
│   └── index.php
│
└── README.md
```


## 1. Configuration de la Base de Données

### includes/config.php

```php
<?php
define('DB_HOST', 'localhost');
define('DB_USER', 'votre_utilisateur');
define('DB_PASS', 'votre_mot_de_passe');
define('DB_NAME', 'gestion_etudiants');

$conn = new mysqli(DB_HOST, DB_USER, DB_PASS, DB_NAME);

if ($conn->connect_error) {
    die("Échec de la connexion : " . $conn->connect_error);
}
?>
```

## 2. Fonctions Utilitaires

### includes/functions.php

```php
<?php
include_once 'config.php';

// Fonctions pour les étudiants
function ajouterEtudiant($nom, $age, $id_programme) {
    global $conn;
    $sql = "INSERT INTO etudiants (nom, age, id_programme) VALUES (?, ?, ?)";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("sii", $nom, $age, $id_programme);
    return $stmt->execute();
}

function getEtudiants() {
    global $conn;
    $sql = "SELECT e.*, p.code, p.intitule FROM etudiants e 
            LEFT JOIN programme p ON e.id_programme = p.id_programme";
    $result = $conn->query($sql);
    return $result->fetch_all(MYSQLI_ASSOC);
}

function updateEtudiant($id, $nom, $age, $id_programme) {
    global $conn;
    $sql = "UPDATE etudiants SET nom = ?, age = ?, id_programme = ? WHERE id = ?";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("siii", $nom, $age, $id_programme, $id);
    return $stmt->execute();
}

function deleteEtudiant($id) {
    global $conn;
    $sql = "DELETE FROM etudiants WHERE id = ?";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("i", $id);
    return $stmt->execute();
}

function getEtudiant($id) {
    global $conn;
    $sql = "SELECT * FROM etudiants WHERE id = ?";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("i", $id);
    $stmt->execute();
    $result = $stmt->get_result();
    return $result->fetch_assoc();
}

// Fonctions pour les programmes
function ajouterProgramme($code, $intitule) {
    global $conn;
    $sql = "INSERT INTO programme (code, intitule) VALUES (?, ?)";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("ss", $code, $intitule);
    return $stmt->execute();
}

function getProgrammes() {
    global $conn;
    $result = $conn->query("SELECT * FROM programme");
    return $result->fetch_all(MYSQLI_ASSOC);
}

function updateProgramme($id_programme, $code, $intitule) {
    global $conn;
    $sql = "UPDATE programme SET code = ?, intitule = ? WHERE id_programme = ?";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("ssi", $code, $intitule, $id_programme);
    return $stmt->execute();
}

function deleteProgramme($id_programme) {
    global $conn;
    $sql = "DELETE FROM programme WHERE id_programme = ?";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("i", $id_programme);
    return $stmt->execute();
}

function getProgramme($id) {
    global $conn;
    $sql = "SELECT * FROM programme WHERE id_programme = ?";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("i", $id);
    $stmt->execute();
    $result = $stmt->get_result();
    return $result->fetch_assoc();
}
?>
```

## 3. API Endpoints

### api/etudiants/add.php

```php
<?php
include_once '../../includes/functions.php';
header('Content-Type: application/json');

$data = json_decode(file_get_contents('php://input'), true);
$result = ajouterEtudiant($data['nom'], $data['age'], $data['id_programme']);

echo json_encode(['success' => $result]);
?>
```

### api/etudiants/update.php

```php
<?php
include_once '../../includes/functions.php';
header('Content-Type: application/json');

$data = json_decode(file_get_contents('php://input'), true);
$result = updateEtudiant($data['id'], $data['nom'], $data['age'], $data['id_programme']);

echo json_encode(['success' => $result]);
?>
```

### api/etudiants/delete.php

```php
<?php
include_once '../../includes/functions.php';
header('Content-Type: application/json');

$id = $_GET['id'];
$result = deleteEtudiant($id);

echo json_encode(['success' => $result]);
?>
```

### api/etudiants/get.php

```php
<?php
include_once '../../includes/functions.php';
header('Content-Type: application/json');

$id = $_GET['id'];
$etudiant = getEtudiant($id);

echo json_encode($etudiant);
?>
```

### api/etudiants/getAll.php

```php
<?php
include_once '../../includes/functions.php';
header('Content-Type: application/json');

echo json_encode(getEtudiants());
?>
```

### api/programmes/add.php

```php
<?php
include_once '../../includes/functions.php';
header('Content-Type: application/json');

$data = json_decode(file_get_contents('php://input'), true);
$result = ajouterProgramme($data['code'], $data['intitule']);

echo json_encode(['success' => $result]);
?>
```

### api/programmes/update.php

```php
<?php
include_once '../../includes/functions.php';
header('Content-Type: application/json');

$data = json_decode(file_get_contents('php://input'), true);
$result = updateProgramme($data['id'], $data['code'], $data['intitule']);

echo json_encode(['success' => $result]);
?>
```

### api/programmes/delete.php

```php
<?php
include_once '../../includes/functions.php';
header('Content-Type: application/json');

$id = $_GET['id'];
$result = deleteProgramme($id);

echo json_encode(['success' => $result]);
?>
```

### api/programmes/get.php

```php
<?php
include_once '../../includes/functions.php';
header('Content-Type: application/json');

$id = $_GET['id'];
$programme = getProgramme($id);

echo json_encode($programme);
?>
```

### api/programmes/getAll.php

```php
<?php
include_once '../../includes/functions.php';
header('Content-Type: application/json');

echo json_encode(getProgrammes());
?>
```

## 4. Interface Utilisateur

### public/index.php

```php
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gestion des Étudiants et Programmes</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header>
        <h1>Gestion des Étudiants et Programmes</h1>
    </header>

    <main>
        <section id="etudiants">
            <h2>Gestion des Étudiants</h2>
            <button onclick="showForm('etudiant')">Ajouter un étudiant</button>
            <div id="etudiantForm" style="display:none;">
                <h3>Ajouter/Modifier un étudiant</h3>
                <form id="formEtudiant">
                    <input type="hidden" id="etudiantId">
                    <input type="text" id="etudiantNom" placeholder="Nom" required>
                    <input type="number" id="etudiantAge" placeholder="Âge" required>
                    <select id="etudiantProgramme" required>
                        <!-- Options de programmes chargées dynamiquement -->
                    </select>
                    <button type="submit">Enregistrer</button>
                </form>
            </div>
            <table id="tableEtudiants">
                <thead>
                    <tr>
                        <th>Nom</th>
                        <th>Âge</th>
                        <th>Programme</th>
                        <th>Actions</th>
                    </tr>
                </thead>
                <tbody>
                    <!-- Données des étudiants chargées dynamiquement -->
                </tbody>
            </table>
        </section>

        <section id="programmes">
            <h2>Gestion des Programmes</h2>
            <button onclick="showForm('programme')">Ajouter un programme</button>
            <div id="programmeForm" style="display:none;">
                <h3>Ajouter/Modifier un programme</h3>
                <form id="formProgramme">
                    <input type="hidden" id="programmeId">
                    <input type="text" id="programmeCode" placeholder="Code" required>
                    <input type="text" id="programmeIntitule" placeholder="Intitulé" required>
                    <button type="submit">Enregistrer</button>
                </form>
            </div>
            <table id="tableProgrammes">
                <thead>
                    <tr>
                        <th>Code</th>
                        <th>Intitulé</th>
                        <th>Actions</th>
                    </tr>
                </thead>
                <tbody>
                    <!-- Données des programmes chargées dynamiquement -->
                </tbody>
            </table>
        </section>
    </main>

    <script src="js/script.js"></script>
</body>
</html>
```

### public/css/style.css

```css
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 20px;
    background-color: #f4f4f4;
}

header {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 1rem;
    margin-bottom: 20px;
}

h1, h2, h3 {
    margin-bottom: 20px;
}

main {
    display: flex;
    justify-content: space-between;
}

section {
    background: #fff;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
    width: 48%;
}

button {
    background-color: #4CAF50;
    color: white;
    padding: 10px 15px;
    border: none;
    cursor: pointer;
    margin: 5px;
}

button:hover {
    background-color: #45a049;
}

form {
    margin-bottom: 20px;
}

input[type="text"], input[type="number"], select {
    width: 100%;
    padding: 8px;
    margin: 5px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
}

table, th, td {
    border: 1px solid #ddd;
}

th, td {
    text-align: left;
    padding: 12px;
}

th {
    background-color: #f2f2f2;
}

.form-container {
    background-color: #f2f2f2;
    padding: 20px;
    border-radius: 5px;
    margin-bottom: 20px;
}
```

### public/js/script.js

```javascript
document.addEventListener('DOMContentLoaded', () => {
    chargerEtudiants();
    chargerProgrammes();
    setupFormListeners();
});

function setupFormListeners() {
    document.getElementById('formEtudiant').addEventListener('submit', handleEtudiantSubmit);
    document.getElementById('formProgramme').addEventListener('submit', handleProgrammeSubmit);
}

function showForm(type) {
    document.getElementById(`${type}Form`).style.display = 'block';
}

function chargerEtudiants() {
    fetch('../api/etudiants/getAll.php')
        .then(response => response.json())
        .then(data => {
            const tbody = document.querySelector('#tableEtudiants tbody');
            tbody.innerHTML = '';
            data.forEach(etudiant => {
                tbody.innerHTML += `
                    <tr>
                        <td>${etudiant.nom}</td>
                        <td>${etudiant.age}</td>
                        <td>${etudiant.intitule}</td>
                        <td>
                            <button onclick="editEtudiant(${etudiant.id})">Modifier</button>
                            <button onclick="deleteEtudiant(${etudiant.id})">Supprimer</button>
                        </td>
                    </tr>
                `;
            });
        })
        .catch(error => console.error('Erreur:', error));
}


### public/js/script.js (suite)

```javascript
function chargerProgrammes() {
    fetch('../api/programmes/getAll.php')
        .then(response => response.json())
        .then(data => {
            const tbody = document.querySelector('#tableProgrammes tbody');
            tbody.innerHTML = '';
            data.forEach(programme => {
                tbody.innerHTML += `
                    <tr>
                        <td>${programme.code}</td>
                        <td>${programme.intitule}</td>
                        <td>
                            <button onclick="editProgramme(${programme.id_programme})">Modifier</button>
                            <button onclick="deleteProgramme(${programme.id_programme})">Supprimer</button>
                        </td>
                    </tr>
                `;
            });
            updateProgrammeSelect(data);
        })
        .catch(error => console.error('Erreur:', error));
}

function updateProgrammeSelect(programmes) {
    const select = document.getElementById('etudiantProgramme');
    select.innerHTML = '';
    programmes.forEach(programme => {
        select.innerHTML += `<option value="${programme.id_programme}">${programme.intitule}</option>`;
    });
}

function handleEtudiantSubmit(e) {
    e.preventDefault();
    const id = document.getElementById('etudiantId').value;
    const nom = document.getElementById('etudiantNom').value;
    const age = document.getElementById('etudiantAge').value;
    const id_programme = document.getElementById('etudiantProgramme').value;

    const data = { id, nom, age, id_programme };
    const url = id ? '../api/etudiants/update.php' : '../api/etudiants/add.php';

    fetch(url, {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(data)
    })
    .then(response => response.json())
    .then(result => {
        if(result.success) {
            chargerEtudiants();
            document.getElementById('formEtudiant').reset();
            document.getElementById('etudiantForm').style.display = 'none';
        } else {
            alert('Erreur lors de l'opération');
        }
    })
    .catch(error => console.error('Erreur:', error));
}

function handleProgrammeSubmit(e) {
    e.preventDefault();
    const id = document.getElementById('programmeId').value;
    const code = document.getElementById('programmeCode').value;
    const intitule = document.getElementById('programmeIntitule').value;

    const data = { id, code, intitule };
    const url = id ? '../api/programmes/update.php' : '../api/programmes/add.php';

    fetch(url, {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(data)
    })
    .then(response => response.json())
    .then(result => {
        if(result.success) {
            chargerProgrammes();
            document.getElementById('formProgramme').reset();
            document.getElementById('programmeForm').style.display = 'none';
        } else {
            alert('Erreur lors de l'opération');
        }
    })
    .catch(error => console.error('Erreur:', error));
}

function editEtudiant(id) {
    fetch(`../api/etudiants/get.php?id=${id}`)
        .then(response => response.json())
        .then(etudiant => {
            document.getElementById('etudiantId').value = etudiant.id;
            document.getElementById('etudiantNom').value = etudiant.nom;
            document.getElementById('etudiantAge').value = etudiant.age;
            document.getElementById('etudiantProgramme').value = etudiant.id_programme;
            showForm('etudiant');
        })
        .catch(error => console.error('Erreur:', error));
}

function deleteEtudiant(id) {
    if(confirm('Êtes-vous sûr de vouloir supprimer cet étudiant ?')) {
        fetch(`../api/etudiants/delete.php?id=${id}`, { method: 'DELETE' })
            .then(response => response.json())
            .then(result => {
                if(result.success) {
                    chargerEtudiants();
                } else {
                    alert('Erreur lors de la suppression');
                }
            })
            .catch(error => console.error('Erreur:', error));
    }
}

function editProgramme(id) {
    fetch(`../api/programmes/get.php?id=${id}`)
        .then(response => response.json())
        .then(programme => {
            document.getElementById('programmeId').value = programme.id_programme;
            document.getElementById('programmeCode').value = programme.code;
            document.getElementById('programmeIntitule').value = programme.intitule;
            showForm('programme');
        })
        .catch(error => console.error('Erreur:', error));
}

function deleteProgramme(id) {
    if(confirm('Êtes-vous sûr de vouloir supprimer ce programme ?')) {
        fetch(`../api/programmes/delete.php?id=${id}`, { method: 'DELETE' })
            .then(response => response.json())
            .then(result => {
                if(result.success) {
                    chargerProgrammes();
                } else {
                    alert('Erreur lors de la suppression');
                }
            })
            .catch(error => console.error('Erreur:', error));
    }
}
```

## Explication finale

Cette structure de projet réorganisée offre plusieurs avantages :

1. **Séparation des préoccupations** : Le code est divisé en sections logiques (API, interface utilisateur, configuration).

2. **Facilité de maintenance** : Chaque composant est dans son propre fichier, ce qui facilite les mises à jour et le débogage.

3. **Sécurité améliorée** : Les fichiers sensibles (comme `config.php`) sont placés en dehors du répertoire public.

4. **API RESTful** : L'API est organisée de manière RESTful, ce qui la rend plus intuitive et extensible.

5. **Réutilisabilité** : Les fonctions dans `functions.php` peuvent être facilement réutilisées dans d'autres parties de l'application.

Pour utiliser cette application :

1. Configurez votre serveur web pour pointer vers le dossier `public/`.
2. Assurez-vous que PHP et MySQL sont correctement configurés.
3. Importez le schéma de base de données (les tables `etudiants` et `programme`).
4. Ajustez les paramètres de connexion à la base de données dans `includes/config.php`.
5. Accédez à l'application via votre navigateur en ouvrant `index.php`.

Cette structure permet une gestion efficace des étudiants et des programmes, avec des opérations CRUD complètes pour les deux entités. L'interface utilisateur est intuitive et réactive, utilisant JavaScript pour interagir avec l'API sans rechargement de page.






