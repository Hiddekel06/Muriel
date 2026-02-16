# 📐 Architecture du Projet TSA·LACH

## 📁 Structure des Fichiers

```
Projet_Muriel/
│
├── 📄 index.html              # Page principale (landing page)
├── 📄 package.json            # Configuration npm et scripts
├── 📄 package-lock.json       # Verrouillage des dépendances
├── 📄 ARCHITECTURE.md         # Ce fichier (documentation)
│
├── 📂 src/                    # Fichiers sources
│   └── 📄 input.css           # Point d'entrée Tailwind CSS
│
├── 📂 dist/                   # Fichiers compilés
│   └── 📄 output.css          # CSS Tailwind compilé (généré automatiquement)
│
├── 📂 images/                 # Assets visuels
│   ├── 🖼️ Logo_Muriel.jpg     # Logo de l'entreprise
│   ├── 🖼️ muriel tête.jpeg    # Photo consultante (v1)
│   ├── 🖼️ murielteteV2.jpeg   # Photo consultante (v2)
│   ├── 🖼️ MurielV3.jfif       # Photo consultante (v3)
│   └── 🖼️ MurielV4.jpg        # Photo consultante (v4 - utilisée)
│
├── 📂 node_modules/           # Dépendances npm (ignoré par git)
└── 📂 .git/                   # Historique Git
```

---

## 🏗️ Stack Technique

### Frontend
- **HTML5** : Structure sémantique de la page
- **Tailwind CSS v4.1.18** : Framework CSS utility-first
- **CSS personnalisé** : Animations et effets (dans `<style>` de index.html)
- **SVG inline** : Icônes vectorielles pour les réseaux sociaux

### Build & Tooling
- **Node.js & npm** : Gestionnaire de paquets
- **@tailwindcss/cli** : Compilateur Tailwind CSS v4
- **PostCSS 8.5.6** : Transformation CSS
- **Autoprefixer 10.4.24** : Compatibilité navigateurs

### Polices
- **Google Fonts - Inter** : Police moderne (400, 500, 600, 700)

---

## ⚙️ Scripts Disponibles

```bash
# Compiler le CSS une fois
npm run build

# Compiler en mode watch (recompile automatiquement)
npm run watch

# Tests (non configuré)
npm run test
```

---

## 🎨 Palette de Couleurs

```css
/* Couleurs principales */
--primary-green: #1A4D3E;      /* Vert profond (texte, accents) */
--accent-orange: #E85C3A;      /* Orange raffiné (CTA, badges) */
--background: #F9F7F5;         /* Blanc cassé (fond principal) */
--white: #FFFFFF;              /* Blanc pur (cartes) */

/* Couleurs réseaux sociaux (officielles) */
--linkedin: #0A66C2;
--instagram-gradient: linear-gradient(#F58529, #DD2A7B, #8134AF);
--facebook: #1877F2;
--tiktok: #000000;
```

---

## 📦 Composants de la Page

### 1. **Header**
- Logo TSA·LACH avec badge
- Navigation (masquée sur mobile)
- Responsive : `sm:flex` pour desktop

### 2. **Carte Hero (Photo + Présentation)**
- Layout grid 5 colonnes : 2 (image) + 3 (texte)
- Image 48×48 (mobile) → 72×72 (desktop)
- Badge "Disponible" avec animation ping
- Tags de compétences (Croissance, Stratégie, Digital)

### 3. **Section Réseaux Sociaux**
- Grid responsive : 1 col (mobile) → 2 cols (tablet+)
- 4 plateformes : LinkedIn, Instagram, Facebook, TikTok
- Effet glow au survol avec transition
- Icônes SVG officielles avec couleurs de marque

### 4. **Footer Contact**
- Email & téléphone avec icônes
- Layout flexible : colonne (mobile) → ligne (desktop)
- Copyright avec année dynamique

---

## 🎯 Fonctionnalités Clés

### ✅ Responsive Design
- **Mobile First** : Optimisé pour petits écrans
- **Breakpoints** :
  - `< 640px` : Mobile
  - `640px - 768px` : Tablet
  - `> 768px` : Desktop

### ✨ Animations & Effets
- **hover-lift** : Élévation au survol des cartes
- **glow-card** : Bordure lumineuse au survol
- **subtle-float** : Animation de flottement subtile
- **ping** : Animation de pulsation (badge "Disponible")

### 🔗 Liens Sociaux
- LinkedIn : ✅ Lien réel configuré
- Instagram : ✅ Lien réel configuré
- Facebook : ⚠️ Placeholder (href="#")
- TikTok : ⚠️ Placeholder (href="#")

### ♿ Accessibilité
- Attributs `alt` sur toutes les images
- Balises sémantiques HTML5
- Contraste de couleurs WCAG AA
- Navigation clavier possible

---

## 🔄 Workflow de Développement

### 1. Modifier le HTML
```bash
# Éditer index.html
code index.html
```

### 2. Modifier les styles Tailwind
```bash
# Les classes Tailwind sont dans index.html
# Le fichier src/input.css importe Tailwind
```

### 3. Compiler le CSS
```bash
# Une fois
npm run build

# Mode watch (auto-recompilation)
npm run watch
```

### 4. Prévisualiser
```bash
# Ouvrir index.html dans un navigateur
# Ou utiliser Live Server (extension VS Code)
```

---

## 📝 Configuration Tailwind CSS v4

Le fichier `src/input.css` contient :

```css
@import "tailwindcss";
@source "../index.html";
```

**Note** : Tailwind CSS v4 utilise `@source` pour scanner les fichiers HTML au lieu d'un fichier `tailwind.config.js`.

---

## 🚀 Déploiement

### Option 1 : Hébergement Statique
- **GitHub Pages** : Push sur branche `gh-pages`
- **Netlify** : Glisser-déposer le dossier
- **Vercel** : Import du repo Git

### Option 2 : Serveur Web
1. Compiler le CSS : `npm run build`
2. Copier ces fichiers sur le serveur :
   - `index.html`
   - `dist/output.css`
   - `images/` (dossier complet)

---

## 🛠️ Maintenance

### Ajouter une Nouvelle Section
1. Éditer `index.html`
2. Ajouter les classes Tailwind
3. Recompiler : `npm run build`

### Changer les Couleurs
1. Chercher les couleurs hex dans `index.html`
2. Remplacer globalement (ex: `#1A4D3E` → nouvelle couleur)
3. Recompiler le CSS

### Optimiser les Images
```bash
# Compresser avec ImageOptim, TinyPNG, ou Squoosh
# Poids cible : < 200KB par image
```

---

## 📊 Performance

- **Poids total** : ~300-400 KB (avec images optimisées)
- **CSS compilé** : ~50-80 KB (dist/output.css)
- **Fonts** : Google Fonts (chargement asynchrone)
- **Icônes** : SVG inline (pas de requête externe)

---

## 🔐 Sécurité

- Pas de scripts externes (hors Google Fonts)
- Liens avec `rel="noopener"` pour sécurité
- Pas de données sensibles dans le code

---

## 📞 Contact Technique

Pour toute question sur l'architecture :
- 📧 contact@tsalach.com
- 📱 +33 6 12 34 56 78

---

**Dernière mise à jour** : Février 2026  
**Version** : 1.0.0
