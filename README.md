<div align="center">
    
# 🏛️ FONCIER REUNION



Monitoring territorial et analyse foncière des 24 communes de La Réunion (974). Un tableau de bord interactif, autonome et souverain pour suivre l'évolution de la fiscalité locale, des prix immobiliers et de la sécurité année après année.

![Last commit](https://img.shields.io/github/last-commit/gunout/foncier-reunion?color=green&style=flat-square)
![Repo size](https://img.shields.io/github/repo-size/gunout/foncier-reunion?style=flat-square)
![Languages](https://img.shields.io/github/languages/top/gunout/foncier-reunion?style=flat-square)
![Stars](https://img.shields.io/github/stars/gunout/foncier-reunion?style=flat-square&color=gold)
![Forks](https://img.shields.io/github/forks/gunout/foncier-reunion?style=flat-square)
![Issues](https://img.shields.io/github/issues/gunout/foncier-reunion?style=flat-square)
![PRs](https://img.shields.io/github/issues-pr/gunout/foncier-reunion?style=flat-square)
![License](https://img.shields.io/github/license/gunout/foncier-reunion?style=flat-square)
![Made with France](https://img.shields.io/badge/Made%20in-La%20Réunion-00a95f?style=flat-square)
![Design](https://img.shields.io/badge/Design-Charte%20Marianne-000091?style=flat-square)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=flat-square&logo=chart.js&logoColor=white)
![Vanilla JS](https://img.shields.io/badge/Vanilla%20JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Open Data](https://img.shields.io/badge/Open%20Data-DVF%20%7C%20DGFiP%20%7C%20INSEE-000091?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-success?style=flat-square)
![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg?style=flat-square)

</div>

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

## Stack Technique

| Composant | Technologie | Badge |
| :--- | :--- | :--- |
| **Structure** | HTML5 sémantique | ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white) |
| **Style** | CSS3 + Tailwind CSS | ![Tailwind](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white) |
| **Logique** | Vanilla JavaScript (ES6+) | ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) |
| **Graphiques** | Chart.js v4 | ![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=flat-square&logo=chart.js&logoColor=white) |
| **Parsing CSV** | PapaParse v5 | ![PapaParse](https://img.shields.io/badge/PapaParse-5C8DBC?style=flat-square) |
| **Design** | Charte Marianne (République Française) | ![Marianne](https://img.shields.io/badge/Charte-Marianne-000091?style=flat-square) |

---

## Démarrage Rapide

Aucune installation requise. Le fichier index.html est 100% autonome (Tailwind, Chart.js et PapaParse sont chargés via CDN).

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

Les données sont issues de l'**Open Data** officiel français :

| Domaine | Source | Millésime |
| :--- | :--- | :--- |
| Fiscalité locale (TFPB, TEOM) | DGFiP - REI | 2002–2025 |
| Prix immobilier | DVF (Cerema) | 2021–2025 |
| Sécurité | SSMSI (Ministère de l'Intérieur) | 2021–2025 |
| Démographie | INSEE | 2022 |

**Note** : Les données immobilières ne sont disponibles qu'à partir de 2021.

---

## Logique de fusion

- Si vous chargez 2026.csv, les nouvelles lignes viennent s'ajouter.
- Si une ligne existe déjà pour la même combinaison (Année, Code INSEE), la nouvelle donnée écrase l'ancienne.
- Le sélecteur d'année et les graphiques s'actualisent instantanément.

---

## Feuille de Route

- [x] Tableau de bord interactif (2025)
- [x] Multi-fichiers CSV (2026)
- [ ] Mode comparaison N communes
- [ ] Export PDF des graphiques
- [ ] Intégration des données de chômage

---

## Contribution

Les contributions sont les bienvenues ! Pour proposer une amélioration :

1. Forkez le projet.
2. Créez une branche (git checkout -b feature/amelioration).
3. Committez vos changements.
4. Pushez.
5. Ouvrez une Pull Request.

Voir la liste des contributeurs : [CONTRIBUTORS.md](CONTRIBUTORS.md)

---

## Licence

Ce projet est distribué sous licence **MIT**. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

---

## Remerciements

- **DGFiP** pour les données fiscales.
- **Cerema** pour les données DVF.
- **INSEE** pour les données démographiques.
- **SSMSI** pour les données de sécurité.
- **La communauté Open Data française**.

---
<div align="center">
Fait avec ❤️ pour La Réunion.

**[⬆ Retour en haut](#foncier-réunion)**

</div>

---

<div align="center">

### 🇫🇷 Gunout · 2026

![Made in France](https://img.shields.io/badge/Made_in-France-002395?style=flat-square&labelColor=FFFFFF&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA5MDAgNjAwIj48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjYwMCIgZmlsbD0iIzAwMjM5NSIvPjxyZWN0IHdpZHRoPSI5MDAiIGhlaWdodD0iNDAwIiB5PSIxMDAiIGZpbGw9IiNmZmYiLz48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjIwMCIgeT0iNDAwIiBmaWxsPSIjZWQyOTM5Ii8+PC9zdmc+)
![GitHub](https://img.shields.io/badge/GitHub-gunout-181717?style=flat-square&logo=github&logoColor=white)
![Year](https://img.shields.io/badge/2026-ED2939?style=flat-square&labelColor=FFFFFF)

<sub>© 2026 <strong>Gunout</strong> — Tous droits réservés.</sub>

</div>
