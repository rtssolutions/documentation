---
title: "05 - Processus d'approbation des formations"
description: "Validation qualité des formations avant leur mise en service"
date: "2026-03-20"
version: "1"
---

# Processus d'approbation des formations

## Principe du processus d'approbation

### Objectif

Le processus d'approbation permet de valider la qualité et la conformité des formations avant leur activation.
Il garantit que les informations sont complètes et correctes avant d'être accessibles en gestion.

### Qui peut approuver

- **Utilisateurs associés à un centre de formation** avec la permission **"Approbation des formations"**

### Déclenchement

L'approbation est requise pour :
- **Les formations importées** lors de l'onboarding de Papaours

---

## Statuts d'approbation

Une formation en approbation peut avoir les statuts suivants :

| Statut | Description |
|--------|-------------|
| **À compléter** | Données insuffisantes, compléments nécessaires |
| **À corriger** | Erreurs détectées, corrections requises |
| **À valider** | Prête pour validation finale |
| **Validée** | Approuvée et mise en service |
| **Refusée** | Non conforme aux critères qualité |

---

## Accéder aux approbations

### Navigation

Dans le cas où vous avez des formations à approuver, un bandeau d'alerte apparaît sur la liste des formations.

Vous pouvez y accéder en cliquant sur le menu **"Formation"**, sous-menu **"Formations"**.
Cliquez ensuite sur **"Finaliser l'importation"** présent dans le bandeau.

---

## Détail d'une approbation

### Informations affichées

La fiche d'approbation présente :
- Les informations de la formation
- Les champs à compléter (surlignés)
- Les champs à corriger (en erreur)
- Le statut actuel

### Actions disponibles

**Approuver une formation**
- Disponible si le statut est "à valider"
- Transfère la formation en gestion

**Refuser une formation**
- Disponible quel que soit le statut
- Passe en statut refusé

**Modifier**
- Permet de modifier les informations de la formation en approbation
- Affiche les champs à compléter et à corriger à l'aide d'un code couleur

---

## Approbations par lot

### Traitement groupé

Il est possible de traiter plusieurs formations simultanément :
- **Tout approuver** : Approbation en masse des formations ayant le statut "à valider"
- **Tout refuser** : Refus en masse

---

## Historique des approbations

### Traçabilité

- **Journal des décisions** : Historique complet des approbations/refus
- **Dates et auteurs** : Traçabilité des actions

---

## Pour aller plus loin

-> [01 - Introduction](01-introduction)
