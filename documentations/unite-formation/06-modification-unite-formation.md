---
title: "06 - Modification d'une unité de formation"
description: ""
date: "2025-09-01"
version: "1"
---

### Table des matières
1. [Accéder à la modification](#accéder-à-la-modification)
2. [Modification des informations générales](#modification-des-informations-générales)
3. [Gestion des lieux de formation](#gestion-des-lieux-de-formation)
4. [Mise à jour des contacts](#mise-à-jour-des-contacts)
5. [Validation des modifications](#validation-des-modifications)
6. [Cas particuliers](#cas-particuliers)

---

## Accéder à la modification

### Prérequis
Pour modifier une unité de formation, vous devez :

- Disposer de la permission **"Écriture des unités de formation"**
- L'unité ne doit pas être **archivée**

### Depuis la fiche de consultation
- Cliquez sur le bouton **"Modifier"** en haut de la fiche

![Bouton modifier depuis fiche](placeholder-modifier-depuis-fiche.png "Accès modification")

### Depuis la liste
- Cliquez sur **"Modifier"** dans les actions de ligne

![Modifier depuis liste](placeholder-modifier-depuis-liste.png "Modification directe")

### Mode de modification
Le système ouvre le formulaire de modification avec les données actuelles pré-remplies.

![Formulaire modification](placeholder-formulaire-modification.png "Interface d'édition")

---

## Modification des informations générales

### Informations non modifiables
Certaines données sont protégées et non éditables :

- **SIRET** : Identifiant légal fixe
- **Dénomination sociale** : Issue du registre officiel
- **Nature juridique** : Données référentiel
- **Adresse du siège** : Liée au SIRET

![Champs protégés](placeholder-champs-proteges.png "Données non modifiables")

### Informations commerciales modifiables

**Nom commercial**
- Modification libre du nom d'usage
- Mise à jour automatique dans tous les modules

![Modification nom commercial](placeholder-modif-nom-commercial.png "Changement d'enseigne")

**Slogan et description**
- **Slogan** : Texte libre
- **Description** : Présentation détaillée, format texte riche

![Modification description](placeholder-modif-description.png "Contenu commercial")

### Informations administratives

**Données fiscales**
- **Régime TVA** : Sélection dans une liste déroulante
- **Numéro TVA** : Validation automatique du format
- **Contrôle de cohérence** avec le régime choisi

![Modification TVA](placeholder-modif-tva.png "Données fiscales")

**Numéro UAI**
- Saisie libre avec validation de format
- **Vérification** à l'aide du numéro INSEE de la commune
- **Alerte** si numéro invalide

![Modification UAI](placeholder-modif-uai.png "Identifiant éducation")

### Sauvegarde des modifications

**Validation des champs**
- **Contrôles en temps réel** du format pendant la saisie
- **Messages d'erreur** contextuels remontés en cas d'incohérence détectée
- **Blocage de sauvegarde** si erreurs critiques

![Validation champs](placeholder-validation-champs.png "Contrôles de saisie")

---

## Gestion des lieux de formation

### Vue d'ensemble des lieux
Interface dédiée à la gestion des sites de formation :

- **Lieu principal** : Siège social (informations limitées)
- **Lieux secondaires** : Modification complète autorisée

![Gestion lieux vue](placeholder-gestion-lieux-vue.png "Interface de gestion")

### Modification d'un lieu existant

Il est toujours requis d'avoir au moins un lieu de formation principale.
Cependant, tous les champs restent modifiable.

![Modification lieu secondaire](placeholder-modif-lieu-secondaire.png "Édition complète")

### Ajout d'un nouveau lieu

**Processus d'ajout**
1. Cliquez sur **"Ajouter un lieu de formation"**
2. Saisissez l'adresse avec autocomplétion
3. Configurez les spécificités du site
4. Validez l'ajout

![Ajout nouveau lieu](placeholder-ajout-lieu.png "Création d'un site")

**Informations requises**
- **Adresse complète** : Rue, code postal, ville

![Config nouveau lieu](placeholder-config-nouveau-lieu.png "Configuration détaillée")

### Suppression d'un lieu

> des règles existe mais je ne m'en souvient plus 
> A compléter

---

## Validation des modifications

### Contrôles automatiques

**Cohérence des données**
- **Correspondance** entre régime TVA et numéro
- **Unicité** des identifiants dans le système

**Contraintes métier**
- **Format** des numéros officiels (SIRET, UAI, TVA)
- **Format** des moyens de contact

### Statut de conformité mis à jour
Après modification, recalcul automatique :

- **Valide** : Toutes les données requises sont valides
- **À corriger** : Informations incorrectes dans des champs obligatoires
- **À compléter** : Des données manquantes

---

### Pour aller plus loin
-> [07 - Suppression d'une unité de formation](07-suppression-unite-formation)