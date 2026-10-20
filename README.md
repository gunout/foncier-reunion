# 🏛️ Foncier Réunion

Monitoring territorial et analyse foncière des 24 communes de La Réunion (974). Un tableau de bord interactif, autonome et souverain pour suivre l'évolution de la fiscalité locale, des prix immobiliers et de la sécurité année après année.

![Last commit](https://img.shields.io/github/last-commit/gunout/foncier-reunion?color=green&style=flat-square)
![Repo size](https://img.shields.io/github/repo-size/gunout/foncier-reunion?style=flat-square)
![Language](https://img.shields.io/github/languages/top/gunout/foncier-reunion?style=flat-square)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=flat-square&logo=chart.js&logoColor=white)
![Open Data](https://img.shields.io/badge/Open%20Data-DVF%20%7C%20DGFiP%20%7C%20INSEE-000091?style=flat-square)

---

## À propos

Foncier Réunion est un outil d'analyse décisionnelle conçu pour les acteurs du territoire (collectivités, observatoires, bureaux d'études, citoyens).

Il agrège les données ouvertes officielles (DGFiP, INSEE, SSMSI, DVF) sur **24 communes** et **13 millésimes (2002–2025)** pour offrir une vision claire et comparative des dynamiques locales.

L'interface s'inspire de la **charte graphique de l'État (Marianne)** : sobriété, accessibilité et confiance.

---

## Fonctionnalités Clés

- **Tableau de bord interactif** : 4 indicateurs clés (TFPB, Prix médian, Délinquance, TEOM) mis à jour en temps réel.
- **Graphiques dynamiques** : évolution temporelle des taxes, classement par pression fiscale, comparaison entre Commune 1 et Commune 2.
- **Légende interactive** : cliquez sur une commune dans le graphique pour la masquer ou l'afficher.
- **Tableau expert** : tri par colonnes, sparklines sur 5 ans pour visualiser les tendances.
- **Export CSV** : extrayez les données filtrées.
- **Multi-fichiers** : glissez-déposez plusieurs CSV (2026, 2027…) pour enrichir l'historique.
- **Thème clair/sombre**.

---

## Démarrage Rapide

Aucune installation requise. Le fichier index.html est 100% autonome.

### Méthode 1 : Utilisation Locale

Clonez le dépôt :

    git clone https://github.com/gunout/foncier-reunion.git
    cd foncier-reunion

Puis ouvrez index.html dans votre navigateur.

**Note** : Certains navigateurs bloquent le chargement du CSV local (CORS). Utilisez un petit serveur local :

    python3 -m http.server 8000

Puis ouvrez http://localhost:8000 dans votre navigateur.

### Méthode 2 : Glisser-Déposer

1. Ouvrez index.html.
2. Glissez-déposez votre fichier reunion_habity.csv dans la zone prévue.

### Méthode 3 : GitHub Pages

1. Allez dans Settings > Pages.
2. Sélectionnez la branche main et le dossier / (root).
3. Votre tableau de bord sera accessible à l'adresse https://gunout.github.io/foncier-reunion/

---

## Structure du Projet

    foncier-reunion/
    ├── index.html
    ├── reunion_habity.csv
    └── README.md

---

## Source des Données

| Domaine | Source | Millésime |
| :--- | :--- | :--- |
| Fiscalité locale (TFPB, TEOM) | DGFiP - REI | 2002–2025 |
| Prix immobilier | DVF (Cerema) | 2021–2025 |
| Sécurité | SSMSI (Ministère de l'Intérieur) | 2021–2025 |
| Démographie | INSEE | 2022 |

**Note** : Les données immobilières ne sont disponibles qu'à partir de 2021.

---

## Stack Technique

- HTML5 / CSS3 (Tailwind CSS)
- Vanilla JavaScript
- Chart.js pour les graphiques
- PapaParse pour le parsing CSV
- Design : Charte Marianne

---

## Logique de fusion

- Si vous chargez 2026.csv, les nouvelles lignes viennent s'ajouter.
- Si une ligne existe déjà pour la même combinaison (Année, Code INSEE), la nouvelle donnée écrase l'ancienne.
- Le sélecteur d'année et les graphiques s'actualisent instantanément.

---

## Contribution

1. Forkez le projet.
2. Créez une branche (git checkout -b feature/amelioration).
3. Committez vos changements.
4. Pushez.
5. Ouvrez une Pull Request.

---

## Licence

Ce projet est distribué sous licence MIT.

---

Fait avec ❤️ pour La Réunion.
