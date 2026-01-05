# Barthès Maçonnerie — Site vitrine

Site vitrine de **Barthès Maçonnerie**, entreprise spécialisée en **maçonnerie traditionnelle**, **restauration du patrimoine** et **éco-construction** 🌱.  
Le site est développé avec **Astro** et hébergé gratuitement via **GitHub Pages**.

---

## 🧱 Stack technique

- **Astro** (site statique, rapide et durable)
- HTML / CSS / JS
- Hébergement : **GitHub Pages**
- Aucun backend
- Aucun CMS
- Zéro dépendance serveur

---

## 🚀 Structure du projet

```text
/
├── src/                # Code source Astro
│   ├── layouts/
│   └── pages/          # Pages du site (index, atelier, realisations, etc.)
├── public/             # Assets statiques (images sources, favicon, etc.)
├── dist/               # Site buildé par Astro (HTML final)
├── index.html          # Copie du build pour GitHub Pages
├── atelier/
├── contact/
├── realisations/
├── savoir-faire/
├── .nojekyll           # Désactive Jekyll sur GitHub Pages
├── astro.config.mjs
├── package.json
└── README.md
```

## ⚠️ Spécificité GitHub Pages (IMPORTANT)

Ce dépôt s’appelle :
```text
barthes-maconnerie.github.io
```

➡️ Il s’agit d’un **User Pages repository** (`<username>.github.io`).

### Règle GitHub Pages
Pour ce type de dépôt :
- GitHub Pages **ne peut servir QUE la racine du dépôt**
- Le dossier `dist/` **n’est jamais utilisé directement**
- GitHub Pages **ne comprend pas Astro**
- GitHub tente par défaut de builder le site avec **Jekyll**

👉 Jekyll est explicitement désactivé via le fichier `.nojekyll`.

---

## 🛠️ Workflow de déploiement (obligatoire)

### 1️⃣ Build du site avec Astro

```sh
npm run build
```

Le site statique est généré dans le dossier dist/ :

```sh
dist/
├── index.html
├── atelier/
├── contact/
├── realisations/
├── savoir-faire/
```
### 2️⃣ Copier le build à la racine du dépôt
⚠️ Étape indispensable pour GitHub Pages

```sh
cp -r dist/* .
```

Cela place les fichiers HTML directement à la racine du repo, ce que GitHub Pages peut servir.

## 🌍 Accès au site

Le site est accessible à l’adresse suivante :

```sh
https://tetaaard.github.io/barthes-maconnerie.github.io/
```