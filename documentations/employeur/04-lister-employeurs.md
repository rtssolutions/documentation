---
title: "04 - Lister les employeurs"
description: "Affichage et navigation dans la liste des employeurs."
date: "2025-10-31"
version: "1"
---

## Table des matières

1. [Vue d'ensemble](#vue-densemble)
2. [Colonnes et informations affichées](#colonnes-et-informations-affichées)
3. [Recherche et filtrage](#recherche-et-filtrage)
4. [Tri et pagination](#tri-et-pagination)
5. [Accès et permissions](#accès-et-permissions)

---

## Vue d'ensemble

La page **Liste des employeurs** permet de consulter tous les employeurs connus du tenant de votre organisation.

- Accessible depuis le menu **Employeurs > Liste**
- Vue centralisée pour la gestion des contrats et financements
- Les actions disponibles dépendent des permissions attribuées

![Page liste employeurs](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/4/liste-employeurs.png)

---

## Colonnes et informations affichées

Chaque ligne de la liste présente les informations principales d’un employeur :

- **Nom commercial**
- **Référence**
- **SIRET**
- **Adresse complète**
- **Statut personnalisé**
- **Statut entreprise** : Actif ou Fermé, donnée récupérer depuis le référentiel d'entreprises de l'état.

---

## Recherche et filtrage

Une barre de recherche est disponible et permet de rechercher un employeur par :

- Nom commercial
- SIRET
- IDCC
- Référence

**Règles de recherche** :

- Minimum 3 caractères pour lancer la recherche
- Les résultats se filtrent en temps réel
- Possibilité d’ajouter des filtres avancés dans de futures versions

![Barre de recherche employeurs](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/4/recherche-employeurs.png)

---

## Tri et pagination

- **Tri par défaut** : Date de dernière modification
- Possibilité de trier par d’autres colonnes dans les futures versions
- **Pagination** : 10 résultats par page, navigation possible entre le page via le composant dédié

---

### Pour aller plus loin

➡️ Poursuivez avec la page suivante :  
[05 - Créer un employeur](05-creation-employeur.md)
