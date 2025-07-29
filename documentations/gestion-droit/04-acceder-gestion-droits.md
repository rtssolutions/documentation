---
title: "04 - Accéder à la gestion des droits"
description: ""
date: "2025-07-29"
version: "1"
---

### Tables des matières

1. [Où trouver la gestion des droits ?](#où-trouver-la-gestion-des-droits)  
2. [Conditions d’accès](#conditions-daccès)  
3. [Que permet le menu "Gestion des droits" ?](#que-permet-le-menu-gestion-des-droits)  
4. [Visibilité des entités](#visibilité-des-entités)  
5. [Visibilité des rôles](#visibilité-des-rôles)  
6. [Visibilité des groupes](#visibilité-des-groupes)  
7. [Visibilité des utilisateurs](#visibilité-des-utilisateurs)  
8. [Sécurité et traçabilité](#sécurité-et-traçabilité)

## Où trouver la gestion des droits ?

Le module **Gestion des droits** est accessible depuis le menu principal de la plateforme Papaours, généralement réservé aux administrateurs et référents organisationnels.  
Il est identifiable par une icône spécifique (ex. : cadenas ou bouclier) et se trouve dans la section "Paramètres" ou "Administration" selon la configuration de votre instance.

## Conditions d’accès

Seuls les utilisateurs ayant un **rôle autorisant explicitement l’accès à la gestion des droits** peuvent voir et utiliser ce module.

Par défaut, les profils suivants peuvent accéder à ce menu :
- Super-administrateur
- Référent sécurité
- Administrateur fonctionnel (si la permission lui est attribuée)

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
- Un administrateur restreint à un centre ou une organisation ne verra que les entités relevant de son périmètre

### Visibilité des rôles

L’utilisateur voit :
- les rôles qu’il peut attribuer selon ses propres droits,
- les rôles créés ou exposés dans son périmètre.

Certains rôles sont réservés et non modifiables.

### Visibilité des groupes

Les groupes visibles sont :
- ceux créés dans le périmètre de l’utilisateur,
- ou ceux auxquels il appartient.

Un utilisateur ne peut pas consulter ou modifier les groupes hors de son périmètre.

### Visibilité des utilisateurs

Selon les droits de l’utilisateur :
- Il peut consulter uniquement les utilisateurs qu’il est autorisé à gérer.
- Certains utilisateurs peuvent être anonymisés ou partiellement masqués.

## Sécurité et traçabilité

Chaque action effectuée dans le module "Gestion des droits" est tracée :
- Historique de création, modification et suppression
- Archivage des changements de rôle, de groupe ou de périmètre
- Journalisation technique (logs) et horodatage précis

Cela permet d’assurer un haut niveau de conformité RGPD et de suivi en cas d’audit interne ou externe.

## Sommaire

1. [Accueil](../accueil)
2. [Création des entités](05-creation-entites)

