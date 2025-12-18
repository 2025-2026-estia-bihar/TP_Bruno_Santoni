🖼️ Sous-projet 1 – Classification d’images (Deep Learning I)
Objectif

Concevoir, implémenter et documenter un pipeline de classification d’images
multi-classes à l’aide de réseaux de neurones convolutifs (CNN).

Le modèle doit prédire la classe associée à une image prise dans un champ de maïs.

Données

Le jeu de données est constitué d’images prises dans un champ de maïs, disponibles
sur Kaggle. Les images ont été capturées à l’aide d’un smartphone afin de simuler
l’utilisation d’une caméra embarquée sur une machine agricole.

Classes cibles

Chao : sol nu

Milho : maïs

Ervas : mauvaises herbes

Milho_ervas : présence conjointe de maïs et de mauvaises herbes

Les noms des classes sont conservés afin de rester cohérents avec la nomenclature
originale du jeu de données.

Méthodologie

Prétraitement des images (redimensionnement, normalisation)

Implémentation d’un CNN simple servant de modèle baseline

Utilisation de l’apprentissage par transfert avec un modèle préentraîné (VGG16)

Évaluation des performances à l’aide :

des courbes de loss et d’accuracy,

d’une matrice de confusion

Analyse qualitative des prédictions :

probabilités par classe,

interprétation locale à l’aide de LIME

Résultats

L’apprentissage par transfert permet d’améliorer significativement les performances
par rapport au CNN baseline. Les analyses montrent néanmoins des confusions
persistantes entre certaines classes visuellement proches.

⏱️ Sous-projet 2 – Prévision de séries temporelles (Machine Learning II)
Objectif

Développer un pipeline de prévision de températures basé sur des séries
temporelles réelles, avec un pas de temps de 3 heures.

Données

Les données proviennent de l’API Open-Meteo (Historical Weather API) et
correspondent à la température à 2 mètres du sol pour une ville donnée,
sur une période pluriannuelle.

Prétraitement

Nettoyage et conversion des données

Agrégation temporelle vers un pas de temps de 3h

Gestion des valeurs manquantes par interpolation

Création de variables retardées (lags)

Modèles expérimentés

Baseline naïve

Régression linéaire

Random Forest Regressor

ARIMA

SARIMA

SARIMAX

Évaluation

Les modèles sont comparés à l’aide des métriques suivantes :

MAE (Mean Absolute Error)

RMSE (Root Mean Squared Error)

Une analyse des résidus est réalisée sur le meilleur modèle afin d’évaluer la qualité
des prédictions et l’absence de biais systématique.

Conclusion

Les résultats montrent que les modèles de Machine Learning, en particulier le
Random Forest, offrent les meilleures performances pour la prévision à court terme,
tandis que les modèles statistiques restent utiles pour l’analyse de la structure
temporelle de la série.
