---
title: "05 - Processus d'approbation"
description: "Comprendre et utiliser le processus d'approbation des formations"
date: "2026-03-20"
version: "1"
---

# Processus d'approbation des formations

## Principe

Le processus d'approbation garantit que toutes les formations de votre catalogue sont validées avant d'être utilisées dans Papaours. Ce mécanisme assure la qualité et la conformité de vos données pédagogiques.

## Quand l'approbation est-elle requise ?

L'approbation est nécessaire dans les cas suivants :

- **Création d'une formation** : toute nouvelle formation ajoutée au catalogue
- **Importation depuis le référentiel** : formations détectées automatiquement
- **Modification majeure** : changements impactant la certification ou le diplôme

## Statuts d'approbation

| Statut | Description | Actions possibles |
|--------|-------------|-------------------|
| **À approuver** | En attente de validation | Approuver, Refuser |
| **Approuvée** | Validée et utilisable | Modifier, Supprimer |
| **Refusée** | Non conforme | Corriger et resoumettre |

## Accéder aux formations à approuver

### Depuis la liste des formations

1. Menu **Formations** > **Formations**
2. Utilisez le filtre **Statut** et sélectionnez **À approuver**
3. La liste affiche les formations en attente

### Indicateur visuel

Les formations à approuver sont identifiables par :
- Un badge de statut spécifique
- Une icône d'avertissement (si applicable)

## Approuver une formation

### Procédure

1. Accédez à la fiche de la formation
2. Vérifiez les informations :
   - Certification RNCP valide
   - Diplôme correctement associé
   - Informations complètes
3. Cliquez sur **Approuver**
4. Confirmez l'approbation

### Éléments à vérifier

Avant d'approuver, contrôlez :

| Élément | Point de vérification |
|---------|----------------------|
| **Certification RNCP** | Code valide et actif |
| **Diplôme** | Correspondance avec la certification |
| **Intitulé** | Conforme à l'offre de formation |
| **Durée** | Cohérente avec le référentiel |
| **Voies d'accès** | Apprentissage inclus |

## Refuser une formation

Si une formation n'est pas conforme :

1. Accédez à la fiche de la formation
2. Cliquez sur **Refuser**
3. Indiquez le motif du refus (recommandé)
4. Confirmez le refus

La formation reste visible mais ne peut pas être utilisée pour créer des actions ou des sessions.

## Pré-alimentation automatique

### Détection des formations

Lors de l'onboarding ou de synchronisations avec le référentiel national, Papaours peut détecter automatiquement des formations à ajouter à votre catalogue.

Ces formations sont créées avec le statut **À approuver** pour validation.

### Alerte d'importation

Lorsque des formations sont en attente, une alerte s'affiche :

> "X Formation(s) en attente d'importation"

Cliquez sur **Finaliser l'importation** pour accéder à la liste et valider chaque formation.

## Bonnes pratiques

- **Vérifiez régulièrement** les formations en attente d'approbation
- **Documentez les refus** pour faciliter les corrections
- **Validez rapidement** les formations issues du référentiel national (généralement conformes)
- **Formez les responsables** au processus d'approbation

## Impact sur les autres modules

Une formation non approuvée ne peut pas être utilisée pour :

- Créer une **action de formation**
- Programmer une **session de formation**
- Rattacher un **dossier de formation**

---

## Pour aller plus loin

Consultez également :
- [Approbation des actions de formation](../action-formation/06-processus-approbation)
- [Approbation des sessions de formation](../session-formation/06-processus-approbation)
- [Approbation des unités de formation](../unite-formation/08-processus-approbation)
