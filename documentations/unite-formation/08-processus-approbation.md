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
Le processus d'approbation permet de valider la qualité et la conformité des unités de formation avant leur activation. Il garantit que les informations sont complètes et correctes.

### Qui peut approuver
- **Utilisateurs associés à un centre de formation** avec la permission **"Approbation des unités de formation"**
- **Basé sur les périmètres** : les approbateurs ne voient que les unités de leur périmètre

### Déclenchement
L'approbation est requise pour :
- **Nouvelles unités de formation** créées
- **Modifications importantes** nécessitant revalidation

---

## États d'approbation

Le système utilise 5 états d'approbation :

### À compléter
- Champs obligatoires manquants
- Informations incomplètes

![État à compléter](placeholder-etat-a-completer.png "Données insuffisantes")

### À corriger  
- Erreurs détectées dans les données
- Formats incorrects ou incohérences

![État à corriger](placeholder-etat-a-corriger.png "Corrections nécessaires")

### À valider
- Toutes les informations sont complètes
- Prêt pour validation finale

![État à valider](placeholder-etat-a-valider.png "Prêt pour validation")

### Validée
- Approbation accordée
- Unité activée et disponible

![État validée](placeholder-etat-validee.png "Approbation accordée")

### Refusée
- Non-conformité détectée
- Approbation refusée

![État refusée](placeholder-etat-refusee.png "Approbation refusée")

---

## Accéder aux approbations

### Navigation
- **Menu Formation** > **Unités de Formation**
- **Onglet "Approbations"** dans l'interface
- Organisation par **onglets selon les statuts**

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

**Approuver une unité**
- Vérification des informations
- Validation en un clic
- Activation automatique

![Action approuver](placeholder-action-approuver.png "Validation d'une unité")

**Refuser une unité**
- Saisie du motif de refus
- Commentaire explicatif
- Notification du refus

![Action refuser](placeholder-action-refuser.png "Refus d'une unité")

**Modifier avant validation**
- Correction directe des informations
- Mise à jour des données
- Retour au statut approprié

![Modification avant validation](placeholder-modif-avant-validation.png "Correction des données")

### Informations d'aide

**Champs manquants**
- Liste des informations obligatoires non renseignées
- Aide contextuelle pour la completion

![Champs manquants](placeholder-champs-manquants.png "Informations à compléter")

**Champs invalides**  
- Détail des erreurs de format ou de contenu
- Suggestions de correction

![Champs invalides](placeholder-champs-invalides.png "Erreurs à corriger")

---

## Approbations par lot

### Traitement groupé
Possibilité de traiter plusieurs unités simultanément :

**Tout approuver**
- Approbation en masse des unités d'un statut
- Vérification automatique de la conformité
- Traitement par lot avec rapport de résultats

![Tout approuver](placeholder-tout-approuver.png "Approbation en masse")

**Tout refuser**
- Refus groupé avec motif commun
- Application à toutes les unités sélectionnées
- Rapport détaillé des actions effectuées

![Tout refuser](placeholder-tout-refuser.png "Refus en masse")

### Gestion des résultats
- **Rapport de traitement** : Succès et échecs détaillés
- **Gestion des erreurs** : Unités non traitées identifiées
- **Actions de suivi** : Possibilité de retraiter les échecs

![Résultats approbations lot](placeholder-resultats-lot.png "Rapport de traitement")

---

## Historique des approbations

### Traçabilité
- **Journal des décisions** : Historique complet des approbations/refus
- **Dates et auteurs** : Traçabilité des actions

![Historique approbations](placeholder-historique-approbations.png "Suivi des décisions")

### Pour aller plus loin
-> [09 - Bonnes pratiques et cas d'usage](09-bonnes-pratiques)