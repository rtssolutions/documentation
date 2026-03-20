---
title: "08 - Processus d'approbation des unités de formation"
description: ""
date: "2025-09-01"
version: "1"
---

### Table des matières
1. [Principe du processus d'approbation](#principe-du-processus-dapprobation)
2. [Accéder aux approbations](#accéder-aux-approbations)
3. [Détail d'une approbation](#détail-dune-approbation)
4. [Approbations par lot](#approbations-par-lot)

---

## Principe du processus d'approbation

### Objectif
Le processus d'approbation permet de valider la qualité et la conformité des unités de formation avant leur activation.<br/>
Il garantit que les informations sont complètes et correctes avant d'être accessibles en gestion.

### Qui peut approuver
- **Utilisateurs associés à un centre de formation** avec la permission **"Approbation des unités de formation"**

### Déclenchement
L'approbation est requise pour :
- **Les unités de formations importées** à l'onboarding de papaours

---

## Accéder aux approbations

### Navigation
Dans le cas où vous avez des unités de formation à approuver, un bandeau d'alerte apparaît sur la liste des unités de formation.<br/>
Vous pouvez y accéder en cliquant sur le menu **"Formation"**, sous-menu **"Unités de Formation"**.<br/>
Cliquez ensuite sur **"Finaliser l'importation"** présent dans le bandeau.

![Menu approbations](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/08/menu-unite-formation.png "315x448")
![Navigation approbations](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/08/liste-unite-formation-approb.png)

### Interface par statuts
L'interface est organisée en onglets :
- **À compléter** : Unités nécessitant des informations
  - Champs obligatoires manquants
  - Informations incomplètes
- **À corriger** : Unités avec erreurs à rectifier
  - Erreurs détectées dans les données
  - Formats incorrects ou incohérences
- **À valider** : Unités prêtes pour validation
  - Toutes les informations sont complètes
  - Prêt pour validation manuelle
- **Refusées** : Unités non validées
  - Approbation refusée manuellement
- **Validée** :
  - Approbation approuvée
  - Unité activée et disponible en gestion

![Interface par statuts](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/08/detail-status-uf-approb.png)

---

## Détail d'une approbation

### Actions disponibles

**Approuver une unité**
- Disponible si le statut est "à valider"
- Transfère l'unité de formation en gestion

**Refuser une unité**
- Disponible qu'importe le statut
- Passe en statut refusé

**Modifier**
- Permet de modifier les informations de l'unité de formation en approbation
- Affiche les champs à compléter et à corriger à l'aide d'un code couleur et des icônes dans les formulaires

![Action approbation](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/08/detail-uf-approb-action.png)

---

## Approbations par lot

### Traitement groupé
Il est possible de traiter plusieurs unités simultanément depuis l'écran qui liste les approbations par statut :
- **Tout approuver**
  - Approbation en masse des unités ayant le statut "à valider"
- **Tout refuser**


![Action masse approbation](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/08/detail-status-uf-approb-actions.png)


## Historique des approbations

### Traçabilité
- **Journal des décisions** : Historique complet des approbations/refus
- **Dates et auteurs** : Traçabilité des actions

### Pour aller plus loin
-> [01 - Introduction](01-introduction)