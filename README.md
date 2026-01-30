# Jolt Energie - Landing Page

Site web de courtier en énergie pour professionnels. Landing page moderne avec design responsive, mode sombre/clair, et formulaire de capture de leads.

## 🚀 Fonctionnalités

- **Design Responsive** - Adapté à tous les écrans (mobile, tablette, desktop)
- **Mode Sombre/Lumière** - Basculement via le bouton dans la navigation
- **Formulaire de Contact Complet** - Capture de leads avec champs dynamiques
- **Animations** - Effets de scroll et transitions fluides
- **SEO Optimisé** - Meta tags, description, keywords
- **Performance** - Code léger, pas de dépendances externes

## 📁 Structure du Projet

```
joltenergie/
├── index.html          # Page principale (tout-en-un)
├── images/
│   └── logo.png        # Logo de l'entreprise
└── README.md           # Cette documentation
```

## 🎨 Personnalisation

### Couleurs

Les couleurs sont définies dans les variables CSS `:root` et `[data-theme="dark"]` :

```css
:root {
    --primary: #FF7200;        /* Couleur principale (orange) */
    --primary-dark: #e55e00;   /* Version sombre du orange */
    --accent: #22c55e;         /* Couleur d'accent (vert) */
    /* ... autres variables */
}
```

Pour changer la couleur dominante, modifiez `--primary` dans les deux thèmes.

### Contenu

Les sections modifiables se trouvent dans `index.html` :

- **Hero** (lignes ~1011-1034) : Titre, sous-titre, badges
- **Stats** (lignes ~1059-1078) : Chiffres clés
- **Features** (lignes ~1081-1121) : Avantages
- **Services** (lignes ~1148-1183) : Services proposés
- **Process** (lignes ~1185-1220) : Étapes du processus
- **Testimonials** (lignes ~1222-1256) : Avis clients
- **Form** (lignes ~1260-1353) : Formulaire de contact

### Images

Remplacez `images/logo.png` par votre propre logo. Les dimensions recommandées sont 40px de hauteur.

## 📝 Formulaire de Contact

Le formulaire capture les informations suivantes :

### Champs

| Champ | Requis | Description |
|-------|--------|-------------|
| clientType | ✓ | Professionnel ou Particulier |
| company | ✓* | Nom de l'entreprise (*si professionnel) |
| sector | ✓* | Secteur d'activité (*si professionnel) |
| name | ✓ | Nom et prénom |
| email | ✓ | Adresse email |
| phone | ✓ | Numéro de téléphone |
| zipcode | ✓ | Code postal |
| city | ✓ | Ville |
| occupancyStatus | ✓ | Statut d'occupation |
| energyType | ✓ | Type d'énergie souhaitée |
| elecConsumption | ✓* | Consommation électrique (*si applicable) |
| pdl | ✓* | Point de Livraison (*si électricité) |
| gasConsumption | ✓* | Consommation gaz (*si applicable) |
| pce | ✓* | Point Comptage Estimation (*si gaz) |
| message | ✗ | Message libre |

### Configuration de l'Envoi

Le formulaire utilise `handleFormSubmit(event)` dans le script. Par défaut, les données sont loggées dans la console.

Pour configurer l'envoi réel :

1. **Via API externe** - Remplacez le `console.log` par un `fetch()` vers votre endpoint
2. **Via email** - Intégrez un service comme EmailJS ou Formspree
3. **Via n8n** - Connectez à un webhook pour automatiser les leads

Exemple de configuration API :

```javascript
const response = await fetch('https://api.votre-service.com/leads', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
        'Authorization': 'Bearer VOTRE_CLE_API'
    },
    body: JSON.stringify(formData)
});

if (!response.ok) {
    throw new Error('Erreur lors de l\'envoi');
}
```

## 🖥️ Déploiement

### Serveur Web Local

```bash
# Python 3
python -m http.server 8000

# PHP
php -S localhost:8000

# Node.js (avec http-server)
npx http-server -p 8000
```

### Hébergement

Le projet fonctionne sur n'importe quel hébergement web statique :

- **GitHub Pages** : Push sur `gh-pages` branch
- **Vercel** : Connectez le repo
- **Netlify** : Drag & drop du dossier
- **FTP** : Uploadez les fichiers sur votre serveur

## 📱 Responsive Breakpoints

```css
/* Tablette */
@media (max-width: 1024px) { ... }

/* Mobile */
@media (max-width: 768px) { ... }

/* Petit mobile */
@media (max-width: 480px) { ... }
```

## 🔧 Maintenance

### Mettre à jour le contenu

Éditez directement `index.html` pour modifier :
- Textes des sections
- Liens et ancres
- Images et logos
- Chiffres et statistiques

### Ajouter une nouvelle section

1. Ajoutez le HTML dans `<body>`
2. Ajoutez le CSS correspondant avant `</style>`
3. Mettez à jour la navigation si nécessaire

## 📄 Licence

Propriété de Jolt Energie. Tous droits réservés.

## 📞 Contact

Pour toute question ou support :
- Email : contact@joltenergie.com
- Site : www.joltenergie.com
