# 🚗 Projet d'Analyse et de Prédiction du Trafic Routier (PeMS07)

Bienvenue dans ce dépôt dédié à l'analyse et à la prédiction du trafic routier, basé sur le célèbre jeu de données californien **PeMS07**.

👉 **[Visualiser le Notebook complet avec tous les graphiques (Atelier.html)](https://zinebsaadeddine11.github.io/TraficRoutier_Projet/Atelier.html)**  


---

## 📖 Description de l'Atelier / Notebook

Le fichier principal (`Atelier.ipynb`) est un pipeline complet allant de l'exploration des données à la prédiction via des modèles de Machine Learning et Deep Learning basés sur des séries temporelles complexes. Voici les grandes étapes traitées :

### 1. Analyse Exploratoire et Traitement des Données (EDA)
- **Chargement et Nettoyage** : Agrégation des données de trafic capturées toutes les 5 minutes sur un réseau de capteurs géants.
- **Bilan de Santé des Capteurs** : Identification des capteurs défaillants ou constants.
- **Classification du Trafic** : Définition de seuils statiques pour catégoriser la circulation (Fluide, Congestion, Bouchons).
- **Profils Temporels** : Extraction et visualisation des comportements de trafic horaires (Profil journalier) et journaliers (Profil hebdomadaire).
- **Corrélations Spatiales** : Étude de la corrélation d'un capteur avec les autres voisins dans le réseau routier.

### 2. Modélisation et Prédiction (Séries Temporelles)
Afin de prédire l'état futur du trafic (séquences de 12 pas de temps, soit 60 minutes de prévision), cinq approches ont été soigneusement implémentées et comparées (suivi d'un benchmark de temps d'exécution) :
- 📊 **SARIMAX (ARIMA + Saisonnalité de Fourier)** : Modèle statistique de référence intégrant des variables exogènes pour modéliser la cyclicité du trafic (ex: pics à l'heure de pointe).
- 📉 **SVM (Support Vector Machine / SVR)** : Modèle de Machine Learning classique robuste, utilisant un noyau RBF adaptatif (implémentation via MultiOutputRegressor).
- 🧠 **Simple RNN (Réseau de Neurones Récurrents)** : Utilisation de modèles séquentiels avec TensorFlow/Keras pour initier l'apprentissage profond sur des séries.
- 💡 **LSTM (Long Short-Term Memory)** : Version avancée du RNN utilisée pour s'affranchir du problème de disparition du gradient et parfaitement modéliser les dépendances temporelles à plus long terme.
- 🌐 **GCN (Graph Convolutional Network)** : Implémentation d'un réseau de neurones convolutif sur graphes personnalisé (Keras Custom Layer) pour modéliser efficacement la topologie et la structure géospatiale du réseau routier.

### 3. Évaluation des Performances Spatio-Temporelles
- Comparaison de l'erreur des **5 modèles** via un classement (Tableau Comparatif détaillé avec graphiques en barres) pour les métriques de régression globales : MSE, RMSE, MAE, R².
- Évaluation de la capacité à détecter spécifiquement les congestions routières via la matrice de confusion, la Précision, le Rappel et le F1-Score.
- Visualisations avancées des prédictions capteur par capteur et distribution globale des résidus d'erreur.

---

## 📂 Contenu de ce dépôt

- `Atelier.ipynb` : Le code source Jupyter en format léger pour être visible directement sur GitHub, incluant le code optimisé des 5 modèles.
- `Atelier.html` : L'export statique complet du notebook avec l'intégralité des exécutions, comparaisons graphiques finales et visualisations interactives.
- `PEMS07/` : Les données sources brutes du projet (trackées avec Git LFS).
