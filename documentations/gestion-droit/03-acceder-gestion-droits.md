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

Le module **Gestion des droits** est accessible depuis le menu principal de la plateforme Papaours, via le menu <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
  <path stroke-linecap="round" stroke-linejoin="round" d="M9.594 3.94c.09-.542.56-.94 1.11-.94h2.593c.55 0 1.02.398 1.11.94l.213 1.281c.063.374.313.686.645.87.074.04.147.083.22.127.325.196.72.257 1.075.124l1.217-.456a1.125 1.125 0 0 1 1.37.49l1.296 2.247a1.125 1.125 0 0 1-.26 1.431l-1.003.827c-.293.241-.438.613-.43.992a7.723 7.723 0 0 1 0 .255c-.008.378.137.75.43.991l1.004.827c.424.35.534.955.26 1.43l-1.298 2.247a1.125 1.125 0 0 1-1.369.491l-1.217-.456c-.355-.133-.75-.072-1.076.124a6.47 6.47 0 0 1-.22.128c-.331.183-.581.495-.644.869l-.213 1.281c-.09.543-.56.94-1.11.94h-2.594c-.55 0-1.019-.398-1.11-.94l-.213-1.281c-.062-.374-.312-.686-.644-.87a6.52 6.52 0 0 1-.22-.127c-.325-.196-.72-.257-1.076-.124l-1.217.456a1.125 1.125 0 0 1-1.369-.49l-1.297-2.247a1.125 1.125 0 0 1 .26-1.431l1.004-.827c.292-.24.437-.613.43-.991a6.932 6.932 0 0 1 0-.255c.007-.38-.138-.751-.43-.992l-1.004-.827a1.125 1.125 0 0 1-.26-1.43l1.297-2.247a1.125 1.125 0 0 1 1.37-.491l1.216.456c.356.133.751.072 1.076-.124.072-.044.146-.086.22-.128.332-.183.582-.495.644-.869l.214-1.28Z" />
  <path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z" />
</svg> Gestion des droits


## Conditions d’accès

Seuls les utilisateurs ayant un **rôle** disposant de permissions contenu dans la section **Gestion des permissions** peuvent voir et utiliser ce module.

Par défaut, les profils suivants peuvent accéder à ce menu :
- Administrateur Centre de formation
- Administrateur Papaours

Les utilisateurs sans les permissions adéquates n’ont pas ce menu visible dans leur interface.

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


