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

![Placeholder vidéo création](placeholder-video-creation-unite.png "Tutoriel de création d'unité de formation")

---

## Recherche d'organismes potentiels

### Accéder à la recherche
Pour créer une nouvelle unité de formation :

- Cliquez sur **"Créer une unité de formation"** dans le header de la page
- Vous devez disposer de la permission **"Écriture des unités de formation"**

![Bouton ajouter unité](placeholder-bouton-ajouter-unite.png "Point d'entrée création")

### Critères de recherche
La recherche s'effectue sur plusieurs critères :

**Par SIRET** *(recommandé)*
- Saisie du numéro SIRET complet (14 chiffres)
- Recherche exacte dans les référentiels d'entreprises
- Affichage immédiat si l'organisme existe

![Recherche par SIRET](placeholder-recherche-siret.png "Champ de recherche SIRET")

**Par dénomination sociale**
- Recherche textuelle sur le nom de l'entreprise
- Support des recherches partielles
- Liste des résultats correspondants

![Recherche par nom](placeholder-recherche-nom.png "Recherche textuelle")

**Par localisation**
- Filtrage par département ou région
- Combinable avec les autres critères
- Affinage géographique des résultats

![Filtres géographiques](placeholder-filtres-geo.png "Sélection géographique")

### Résultats de recherche
Les organismes potentiels s'affichent dans un tableau avec :

- **Dénomination sociale**
- **SIRET**
- **Adresse** du siège social

![Tableau résultats recherche](placeholder-tableau-resultats.png "Liste des organismes trouvés")

---

## Sélection d'un organisme

### Actions de sélection

**Sélectionner un organisme**
- Cliquez sur **"Sélectionner"** dans la ligne correspondante
- Vérification automatique de l'éligibilité
- Pré-remplissage des données disponibles

![Bouton sélection](placeholder-bouton-selectionner.png "Action de sélection")

---

## Saisie des informations

### Informations automatiquement remplies
Après sélection, certains champs sont pré-remplis depuis les référentiels :

- **Dénomination sociale** *(non modifiable)*
- **SIRET** *(non modifiable)*
- **Adresse du siège** *(non modifiable)*
- **Code NAF** *(non modifiable)*
- **Nature juridique** *(non modifiable)*

![Champs pré-remplis](placeholder-champs-preremplis.png "Données automatiques")

### Informations obligatoires à compléter

**Informations commerciales**
- **Nom commercial** : Nom sous lequel l'organisme exerce
- **Slogan** *(optionnel)* : Phrase d'accroche commerciale
- **Description** : Présentation de l'organisme et de son expertise

![Informations commerciales](placeholder-infos-commerciales.png "Données marketing")

**Informations fiscales**
- **Régime TVA** : Non assujetti, Assujetti, Franchise en base
- **Numéro de TVA intracommunautaire** *(si applicable)*

![Informations fiscales](placeholder-infos-fiscales.png "Données fiscales")

**Numéro UAI** *(optionnel)*
- Identifiant du ministère de l'Éducation nationale

![Numéro UAI](placeholder-numero-uai.png "Identifiant éducation")

### Moyens de contact

**Contact** *(optionnels)*
- **Téléphone** : Numéro principal de l'organisme
- **Email** : Adresse email institutionnelle
- **Site web** : URL du site officiel

![Moyens de contact](placeholder-moyens-contact.png "Coordonnées de contact")

### Validation des données
Le système effectue des contrôles automatiques :

- **Format SIRET** : Vérification de la clé de contrôle
- **Format email** : Validation de la syntaxe
- **Format téléphone** : Contrôle du format français/international
- **Cohérence TVA** : Vérification du numéro intracommunautaire
- **Numéro UAI** : Respect du code INSEE associé et du format

![Validation automatique](placeholder-validation-donnees.png "Contrôles de cohérence")

---

## Configuration des lieux de formation

### Lieu principal
Le siège social est automatiquement défini comme lieu de formation principal :

- **Adresse** : Reprise depuis les données SIRET
- **Statut** : Principal (non modifiable)

![Lieu principal](placeholder-lieu-principal.png "Configuration siège social")

### Lieux secondaires

**Ajouter un lieu secondaire**
- Cliquez sur **"Ajouter un autre lieu"**
- Saisissez l'adresse complète

![Ajouter lieu secondaire](placeholder-ajouter-lieu.png "Nouveau site de formation")

**Informations par lieu**
- **Dénomination** : Nom du site (obligatoire)
- **Adresse complète** : Localisation précise

![Configuration lieu](placeholder-config-lieu.png "Détail d'un lieu de formation")

### Gestion des lieux
- **Modifier** un lieu existant
- **Supprimer** un lieu secondaire (principal non supprimable)
- **Dupliquer** les informations entre lieux similaires

![Gestion des lieux](placeholder-gestion-lieux.png "Actions sur les lieux")

---

## Finalisation et validation

### Vérification avant enregistrement
Avant finalisation, contrôlez :

✅ **Toutes les informations obligatoires** sont renseignées
✅ **Au moins un lieu de formation** est configuré
✅ **Les moyens de contact** sont valides
✅ **Les données fiscales** sont cohérentes

![Check-list validation](placeholder-checklist.png "Points de contrôle final")

### Statut de conformité
Le système calcule automatiquement le statut :

- **Valide** : Prêt pour l'association à des formations
- **Non conforme** : Données manquantes ou invalides
- **À compléter** : Informations manquantes

![Statut conformité](placeholder-statut-conformite.png "Niveau de complétude")

### Actions post-création
Après création, vous pouvez :

- **Consulter** la fiche complète de l'unité
- **Modifier** les informations si nécessaire
- **Créer des actions de formation** rattachées
- **Gérer les lieux** de formation additionnels

![Actions post-création](placeholder-actions-post-creation.png "Suite du workflow")

### Pour aller plus loin
-> [05 - Consultation et lecture d'une unité de formation](05-consultation-unite-formation)