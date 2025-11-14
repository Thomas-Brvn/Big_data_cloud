# Dashboard interactif des restaurants de New York  
Analyse, visualisation et exploration des restaurants de NYC via Streamlit et MongoDB Atlas

---

## Présentation du projet

Ce projet propose une application Streamlit permettant d'explorer les restaurants de New York à partir de la base d'exemple MongoDB Atlas "sample_restaurants".  
Elle permet de :

- Visualiser les restaurants sur une carte interactive en mode points ou heatmap
- Filtrer par borough (Manhattan, Brooklyn, etc.)
- Filtrer par type de cuisine
- Afficher un tableau des données filtrées
- Générer des graphiques (Seaborn / Matplotlib)

Ce projet montre l'utilisation combinée de :
- MongoDB Atlas
- Streamlit
- PyDeck pour la visualisation géographique

---

## Fonctionnalités principales

### Carte interactive
- Affichage des restaurants géolocalisés
- Mode heatmap pour visualiser la densité
- Tooltip dynamique contenant le nom et le type de cuisine

### Filtres
- Filtre par borough
- Filtre par type de cuisine

### Visualisations
- Répartition du nombre de restaurants par borough
- Top 10 des types de cuisines
- Tableau des restaurants filtrés

---

## Installation

### 1. Cloner le projet
```bash
git clone https://github.com/<votre-username>/<nom-du-repo>.git
cd <nom-du-repo>
```


### 2. Créer un environnement virtuel 

```bash
python3 -m venv env
source env/bin/activate   # Mac / Linux
env\Scripts\activate      # Windows
```

### 3. Installer les dépendances

```bash
pip install -r requirements.txt
```


### 4. Lancement de l'application

```bash
streamlit run app.py
```

### Base de données
Ce dashboard utilise une base MongoDB Atlas.
Si vous utilisez votre propre cluster, remplacez l’URI dans app.py :

```bash
mongodb+srv://<user>:<password>@<cluster>.mongodb.net/
```

### Structure du projet
```bash
projet-restaurants-nyc/
│
├── app.py                 # Code principal Streamlit
├── README.md              # Documentation du projet
├── requirements.txt       # Dépendances
├── .gitignore             # Fichiers ignorés par Git
└── run.sh                 # Script de lancement (Linux / Mac)
```


