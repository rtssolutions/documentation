---
title: "04 - Créer une action de formation"
description: "Guide pas à pas pour créer une nouvelle action de formation"
date: "2026-03-20"
version: "1"
---

# Créer une action de formation

## Prérequis

Avant de créer une action de formation, assurez-vous que :

- La **formation** existe dans le catalogue
- L'**unité de formation** existe
- Vous disposez des **droits** nécessaires à la création

## Accéder à la création

### Depuis une formation

1. Accédez à la fiche de la formation
2. Onglet **Actions de formation**
3. Cliquez sur **Ajouter une action**

### Depuis une unité de formation

1. Accédez à la fiche de l'unité de formation
2. Onglet **Actions de formation**
3. Cliquez sur **Ajouter une action**

## Formulaire de création

### Étape 1 : Sélectionner l'unité de formation

La première étape consiste à associer une ou plusieurs unités de formation à la formation sélectionnée.

![Sélection de l'unité de formation](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/action-formation/04-creation-action-etape1.png "800x450")

### Étape 2 : Configurer l'action

Une fois l'unité sélectionnée, configurez les paramètres de l'action :

![Configuration de la durée et du volume d'heures](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/action-formation/05-creation-action-etape2.png "800x450")

### Informations obligatoires

| Champ | Description |
|-------|-------------|
| **Formation** | Sélectionnez la formation du catalogue |
| **Unité de formation** | Sélectionnez le site dispensateur |
| **Durée de l'action** | Durée en mois (pré-remplie avec la durée théorique de la formation) |

### Lieux de formation

Les lieux de formation sont **automatiquement hérités** de l'unité de formation sélectionnée :

- Le lieu principal de l'unité devient le lieu principal de l'action
- Les lieux secondaires sont également récupérés

Ces lieux peuvent être modifiés après la création de l'action.

### Informations optionnelles

| Champ | Description |
|-------|-------------|
| **Code interne** | Référence interne de l'action |
| **Commentaires** | Notes complémentaires |

## Validation

1. Vérifiez les informations saisies
2. Cliquez sur **Créer**
3. L'action est créée

## Après la création

Une fois l'action de formation créée, vous pouvez :

- Modifier les lieux de formation (principal et secondaires)
- Créer des sessions de formation
- Consulter et modifier les paramètres

## Erreurs courantes

### "Une action de formation existe déjà pour cette formation, cette unité de formation et cette durée"

Une action de formation existe déjà avec le même triplet (formation + unité + durée). Vous pouvez :

- Rechercher l'action existante plutôt que d'en créer une nouvelle
- Créer une action avec une **durée différente** si vous souhaitez proposer un parcours alternatif

---

## Pour aller plus loin

-> [05 - Consulter et modifier une action](05-consultation-modification)
