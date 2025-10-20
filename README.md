# Wakapi Dashboard

Un tableau de bord élégant inspiré de WakaTime pour afficher les statistiques de codage depuis votre instance Wakapi.

## 🚀 Fonctionnalités

- **Design Dark Mode** - Interface sombre moderne similaire à WakaTime
- **Statistiques en temps réel** - Affichage des données de votre API Wakapi
- **Graphique d'activité** - Visualisation SVG de votre activité de codage
- **Badge Wakapi** - Badge dynamique du temps de codage total
- **Statistiques détaillées** :
  - Langages de programmation
  - Éditeurs utilisés
  - Systèmes d'exploitation
  - Catégories de projets
- **Animations fluides** - Barres de progression animées et effets visuels
- **Responsive** - S'adapte à tous les écrans
- **GitHub Pages Ready** - Déployable facilement sur GitHub Pages

## 📋 Configuration

1. Modifiez les variables dans le fichier `index.html` :
   ```javascript
   const API_BASE = 'https://wakapi.ezariel.fr/api';
   const USERNAME = 'Cepheus';
   ```

2. Remplacez par votre propre instance Wakapi et nom d'utilisateur.

## 🌐 Déploiement sur GitHub Pages

1. Créez un nouveau repository GitHub
2. Uploadez les fichiers `index.html`, `styles.css` dans votre repository
3. Allez dans Settings > Pages
4. Sélectionnez "Deploy from a branch" et choisissez "main"
5. Votre dashboard sera disponible à `https://username.github.io/repository-name`

## 📁 Structure des fichiers

```
wakapidashboard/
├── index.html      # Page principale du dashboard
├── styles.css      # Styles personnalisés et animations
└── README.md       # Documentation
```

## 🎨 Personnalisation

### Couleurs des barres de progression

Modifiez les couleurs dans la variable `colors` :
```javascript
const colors = {
    languages: ['blue', 'green', 'purple', 'pink', 'yellow', 'indigo'],
    editors: ['purple', 'pink', 'blue'],
    os: ['green', 'blue', 'yellow'],
    categories: ['yellow', 'orange', 'red']
};
```

### Thème

Le design utilise Tailwind CSS via CDN. Vous pouvez personnaliser les couleurs dans la configuration :
```javascript
tailwind.config = {
    theme: {
        extend: {
            colors: {
                dark: {
                    bg: '#0f1419',      // Arrière-plan principal
                    card: '#1a1f2e',    // Cartes
                    border: '#2a2f3e',  // Bordures
                    text: '#e5e7eb'     // Texte
                }
            }
        }
    }
}
```

## 🔧 API Wakapi

Le dashboard utilise l'API compatible WakaTime de Wakapi :
- **Stats** : `/api/compat/wakatime/v1/users/{username}/stats/all_time`
- **Graphique** : `/api/activity/chart/{username}.svg`
- **Badge** : `/api/compat/shields/v1/{username}/interval:all_time`

### Badge Wakapi

Le badge affiche le temps total de codage et peut être utilisé dans vos README :
```markdown
![Wakapi](https://img.shields.io/endpoint?url=https://wakapi.ezariel.fr/api/compat/shields/v1/Cepheus/interval:all_time&label=All%20time&color=blue)
```

Vous pouvez personnaliser :
- `label` : Texte affiché (ex: "Coding time", "Total")
- `color` : Couleur du badge (blue, green, red, etc.)
- `interval` : Période (all_time, last_7_days, last_30_days, etc.)

## ✨ Fonctionnalités techniques

- **Pas de framework** - Vanilla HTML/CSS/JavaScript
- **Tailwind CSS via CDN** - Pas besoin de build
- **Fetch API** - Appels AJAX modernes
- **CSS Animations** - Animations fluides
- **Responsive Design** - Mobile-friendly
- **Error Handling** - Gestion des erreurs réseau

## 🛠️ Développement local

Ouvrez simplement `index.html` dans votre navigateur. Aucun serveur web requis !

Pour les tests avec CORS, vous pouvez utiliser :
```bash
# Avec Python
python -m http.server 8000

# Avec Node.js
npx serve .
```

## 📸 Aperçu

Le dashboard reproduit fidèlement l'apparence de WakaTime avec :
- Profil utilisateur avec avatar
- Grille d'activité GitHub-style
- Statistiques de temps de codage
- Graphique d'activité annuel
- Barres de progression pour les langages, éditeurs, etc.

## 🤝 Contribution

Les contributions sont les bienvenues ! N'hésitez pas à :
- Signaler des bugs
- Proposer des améliorations
- Ajouter de nouvelles fonctionnalités

## 📄 Licence

Ce projet est libre d'utilisation pour vos propres dashboards Wakapi.