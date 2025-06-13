# Examen d'Industrialisation des Services - Printemps 2024

- **Département :** Informatique de Gestion  
- **Module :** Industrialisation des services  
- **Module n° :** 62-61  
- **Date :** 12/06/2024  
- **Durée :** 2 heures  

## Étudiant-e

- **Nom :**  
- **Prénom :**  

## Examinateur

- **Nom :** Robin  
- **Prénom :** Matthieu  

---

## Question 1 : Git et GitFlow (20 points)

### Git

#### Fonctionnement général (5 pts)
#### Décrivez le fonctionnement de Git en termes de gestion de versions distribuée. Discutez de la différence entre un dépôt local et un dépôt distant. (5 points)

Git est un **système de gestion de version distribué**. Cela signifie que chaque développeur possède une **copie complète du projet**, avec tout son historique, localement.  
- Un **dépôt local** est celui présent sur ta machine, sur lequel tu travailles avec `git add`, `git commit`, etc.  
- Un **dépôt distant** (souvent sur GitHub, GitLab…) est une version centralisée du projet, utilisée pour collaborer via `git push` et `git pull`.

#### git merge vs git rebase (5 pts)

| Commande     | Description | Exemple d’usage |
|--------------|-------------|------------------|
| `git merge`  | Combine deux branches tout en conservant l’historique (avec un commit de fusion) | Fusionner `feature-x` dans `develop` sans réécrire l’historique |
| `git rebase` | Applique les commits d’une branche sur une autre de manière linéaire | Nettoyer l’historique de `feature-x` avant de la fusionner dans `develop` |

**Exemple :**
```bash
# Avec merge
git checkout develop
git merge feature-x

# Avec rebase
git checkout feature-x
git rebase develop

#### Imaginez que vous travaillez sur une équipe de développement de 10 personnes avec des cycles de release mensuels. Détaillez comment vous gérerez les branches et les versions en utilisant GitFlow, en tenant compte des pull-requests et des revues de code. 

🔹 GitFlow
🔸 Branches GitFlow (5 pts)
main/master : contient les versions stables mises en production.

develop : version de développement intégrant les dernières fonctionnalités.

feature/ : une branche par fonctionnalité en cours de dev, issue de develop.

release/ : préparation d’une nouvelle version stable (tests, corrections…).

hotfix/ : correction urgente d’un bug détecté sur main.

🔸 Organisation d’une équipe (5 pts)
Avec 10 personnes et des cycles mensuels :

Chaque dev travaille sur une feature branch.

À la fin du sprint, les features sont mergées sur develop via pull-request + code review.

Une release branch est créée pour stabiliser la version.

Après validation, la branche est mergée dans main et develop.
