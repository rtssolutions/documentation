---
title: "11 - Valeurs distinctes dans les tableaux"
description: "Afficher uniquement les valeurs distinctes lors des tableaux dans les templates"
date: "2025-11-20"
version: "1"
---

# Valeurs distinctes dans les tableaux

Afficher uniquement des valeurs uniques

---

## Overview

Cette page décrit comment **afficher uniquement les valeurs distinctes** sur un tableau JSON dans un template de document avec la plateforme.

Cela permet :
- d’éviter les doublons
- de créer des listes uniques
- d’extraire des catégories ou types distincts

---

## Principe

Le comportement *distinct* repose sur l’utilisation d’un **itérateur basé sur un attribut** plutôt que sur l’indice numérique `i`.

Lorsque l’on utilise un attribut (ex. `type`) comme itérateur :
- chaque valeur unique de cet attribut est utilisée une seule fois
- seules les **premières occurrences** sont affichées
- les doublons sont ignorés

---

## Exemple simple

### data

```json
[
  { "type": "car"  , "brand": "Hyundai" },
  { "type": "plane", "brand": "Airbus" },
  { "type": "plane", "brand": "Boeing" },
  { "type": "car"  , "brand": "Toyota" }
]
```

### template

```text
Vehicles
{d[type].brand}
{d[type+1].brand}
```

### Document généré

```text
Vehicles
Hyundai
Airbus
```

Dans cet exemple :
- l’itérateur `[type]` sélectionne chaque valeur unique de `type`
- seules les premières occurrences de `car` et `plane` sont conservées

---

## Cas d’usage

- Afficher une liste de catégories uniques
- Générer des en-têtes à partir de données répétées
- Éviter les doublons dans des tableaux ou des sections répétées

---


## Pour aller plus loin

-> [12 - Formater les données](12-apercu-formatters)
