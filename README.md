# Barthès Maçonnerie — Site vitrine

Site vitrine de **Barthès Maçonnerie**, entreprise spécialisée en **maçonnerie traditionnelle**, **restauration du patrimoine** et **éco-construction** 🌱.
Le site est développé avec **Astro** et déployé automatiquement via **GitHub Pages** à l’aide de **GitHub Actions**.

---

## 🧱 Stack technique

* **Astro** (site statique, rapide et durable)
* HTML / CSS / JS
* Hébergement : **GitHub Pages**
* Déploiement automatique : **GitHub Actions**
* Aucun backend
* Aucun CMS
* Zéro dépendance serveur

---

## 🚀 Structure du projet

```text
/
├── src/                # Code source Astro
│   ├── layouts/
│   └── pages/          # Pages du site (index, atelier, realisations, etc.)
├── public/             # Assets statiques (images, favicon, etc.)
├── dist/               # Build Astro (généré automatiquement, non versionné)
├── .github/
│   └── workflows/
│       └── deploy.yml  # Workflow GitHub Actions (build + déploiement)
├── .gitignore
├── .nojekyll           # Désactive Jekyll sur GitHub Pages
├── astro.config.mjs
├── package.json
└── README.md
```

> ⚠️ Le dossier `dist/` est **généré automatiquement** par GitHub Actions et **ne doit jamais être commité**.

---

## ⚙️ Configuration GitHub Pages (important)

Ce dépôt est un **Project Pages repository** :

```text
tetaaard.github.io/barthes-maconnerie.github.io
```

➡️ Le site n’est **pas** servi à la racine du domaine, mais sous un sous-chemin correspondant au nom du dépôt.

La configuration Astro reflète cela :

```js
export default defineConfig({
  site: 'https://tetaaard.github.io',
  base: '/barthes-maconnerie.github.io',
  trailingSlash: 'always',
});
```

---

## 🔗 Gestion des liens (bonne pratique Astro)

Tous les liens internes utilisent la variable officielle Astro :

```js
import.meta.env.BASE_URL
```

Exemple :

```astro
const base = import.meta.env.BASE_URL;

<a href={`${base}realisations/`}>Réalisations</a>
```

Cela garantit :

* un fonctionnement identique en local et en production
* la compatibilité avec GitHub Pages
* une migration future facile vers un domaine personnalisé

---

## 🛠️ Workflow de déploiement

Le déploiement est **100 % automatisé**.

### Fonctionnement

1. Push du code source sur la branche `main`
2. GitHub Actions :

   * installe les dépendances
   * lance `npm run build`
   * génère le site dans `dist/`
   * déploie automatiquement sur GitHub Pages

👉 **Aucune copie manuelle de `dist/` n’est nécessaire.**

---

## ▶️ Développement local

```sh
npm install
npm run dev
```

Avec la configuration `base`, le site est accessible en local à :

```text
http://localhost:4321/barthes-maconnerie.github.io/
```

Ceci est **normal et attendu** pour un Project Pages repository.

---

## 🌍 Accès au site en production

Le site est accessible à l’adresse suivante :

👉 **[https://tetaaard.github.io/barthes-maconnerie.github.io/](https://tetaaard.github.io/barthes-maconnerie.github.io/)**

---

## Évolutions prévues

* Ajout d’un **nom de domaine personnalisé**
* Optimisation des images et performances
* Amélioration de la page d’accueil (hero visuel)
* Grille visuelle des réalisations

---

## 📜 Licence

Projet privé — Tous droits réservés
© Pierre Barthès — Barthès Maçonnerie
Développement : [https://github.com/Tetaaard](https://github.com/Tetaaard)
