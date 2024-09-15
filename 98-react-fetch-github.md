# Tutoriel : Création d'une application React de recherche d'utilisateurs GitHub

# 1. Création du projet

Ouvrez un terminal et exécutez :

```
npx create-react-app github-user-search
cd github-user-search
```

# 2. Installation des dépendances

Installez Bootstrap :

```
npm install bootstrap
```

# 3. Nettoyage du projet

Supprimez les fichiers suivants dans le dossier `src` :
- App.test.js
- logo.svg
- reportWebVitals.js
- setupTests.js

# 4. Modification du fichier index.js

Ouvrez `src/index.js` et remplacez son contenu par :

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

# 5. Création du composant App

Remplacez le contenu de `src/App.js` par :

```jsx
import React, { useState, useEffect } from 'react';
import 'bootstrap/dist/css/bootstrap.min.css';
import './App.css';

function App() {
  const [searchTerm, setSearchTerm] = useState('');
  const [users, setUsers] = useState([]);

  useEffect(() => {
    if (searchTerm) {
      const debounceSearch = setTimeout(() => {
        searchUsers();
      }, 300);

      return () => clearTimeout(debounceSearch);
    } else {
      setUsers([]);
    }
  }, [searchTerm]);

  const searchUsers = async () => {
    try {
      const response = await fetch(`https://api.github.com/search/users?q=${searchTerm}`);
      const data = await response.json();
      const detailedUsers = await Promise.all(
        data.items.slice(0, 8).map(async (user) => {
          const userResponse = await fetch(user.url);
          return userResponse.json();
        })
      );
      setUsers(detailedUsers);
    } catch (error) {
      console.error('Erreur lors de la recherche:', error);
    }
  };

  return (
    <div className="container mt-5">
      <h1 className="text-center mb-4">Recherche d'utilisateurs GitHub</h1>
      <div className="row justify-content-center">
        <div className="col-md-6">
          <input
            type="text"
            className="form-control mb-4"
            placeholder="Entrez un nom d'utilisateur"
            value={searchTerm}
            onChange={(e) => setSearchTerm(e.target.value)}
          />
        </div>
      </div>
      <div className="row g-4">
        {users.map((user) => (
          <UserCard key={user.id} user={user} />
        ))}
      </div>
    </div>
  );
}

function UserCard({ user }) {
  return (
    <div className="col-md-3 mb-4">
      <div className="card user-card h-100">
        <img src={user.avatar_url} className="user-avatar card-img-top mx-auto mt-3" alt={user.login} />
        <div className="card-body text-center">
          <h5 className="card-title">{user.name || user.login}</h5>
          <p className="card-text">
            <small className="text-muted">@{user.login}</small><br />
            {user.bio && <><small>{user.bio}</small><br /></>}
            <small>Repos: {user.public_repos} | Followers: {user.followers}</small>
          </p>
          <a href={user.html_url} className="btn btn-primary btn-sm" target="_blank" rel="noopener noreferrer">Voir le profil</a>
        </div>
      </div>
    </div>
  );
}

export default App;
```

# 6. Création du fichier CSS

Créez ou modifiez `src/App.css` avec le contenu suivant :

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

# 7. Lancement de l'application

Dans le terminal, exécutez :

```
npm start
```

Votre application devrait maintenant être accessible à l'adresse http://localhost:3000.

# 8. Explication du code

- Le composant `App` gère l'état de la recherche et des utilisateurs trouvés.
- `useEffect` est utilisé pour déclencher la recherche avec un délai de 300ms après chaque modification de la saisie.
- La fonction `searchUsers` effectue la recherche via l'API GitHub et récupère les détails de chaque utilisateur.
- Le composant `UserCard` affiche les informations de chaque utilisateur dans une carte.

# 9. Personnalisation

Vous pouvez maintenant personnaliser davantage l'application en ajoutant des fonctionnalités comme la pagination, la gestion des erreurs, ou en améliorant le design.

# 10. Construction pour la production

Lorsque vous êtes prêt à déployer, exécutez :

```
npm run build
```

Cela créera une version optimisée de votre application dans le dossier `build`.

Ce tutoriel vous guide à travers la création de l'application React de recherche d'utilisateurs GitHub. N'hésitez pas à expérimenter et à ajouter d'autres fonctionnalités pour améliorer l'application !
