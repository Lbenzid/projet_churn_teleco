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
- Construire et comparer plusieurs modèles de classification
- Sélectionner les variables les plus pertinentes pour affiner les performances(via xgboost)

## Étapes réalisées

- **Chargement et nettoyage des données**
- **Analyse exploratoire (EDA)** :
  - Corrélation entre les variables et la variable cible (`Churn`)
  - Statistiques descriptives et visualisation des distributions
- **Encodage** :
- Encodage des variables catégorielles (OneHot et booléens)
- Feature engineering : création de nouvelles variables (`AvgChargesPerMonth`, `HasMultipleServices`, `IsAlone`)
- Sélection des 10 variables les plus importantes (via RandomForest)
- **Création d’un environnement de travail modulaire** avec :
  - `requirements.txt`
  - `README.md` documenté
  - Arborescence propre pour évoluer vers la modélisation


## 📊 Modèles Entraînés

### Régression Logistique (toutes variables)
| Classe | Precision | Recall | F1-Score |
|--------|-----------|--------|----------|
| 0 (non churn) | 0.83 | 0.89 | 0.86 |
| 1 (churn)     | 0.62 | 0.51 | 0.56 |
| **Accuracy globale** | **0.79** |

---

### Random Forest (toutes variables)
| Classe | Precision | Recall | F1-Score |
|--------|-----------|--------|----------|
| 0 | 0.83 | 0.89 | 0.86 |
| 1 | 0.62 | 0.48 | 0.54 |
| **Accuracy** | **0.78** |

---

### XGBoost (toutes variables)
| Classe | Precision | Recall | F1-Score |
|--------|-----------|--------|----------|
| 0 | 0.83 | 0.88 | 0.86 |
| 1 | 0.61 | 0.50 | 0.55 |
| **Accuracy** | **0.78** |

---

## Sélection des variables

Nous avons retenu les **10 variables les plus importantes** selon le modèle Random Forest :
- InternetService_Fiber optic
- Contract_Two year
- InternetService_No
- Contract_One year
- tenure
- StreamingMovies_Yes
- OnlineSecurity_Yes
- TechSupport_Yes
- PhoneService
- PaymentMethod_Electronic check


## Résultats après sélection des variables importantes

### Régression Logistique
| Classe | Precision | Recall | F1-Score |
|--------|-----------|--------|----------|
| 0 | 0.84 | 0.89 | 0.86 |
| 1 | 0.64 | 0.52 | 0.57 |
| **Accuracy** | **0.79** |

### Random Forest
| Classe | Precision | Recall | F1-Score |
|--------|-----------|--------|----------|
| 0 | 0.83 | 0.82 | 0.83 |
| 1 | 0.53 | 0.55 | 0.54 |
| **Accuracy** | **0.75** |

### XGBoost
| Classe | Precision | Recall | F1-Score |
|--------|-----------|--------|----------|
| 0 | 0.83 | 0.86 | 0.85 |
| 1 | 0.57 | 0.51 | 0.54 |
| **Accuracy** | **0.77** |


## Conclusion

- Le modèle de **régression logistique** s'est avéré aussi performant, voire meilleur que les autres en termes d'équilibre entre les métriques.
- La sélection des variables permet une simplification sans perte significative de performance.
- D'autres améliorations potentielles : tuning d’hyperparamètres, gestion du déséquilibre via oversampling/smote.


## Environnement

Voir le fichier `requirements.txt`.


## Prochaines étapes

- Export des modèles et automatisation du pipeline

## 💡 Auteur

Projet réalisé par **Lilia Benzid** – Data Scientist junior, passionnée par la data et l’IA appliquée.
