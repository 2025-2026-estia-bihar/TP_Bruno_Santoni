# MSc BIHAR – Projet Final (BIHAR-CORSE)

Ce dépôt contient les premiers sous-projets réalisés dans le cadre du **Projet Final MSc BIHAR (ESTIA)** :
-  Classification d’images (Deep Learning I)
-  Prévision de séries temporelles (Machine Learning II)

L’objectif est de concevoir, implémenter et documenter des pipelines de modèles
adaptés à différents types de données (images et séries temporelles).

---

## 📁 Structure du dépôt

```text
├── README.md
├── api/
│   └── main.py
├── data/
│   └── .gitkeep
├── model/
│   └── registry/
├── monitoring/
│   └── output/
│       └── .gitkeep
├── notebooks/
│   ├── time_series_forecasting.ipynb
│   └── image_classification.ipynb
└── visualizations/
    └── monitoring/
        └── monitoring.py



 Sous-projet 1 – Classification d’images (Deep Learning I)
 Objectif

Classifier des images prises dans un champ de maïs en plusieurs catégories à l’aide de réseaux de neurones convolutifs.

📊 Données

Images issues d’un champ de maïs (Kaggle), capturées par smartphone pour simuler une caméra embarquée agricole.

🏷️ Classes

Chao : sol nu

Milho : maïs

Ervas : mauvaises herbes

Milho_ervas : maïs + mauvaises herbes

(Les noms sont conservés tels quels pour rester cohérent avec le dataset.)

 Outils et modèles utilisés:

Python

TensorFlow / Keras

CNN simple (baseline)

VGG16 préentraîné (Transfer Learning)

LIME (explicabilité locale)

 Évaluation

Courbes d’accuracy et de loss

Matrice de confusion

Analyse qualitative des prédictions (probabilités + LIME)

📋 Comparaison des modèles
Modèle	Accuracy validation
CNN simple (baseline)	~82 %
VGG16 (transfer learning)	~93 %

 Conclusion

Le modèle VGG16 préentraîné améliore nettement les performances par rapport au CNN baseline.
Des confusions subsistent entre les classes visuellement proches (Milho / Milho_ervas), ce qui est cohérent avec la nature des données.

Sous-projet 2 – Prévision de séries temporelles (Machine Learning II)
 Objectif

Prédire la température à 2 mètres du sol avec un pas de temps de 3 heures à partir de données météorologiques historiques.

 Données

Source : Open-Meteo (Historical Weather API)

Données de température sur plusieurs années

 Outils et modèles utilisés

Python

Pandas / NumPy

Scikit-learn

Statsmodels

 Prétraitement

Nettoyage et conversion des données

Agrégation temporelle (pas de 3h)

Interpolation des valeurs manquantes

Création de variables retardées (lags)

📈 Modèles testés

Baseline naïve

Régression linéaire

Random Forest Regressor

ARIMA

SARIMA

SARIMAX

📋 Comparaison des modèles
Modèle	MAE	RMSE
Baseline naïve	0.759	1.069
Régression linéaire	0.604	0.877
Random Forest	0.593	0.845
ARIMA (2,1,2)	5.819	6.933
SARIMA	21.58	23.06
SARIMAX	21.57	23.05

Analyse des résidus

Une analyse des résidus (histogramme + évolution temporelle) a été réalisée sur le Random Forest, montrant des erreurs globalement centrées et sans structure temporelle marquée.

 Conclusion

Les modèles de Machine Learning, en particulier le Random Forest, offrent les meilleures performances pour la prévision de température à court terme.
Les modèles statistiques (ARIMA, SARIMA, SARIMAX) restent utiles pour l’analyse de la structure temporelle mais sont moins performants en précision sur ce jeu de données.
