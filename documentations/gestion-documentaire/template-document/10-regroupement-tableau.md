---
title: "10 - Regroupement dans les tableaux"
description: "Regrouper des éléments d’un tableau JSON et appliquer des agrégations"
date: "2025-11-20"
version: "1"
---

# Regroupement dans les répétitions

Regrouper des données dans un tableau

---

## Overview

Cette page décrit comment **regrouper les éléments d’un tableau JSON** lors d’une répétition dans un template de document avec la plateforme.

Le regroupement permet :
- de créer des groupes selon la valeur d’un attribut
- de calculer des agrégats (sommes, totaux) par groupe
- de restructurer des données plates

---

## Regroupement et somme

Il est possible de regrouper un tableau selon la valeur d’un attribut, puis d’utiliser des **formatters d’agrégation** pour calculer une valeur par groupe.

### data

```json
[
  { "brand":"Lucid"   , "qty":1  },
  { "brand":"Faraday" , "qty":4  },
  { "brand":"Venturi" , "qty":3  },
  { "brand":"Faraday" , "qty":2  },
  { "brand":"Aptera"  , "qty":1  },
  { "brand":"Lucid"   , "qty":10 }
]
```

### template

```text
Vehicles Quantity
{d[brand].brand}
{d[brand].qty:aggSum(.brand)}
{d[brand+1].brand}
```

### Document généré

```text
Vehicles Quantity
Aptera 1
Faraday 6
Lucid 11
Venturi 3
```

Chaque groupe est identifié par une valeur unique de `brand`, et la quantité est additionnée par groupe.

---

## Transformer un résultat de base de données

Depuis la version **v4.23.0+** (option *pre-release* activée), il est possible de **transformer la structure JSON** avant de l’utiliser dans une répétition.

Cela permet par exemple de transformer un tableau plat en structure hiérarchique.

### data

```json
[
  { "country": "France", "city": "Paris" },
  { "country": "France", "city": "Nantes" },
  { "country": "France", "city": "Pouzauges" },
  { "country": "Italy",  "city": "Rome" },
  { "country": "Italy",  "city": "Venise" }
]
```

### template

```text
{d[].city:set(c.countries[id=.country].cities[].name)}
{c.countries[i].id}
{c.countries[i].cities[i].name}
{c.countries[i].cities[i+1].name}
{c.countries[i+1].id}
```

### Document généré

```text
France
Paris
Nantes
Pouzauges
Italy
Rome
Venise
```

---

## Bonnes pratiques

- Tester avec des jeux de données variés
- Combiner regroupement, tri et filtrage si nécessaire
- Réserver le regroupement à la présentation des données

---

## Pour aller plus loin

-> [11 - Valeurs distinctes dans les tableaux](11-repetitions-distinct)
