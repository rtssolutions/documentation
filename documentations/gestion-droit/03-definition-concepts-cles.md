---
title: "03 - Définition des concepts clés"
description: ""
date: "2025-07-29"
version: "1"
---
### 📚 Tables des matières

1. [Diagramme conceptuel](#diagramme-conceptuel)  
2. [Définitions](#définitions)  
3. [Description des relations](#description-des-relations)  
4. [Gestion des permissions](#gestion-des-permissions)  
5. [Liste des permissions](#liste-des-permissions)  
6. [Consultation des permissions](#consultation-des-permissions)  
7. [Non modifiable par l’utilisateur](#non-modifiable-par-lutilisateur)

## Diagramme conceptuel

Le diagramme conceptuel permet de visualiser les relations principales entre les entités utilisées dans la gestion des droits.  
Il sert de base de compréhension pour tout utilisateur impliqué dans l’administration de la plateforme.

Les éléments suivants sont représentés :
- Rôles
- Groupes d’utilisateurs
- Utilisateurs
- Périmètres
- Permissions

Chaque entité est connectée selon les règles suivantes :
- Un **utilisateur** peut avoir plusieurs **rôles** ou appartenir à plusieurs **groupes**.
- Un **groupe** est associé à un ou plusieurs **rôles**.
- Un **rôle** donne accès à un ensemble de **permissions** sur un périmètre donné.

<img src="https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/gestion-des-droits/diagramme-concept.png" alt="Concept clés" height="200" />

## Définitions

- **Utilisateur** : personne ayant un compte sur la plateforme, identifiable par une adresse e-mail unique.
- **Rôle** : ensemble de droits applicables à un périmètre fonctionnel donné. Un rôle définit ce qu’un utilisateur peut faire.
- **Groupe d’utilisateurs** : collection d’utilisateurs partageant des rôles communs.
- **Permission** : action élémentaire autorisée par un rôle (ex. : lire, modifier, supprimer).
- **Périmètre** : espace ou contexte sur lequel s’appliquent les rôles (ex. : un centre de formation, une organisation, un domaine fonctionnel).

## Description des relations

Les relations entre entités sont les suivantes :
- Un utilisateur **peut cumuler** plusieurs rôles et groupes.
- Les **permissions ne sont pas attribuées directement** à un utilisateur, mais via un rôle.
- Les rôles peuvent être attribués :
  - directement à un utilisateur,
  - ou indirectement via un groupe.
- Un périmètre est un ensemble d'organisations

## Gestion des permissions

Les permissions sont centralisées et prédéfinies par la plateforme Papaours.  
Elles sont regroupées par modules ou fonctionnalités (ex. : gestion des apprenants, contrats, sessions de formation, etc.).

### Liste des permissions

Chaque permission est identifiée par :
- un code technique (ex. : `apprenant.lire`)
- une description fonctionnelle (ex. : “Consulter les informations d’un apprenant”)

### Consultation des permissions

Les administrateurs ont une interface dédiée leur permettant de :
- visualiser l’ensemble des permissions existantes,
- rechercher une permission par mot-clé ou code,
- visualiser les permissions d'un rôle.

### Non modifiable par l’utilisateur

Les permissions sont gérées par l’éditeur de la plateforme Papaours
Un utilisateur ne peut pas modifier ses propres permissions.


### Pour aller plus loin
-> [04 - Accéder à la gestion des droits](04-acceder-gestion-droits)
   
[Retour à l'Accueil](../accueil)
