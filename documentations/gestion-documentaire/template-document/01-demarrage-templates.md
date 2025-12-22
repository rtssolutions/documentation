---
title: "01 - Démarrer avec les templates de document"
description: "Comprendre les principes de base pour créer et utiliser des templates de document avec la plateforme"
date: "2025-12-16"
version: "1"
---

# Démarrer avec les templates de document

## Objectif

Cette page explique les **principes fondamentaux** permettant de créer un **template de document** utilisable dans notre application grâce à la plateforme.

L’utilisateur final n’utilise pas directement la plateforme :  
il crée uniquement un **document modèle (template)** qui sera ensuite référencé et exploité par l’application.

---

## Qu’est-ce qu’un template de document ?

Un **template de document** est un fichier servant de modèle pour générer automatiquement des documents à partir de données.

Il est créé à l’aide d’un éditeur classique, par exemple :
- Microsoft Word
- LibreOffice
- Google Docs
- Tout autre outil compatible avec les formats supportés

Les formats de fichiers les plus courants sont :
- **DOCX**
- **ODT**
- **XLSX**
- **HTML**
- **Markdown**

Le template contient à la fois :
- La **mise en forme** du document (textes, tableaux, styles)
- Des **balises** indiquant où les données doivent être injectées

---

## Qu’est-ce que les données JSON ?

Les données utilisées pour générer un document sont fournies au format **JSON**.

Le JSON est un format standard de représentation des données, lisible et structuré, utilisé pour transmettre :
- Les informations métier
- Les listes
- Les valeurs dynamiques à insérer dans le document final

Ces données sont générées par l’application puis transmises à la plateforme lors de la génération du document.

---

## Qu’est-ce qu’une balise (placeholder) ?

Une **balise** (ou *placeholder*) est un élément inséré dans le template pour indiquer :
- **où** une donnée doit apparaître
- **comment** elle doit être affichée

Les balises sont toujours écrites entre **accolades `{}`**.

### Exemples de types de balises

| Type de balise | Rôle |
|---------------|------|
| `{d.…}` | Accès aux données principales |
| `{c.…}` | Accès à des données complémentaires |
| `{# …}` | Déclaration d’alias (raccourci) |
| `{t(…)}` | Gestion des traductions |
| `{o.…}` | Options avancées de rendu |

Ces balises sont interprétées par la plateforme lors de la génération du document.

---

## Principe de fonctionnement global

Le fonctionnement repose sur une étape de **fusion** entre :
- Un **template de document**
- Des **données JSON**

### Étapes de génération

1. Le template est créé et stocké
2. L’application prépare les données JSON
3. La plateforme fusionne le template et les données
4. Un document final est généré (PDF, DOCX, HTML, etc.)

---

## Création d’un premier template

### Étape 1 : Créer le document

- Ouvrez votre éditeur de document
- Créez la structure du document (titres, tableaux, sections)
- Insérez les balises aux emplacements où les données doivent apparaître

### Étape 2 : Enregistrer le template

- Enregistrez le fichier dans un format compatible
- Le template est ensuite référencé dans l’application

### Étape 3 : Génération du document

- L’application fournit les données JSON
- Le document est généré automatiquement à partir du template

---

## Bonnes pratiques

- La majorité du rendu dépend du **template lui-même**
- Les balises servent uniquement à injecter et transformer les données
- Il est recommandé de :
  - Tester les templates avec des données simples
  - Structurer clairement le document avant d’ajouter des balises
  - Limiter la logique complexe dans les premières versions

👉 En pratique, **la mise en page représente l’essentiel du travail**, la logique de balisage venant en complément.

---

## Pour aller plus loin

-> [02 - Bonnes pratiques de conception](02-design-best-practices)
