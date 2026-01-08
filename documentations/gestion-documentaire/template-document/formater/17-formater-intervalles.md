---
title: "17 - Formatage des intervalles"
description: "Formatters pour manipuler et afficher des intervalles et des durées"
date: "2025-11-20"
version: "1"
---

# Formatage des intervalles

Formatters pour manipuler et afficher des intervalles et des durées

---

## :formatI(patternOut, patternIn)

Le formatter `:formatI` permet de **formater des intervalles ou des durées** selon une unité cible ou un format lisible.

Les intervalles peuvent être exprimés :
- en millisecondes (par défaut)
- dans une autre unité (`second`, `minute`, `hour`, etc.)
- au format ISO‑8601 (`P1Y2M3DT4H5M6S`)

---

## Paramètres

- `patternOut` : format de sortie  
  Valeurs possibles :
  - `human` → affichage lisible compact  
  - `human+` → affichage lisible détaillé  
  - `millisecond(s)`, `ms`
  - `second(s)`, `s`
  - `minute(s)`, `m`
  - `hour(s)`, `h`
  - `day(s)`, `d`
  - `week(s)`, `w`
  - `month(s)`, `M`
  - `year(s)`, `y`

- `patternIn` (optionnel) : unité d’entrée si différente de la milliseconde

Les unités sont **insensibles à la casse** et acceptent les formes abrégées ou complètes.

---

## Exemples avec millisecondes

```text
2000:formatI('second')  // 2
2000:formatI('seconds') // 2
2000:formatI('s')       // 2
3600000:formatI('minute') // 60
3600000:formatI('hour')   // 1
2419200000:formatI('days') // 28
```

---

## Exemples en format lisible

```text
2000:formatI('human') // "quelques secondes"
2000:formatI('human+') // "dans quelques secondes"
-2000:formatI('human+') // "il y a quelques secondes"
```

---

## Changer l’unité d’entrée

```text
60:formatI('ms', 'minute')   // 3600000
4:formatI('ms', 'weeks')     // 2419200000
```

---

## Intervalles ISO‑8601

Le formatter supporte les durées au format ISO‑8601.

```text
'P1M':formatI('ms')        // 2592000000
'P1Y2M3DT4H5M6S':formatI('hour')
```

---

## Bonnes pratiques

- Utiliser `human` ou `human+` pour des rendus utilisateur
- Toujours préciser `patternIn` si l’entrée n’est pas en millisecondes
- Combiner avec `:diffD` pour calculer des durées entre deux dates
- Tester les valeurs négatives et les durées longues

---

## Pour aller plus loin

-> [18 - Formatters de tableaux](18-formater-tableau)
