---
title: "03 - Situation actuelle"
description: "Comprendre le calcul et le role de la situation actuelle"
date: "2025-09-29"
version: "2"
---

# La situation actuelle

## Qu'est-ce que la situation actuelle ?

La **situation actuelle** est un indicateur qui reflète l'état du dossier de formation d'un apprenant à un instant donné. Elle est **calculée automatiquement** par le système en fonction des actions réalisées et des données présentes dans le dossier.

## Comment est-elle calculee ?

### Principe de calcul

La situation actuelle n'est pas une donnée stockée mais un **calcul en temps réel** basé sur plusieurs critères :

1. **Existence d'un contrat** : Y a-t-il un contrat associé au dossier ?
2. **État du contrat** : Si un contrat existe, quel est son statut ?
3. **Dates** : Les dates de début et fin de la session de formation sont-elles atteintes ?
4. **Statut administratif** : L'apprenant est-il en SFP ?
5. **Inscription** : L'inscription est-elle active ou annulée ?


### Déclencheurs de recalcul

La situation est recalculée automatiquement lors de :
- **Création** d'un contrat
- **Signature** d'un contrat
- **Rupture** d'un contrat
- **Passage en SFP** de l'apprenant
- **Annulation** de l'inscription
- **Arrivée à échéance** des dates de la session de formation ou SFP (début, fin)

### Actions par situation

#### Inscrit à la formation
**Actions autorisées** :
- Créer un brouillon de contrat
- Ajouter/supprimer des documents
- Annuler l'inscription

#### SFP avant contrat
**Actions autorisées** :
- Consulter les informations
- Ajouter des documents

**Actions bloquées** :
- Créer un nouveau contrat
- Supprimer le dossier

#### Inscription annulée
**Actions autorisées** :

**Actions bloquées** :
- Création de contrat
- Ajout d'une SFP

## Pour aller plus loin
→ [04 - Inscription d'un apprenant](04-inscription-apprenant.md)