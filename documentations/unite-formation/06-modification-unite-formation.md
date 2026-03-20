---
title: "06 - Modification d'une unité de formation"
description: ""
date: "2025-09-01"
version: "1"
---

### Table des matières
1. [Accéder à la modification](#accéder-à-la-modification)
2. [Modification des informations générales](#modification-des-informations-générales)
3. [Validation des modifications](#validation-des-modifications)
4. [Gestion des lieux de formation](#gestion-des-lieux-de-formation)

---

## Accéder à la modification

### Prérequis
Pour modifier une unité de formation, vous devez :

- Disposer de la permission **"Écriture des unités de formation"**
- L'unité ne doit pas être **archivée**

### Depuis la fiche de consultation
- Cliquez sur le bouton **"Modifier"** en haut de la fiche

![Bouton modifier depuis fiche](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/06/detail-uf-btn-modifier.png)

### Depuis la liste
- Cliquez sur **"Modifier"** dans les actions de ligne

![Modifier depuis liste](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/06/liste-uf-modifier.png)

### Mode de modification
Le système ouvre le formulaire de modification avec les données actuelles pré-remplies.

![Formulaire modification](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/06/modification-uf.png)

---

## Modification des informations générales

### Informations non modifiables
Certaines données sont protégées et non éditables :

- **SIRET** : Identifiant légal fixe
- **Dénomination sociale** : Issue du registre officiel
- **Nature juridique** : Données référentiel
- **Adresse du siège** : Liée au SIRET

### Informations commerciales modifiables

**Nom commercial**
- Modification libre du nom d'usage
- Mise à jour automatique dans tous les modules

**Slogan et description**
- **Slogan** : Texte libre
- **Description** : Présentation détaillée, format texte riche

### Informations administratives

**Données fiscales**
- **Régime TVA** : Sélection dans une liste déroulante
- **Numéro TVA** : Validation automatique du format
- **Contrôle de cohérence** avec le régime choisi

**Numéro UAI**
- Saisie libre avec validation de format
- **Vérification** à l'aide du numéro INSEE de la commune
- **Alerte** si numéro invalide

### Sauvegarde des modifications

**Validation des champs**
- **Contrôles en temps réel** du format pendant la saisie
- **Messages d'erreur** contextuels remontés en cas d'incohérence détectée
- **Blocage de sauvegarde** si erreurs critiques

![Validation champs](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/06/modification-uf-champs.png)

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
Après modification, le statut est re-calculé automatiquement :
- **Valide** : Toutes les données requises sont valides
- **À corriger** : Informations incorrectes dans des champs obligatoires
- **À compléter** : Des données manquantes

---

## Gestion des lieux de formation

### Vue d'ensemble des lieux
Une carte est présente dans le détail d'une unité de formation.
Elle affiche les lieux de formation principaux et secondaires

![Carte lieux de formations](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/06/carte-lieux.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=SCW2X6M8ABHWFXEYGDMV%2F20250925%2Ffr-par%2Fs3%2Faws4_request&X-Amz-Date=20250925T121347Z&X-Amz-Expires=3599&X-Amz-Signature=853ff8fa113862026671dde53626b35273f15d2393b6a489211fe6ef823c6b11&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)

### Modification des lieux

Il est toujours requis d'avoir au moins un lieu de formation principale.
Cependant, tous les champs restent modifiable.

![Modification lieu](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/06/modification-lieux.png)

### Ajout d'un nouveau lieu

**Processus d'ajout**
1. Cliquez sur **"Ajouter un autre lieu"**
2. Saisissez l'adresse avec autocomplétion
3. Configurez les spécificités du site
4. Validez l'ajout

**Informations requises**
- **Adresse complète** : Rue, code postal, ville
- **Nom** : Utilisé pour reconnaître facilement le lieu

### Suppression d'un lieu

La suppression est une action critique sur des unités de formation.<br/>
Une confirmation de suppression est donc demandée avant de supprimer le lieu.<br/>
Certains cas ne permettent donc pas de supprimer un lieu :
- Si le lieu est **Principal** pour l'unité de formation
- Si le lieu est **Principal** dans une session ou action enfant.

Les lieux qui sont secondaires de l'unité et non principaux dans une session ou action de formation enfant sont eux supprimables.

![Suppression lieu](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/06/confirmation-supp-lieu.png "578×235")
![Suppression lieu échec](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/06/echec-supp-lieux.png "1123×235")

---

### Pour aller plus loin
-> [07 - Suppression d'une unité de formation](07-suppression-unite-formation)