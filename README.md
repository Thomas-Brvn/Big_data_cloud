# Dashboard Vélib Paris - TD1 🚲

## Description

Ce projet est un **dashboard interactif** pour visualiser la disponibilité des vélos Vélib en temps réel à Paris.  
Il se connecte à une **base de données MongoDB** contenant les données des stations, et affiche :  

![Exemple de la carte](https://github.com/Thomas-Brvn/images/blob/main/velib1.jpg)


- Une **carte interactive** des stations avec un code couleur selon la disponibilité des vélos.  
- Un **tableau des stations les plus proches** par rapport à une adresse entrée par l’utilisateur.  
- Des **graphes analytiques** :  
  - Jauge du nombre total de vélos disponibles  
  - Top 10 des stations avec le plus de vélos  
  - Répartition des vélos par arrondissement
 

![Exemple de la carte](https://github.com/Thomas-Brvn/images/blob/main/velib2.jpg)

L’utilisateur peut entrer son **adresse à Paris** pour visualiser les stations autour de lui et la distance vers chacune.  

---

## Fonctionnalités principales

1. **Carte interactive (Folium)**  
   - Marqueurs colorés :  
     - **Vert** : plus de 5 vélos  
     - **Orange** : 1 à 5 vélos  
     - **Rouge** : 0 vélo disponible  
   - Marqueur bleu indiquant **l’adresse de l’utilisateur**  
   - Trait bleu vers les stations proches (<500 m)  

2. **Tableau des stations les plus proches**  
   - Nom de la station  
   - Nombre de vélos disponibles  
   - Distance (en mètres) par rapport à l’adresse  

3. **Graphiques analytiques (Plotly)**  
   - Jauge de vélos totaux disponibles  
   - Top 10 stations avec le plus de vélos  
   - Répartition des vélos par arrondissement  

velib_dashboard/
│
├── app.py # Code principal Streamlit
├── requirements.txt # Dépendances Python
├── README.md # Documentation du projet
└── data/ # (Optionnel) dossier pour fichiers de données locaux



- **MongoDB Atlas** contient la collection `stations` avec les données des stations Vélib.  
- **Python** et **Streamlit** permettent la visualisation interactive.  
- **Folium** pour la carte et le clustering des stations.  
- **Plotly** pour les graphiques interactifs.  

---

## Installation

1. Cloner le projet :  
```bash
git clone https://github.com/ton-compte/velib_dashboard.git
cd velib_dashboard
```
2. Cloner le projet :
```bash
python -m venv venv
source venv/bin/activate   # Mac/Linux
# ou venv\Scripts\activate # Windows

pip install -r requirements.txt
```
## Utilisation
Entrez une adresse à Paris dans le champ prévu.
La carte s’affiche avec les stations et leur disponibilité.
Le tableau à droite montre les stations les plus proches avec la distance.
Les graphes en dessous permettent d’analyser rapidement la disponibilité des vélos dans toute la ville.


# Projet Neo4j - Analyse de données type Stack Overflow - TD2

Ce projet consiste en la création d'une base de données **graph** avec Neo4j à partir de données liées à une plateforme de questions/réponses similaire à Stack Overflow. L'objectif est d'explorer les relations entre utilisateurs, questions, réponses et tags, et de créer un **dashboard** pour visualiser certaines analyses.

---
![Exemple de la carte](https://github.com/Thomas-Brvn/images/blob/main/neo4j3.jpg)
## Contenu du projet

- **Import des données** : Les données ont été importées dans Neo4j et structurées sous forme de graphes, permettant d'exploiter les relations entre utilisateurs, questions, réponses et tags.  
- **Graphes créés** : 
  - Utilisateurs et leurs réponses
  - Questions et leurs tags
  - Relations entre utilisateurs et tags via leurs contributions
- **Requêtes Cypher** : Plusieurs requêtes ont été développées pour analyser les données :
  - Nombre de questions posées et réponses apportées par utilisateur
  - Questions les plus populaires par tag
  - Utilisateurs les plus actifs sur certains tags
  - Graph des relations entre utilisateurs et tags
- **Dashboard** : Un dashboard final permet de visualiser les statistiques principales et les insights issus des graphes.


---

## Technologies utilisées

- **Neo4j** : Base de données graphe pour stocker et interroger les données.  
- **Cypher** : Langage de requête pour graphes Neo4j.  
- **Tableau / Neo4j Bloom / Dashboards personnalisés** : Pour la visualisation et l'analyse des résultats.

---

## Exemple de requêtes

```cypher
// Nombre de questions par utilisateur
MATCH (u:User)-[:ASKED]->(q:Question)
RETURN u.name, COUNT(q) AS nb_questions
ORDER BY nb_questions DESC
LIMIT 10;

// Top tags les plus utilisés
MATCH (:Question)-[:HAS_TAG]->(t:Tag)
RETURN t.name, COUNT(*) AS nb_questions
ORDER BY nb_questions DESC
LIMIT 10;
```

Objectifs
Explorer les interactions entre utilisateurs et contenus.
Identifier les utilisateurs les plus actifs et les tags les plus populaires.
Créer des visualisations intuitives pour représenter les insights issus du graphe.

## Organisation du projet

/projet-neo4j/
│
├─ data/                  # Données importées
├─ scripts/               # Scripts d'import et requêtes Cypher
├─ dashboard/             # Visualisations finales
└─ README.md


## Apercu
![Exemple de la carte](https://github.com/Thomas-Brvn/images/blob/main/neo4j1.jpg)
![Exemple de la carte](https://github.com/Thomas-Brvn/images/blob/main/neo4j2.jpg)

