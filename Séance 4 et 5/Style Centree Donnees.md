# Exploration du Style Architectural "Centré sur les données" : Naviguer à travers les Données

## Partie Théorique
**Durée estimée : 30 minutes**

### Objectifs
- Comprendre le concept du style architectural centré sur les données.
- Découvrir les avantages et les défis associés à ce style.
- Reconnaître les scénarios d'application typiques de ce style.

### Étapes

1. **Introduction au style centré sur les données** :
   - Dans ce style, l'accent est mis sur la manière dont les données sont stockées, accédées et gérées, tandis que la logique du système est souvent structurée autour des données elles-mêmes. 📊

2. **Avantages** :
   - Cohérence des données: Facilité de maintien de l'intégrité des données.
   - Performance: Optimisation des accès aux données.

3. **Inconvénients** :
   - Couplage: Risque de dépendance forte entre les données et la logique.
   - Flexibilité: Difficulté de modification de la structure des données.

4. **Cas d'utilisation typiques** :
   - Bases de données, Systèmes de gestion de données, etc.

5. **Discussion en classe** :
   - Partagez des exemples de la vie réelle où ce style est utilisé, et discutez de son efficacité dans ces scénarios. 💬

## Partie Pratique
**Durée estimée : 1 heure 30 minutes**

### Objectifs
- Imprégner le style centré sur les données via un exemple codé.
- Analyser et modifier un exemple donné pour mieux comprendre et appliquer ce style.

### Étapes

1. **Exemple Guidé** :
   - Voici un exemple d'une application Python simple qui utilise une base de données SQLite pour stocker et récupérer des données. 🐍

```python
import sqlite3

# Connexion à la base de données
conn = sqlite3.connect('example.db')

def create_table():
    with conn:
        conn.execute("""
            CREATE TABLE IF NOT EXISTS user (
                id INTEGER PRIMARY KEY,
                name TEXT,
                age INTEGER
            );
        """)

def insert_data(name, age):
    with conn:
        conn.execute("INSERT INTO user (name, age) VALUES (?, ?);", (name, age))

def fetch_data():
    with conn:
        data = conn.execute("SELECT * FROM user;").fetchall()
    return data

def display_data(data):
    for row in data:
        print(f'ID: {row[0]}, Name: {row[1]}, Age: {row[2]}')

# Appel principal
create_table()
insert_data('Alice', 25)
insert_data('Bob', 30)
data = fetch_data()
display_data(data)
```

2. **Analyse et Amélioration** :
   - Analysez le code fourni. Identifiez des moyens d'améliorer la gestion des erreurs, de modulariser davantage le code, ou d'ajouter des fonctionnalités supplémentaires comme la mise à jour et la suppression des données. 🔄

3. **Exercice Individuel** :
   - Ajoutez des méthodes pour mettre à jour et supprimer des données dans la base de données. Assurez-vous que votre code est bien structuré et suit le style centré sur les données. 🚀

4. **Retour en Groupe** :
   - Partagez vos solutions, discutez des différentes approches, et explorez les bonnes pratiques pour la gestion des données et la modularité dans le style centré sur les données.

🤗

5. **Discussion finale** :
   - Réflexion sur les leçons apprises, et comment elles peuvent être appliquées dans des projets futurs. Récapitulatif des points clés du style centré sur les données. 🎉

Cette activité devrait vous aider à avoir une compréhension solide du style architectural centré sur les données, et à être prêt à l'appliquer dans vos futurs projets !