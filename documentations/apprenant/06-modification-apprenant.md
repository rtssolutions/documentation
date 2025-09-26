---
title: "06 - Modification d'une apprenant"
description: ""
date: "2025-09-25"
version: "1"
---

### Table des matières
1. [Accéder à la modification](#accéder-à-la-modification)
2. [Modification des informations générales](#modification-des-informations-générales)
3. [Validation des modifications](#validation-des-modifications)

---

## Accéder à la modification

### Prérequis
Pour modifier un apprenant, vous devez :

- Disposer de la permission **"Écriture des apprenants"**
- L'apprenant ne doit pas être **archivée**

### Depuis la fiche de consultation
- Cliquez sur le bouton **"Modifier"** en haut de la fiche

![Bouton modifier depuis fiche](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/6/action-modifier-fiche.png)

### Depuis la liste
- Cliquez sur **"Modifier"** dans les actions de ligne

![Modifier depuis liste](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/6/action-modifier-liste.png)

### Mode de modification
Le système ouvre le formulaire de modification avec les données actuelles pré-remplies.

![Formulaire modification](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/6/formulaire-modification.png)

---

## Modification des informations générales

### Informations non modifiables
Aucune données de l'apprenant est non modifiable.
Cependant les mêmes contrôles de cohérences et de validités que lors de la création sont appliqués.
Les mêmes référentiels sont utilisés pour les listes déroulantes.

### Informations modifiables
Toutes les informations sont modifiables.

### Sauvegarde des modifications

**Validation des champs**
- **Contrôles en temps réel** du format pendant la saisie : 
![Validation champs](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/6/formulaire-erreurs-validites.png)
- **Messages d'erreur** contextuels remontés en cas d'incohérence détectée :
![Validation cohérence](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/6/formulaire-erreurs-coherence.png)
- **Blocage de sauvegarde** si erreurs critiques

---

## Validation des modifications

### Contrôles automatiques

Le système effectue des contrôles automatiques(identiques à la création) :

- **Nom**: Pas de caractères spéciaux ni de chiffres
- **Prénom**: Pas de caractères spéciaux ni de chiffres
- **Date de naissance**: Doit être une date valide et l'apprenant doit avoir plus de 14ans
- **Courriel**: Doit respecter le format standard (ex: mail@mail.mail)
- **Téléphone**: Doit respecter le format international (ex: +33 6 12 34 56 78 ou +1 123 456 7890)
- **Numéro de sécurité sociale**: Doit respecter le format standard (ex: 1 99 99 99 999 999 99) et doit être cohérent avec les autres informations renseignées (date de naissance, sexe, pays de naissance, commune de naissance)
- **Adresse**: Doit être une adresse française valide et complète (numéro, rue, code postal, ville, pays) complétable via le référentiel des adresses
- **Nationalité**: Doit être une nationalité reconnue (liste déroulante)
- **Pays de naissance**: Doit être un pays reconnu (liste déroulante)
- **Commune de naissance**: Doit être une commune française valide (liste déroulante) ou champs libre si né hors France
- **Sexe**: Doit être "Homme" ou "Femme"
- **Parcours**: Les valeurs des différents champs sont complétable via la liste déroulante

---

### Pour aller plus loin
-> [07 - Suppression d'un apprenant](07-supression-apprenant)
