---
title: "07 - Modification d'un employeur"
description: "Procédure et règles pour modifier les informations d'un employeur existant."
date: "2025-10-31"
version: "1"
---

## Table des matières

1. [Accéder à la modification](#accéder-à-la-modification)
2. [Champs modifiables](#champs-modifiables)
3. [Validation des modifications](#validation-des-modifications)
4. [Historisation](#historisation)

---

## Accéder à la modification

### Prérequis

Pour modifier un employeur, vous devez :

- Disposer de la permission **Écriture sur les employeurs**
- L’employeur ne doit pas être archivé

### Depuis la fiche de consultation

- Cliquez sur le bouton **"Modifier"** en haut de la fiche détail
  ![Bouton modifier](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/7/action-modifier-fiche.png)

### Depuis la liste

- Cliquez sur **"Modifier"** dans les actions de ligne
  ![Modifier depuis liste](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/7/action-modifier-liste.png)

---

### Champs obligatoires modifiables

- **Nom commercial**

### Champs optionnels modifiables

- Coordonnées : téléphone, courriel, site internet
- Convention collective principale (IDCC)
- Autres conventions collectives
- Régime social
- Effectif total
- Caisse de retraite
- Secteur d’activité
- Type d'employeur
- Employeur Spécifique
- TVA et régime applicable

### Champs non modifiables

- SIREN
- SIRET
- Adresse
- Statut entreprise
- Dénomination Sociale
- Nature juridique
- Code APE/NAF
- Code employeur

## Validation des modifications

![Ecran de modification](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/7/formulaire-modification.png)

### Contrôles automatiques

- Nom commercial : pas de caractères spéciaux ni chiffres ni une chaine de caractères blancs
- Téléphone : format international valide
- Courriel : format standard valide
- Effectif : entier positif
- Caisse de retraite (liste référentielle)
- Secteur d’activité (liste référentielle)
- Type Employeur (liste référentielle)
- Employeur Spécifique (liste référentielle)
- TVA :
    - Soumis ou non
    - Si soumis : régime de TVA (franchise, simplifié, réel normal)
    - Si soumis : taux de TVA (20%, 10%, 5.5%, ou valeur personnalisée à deux décimales)
- Conventions collectives : sélection valide depuis le référentiel
- Régime social (MSA/URSSAF)

### Blocage

- La sauvegarde est bloquée si des erreurs sont détectées
- Messages d’erreur contextuels pour guider l’utilisateur

---

## Historisation

- Chaque modification est historisée avec :
    - Champ modifié
    - Ancienne valeur
    - Nouvelle valeur
    - Auteur
    - Date
- L’historique est consultable depuis le bloc Historique de la fiche employeur

---

### Pour aller plus loin

➡️ Consultez la page suivante :  
[08 - Suppression et archivage d'un employeur](08-suppression-employeur)
