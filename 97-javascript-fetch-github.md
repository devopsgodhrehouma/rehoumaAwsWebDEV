# Tutoriel : Application de recherche d'utilisateurs GitHub (HTML, CSS, JavaScript)

# Tous le code :


```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Recherche d'utilisateurs GitHub</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        .user-card {
            transition: all 0.3s ease;
        }
        .user-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }
        .user-avatar {
            width: 100px;
            height: 100px;
            object-fit: cover;
            border-radius: 50%;
        }
    </style>
</head>
<body>
    <div class="container mt-5">
        <h1 class="text-center mb-4">Recherche d'utilisateurs GitHub</h1>
        <div class="row justify-content-center">
            <div class="col-md-6">
                <input type="text" id="searchInput" class="form-control mb-4" placeholder="Entrez un nom d'utilisateur">
            </div>
        </div>
        <div id="results" class="row g-4"></div>
    </div>

    <script>
        const searchInput = document.getElementById('searchInput');
        const resultsContainer = document.getElementById('results');

        searchInput.addEventListener('input', debounce(searchUsers, 300));

        function debounce(func, delay) {
            let timeoutId;
            return function (...args) {
                clearTimeout(timeoutId);
                timeoutId = setTimeout(() => func.apply(this, args), delay);
            };
        }

        async function searchUsers() {
            const searchTerm = searchInput.value.trim();
            if (searchTerm.length === 0) {
                resultsContainer.innerHTML = '';
                return;
            }

            try {
                const response = await fetch(`https://api.github.com/search/users?q=${searchTerm}`);
                const data = await response.json();
                displayUsers(data.items.slice(0, 8));
            } catch (error) {
                console.error('Erreur lors de la recherche:', error);
            }
        }

        async function displayUsers(users) {
            resultsContainer.innerHTML = '';
            for (const user of users) {
                try {
                    const userResponse = await fetch(user.url);
                    const userData = await userResponse.json();
                    const userCard = createUserCard(userData);
                    resultsContainer.appendChild(userCard);
                } catch (error) {
                    console.error('Erreur lors de la récupération des détails de l\'utilisateur:', error);
                }
            }
        }

        function createUserCard(user) {
            const card = document.createElement('div');
            card.className = 'col-md-3 mb-4';
            card.innerHTML = `
                <div class="card user-card h-100">
                    <img src="${user.avatar_url}" class="user-avatar card-img-top mx-auto mt-3" alt="${user.login}">
                    <div class="card-body text-center">
                        <h5 class="card-title">${user.name || user.login}</h5>
                        <p class="card-text">
                            <small class="text-muted">@${user.login}</small><br>
                            ${user.bio ? `<small>${user.bio}</small><br>` : ''}
                            <small>Repos: ${user.public_repos} | Followers: ${user.followers}</small>
                        </p>
                        <a href="${user.html_url}" class="btn btn-primary btn-sm" target="_blank">Voir le profil</a>
                    </div>
                </div>
            `;
            return card;
        }
    </script>
</body>
</html>

```

# Sinon suivez les étapes : 

# Étape 1 : Création du fichier HTML

Créez un nouveau fichier nommé `index.html` et copiez-y le code HTML suivant :

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Recherche d'utilisateurs GitHub</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container mt-5">
        <h1 class="text-center mb-4">Recherche d'utilisateurs GitHub</h1>
        <div class="row justify-content-center">
            <div class="col-md-6">
                <input type="text" id="searchInput" class="form-control mb-4" placeholder="Entrez un nom d'utilisateur">
            </div>
        </div>
        <div id="results" class="row g-4"></div>
    </div>
    <script src="script.js"></script>
</body>
</html>
```

# Étape 2 : Création du fichier CSS

Créez un nouveau fichier nommé `styles.css` et ajoutez-y le code CSS suivant :

```css
.user-card {
    transition: all 0.3s ease;
}

.user-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
}

.user-avatar {
    width: 100px;
    height: 100px;
    object-fit: cover;
    border-radius: 50%;
}
```

# Étape 3 : Création du fichier JavaScript

Créez un nouveau fichier nommé `script.js` et ajoutez-y le code JavaScript suivant :

```javascript
const searchInput = document.getElementById('searchInput');
const resultsContainer = document.getElementById('results');

searchInput.addEventListener('input', debounce(searchUsers, 300));

function debounce(func, delay) {
    let timeoutId;
    return function (...args) {
        clearTimeout(timeoutId);
        timeoutId = setTimeout(() => func.apply(this, args), delay);
    };
}

async function searchUsers() {
    const searchTerm = searchInput.value.trim();
    if (searchTerm.length === 0) {
        resultsContainer.innerHTML = '';
        return;
    }

    try {
        const response = await fetch(`https://api.github.com/search/users?q=${searchTerm}`);
        const data = await response.json();
        displayUsers(data.items.slice(0, 8));
    } catch (error) {
        console.error('Erreur lors de la recherche:', error);
    }
}

async function displayUsers(users) {
    resultsContainer.innerHTML = '';
    for (const user of users) {
        try {
            const userResponse = await fetch(user.url);
            const userData = await userResponse.json();
            const userCard = createUserCard(userData);
            resultsContainer.appendChild(userCard);
        } catch (error) {
            console.error('Erreur lors de la récupération des détails de l\'utilisateur:', error);
        }
    }
}

function createUserCard(user) {
    const card = document.createElement('div');
    card.className = 'col-md-3 mb-4';
    card.innerHTML = `
        <div class="card user-card h-100">
            <img src="${user.avatar_url}" class="user-avatar card-img-top mx-auto mt-3" alt="${user.login}">
            <div class="card-body text-center">
                <h5 class="card-title">${user.name || user.login}</h5>
                <p class="card-text">
                    <small class="text-muted">@${user.login}</small><br>
                    ${user.bio ? `<small>${user.bio}</small><br>` : ''}
                    <small>Repos: ${user.public_repos} | Followers: ${user.followers}</small>
                </p>
                <a href="${user.html_url}" class="btn btn-primary btn-sm" target="_blank">Voir le profil</a>
            </div>
        </div>
    `;
    return card;
}
```

# Étape 4 : Explication du code

1. **HTML** : La structure de base de la page avec un champ de recherche et un conteneur pour les résultats.

2. **CSS** : Styles pour les cartes d'utilisateur, avec des effets de survol et de transition.

3. **JavaScript** :
   - `debounce` : Fonction pour limiter le nombre d'appels à l'API lors de la saisie.
   - `searchUsers` : Fonction pour rechercher les utilisateurs via l'API GitHub.
   - `displayUsers` : Fonction pour afficher les utilisateurs trouvés.
   - `createUserCard` : Fonction pour créer une carte HTML pour chaque utilisateur.

# Étape 5 : Utilisation de l'application

1. Ouvrez le fichier `index.html` dans un navigateur web.
2. Commencez à taper un nom d'utilisateur dans le champ de recherche.
3. L'application recherchera automatiquement les utilisateurs après une courte pause dans la saisie.
4. Les résultats s'afficheront sous forme de cartes avec les informations de l'utilisateur.

# Étape 6 : Personnalisation (optionnel)

Vous pouvez personnaliser davantage l'application en :
- Ajoutant une gestion des erreurs plus détaillée.
- Implémentant une pagination pour afficher plus de résultats.
- Améliorant le design avec des animations CSS supplémentaires.
