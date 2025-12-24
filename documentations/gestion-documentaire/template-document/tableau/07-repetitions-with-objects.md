---
title: "07 - Répétitions avec des objets"
description: "Répéter des sections de document en parcourant des objets JSON"
date: "2025-11-20"
version: "1"
---

# Répétitions avec des objets

Répéter des sections de document à partir d’objets JSON

---

## Overview

Cette page décrit comment **répéter une partie d’un document** lorsque les données à parcourir sont des **objets JSON** (et non des tableaux).

Contrairement aux tableaux, les objets ne disposent pas d’index numériques.  
La plateforme permet néanmoins de les parcourir en utilisant un itérateur interne.

---

## Principe

Pour parcourir un objet, la plateforme :
- itère sur chacune de ses **propriétés**
- expose implicitement une paire **clé / valeur**
- répète le motif détecté pour chaque propriété de l’objet

Comme pour les tableaux, il suffit d’indiquer dans le template :
- une occurrence avec `i`
- une occurrence avec `i+1`

La seconde occurrence (`i+1`) est utilisée uniquement pour détecter le motif et est supprimée avant le rendu final.

---

## Exemple simple avec un objet

### data

```json
{
  "cars": {
    "toyota": { "id": 1 },
    "hyundai": { "id": 2 },
    "bmw": { "id": 3 }
  }
}
```

### template

```text
Cars id{d.cars[i].id}{d.cars[i+1].id}
```

### Document généré

```text
Cars id 1 2 3
```

---

## Accéder à la clé et à la valeur

Lorsqu’un objet est parcouru :
- `.key` permet d’accéder à la **clé**
- `.value` permet d’accéder à la **valeur**

### data

```json
{
  "cars": {
    "toyota": { "power": 90 },
    "hyundai": { "power": 110 }
  }
}
```

### template

```text
{d.cars[i].key}: {d.cars[i].value.power}{d.cars[i+1].key}
```

### Document généré

```text
toyota: 90
hyundai: 110
```

---

## Objets imbriqués

### data

```json
{
  "brands": {
    "toyota": {
      "models": {
        "prius": { "power": 125 },
        "yaris": { "power": 100 }
      }
    },
    "kia": {
      "models": {
        "ev6": { "power": 500 }
      }
    }
  }
}
```

### template

```text
{d.brands[i].key}
{d.brands[i].value.models[i].key} - {d.brands[i].value.models[i].value.power}
{d.brands[i].value.models[i+1].key}{d.brands[i+1].key}
```

### Document généré
```text
toyota
prius - 125
yaris - 100
kia
ev6 - 500
```

---
## Pour aller plus loin

-> [08 - Tri dans les tableaux](08-tri-tableau)
