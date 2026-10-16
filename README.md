<div align="center">

  <p align="center">
    <a href="https://docs.python.org/3/"><img src="https://img.shields.io/badge/Python-3-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python 3"></a>
    <a href="https://github.com/Lamizana/DSLR"><img src="https://img.shields.io/badge/Projet-42-000000?style=for-the-badge&logo=42&logoColor=white" alt="Projet 42"></a>
  </p>

  <h1>DSLR</h1>

  <p><strong>Data Science × Logistic Regression - Reconstruire le Choixpeau de Poudlard par régression logistique.</strong></p>

  <p><em>Projet de l'école 42.</em></p>
  <p>Créé le 02/02/2026 · Dernière mise à jour : 16/10/2026</p>

  <a href="https://lamizana.github.io/ZehdBox/projets/">
    <img src="https://img.shields.io/badge/Portfolio-Fiche%20du%20projet-8A2BE2?style=for-the-badge&logo=githubpages&logoColor=white" alt="Fiche du projet">
  </a>

</div>

---

## Sommaire

<details>
<summary>Afficher le sommaire</summary>

- [Sommaire](#sommaire)
- [À propos](#à-propos)
- [Fonctionnalités](#fonctionnalités)
- [Comment ça marche](#comment-ça-marche)
- [Installation](#installation)
  - [Prérequis](#prérequis)
  - [Étapes](#étapes)
- [Bibliothèques](#bibliothèques)
- [Utilisation](#utilisation)
- [Structure du projet](#structure-du-projet)
- [Documentation](#documentation)
- [Contribuer](#contribuer)
- [Auteur](#auteur)
- [Remerciements](#remerciements)

</details>

---

## À propos

**DSLR** (Data Science × Logistic Regression) est le projet de découverte du **Machine Learning** du cursus 42. Partant d'un jeu de données d'élèves de Poudlard, il implémente une *régression logistique multiclasse (one-vs-all)* **from scratch** pour prédire la maison de chaque élève: Gryffondor, Poufsouffle, Serdaigle ou Serpentard.

| Ressource | Lien |
| --- | --- |
| *Enoncé* | [`docs/enonce.md`](docs/enonce.md) |
| *Fiche du projet (portfolio)* | [ZehdBox](https://lamizana.github.io/ZehdBox/) |


---

## Fonctionnalités

| Programme | Rôle |
| --- | --- |
| `Data_Analysis/describe.py` | Statistiques descriptives des features numériques |
| `Data_Visualization/histogram.py` | Histogramme : cours à répartition homogène entre maisons |
| `Data_Visualization/scatter_plot.py` | Nuage de points : caractéristiques similaires |
| `Data_Visualization/pair_plot.py` | Pair plot : sélection des features pour la régression |
| `Logistic_Regression/logreg_train.py` | Entraînement du modèle (descente de gradient) |
| `Logistic_Regression/logreg_predict.py` | Prédiction → `houses.csv` |

---

## Comment ça marche

Le classifieur est une régression logistique **one-vs-all** : un modèle binaire est entraîné par maison, puis la classe retenue est celle dont la probabilité est la plus élevée. Les features sont standardisées pour accélérer la convergence de la descente de gradient.

```console
dataset_train.csv ──► standardisation ──► descente de gradient ──► thetas
dataset_test.csv  ──► sigmoïde ──► argmax ──► houses.csv
```

> [!NOTE]
> L'évaluation se fait sur `dataset_test.csv` avec le score de précision de Scikit-Learn ; la cible du sujet est **98 %**.

---

## Installation

### Prérequis

- Python 3.8+
- `pip`

### Étapes

```bash
git clone https://github.com/Lamizana/DSLR.git
cd DSLR
```

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

---

## Bibliothèques

| Bibliothèque | Rôle |
| --- | --- |
| [`numpy`](https://numpy.org/) | Calcul matriciel et statistiques |
| [`pandas`](https://pandas.pydata.org/) | Chargement et manipulation des données |
| [`matplotlib`](https://matplotlib.org/) | Visualisation des données |
| [`seaborn`](https://seaborn.pydata.org/) | Graphiques statistiques |
| [`scikit-learn`](https://scikit-learn.org/) | Évaluation du score de précision |

---

## Utilisation

```bash
# Entraînement du modèle
python Logistic_Regression/logreg_train.py datasets/dataset_train.csv

# Prédiction
python Logistic_Regression/logreg_predict.py datasets/dataset_test.csv <fichier_thetas>
```

> [!TIP]
> Les jeux de données attendus sont dans `datasets/` (`dataset_train.csv`, `dataset_test.csv`).

---

## Structure du projet

```console
DSLR/
├── Bonus/                    # Bonus : SGD, accuracy_score
├── Data_Analysis/            # describe.py
├── Data_Utils/               # Utilitaires math / logger
├── Data_Visualization/       # histogram, scatter_plot, pair_plot
├── Logistic_Regression/      # logreg_train, logreg_predict, houses.csv
├── Scikit_Learn/             # Comparaison avec scikit-learn
├── datasets/                 # dataset_train.csv, dataset_test.csv
├── docs/                     # Sujet et documentation
│   └── enonce.md
├── requirements.txt
└── README.md
```

---

## Documentation

| Fichier | Descriptif |
| --- | --- |
| [`docs/enonce.md`](docs/enonce.md) | Sujet officiel du projet 42 (consignes, mandatory, bonus) |

---

## Contribuer

Projet pédagogique 42 : les remarques sont bienvenues via une **issue** ou une **pull request**.

---

## Auteur

**Alex Lamizana**, étudiant à 42 Angoulême, spécialisation Data & IA

- [Site](https://lamizana.github.io/ZehdBox/)
- [GitHub](https://github.com/Lamizana)

---

## Remerciements

- [42 Angoulême](https://www.42angouleme.fr/) : cadre pédagogique du projet

---

<div align="center">

*Ce projet a été réalisé conformément à la norme et au sujet officiel de 42.*

</div>
