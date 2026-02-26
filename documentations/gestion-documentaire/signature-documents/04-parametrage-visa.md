---
title: "Paramétrage des visas"
description: "Configurer les tampons numériques des organisations"
date: "2026-02-26"
version: "1"
---

# Paramétrage des visas

Un visa est un tampon numérique d'une organisation (personne morale) qui peut être apposé sur les documents signés. Le visa permet d'authentifier et valider un document au nom d'une entité.

## Entités pouvant avoir un visa

Trois types d'entités peuvent disposer d'un visa :

| Entité | Accès |
|--------|-------|
| **Centre de formation** | Profil > Mon centre |
| **Unité de formation** | Unités de formation > [Unité] |
| **Employeur** | Employeurs > [Employeur] |

<!-- TODO: Screenshot - Carte visa sur la page d'un employeur -->
![Carte visa](/images/signature/visa/carte-visa.png "800x400")

## Créer un visa

<!-- TODO: Screenshot - Dialog de création de visa -->
![Création visa](/images/signature/visa/creation-visa.png "600x500")

1. Accédez à la fiche de l'entité concernée
2. Dans la carte **Visa**, cliquez sur **Ajouter un visa**
3. Renseignez les informations :

| Champ | Description | Obligatoire |
|-------|-------------|-------------|
| **Code visa** | Identifiant unique du visa (3-50 caractères alphanumériques, `_`, `-`, `|`) | Oui |
| **Mode de signature** | Automatique ou Validation par courriel | Oui |
| **Courriel** | Adresse email du responsable pour validation | Si mode "Validation par courriel" |
| **Image du tampon** | Fichier image du tampon/cachet | Oui |

4. Cliquez sur **Créer**

## Modes de signature

### Automatique

Le tampon est apposé automatiquement sur le document sans intervention humaine. Ce mode est adapté lorsque la validation du document par les autres signataires suffit.

### Validation par courriel

Un responsable de l'organisation reçoit un email lui demandant de valider l'apposition du visa. Il doit alors :

1. Cliquer sur le lien dans l'email
2. Vérifier le document
3. Valider l'apposition du tampon

Ce mode est adapté lorsqu'une vérification humaine est requise avant d'engager l'organisation.

<!-- TODO: Screenshot - Email de validation de visa -->
![Email validation visa](/images/signature/visa/email-validation-visa.png "600x400")

## Image du tampon

### Formats acceptés

| Format | Extension | Recommandation |
|--------|-----------|----------------|
| **PNG** | `.png` | Recommandé (supporte la transparence) |
| **JPEG** | `.jpg`, `.jpeg` | Accepté |

### Contraintes

- **Taille maximale** : 10 Mo
- **Transparence** : utilisez le format PNG si votre tampon a un fond transparent

### Recommandations

- Utilisez une image de bonne qualité (300 DPI minimum pour impression)
- Privilégiez le format PNG pour les tampons avec fond transparent
- Dimensions suggérées : 300x300 pixels minimum pour une bonne lisibilité

<!-- TODO: Screenshot - Aperçu du tampon dans la carte visa -->
![Aperçu tampon](/images/signature/visa/apercu-tampon.png "400x300")

## Utilisation dans les signatures

### Documents générés

Pour les documents générés depuis un template, le visa est récupéré automatiquement selon la configuration du template :

- Le template définit quelle entité fournit le visa (via le chemin dossier)
- Exemple : pour un CERFA FA13, le visa du **Centre de formation** est utilisé

> **Important** : Si aucun visa n'est paramétré sur l'entité concernée, il n'y aura pas de signataire moral sur la signature.

### Exemple : CERFA FA13

Pour le CERFA FA13 (contrat d'apprentissage) :

1. Le template est configuré pour utiliser le visa du Centre de formation
2. Lors de la génération, le système récupère le visa paramétré sur le Centre
3. Le visa apparaît comme signataire moral dans la liste des signataires
4. Selon le mode configuré :
   - **Automatique** : le tampon est apposé dès que les autres signataires ont signé
   - **Validation par courriel** : le responsable reçoit un email pour valider

## Modifier un visa

<!-- TODO: Screenshot - Dialog de modification de visa -->
![Modification visa](/images/signature/visa/modification-visa.png "600x500")

1. Accédez à la fiche de l'entité
2. Dans la carte **Visa**, cliquez sur **Modifier**
3. Vous pouvez modifier :
   - Le mode de signature (automatique / validation par courriel)
   - Le courriel du responsable
   - L'image du tampon
4. Cliquez sur **Enregistrer**

> **Note** : Le code visa ne peut pas être modifié après création.

## Bonnes pratiques

### Choix du code visa

- Utilisez un code explicite et unique
- Exemples : `VISA-CFA-MONTPELLIER`, `VISA_EMPLOYEUR_DUPONT`
- Évitez les codes trop génériques

### Choix du mode de signature

| Situation | Mode recommandé |
|-----------|-----------------|
| Documents standards, processus automatisé | Automatique |
| Documents sensibles nécessitant une vérification | Validation par courriel |
| Volume important de documents | Automatique |
| Engagement juridique fort | Validation par courriel |

### Gestion du courriel

- Utilisez une adresse email professionnelle
- Préférez une adresse générique (ex: `signature@cfa.fr`) plutôt que personnelle
- Assurez-vous que la boîte email est consultée régulièrement
