---
title: "08 - Processus d'approbation des unités de formation"
description: ""
date: "2025-09-01"
version: "1"
---

### Table des matières
1. [Principe du processus d'approbation](#principe-du-processus-dapprobation)
2. [États d'approbation](#états-dapprobation)
3. [Accéder aux approbations](#accéder-aux-approbations)
4. [Traitement des approbations](#traitement-des-approbations)
5. [Approbations par lot](#approbations-par-lot)

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

## États d'approbation

Le système utilise 5 états d'approbation :



![État des unités](placeholder-etat-a-completer.png "Données insuffisantes")


### À compléter
- Champs obligatoires manquants
- Informations incomplètes
- 
### À corriger  
- Erreurs détectées dans les données
- Formats incorrects ou incohérences

### À valider
- Toutes les informations sont complètes
- Prêt pour validation manuelle

### Validée
- Approbation approuver
- Unité activée et disponible en gestion

### Refusée
- Approbation refusée manuellement

---

## Accéder aux approbations

### Navigation
Dans le cas où vous avez des unités de formations à approuver, un bandeau d'alerte apparait sur la liste des unités de formation.
Vous pouvez y accéder en cliquant sur le menu **"Formation"**, sous-menu **"Unités de Formation"**.
Cliquez ensuite sur **"Finaliser l'importation"** présent dans le bandeau.

![Navigation approbations](placeholder-navigation-approbations.png "Accès aux approbations")

### Interface par statuts
L'interface est organisée en onglets :
- **À compléter** : Unités nécessitant des informations
- **À corriger** : Unités avec erreurs à rectifier  
- **À valider** : Unités prêtes pour validation
- **Refusées** : Unités non validées

![Interface par statuts](placeholder-interface-statuts.png "Organisation par onglets")

---

## Traitement des approbations

### Actions disponibles


![Actions](placeholder-action-refuser.png "Refus d'une unité")

**Approuver une unité**
- Disponible si le statut est "à valider"
- Transfère l'unité de formation en gestion

**Refuser une unité**
- Disponible qu'importe le statut
- Passe en statut refusé

**Modifier**
- Permet de modifier les informations de l'unité de formation en approbation
- Affiche les champs à compléter et à corrigé à l'aide d'un code couleur et des icones dans les formulaire
![Modification avant validation](placeholder-modif-avant-validation.png "Correction des données")

---

## Approbations par lot

### Traitement groupé
Possibilité de traiter plusieurs unités simultanément :

**Tout approuver**
- Approbation en masse des unités ayant le statut "à valider"
**Tout refuser**

![Tout refuser](placeholder-tout-refuser.png "Refus en masse")

## Historique des approbations

### Traçabilité
- **Journal des décisions** : Historique complet des approbations/refus
- **Dates et auteurs** : Traçabilité des actions

![Historique approbations](placeholder-historique-approbations.png "Suivi des décisions")

### Pour aller plus loin
-> [09 - Bonnes pratiques et cas d'usage](09-bonnes-pratiques)