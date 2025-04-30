# Prédiction du Churn - Télécommunications

Ce projet a pour objectif d'analyser et de prédire le désabonnement des clients d'une entreprise de télécommunications (churn). Il a été mené entièrement sous VS Code en scripts Python, dans une démarche rigoureuse de data science appliquée.

---

##  Structure du projet
projet_churn_telco/
├── data/                # Données brutes ou nettoyées (ex : WA_Fn-UseC_-Telco-Customer-Churn.csv)
├── models/              # (À venir) Sauvegarde des modèles entraînés
├── notebooks/           # Contient le script EDA et preprocessing (au format .ipynb pour initialisation rapide)
├── src/                 # (À venir) Fonctions réutilisables ou modules Python
├── requirements.txt     # Librairies Python nécessaires
└── README.md            # Documentation du projet


## Objectifs

- Identifier les variables influentes sur le churn client à partir des données disponibles.
- Réaliser une analyse exploratoire (EDA) approfondie.
- Préparer les données pour une future modélisation (encodage, traitement des valeurs manquantes, etc.).
- Mettre en place un pipeline reproductible via des scripts dans un environnement structuré.

## Étapes réalisées

- **Chargement et nettoyage des données**
- **Analyse exploratoire (EDA)** :
  - Corrélation entre les variables et la variable cible (`Churn`)
  - Statistiques descriptives et visualisation des distributions
- **Encodage** :
  - Transformation des variables catégorielles par `get_dummies` (one-hot encoding)
- **Création d’un environnement de travail modulaire** avec :
  - `requirements.txt`
  - `README.md` documenté
  - Arborescence propre pour évoluer vers la modélisation

## Prochaines étapes

- Implémentation des modèles prédictifs (Logistic Regression, Random Forest, etc.)
- Évaluation des performances (Accuracy, Recall, AUC, etc.)
- Export des modèles et automatisation du pipeline

## 💡 Auteur

Projet réalisé par **Lilia Benzid** – Data Scientist junior, passionnée par la data et l’IA appliquée.
