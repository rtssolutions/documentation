---
title: "04 - Création d'une unité de formation"
description: ""
date: "2025-09-01"
version: "1"
---

### Table des matières
1. [Processus de création](#processus-de-création)
2. [Recherche d'organismes potentiels](#recherche-dorganismes-potentiels)
3. [Sélection d'un organisme](#sélection-dun-organisme)
4. [Saisie des informations](#saisie-des-informations)
5. [Configuration des lieux de formation](#configuration-des-lieux-de-formation)
6. [Finalisation et validation](#finalisation-et-validation)

---

## Processus de création

La création d'une unité de formation suit un workflow structuré en plusieurs étapes pour garantir la qualité et la conformité des données. Le processus débute par la recherche d'organismes potentiels dans les référentiels externes.

### 🎥 Tutoriel vidéo

<video controls>
  <source src="https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/04/creation-unite-formation.mp4" type="video/mp4" />
</video>

---

## Recherche d'organismes potentiels

### Accéder à la recherche
Pour créer une nouvelle unité de formation :

- Cliquez sur **"Créer une unité de formation"** dans le header de la page
- Vous devez disposer de la permission **"Écriture des unités de formation"**

![Bouton création unité](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/03/liste-unite-formation-creation.png)

### Critères de recherche
La recherche s'effectue sur plusieurs critères :

**Par SIRET** *(recommandé)*
- Saisie du numéro SIRET complet (14 chiffres)
- Recherche exacte dans les référentiels d'entreprises
- Affichage immédiat si l'organisme existe

**Par dénomination sociale**
- Recherche textuelle sur le nom de l'entreprise
- Support des recherches partielles
- Liste des résultats correspondants

**Par localisation**
- Filtrage par département ou région
- Combinable avec les autres critères
- Affinage géographique des résultats

![Recherche unité](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/04/creation-uf-recherche.png)


### Résultats de recherche
Les organismes potentiels s'affichent dans un tableau avec :

- **Dénomination sociale**
- **SIRET**
- **Adresse** du siège social
---

## Sélection d'un organisme

### Actions de sélection

**Sélectionner un organisme**
- Cliquez sur **"Sélectionner"** dans la ligne correspondante
- Vérification automatique de l'éligibilité
- Pré-remplissage des données disponibles

![Bouton sélection](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/04/creation-uf-selection.png)

---

## Saisie des informations

![Bouton création unité](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/04/creation-uf-detail.png)


### Informations automatiquement remplies
Après sélection, certains champs sont pré-remplis depuis les référentiels :

- **Dénomination sociale** *(non modifiable)*
- **SIRET** *(non modifiable)*
- **Adresse du siège** *(non modifiable)*
- **Code NAF** *(non modifiable)*
- **Nature juridique** *(non modifiable)*

### Informations obligatoires à compléter

**Informations commerciales**
- **Nom commercial** : Nom sous lequel l'organisme exerce
- **Slogan** *(optionnel)* : Phrase d'accroche commerciale
- **Description** : Présentation de l'organisme et de son expertise

**Informations fiscales**
- **Régime TVA** : Non assujetti, Assujetti, Franchise en base
- **Numéro de TVA intracommunautaire** *(si applicable)*

**Numéro UAI** *(optionnel)*
- Identifiant du ministère de l'Éducation nationale

### Moyens de contact

**Contact** *(optionnels)*
- **Téléphone** : Numéro principal de l'organisme
- **Email** : Adresse email institutionnelle
- **Site web** : URL du site officiel

### Validation des données
Le système effectue des contrôles automatiques :

- **Format SIRET** : Vérification de la clé de contrôle
- **Format email** : Validation de la syntaxe
- **Format téléphone** : Contrôle du format français/international
- **Cohérence TVA** : Vérification du numéro intracommunautaire
- **Numéro UAI** : Respect du code INSEE associé et du format

---

## Configuration des lieux de formation

### Lieu principal
Le siège social est automatiquement défini comme lieu de formation principal :

- **Adresse** : Reprise depuis les données SIRET
- **Statut** : Principal (non modifiable)

![Lieu principal](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/04/creation-uf-lieu.png)

### Lieux secondaires

**Ajouter un lieu secondaire**
- Cliquez sur **"Ajouter un autre lieu"**
- Saisissez l'adresse complète qui sera complétée via un référentiel d'adresses

![Bouton création unité](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/04/creation-uf-lieu-secondaire.png)

**Informations par lieu**
- **Dénomination** : Nom du site (obligatoire)
- **Adresse complète** : Localisation précise

### Gestion des lieux
- **Modifier** un lieu existant
- **Supprimer** un lieu secondaire (principal non supprimable)

---

## Finalisation et validation

### Vérification avant enregistrement
Avant finalisation, contrôlez :
- ✅ **Toutes les informations obligatoires** sont renseignées
- ✅ **Au moins un lieu de formation** est configuré
- ✅ **Les moyens de contact** sont valides
- ✅ **Les données fiscales** sont cohérentes

### Statut de conformité
Le système calcule automatiquement le statut :

- **Valide** : Prêt pour l'association à des formations
- **Non conforme** : Données manquantes ou invalides
- **À compléter** : Informations manquantes


### Actions post-création
Après création, vous pouvez :

- **Consulter** la fiche complète de l'unité
- **Modifier** les informations si nécessaire
- **Créer des actions de formation** rattachées
- **Gérer les lieux** de formation additionnels

![Confirmation post création](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/04/confiramtion-creation-uf.png "811×434")

### Pour aller plus loin
-> [05 - Consultation et lecture d'une unité de formation](05-consultation-unite-formation)