---
title: "01 - Introduction"
description: "Présentation du dossier de formation"
date: "2025-01-26"
version: "1"
---
# Le dossier de formation dans Papaours

## Table des matières

1. [Qu'est-ce qu'un dossier de formation ?](#quest-ce-quun-dossier-de-formation)
   - [Définition et rôle](#définition-et-rôle)
   - [Fonctions principales](#fonctions-principales)
   - [Public visé par la documentation](#public-visé-par-la-documentation)
2. [Les composants d'un dossier](#les-composants-dun-dossier)
   - [Documents associés](#documents-associés)
3. [États et situations](#états-et-situations)
   - [Les 5 états d'un dossier de formation](#les-5-états-dun-dossier-de-formation)
   - [Transitions entre états](#transitions-entre-états)
   - [Règles de création de contrat](#règles-de-création-de-contrat)

## Qu'est-ce qu'un dossier de formation ?

### Définition et rôle

Un **dossier de formation** regroupe toutes les informations et documents liés au parcours d'un apprenant dans une session de formation.

Chaque dossier associe :
- **Un apprenant** : personne inscrite à la formation
- **Une session de formation** : période durant laquelle se déroule la formation
- **Une liste potentielle de contrat**
- **Des documents** : pièces administratives et pédagogiques

Le dossier permet le suivi individuel de chaque apprenant au sein d'une session de formation.

### Fonctions principales

Le dossier de formation remplit plusieurs fonctions :

- **Centralisation** : Il rassemble en un seul endroit tous les éléments du parcours de l'apprenant 
- **Timeline**  : Il permet de comprendre dans le temps ce qui constitue la période de formation d’un apprenant pour l’obtention d’un titre ou diplôme via la timeline du dossier. 
- **Suivi** : Le système calcule pour vous la situation actuelle du dossier. C’est ce qui permet de suivre vos effectifs et situation de chacun de vos apprenants au sein de votre centre.
### Public visé par la documentation

Cette documentation s'adresse aux administrateurs et gestionnaires qui interviennent dans le cycle de vie d'un dossier de formation.

## Les composants d'un dossier

### Documents associés

Un encart **Documents** centralise les pièces du dossier :

- **Documents administratifs** : Cerfa P2S, conventions, attestations, etc.

## États et situations

Le dossier possède un **état** qui évolue automatiquement selon la progression de l'apprenant.

### Les états d'un dossier de formation

1. **Inscrit à la formation** : L'apprenant est inscrit à la formation mais n'a pas encore de contrat
2. **SFP avant contrat** : L'apprenant est en SFP avant la signature du contrat
3. **Apprenti sous contrat** : L'apprenant a un contrat d'apprentissage actif
4. **Contrat terminé** : Le contrat de l'apprenant est terminé (fin normale ou rupture)
5. **Inscription annulée** : L'inscription de l'apprenant a été annulée

### Transitions entre états

Les changements d'état se font automatiquement selon les événements :
- Signature d'un contrat → passage à **Apprenti sous contrat**
- Fin ou rupture de contrat → passage à **Contrat terminé**
- Annulation de l'inscription → passage à **Inscription annulée**

### Règles de création de contrat

**Condition pour créer un brouillon de contrat** : Le dossier doit être dans l'état **Inscrit à la formation** uniquement.

Un brouillon de contrat ne peut pas être créé si :
- L'apprenant est déjà en SFP
- L'apprenant a déjà un contrat actif
- L'inscription a été annulée