---
title: "03 - Situation actuelle"
description: "Comprendre la situation actuelle d'un dossier de formation et les actions réalisables"
date: "2025-10-31"
version: "1"
---

# La situation actuelle du dossier de formation

## Qu'est-ce que la situation actuelle ?

La **situation actuelle** correspond à l'**état** du dossier de formation. Elle reflète en temps réel la progression de l'apprenant dans son parcours de formation et détermine les actions qui peuvent être réalisées sur le dossier.

La situation actuelle est visible dans la colonne "Situation actuelle" de la liste des dossiers de formation.

## Comment est calculée la situation actuelle ?

La situation actuelle évolue **automatiquement** en fonction des actions réalisées sur le dossier de formation. Le système met à jour l'état du dossier selon les événements suivants :

- **Inscription à une session** → État "Inscrit à la formation"
- **Déclaration d'une SFP avant contrat** → État "SFP avant contrat"
- **Signature d'un contrat** → État "Apprenti sous contrat"
- **Fin ou rupture de contrat** → État "Contrat terminé"
- **Annulation de l'inscription** → État "Inscription annulée"

## Les 5 situations possibles

### 1. Inscrit à la formation

**Description** : L'apprenant est inscrit à la formation mais n'a pas encore de contrat.

**Actions réalisables** :
- Annuler l'inscription
- Déclarer une SFP avant contrat
- Créer un brouillon de contrat
- Générer le formulaire CERFA P2S

### 2. SFP avant contrat

**Description** : L'apprenant est en situation de formation professionnelle (SFP) avant la signature du contrat. Cette période dédiée permet à l'apprenant de commencer sa formation en attendant la finalisation du contrat.

**Actions réalisables** :
- Créer un brouillon de contrat
- Générer le formulaire CERFA P2S
**Actions non réalisables** :
- Annuler l'inscription (non disponible en SFP)
- Déclarer une nouvelle SFP (une SFP existe déjà)

### 3. Apprenti sous contrat

**Description** : L'apprenant a un contrat d'apprentissage actif. Le parcours de formation est officiellement en cours.

**Actions réalisables** :
- Consulter le(s) contrat(s)
-  Gérer les documents du dossier
**Actions non réalisables** :
- Annuler l'inscription (contrat en cours)
- Déclarer une SFP (contrat déjà signé)
- Créer un nouveau brouillon de contrat

### 4. Contrat terminé

**Description** : Le contrat de l'apprenant est terminé, que ce soit par une fin normale (obtention du diplôme) ou par rupture anticipée.

**Actions réalisables** :
- Consulter l'historique du dossier
- Consulter les contrats terminés
**Actions non réalisables** :
- Annuler l'inscription
- Déclarer une SFP
- Créer un nouveau brouillon de contrat

### 5. Inscription annulée

**Description** : L'inscription de l'apprenant a été annulée. Le dossier est clos et ne peut plus être modifié.

**Actions réalisables** :
- Consulter l'historique du dossier
**Actions non réalisables** :
- Toutes les autres actions sont bloquées

## Règles importantes

### Conditions pour annuler une inscription

L'inscription peut être annulée **uniquement** si :
- Le dossier est dans l'état "Inscrit à la formation"
- Aucun contrat ou financement n'est engagé

### Conditions pour déclarer une SFP avant contrat

Une SFP avant contrat peut être déclarée si :
- Le dossier est dans l'état "Inscrit à la formation"
- Aucune SFP n'existe déjà pour ce dossier
- Aucun contrat n'a été signé à la date d'entrée en formation

**Note** : Le système peut être configuré pour déclencher automatiquement le passage en SFP après un certain délai (paramétrage dans les réglages des dossiers de formation).

## Pour aller plus loin

- [02 - Définition et concepts clés](02-definition-concepts-cles.md)
- [Notes de version 0.5.0 - Gestion des situations](../release-notes/0.5.0.md)

---

> 💡 **Astuce** : La situation actuelle permet de comprendre rapidement où en est chaque apprenant dans son parcours et quelles actions sont possibles pour faire avancer son dossier.
