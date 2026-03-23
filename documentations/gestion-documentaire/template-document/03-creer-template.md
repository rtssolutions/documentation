---
title: "03 - Créer un template"
description: "Guide pas-à-pas pour créer un template de document personnalisé dans Papaours"
date: "2026-03-13"
version: "1"
---

# Créer un template

## Prérequis

Avant de créer un template, assurez-vous de :

- Disposer des droits nécessaires pour la gestion documentaire
- Avoir préparé votre fichier template (DOCX ou HTML)
- Connaître les entités liées dont vous aurez besoin

---

## Accéder à la gestion des templates

1. Dans le menu principal, accédez à **Paramètres**
2. Sélectionnez **Gestion documentaire**
3. Cliquez sur **Templates de documents**

---

## Créer un nouveau template

### Étape 1 : Informations générales

Cliquez sur **Ajouter un template** et renseignez les informations suivantes :

| Champ | Description | Obligatoire |
|-------|-------------|-------------|
| **Titre** | Nom affiché du template | Oui |
| **Description** | Explication du contenu et de l'usage | Non |
| **Type de document** | Catégorie du document généré | Oui |
| **Format de sortie** | PDF (recommandé) ou autre | Oui |

### Étape 2 : Entités liées

Sélectionnez les entités dont les données seront accessibles dans le template :

- **Contrat** : données du contrat d'apprentissage, de l'apprenant, de l'employeur et du CFA
- **Apprenant** : données de la fiche apprenant uniquement
- **Employeur** : données de la fiche employeur uniquement
- **Dossier de formation** : données du dossier, de la session et de la formation
- **Centre de formation** : données du CFA

> Le choix des entités liées détermine les variables `{d.xxx}` disponibles dans votre template.

### Étape 3 : Uploader le fichier template

1. Préparez votre fichier au format **DOCX** ou **HTML**
2. Intégrez les balises de substitution `{d.xxx}` dans le document
3. Uploadez le fichier dans l'interface

---

## Structure d'un template

### Formats acceptés

| Format | Extension | Recommandation |
|--------|-----------|----------------|
| Word | `.docx` | Idéal pour les documents textuels |
| HTML | `.html` | Idéal pour les formulaires complexes (CERFA) |

### Balises de substitution

Les balises suivent la syntaxe de templating :

```text
{d.nomDuChamp}
```

Exemple pour un template lié à l'entité **Apprenant** :

```text
Nom : {d.apprenant.nom}
Prénom : {d.apprenant.prenom}
Date de naissance : {d.apprenant.dateDeNaissance:formatD(DD/MM/YYYY)}
```

---

## Bonnes pratiques

1. **Testez votre template** avec des données réelles avant de le déployer
2. **Utilisez des noms explicites** pour faciliter la recherche
3. **Documentez l'usage** dans la description du template
4. **Versionnez vos templates** en cas de modification majeure

---

## Pour aller plus loin

-> [03 - Entités liées](03-entites-liees)
