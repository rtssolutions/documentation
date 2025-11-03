---
title: "05 - Création d'un employeur"
description: "Procédure de création et règles de gestion des employeurs."
date: "2025-10-31"
version: "1"
---

## Table des matières

1. [Processus de création](#processus-de-création)
2. [Recherche dans la base SIRENE](#recherche-dans-la-base-sirene)
3. [Saisie des informations](#saisie-des-informations)
4. [Génération du code employeur](#génération-du-code-employeur)
5. [Création de la visibilité](#création-de-la-visibilité)
6. [Finalisation et validation](#finalisation-et-validation)

---

## Processus de création

La création d’un employeur se fait via un formulaire structuré permettant de saisir toutes les informations nécessaires.
Certains champs sont pré-remplis via la base SIRENE.

- Accès : **Menu Employeurs > Création d'un employeur** ou le bouton **Ajouter un employeur** sur la page principal du
  module
- Vous devez disposer de la permission Ecriture sur les employeurs pour accéder à cette fonctionnalité
- Toutes les créations sont historisées

---

## Recherche dans la base SIRENE

La création d’un employeur s’effectue via une recherche au sein de la base SIRENE de l’État français :

1. **Critères de recherche** :
    - SIRET de l'établissement
    - Dénomination sociale (minimum 3 caractères)
    - Adresse de l'établissement

2. **Résultats affichés** :
    - Dénomination sociale
    - SIRET
    - Adresse complète (Code postal / Ville)
    -  Identifiant de convention collective (IDCC)
    - État administratif (actif / fermé) ou si votre employeur est déjà dans votre base de gestion : "employeur connu"

3. **Sélection d’un résultat** :
    - Si l’employeur existe déjà au sein de votre organisation, vous disposez d’un bouton voir, vous permettrez d’accéder à sa fiche employeur connu de votre organisation.
    - Sinon, un bouton sélectionner apparait, entrainant la création de l'employeur en base de gestion et redirection vers le formulaire de complétion des informations.

![Recherche SIRENE](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/5/recherche-sirene.png)

---

## Saisie des informations

### Champs obligatoires modifiables

- **Nom commercial**
- **Statut personnalisé** (valeur par défaut à la création : Nouveau)

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

![Formulaire création employeur](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/5/formulaire-creation.png)

---

## Génération du code employeur

- Format : **EMPYYYY-XXXXXX**
    - **EMP** : préfixe pour Employeur
    - **YYYY** : année de création
    - **XXXXXX** : compteur incrémental, débutant à 000001 chaque année
- Généré automatiquement lors de la création
- Non modifiable après création
- Utilisé dans :
    - Historique des actions
    - Export et rapports (dans une future version)
    - Liens fonctionnels avec contrats et dossiers de formation

---

## Création de la visibilité

Lors de la création, le système génère automatiquement la visibilité :

- **Centre de formation propriétaire** : défini comme propriétaire
- **Organisation de l’utilisateur créateur** : ajoutée aux organisations autorisées
- Type de visibilité : personnalisée ou privée (non publique)

---

## Finalisation et validation

### Vérification avant enregistrement

- Contrôle de complétude des champs obligatoires
- Contrôle de cohérence des données (ex : format TVA correct, nom commercial valide, etc.)
- Blocage de la sauvegarde en cas d’erreurs

### Actions post-création

- Redirection vers la fiche détail de l’employeur

---

### Pour aller plus loin

➡️ Poursuivez avec la page suivante :  
[06 - Consultation d'un employeur](06-consultation-employeur.md)
