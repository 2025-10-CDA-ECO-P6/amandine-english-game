# English Game

🔗 **Démo en ligne :** [https://2025-10-cda-eco-p6.github.io/amandine-english-game/](https://2025-10-cda-eco-p6.github.io/amandine-english-game/)

---

## 📋 Description

Cette interface propose :

- Une **navigation responsive** avec barre fixe en bas sur mobile
- Une **section hero** avec titre, description, vidéo et call-to-action
- Une **section benefits** présentant les 3 points forts du challenge sous forme de grille de cartes

---

## 🛠️ Stack technique

| Technologie | Rôle |
|---|---|
| HTML | Structure sémantique |
| SCSS (avec BEM) | Styles modulaires et maintenables |
| CSS Grid | Mise en page responsive |
| Variables SCSS | Système de design (couleurs, espacements, breakpoints) |

---

## 🗂️ Architecture du projet

```
amandine-english-game/
├── index.html                    # Page principale
├── README.md
├── package.json
├── pnpm-lock.yaml
├── public/
│   └── css/
│       ├── main.css              # CSS compilé depuis SCSS
│       └── main.css.map          # Source map pour le debug
├── resources/
│   ├── icons/                    # Logo MDS + icône notification
│   ├── images/                   # Images des cartes benefits + poster vidéo
│   └── mock-ups/                 # Maquettes du projet (8 visuels)
└── scss/
    ├── main.scss                 # Point d'entrée SCSS
    ├── layout/
    │   └── _nav.scss             # Header + navigation + responsive mobile
    └── vars/
        └── _variables.scss       # Couleurs, espacements, breakpoints, radius, ombres
```

---

## 🎨 Système de design

### Couleurs principales

| Variable | Valeur | Usage |
|---|---|---|
| `$primary950` | `#083c44` | Fond hero |
| `$primary600` | `#09aab1` | Bouton CTA |
| `$primary700` | `#0f878f` | Bouton CTA hover |
| `$neutral0` | `#ffffff` | Fond benefits, textes clairs |
| `$neutral900` | `#1a1a1a` | Textes principaux |

### Breakpoints

| Variable | Valeur | Usage |
|---|---|---|
| `$breakpoint-sm` | `480px` | Très petit mobile |
| `$breakpoint-md` | `640px` | Mobile standard |
| `$breakpoint-lg` | `900px` | Tablette |
| `$breakpoint-xl` | `1200px` | Grand écran |

---

## 📐 Composants

### Header / Navigation

- Logo à gauche, menu centré, actions à droite
- Sur mobile (`< 640px`) : la nav se transforme en **barre fixe en bas** de l'écran
- Icône de notification + bouton profil circulaire

### Section Hero

- Layout en **2 colonnes** sur desktop (titre + description | vidéo)
- Sur mobile : empilement vertical (titre → vidéo → description)
- Chevauchement visuel avec la section suivante via `margin-top: -24px` sur `.benefits`

### Section Benefits

- **Grille de 3 cartes** sur desktop (`repeat(3, 1fr)`)
- **1 colonne** sur tablette/mobile
- Chaque carte : image avec ratio `4/3` fixe + titre + description
- Padding bas calculé avec `calc()` sur mobile pour éviter la superposition avec la nav fixe

---

## 📱 Responsive

| Taille | Comportement |
|---|---|
| Desktop `> 900px` | Hero 2 colonnes, benefits 3 colonnes |
| Tablette `≤ 900px` | Hero et benefits en 1 colonne |
| Mobile `≤ 640px` | Nav en barre fixe basse, padding compensatoire, titres réduits |

---

### BEM

La convention BEM est appliquée sur tous les composants :
- **Block** : `.hero`, `.benefits`, `.nav`
- **Element** : `&__title`, `&__card`, `&__btn`
- **Modifier** : non utilisé dans cette version

---

## 🌱 Axes d'amélioration :

### Éco-conception & performance

- **Optimiser les images** : convertir les `.png`/`.jpg` en **WebP** (réduction de 25 à 35 % du poids), et utiliser des formats **AVIF** pour les navigateurs compatibles
- **Redimensionner les images à la bonne taille** : ne pas servir une image 1200px si elle est affichée en 400px — utiliser l'attribut `srcset` et `sizes`
- **Minifier le CSS** compilé en production pour réduire le poids des assets
- **Ajouter des dimensions `width` et `height`** explicites sur les balises `<img>` pour éviter les Layout Shifts (CLS)

### Fonctionnalités

- Faire la suite x)

---

## 🚀 Installation

```bash
# Cloner le projet
git clone https://github.com/2025-10-CDA-ECO-P6/amandine-english-game.git

# Compiler le SCSS (exemple avec sass CLI)
sass scss/main.scss public/css/main.css --watch
```

Ouvrir `index.html` dans un navigateur

---

## 🖼️ Maquettes

<table>
  <tr>
    <td><img src="./resources/mock-ups/mock-ups3.jpg" alt="Maquette 3" width="1460"/></td>
  </tr>
</table>

---

## 👤 Contact

**Amandine** – Développeuse

[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/amandinekemp)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/amandinedelbouve/)
