---
title: "04 - Création d'un apprenant"
description: ""
date: "2025-09-25"
version: "1"
---

### Table des matières

1. [Processus de création](#processus-de-création)
2. [Saisie des informations](#saisie-des-informations)
6. [Finalisation et validation](#finalisation-et-validation)

---

## Processus de création

La création d'un apprenant se fait via un formulaire avec de nombreux champs (non obligatoires pour la plupart).
Certains champs s'appuient sur des référentiels de données pour faciliter la complétion. Des validateurs de syntaxe et de
cohérence sont également mis en place sur certains champs.

### 🎥 Tutoriel vidéo

<video controls>
  <source src="https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/4/creation-apprenant.mp4" type="video/mp4" />
</video>

---

## Saisie des informations
Pour accéder à la page de création, deux options s'offrent à vous, dans la barre de navigation principale vous pouvez cliquer sur le lien Apprenants puis sur le sous-lien création d'un apprenant.
![Menu d'accès aux apprenants](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/4/menu-creation-apprenant.png "259×397")

Vous pouvez aussi créer un apprenant depuis la liste des apprenants.
![Bouton création apprenant](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/3/creer-apprenant.png)

### Informations obligatoires à compléter

Les quatre champs suivants sont obligatoires :
- **Nom**
- **Prénom**
- **Date de naissance**
- **Courriel**

Ces informations permettent d'identifier l'apprenant et de garantir l'unicité de son profil.

Toutes les autres informations sont optionnelles.

### Validation des données

Le système effectue des contrôles automatiques :

- **Nom**: Pas de caractères spéciaux ni de chiffres
- **Prénom**: Pas de caractères spéciaux ni de chiffres
- **Date de naissance**: Doit être une date valide et l'apprenant doit avoir plus de 14 ans
- **Courriel**: Doit respecter le format standard (ex: mail@mail.mail)
- **Téléphone**: Doit respecter le format international (ex: +33 6 12 34 56 78 ou +1 123 456 7890)
- **Numéro de sécurité sociale**: Doit respecter le format standard (ex: 1 99 99 99 999 999 99) et doit être cohérent avec les autres informations renseignées (date de naissance, sexe, pays de naissance, commune de naissance)
- **Adresse**: Doit être une adresse française valide et complète (numéro, rue, code postal, ville, pays) complétable via le référentiel des adresses
- **Nationalité**: Doit être une nationalité reconnue (liste déroulante)
- **Pays de naissance**: Doit être un pays reconnu (liste déroulante)
- **Commune de naissance**: Doit être une commune française valide (liste déroulante) ou champ libre si né hors France
- **Sexe**: Doit être "Homme" ou "Femme"
- **Parcours**: Les valeurs des différents champs sont complétables via la liste déroulante

---

## Finalisation et validation

### Vérification avant enregistrement

Avant de valider l’enregistrement d’un apprenant, le système effectue plusieurs contrôles afin de garantir l’intégrité des données :

- ✅ **Contrôle de complétude** : vérifie que tous les champs obligatoires sont renseignés.
- ✅ **Contrôle de cohérence** : détecte les incohérences entre les données saisies (ex. : date de naissance incompatible avec l’âge requis, format d’e-mail invalide, etc.).
- ✅ **Contrôle de validité des données** : s’assure que les données respectent les formats attendus (nombres, dates, formats spécifiques, etc.).
- ✅ **Blocage de l’enregistrement** si une erreur critique est détectée (absence d’un champ obligatoire, incohérence majeure, etc.).
- ✅ **Enregistrement autorisé** uniquement si l’ensemble des contrôles est passé avec succès.


### Actions post-création

Après la création vous êtes redirigé sur la fiche de l'apprenant. 
À noter que les besoins spécifiques de l'apprenant ne sont complétables qu'une fois le processus de création terminé, depuis la fiche de l'apprenant avec des permissions spécifiques.

### Pour aller plus loin

-> [05 - Consultation et lecture d'un apprenant](05-consultation-apprenant)