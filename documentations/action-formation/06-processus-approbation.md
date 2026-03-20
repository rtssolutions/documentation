---
title: "06 - Processus d'approbation des actions de formation"
description: "Validation qualité des actions de formation avant leur mise en service"
date: "2026-03-20"
version: "1"
---

# Processus d'approbation des actions de formation

## Principe du processus d'approbation

### Objectif

Le processus d'approbation permet de valider la qualité et la conformité des actions de formation avant leur activation.
Il garantit que les informations sont complètes et correctes avant d'être accessibles en gestion.

### Qui peut approuver

- **Utilisateurs associés à un centre de formation** avec la permission **"Approbation des actions de formation"**

### Déclenchement

L'approbation est requise pour :
- **Les actions de formation importées** lors de l'onboarding de Papaours

---

## Statuts d'approbation

Une action de formation en approbation peut avoir les statuts suivants :

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

Dans le cas où vous avez des actions de formation à approuver, un bandeau d'alerte apparaît sur la liste des actions.

![Bandeau d'alerte d'approbation](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/action-formation/06-approbation-formations.png "800x450")

Vous pouvez y accéder depuis :
- La fiche d'une **formation** → section **Actions de formation**
- La fiche d'une **unité de formation** → section **Actions de formation**

Cliquez ensuite sur **"Finaliser l'importation"** présent dans le bandeau.

---

## Détail d'une approbation

### Informations affichées

La fiche d'approbation présente :
- Les informations de l'action de formation
- La formation et l'unité de formation associées
- Les lieux de formation
- Les champs à compléter (surlignés)
- Les champs à corriger (en erreur)
- Le statut actuel

### Actions disponibles

**Approuver une action**
- Disponible si le statut est "à valider"
- Transfère l'action de formation en gestion

**Refuser une action**
- Disponible quel que soit le statut
- Passe en statut refusé

**Modifier**
- Permet de modifier les informations de l'action en approbation
- Affiche les champs à compléter et à corriger à l'aide d'un code couleur

---

## Approbations par lot

### Traitement groupé

Il est possible de traiter plusieurs actions de formation simultanément :
- **Tout approuver** : Approbation en masse des actions ayant le statut "à valider"
- **Tout refuser** : Refus en masse

---

## Historique des approbations

### Traçabilité

- **Journal des décisions** : Historique complet des approbations/refus
- **Dates et auteurs** : Traçabilité des actions

---

## Pour aller plus loin

-> [01 - Introduction](01-introduction)
