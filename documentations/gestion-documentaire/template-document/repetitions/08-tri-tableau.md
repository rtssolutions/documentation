---
title: "08 - Tri dans les tableaux"
description: "Trier des tableaux JSON lors des répétitions dans les templates"
date: "2025-11-20"
version: "1"
---

# Tri dans les répétitions

Trier les données lors des répétitions

---

## Overview

Cette page décrit comment **trier un tableau JSON directement dans un template**, au moment d’une répétition.

Le tri est effectué **avant** l’application du motif de répétition.  
Il est basé sur les **attributs des objets** du tableau, et non sur l’indice `i`.

---

## Tri ascendant

Le tri ascendant est le comportement par défaut.  
Les éléments sont triés selon un ou plusieurs attributs.

Si deux éléments ont la même valeur pour un attribut donné, la plateforme utilise **l’indice d’origine du tableau (`i`)** comme critère de départage.

### data

```json
{
  "cars": [
    { "brand": "Ferrari", "power": 3 },
    { "brand": "Peugeot", "power": 1 },
    { "brand": "BMW",     "power": 2 },
    { "brand": "Lexus",   "power": 1 }
  ]
}
```

### template

```text
Cars
{d.cars[power, i].brand}
{d.cars[power+1, i+1].brand}
```

### Document généré

```text
Cars
Peugeot
Lexus
BMW
Ferrari
```

---

## Tri avec plusieurs attributs

Il est possible de trier un tableau sur **plusieurs attributs successifs**.

Les éléments sont triés :
1. selon le premier attribut
2. puis selon le deuxième attribut
3. puis selon l’ordre initial (`i`) si nécessaire

### data

```json
{
  "cars": [
    { "brand": "Ferrari", "power": 3, "sub": { "size": 1 } },
    { "brand": "Aptera",  "power": 1, "sub": { "size": 20 } },
    { "brand": "Peugeot", "power": 1, "sub": { "size": 20 } },
    { "brand": "BMW",     "power": 2, "sub": { "size": 1 } },
    { "brand": "Kia",     "power": 1, "sub": { "size": 10 } }
  ]
}
```

### template

```text
Cars
{d.cars[power, sub.size, i].brand}
{d.cars[power+1, sub.size+1, i+1].brand}
```

### Document généré

```text
Cars
Kia
Aptera
Peugeot
BMW
Ferrari
```

---

## Tri descendant

Le tri descendant (ordre inverse) **n’est pas encore disponible** à ce jour.

Cette fonctionnalité est prévue pour une version future de la plateforme (v5).

---

## Pour aller plus loin

-> [09 - filtres dans les tableaux](09-filtre-tableau)
