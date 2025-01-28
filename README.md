# IFT5768A_Projet Équipe A-04

**Étape 1 : Traitement et Visualisation des Données NHL**

Aperçu du Projet
Dans cette étape, nous nous concentrons sur l’acquisition et l’exploration des données de jeu en direct de la NHL en utilisant l'API publique de la NHL. Les principaux objectifs de ce projet incluent:

1. **Traitement des données:** Acquisition des données brutes de l'API de la NHL et conversion en un format utilisable.
2. **Nettoyage des données** Pour une analyse ultérieure.
3. **Debbogeur interactif:** Offre une exploration approfondie de tous les évéenments par saison donnée.
4. **Visualisation:** Création de visualisations simples et avancées pour obtenir des informations à partir des données, y compris des cartes de tirs et de buts.
5. **Article de Blog:** Documentation des résultats dans un blog statique en utilisant Jekyll.

**Étape 2 : l'ingénierie des caractéristiques, la sélection des caractéristiques et la modélisation statistique**

1. **Ingénierie des caractéristiques**

**Création et sélection de caractéristiques** : Identifier et concevoir des caractéristiques pertinentes à partir des données disponibles, comme la position des tirs, le temps de jeu restant, ou encore les informations contextuelles telles que le score au moment de l'action.  
**Encodage et transformation** : Préparer les caractéristiques non numériques ou catégoriques en utilisant des méthodes comme le one-hot encoding, le label encoding, ou encore les embeddings si nécessaire.  

2. **Modélisation statistique et apprentissage automatique**

**Expérimentation avec différents classificateurs** : Tester plusieurs algorithmes d’apprentissage automatique, tels que la regression logistique, XG boost, les forêts aléatoires (Random Forest), les machines à vecteurs de support (SVM), ou les réseaux neuronaux.  
**Combinaison des caractéristiques** : Analyser l'impact de différentes combinaisons de caractéristiques sur la performance des modèles et ajuster en conséquence.  
**Métriques d'évaluation** : Se familiariser avec et utiliser des métriques clés comme les courbes ROC, l'AUC, la précision,  pour évaluer les performances des modèles.  
**Justification des résultats** : Produire des graphiques et des visualisations (courbes ROC, importance des caractéristiques, etc.) pour appuyer les choix méthodologiques.

3. **Reproductibilité et suivi des expériences**

Bonnes pratiques : Adopter de  l'outil wandb pour suivre les hyperparamètres, les versions de données et les performances des modèles.  
Documentation : Enregistrer chaque expérience, incluant les configurations des modèles et les résultats obtenus, pour une analyse future et une reproductibilité totale.  

4. **Article de Blog:** Documentation des résultats dans un blog statique en utilisant Jekyll.


**Étape 3 : Déploiement et Visualisation des Modèles NHL**

1. **Modèle "Déploiement"**  
**Modèle en tant que service** :  
Transformer les modèles d'apprentissage automatique en services accessibles via une API. Cela inclut la création d’un endpoint permettant aux utilisateurs de soumettre des données et de recevoir des prédictions en retour.  
**Gestion des dépendances de modèles (Docker) :**  
Utiliser Docker pour contenir et gérer les dépendances du modèle (frameworks ML, bibliothèques spécifiques). Construire une image Docker pour faciliter le déploiement.
**API REST :**  
Mettre en œuvre une API REST avec le framework  Flask  pour rendre le modèle accessible à d'autres utilisateurs.  

2. **"Production"/Live Workflows**  
**Écriture :**  
Intégrer le modèle dans des workflows de production, comme Un système qui analyse les tirs en direct lors des matchs et affiche les probabilités en temps réel.  
3. **Visualisation interactive**  
**Streamlit pour une accessibilité intuitive** :  
Créer une application Streamlit pour permettre aux utilisateurs non techniques d’explorer les prédictions et les résultats du modèle (utilisateurs peuvent entrer des données manuellement (position du tir, distance, etc.) et visualiser les prédictions.)  

### Structure de projet
/ift6758_projet  
├── /data                # Stocke les données brutes et traitées  
├── /docker-project_vf   # Servive Doker  
├── /figures              # Tous les images utilisées dans les visualisations et tous les visualisations  
├── /notebooks           # Notebooks Jupyter pour toutes les etapes du projet  
├── /source                 # Code source Python pour les applications  
├── README.md            # Aperçu du projet et instructions  
└── requirements.txt     # Dépendances Python  

### Instructions d’Installation
1. Cloner le Dépôt
```bash
Copy code
git clone https://github.com/votre-utilisateur/ift6758_projet.git
cd ift6758_projet
```

2. Installer les Dépendances
Vous pouvez installer les packages requis en utilisant soit conda, soit pip.

Utiliser Conda :
```
bash
Copy code
conda env create -f environment.yml
conda activate ift6758
```
Utiliser Pip :

```
bash
Copy code
pip install -r requirements.txt
```

3. Télécharger les Données NHL
Pour télécharger les données de jeu en direct de la NHL, vous pouvez exécuter le script suivant :
```
bash
Copy code
python src/data_acquisition.py
```
Le script téléchargera les données pour les saisons NHL spécifiées et les stockera dans le dossier /data.

4. Lancer les Notebooks Jupyter
Pour explorer et visualiser les données, lancez les Notebooks Jupyter :
```
bash
Copy code
jupyter notebook
```
