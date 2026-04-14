# 🚗 Projet d'Analyse et de Prédiction du Trafic Routier (PeMS07)

Bienvenue dans ce dépôt dédié à l'analyse et à la prédiction du trafic routier, basé sur le célèbre jeu de données californien **PeMS07**.

👉 **[Visualiser le Notebook complet avec tous les graphiques (Atelier.html)](https://zinebsaadeddine11.github.io/TraficRoutier_Projet/Atelier.html)**  
*(Nécessite l'activation de GitHub Pages)*

---

## 📖 Description de l'Atelier / Notebook

Le fichier principal (`Atelier.ipynb`) est un pipeline complet allant de l'exploration des données à la prédiction via des modèles de Machine Learning et Deep Learning. Voici les grandes étapes traitées :

### 1. Analyse Exploratoire et Traitement des Données (EDA)
- **Chargement et Nettoyage** : Agrégation des données de trafic capturées toutes les 5 minutes sur un réseau de capteurs.
- **Bilan de Santé des Capteurs** : Identification des capteurs défaillants ou constants.
- **Classification du Trafic** : Définition de seuils statiques pour catégoriser la circulation (Fluide, Congestion, Bouchons).
- **Profils Temporels** : Extraction et visualisation des comportements de trafic horaires (Profil journalier) et journaliers (Profil hebdomadaire).
- **Corrélations Spatiales** : Étude de la corrélation d'un capteur avec les autres.

### 2. Modélisation et Prédiction (Séries Temporelles)
Afin de prédire l'état futur du trafic (séquences de 12 pas de temps, soit 60 minutes de prévision), trois approches différentes sont implémentées et comparées :
- 🧠 **Simple RNN (Réseau de Neurones Récurrents)** : Utilisation de TensorFlow/Keras pour capturer la dynamique temporelle complexe.
- 📉 **SVM (Support Vector Machine / SVR)** : Modèle de Machine Learning classique utilisant un noyau RBF (implémentation via MultiOutputRegressor).
- 📊 **SARIMAX (ARIMA + Saisonnalité de Fourier)** : Modèle statistique de référence intégrant des variables exogènes pour modéliser la cyclicité du trafic.

### 3. Évaluation des Performances
- Comparaison de l'erreur des modèles via des métriques de régression (MSE, RMSE, MAE, R²).
- Évaluation de la capacité à détecter spécifiquement les embouteillages via la Précision, le Rappel, le F1-Score et des Matrices de Confusion.
- Visualisations des prédictions capteur par capteur et distribution des résidus d'erreur.

---

## 📂 Contenu de ce dépôt

- `Atelier.ipynb` : Le code source Jupyter (nettoyé de ses sorties pour être visible de manière fluide directement sur GitHub).
- `Atelier.html` : L'export statique complet du notebook incluant toutes les exécutions et visualisations (accessible via le lien tout en haut).
- `PEMS07/` : Les données sources du projet.