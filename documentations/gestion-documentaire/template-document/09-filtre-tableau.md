---
title: "09 - Filtrage dans les tableaux"
description: "Filtrer des tableaux JSON lors des répétitions dans les templates"
date: "2025-11-20"
version: "1"
---

# Filtrage dans les tableaux

---

## Overview

Cette page décrit comment **filtrer un tableau JSON directement dans un template**, avant ou pendant une répétition.

Le filtrage permet de :
- inclure uniquement certains éléments
- exclure des éléments selon des critères
- limiter le nombre d’éléments parcourus

---

## Filtres numériques

Les filtres numériques permettent de comparer la valeur d’un attribut à une constante.

### Opérateurs supportés

- `=` égal
- `!=` différent
- `>` supérieur
- `<` inférieur
- `>=` supérieur ou égal
- `<=` inférieur ou égal

### data

```json
{
  "cars": [
    { "brand": "Ferrari", "power": 3 },
    { "brand": "Peugeot", "power": 1 },
    { "brand": "BMW",     "power": 2 }
  ]
}
```

### template

```text
Cars
{d.cars[power > 1].brand}
{d.cars[power > 1 + 1].brand}
```

### Document généré

```text
Cars
Ferrari
BMW
```

---

## Filtres sur les chaînes de caractères

Les filtres sur les chaînes permettent de sélectionner des éléments selon la valeur exacte d’un attribut texte.

### data

```json
{
  "cars": [
    { "brand": "Ferrari" },
    { "brand": "Peugeot" },
    { "brand": "BMW" }
  ]
}
```

### template

```text
Cars
{d.cars[brand = 'BMW'].brand}
```

### Document généré

```text
Cars
BMW
```

---

## Filtrer les N premiers éléments

Il est possible de limiter une répétition aux **N premiers éléments** d’un tableau.

### data

```json
{
  "cars": [
    { "brand": "Ferrari" },
    { "brand": "Peugeot" },
    { "brand": "BMW" }
  ]
}
```

### template

```text
Cars
{d.cars[:2].brand}
{d.cars[:2 + 1].brand}
```

### Document généré

```text
Cars
Ferrari
Peugeot
```

---

## Exclure les N derniers éléments

Il est possible d’exclure les **N derniers éléments** d’un tableau.

### data

```json
{
  "cars": [
    { "brand": "Ferrari" },
    { "brand": "Peugeot" },
    { "brand": "BMW" }
  ]
}
```

### template

```text
Cars
{d.cars[:-1].brand}
{d.cars[:-1 + 1].brand}
```

### Document généré

```text
Cars
Ferrari
Peugeot
```

---

## Filtrage intelligent (Smart filter)

Le **smart filter** permet d’activer ou désactiver dynamiquement un filtre selon une condition.

### data

```json
{
  "cars": [
    { "brand": "Ferrari", "power": 3 },
    { "brand": "Peugeot", "power": 1 }
  ],
  "filterEnabled": true
}
```

### template

```text
Cars
{d.cars[power > 1:if(.filterEnabled)].brand}
{d.cars[power > 1:if(.filterEnabled) + 1].brand}
```

### Document généré

```text
Cars
Ferrari
```

Si la condition `filterEnabled` est fausse, le filtre n’est pas appliqué et tous les éléments sont parcourus.

---

## Filtres avancés

Des fonctionnalités de filtrage avancées sont prévues dans des versions futures de la plateforme.

---

## Pour aller plus loin

-> [10 - Regroupement dans les tableaux](10-regroupement-tableau)
