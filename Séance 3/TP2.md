# Découverte du Modèle d'Architecture 3-tiers 🌐

## Introduction

### Objectifs
- Comprendre le principe fondamental du modèle 3-tiers.
- Identifier les avantages et les cas d'utilisation de cette architecture.

### Étapes
1. **Discussion initiale** 🗣️ : En groupe, échangez sur ce que vous savez déjà concernant le modèle d'architecture 3-tiers. Notez les points clés.
2. **Recherche rapide** 💻 : Chacun, sur son ordinateur, recherchera rapidement sur Internet une définition et une illustration représentant l'architecture 3-tiers.
3. **Mise en commun** 📊 : Partagez vos trouvailles avec le groupe et élaborez une définition commune.

---

## Exploration du modèle 3-tiers

### Objectifs
- Comprendre en détail la séparation des préoccupations du modèle 3-tiers.
- Distinguer clairement et comprendre le rôle de chaque couche : Présentation, Logique Métier et Données.

### Étapes
1. **Présentation des couches** 📜 :
   - **Couche de Présentation** : C'est la couche qui interagit directement avec l'utilisateur. Elle affiche les données à l'utilisateur et prend en charge les interactions utilisateur (UI/UX).
   - **Couche Logique Métier** : C'est le cœur de l'application. Elle traite la logique et les validations.
   - **Couche de Données** : Cette couche interagit avec la base de données et gère les opérations CRUD (Créer, Lire, Mettre à jour, Supprimer).

2. **Discussion sur les couches** 📜 :
   - **Couche de Présentation** : Discutez de l'importance de l'interaction utilisateur et comment cela influence le design et les technologies choisies. Pourquoi est-il crucial de séparer cette couche des autres?
   - **Couche Logique Métier** : Débattez sur les types de logiques et de validations qui pourraient être nécessaires dans diverses applications. Pourquoi cette couche ne devrait-elle pas interagir directement avec la base de données?
   - **Couche de Données** : Pourquoi est-il essentiel de séparer la gestion des données de la logique métier? Discutez de l'importance des opérations CRUD.

3. **Exercice individuel** 📖 : 
   - Chaque étudiant prendra une application qu'il utilise régulièrement (par exemple, une application de messagerie ou de médias sociaux). Essayez de décomposer cette application en couches 3-tiers. Notez les éléments que vous estimez faire partie de chaque couche.

4. **Partage des décompositions** 💬 : 
   - Formez de petits groupes et partagez vos décompositions. Comparez vos choix avec ceux de vos camarades et discutez des différences.

5. **Exemple détaillé** 🚀 : Prenons une application de réservation de cinéma en ligne.
   - **Couche de Présentation** : Interface permettant de voir les films à l'affiche, de choisir une séance, de sélectionner des sièges, etc.
   - **Couche Logique Métier** : Vérification de la disponibilité des sièges, calcul du prix total en fonction des promotions ou des réductions de fidélité, etc.
   - **Couche de Données** : Base de données contenant les informations sur les films, les séances, les sièges réservés, etc.

6. **Exercice d'application** 🛠️ : 
   - À partir de l'exemple du cinéma, choisissez une fonctionnalité spécifique (par exemple, la réservation d'un siège). Essayez de détailler comment chaque couche interviendrait dans cette fonctionnalité. Rédigez un pseudo-code ou un diagramme pour illustrer cela.


---

## Activité pratique : Conception d'une mini-application selon le modèle 3-tiers

### Objectifs
- Appliquer la connaissance du modèle 3-tiers.
- Créer une mini-application suivant ce modèle.

### Étapes
1. **Choix du sujet** 🧠 : En groupe, choisissez une idée simple pour une mini-application (par exemple, une application de gestion de tâches).
2. **Esquisse de la Couche de Présentation** 🎨 : Dessinez ou utilisez un outil de maquettage pour créer une interface utilisateur simple.
3. **Logique Métier** 💼 : Écrivez pseudo-code ou du vrai code pour la logique métier de votre application. Par exemple:
   ```python
   def ajouter_tache(liste, tache):
       if tache not in liste:
           liste.append(tache)
       return liste

   # ...
   ```
4. **Couche de Données** 💽 : Créez une structure de données simple (comme une liste ou un dictionnaire) pour stocker les données de votre application. Pensez à comment vous interagirez avec cette structure pour les opérations CRUD.
5. **Intégration** 🔗 : Essayez de combiner toutes les étapes pour avoir une vue d'ensemble de votre mini-application.

---

## Conclusion et Retour

### Objectifs
- Réfléchir sur ce que vous avez appris.
- Discuter des avantages et inconvénients du modèle 3-tiers.

### Étapes
1. **Discussion de groupe** 🌟 : Qu'avez-vous appris ? Quels sont les avantages du modèle 3-tiers ? Y a-t-il des inconvénients ou des défis spécifiques ?
2. **Feedback** 📝 : Chaque étudiant écrit un court retour sur cette activité. Qu'avez-vous aimé ? Qu'est-ce qui pourrait être amélioré ?

N'oubliez pas de **pusher** votre travail sur GitHub et de partager vos liens avec la classe ! 🚀🎉

---

Bonne découverte et bon travail à tous ! 🌟👩‍💻👨‍💻