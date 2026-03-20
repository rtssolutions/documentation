---
title: "06 - Processus d'approbation"
description: "Comprendre et utiliser le processus d'approbation des actions de formation"
date: "2026-03-20"
version: "1"
---

# Processus d'approbation des actions de formation

## Principe

Le processus d'approbation garantit que toutes les actions de formation sont validées avant d'être utilisées. Une action non approuvée ne permet pas de créer des sessions de formation.

## Quand l'approbation est-elle requise ?

L'approbation est nécessaire dans les cas suivants :

- **Création d'une action** : toute nouvelle action de formation
- **Pré-alimentation** : actions détectées lors de l'onboarding

## Statuts d'approbation

| Statut | Description | Actions possibles |
|--------|-------------|-------------------|
| **À approuver** | En attente de validation | Approuver, Refuser |
| **Approuvée** | Validée et utilisable | Modifier, Désactiver |
| **Refusée** | Non conforme | Corriger et resoumettre |

## Accéder aux actions à approuver

### Depuis la liste des actions

1. Menu **Formations** > **Actions de formation**
2. Utilisez le filtre **Statut** et sélectionnez **À approuver**
3. La liste affiche les actions en attente

### Indicateur visuel

Les actions à approuver sont identifiables par un badge de statut spécifique.

## Approuver une action de formation

### Procédure

1. Accédez à la fiche de l'action
2. Vérifiez les informations :
   - Formation valide et approuvée
   - Unité de formation valide et approuvée
   - Cohérence du rattachement
3. Cliquez sur **Approuver**
4. Confirmez l'approbation

### Éléments à vérifier

Avant d'approuver, contrôlez :

| Élément | Point de vérification |
|---------|----------------------|
| **Formation** | Approuvée et active |
| **Unité de formation** | Approuvée et active |
| **Cohérence** | L'unité peut dispenser cette formation |

## Refuser une action de formation

Si une action n'est pas conforme :

1. Accédez à la fiche de l'action
2. Cliquez sur **Refuser**
3. Indiquez le motif du refus (recommandé)
4. Confirmez le refus

L'action reste visible mais ne peut pas être utilisée.

## Pré-alimentation automatique

### Détection des actions

Lors de l'onboarding ou de synchronisations, Papaours peut détecter automatiquement des actions de formation à partir des données existantes.

Ces actions sont créées avec le statut **À approuver** pour validation.

### Vérification recommandée

Pour les actions pré-alimentées, vérifiez particulièrement :

- La correspondance Formation / Unité
- L'absence de doublon avec des actions existantes

## Impact sur les autres modules

Une action de formation non approuvée ne peut pas être utilisée pour :

- Créer une **session de formation**
- Rattacher un **dossier de formation**

## Bonnes pratiques

- **Vérifiez régulièrement** les actions en attente d'approbation
- **Approuvez rapidement** les actions issues de formations et unités déjà validées
- **Documentez les refus** pour faciliter les corrections
- **Coordonnez** avec les responsables des formations et unités concernées

---

## Pour aller plus loin

Consultez également :
- [Approbation des formations](../formation/05-processus-approbation)
- [Approbation des sessions de formation](../session-formation/06-processus-approbation)
- [Approbation des unités de formation](../unite-formation/08-processus-approbation)
