---
title: "03 - Accéder à la gestion des droits"
description: ""
date: "2025-07-29"
version: "1"
---
### 📚 Tables des matières
1. [Où trouver la gestion des droits ?](#où-trouver-la-gestion-des-droits)  
2. [Conditions d’accès](#conditions-daccès)  
3. [Que permet le menu "Gestion des droits" ?](#que-permet-le-menu-gestion-des-droits)  
4. [Visibilité des entités](#visibilité-des-entités)  
5. [Visibilité des rôles](#visibilité-des-rôles)  
6. [Visibilité des groupes](#visibilité-des-groupes)  
7. [Visibilité des utilisateurs](#visibilité-des-utilisateurs)  
8. [Sécurité et traçabilité](#sécurité-et-traçabilité)

## Où trouver la gestion des droits ?
Le module **Gestion des droits** est accessible depuis le menu principal de la plateforme Papaours, via le menu Gestion des droits

## Conditions d’accès
Seuls les utilisateurs ayant un **rôle** disposant de permissions contenu dans la section **Gestion des permissions** peuvent voir et utiliser ce module.

Par défaut, les profils suivants peuvent accéder à ce menu :
- Administrateur Centre de formation
- Administrateur Papaours

Les utilisateurs sans les permissions adéquates n’ont pas ce menu visible dans leur interface.

![Menu d'accès à la gestion des droits](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-gestion-droits.png "338*388")


## Que permet le menu "Gestion des droits" ?
Ce menu permet de :
- Créer, modifier ou supprimer des **utilisateurs**
- Créer, modifier ou supprimer des **groupes**
- Créer, modifier ou supprimer des **rôles**
- Attribuer ou retirer des **rôles à des utilisateurs** ou groupes
- Gérer les **périmètres** associés aux rôles
- Visualiser la répartition des permissions sur les entités

C’est un **module central** pour la gouvernance des accès et la sécurisation des usages au sein de Papaours.

## Visibilité des entités
L’interface s’adapte au périmètre de l’utilisateur :  
- Un administrateur global peut voir toutes les entités
- Un administrateur restreint à une organisation ne verra que les entités relevant de son périmètre

### Visibilité des rôles
L’utilisateur voit la bibliothéque complète des rôles définis au sein de sa plateforme Papaours
> Certains rôles sont réservés et non modifiables. Ce sont généralement des rôles gérés par la plateforme Papaours directement.

### Visibilité des groupes
Les groupes visibles sont :
- ceux créés dans le périmètre de l’utilisateur,
- ou ceux auxquels il appartient.

Un utilisateur ne peut pas consulter ou modifier les groupes hors de son périmètre.

### Visibilité des utilisateurs
Selon les droits de l’utilisateur :
- Il peut consulter uniquement les utilisateurs qu’il est autorisé à gérer. 

Un utilisateur ne peut pas consulter ou modifier les utilisateurs hors de son périmètre.


## Sécurité et traçabilité
Chaque action effectuée dans le module "Gestion des droits" est tracée :
- Historique de création, modification et suppression
- Journalisation technique (logs) et horodatage précis

Retrouvez dans la section [Historique](../historique/historique), comment rechercher l'historique des actions sur ces informations


### Pour aller plus loin
-> [04 - Créer des rôles, groupes et utilisateurs](04-creation-des-entites)
   
[Retour à l'Accueil](../accueil)


