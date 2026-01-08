---
title: "18 - Formatters de tableaux"
description: "Liste exhaustive des formatters applicables aux tableaux (arrays)"
date: "2025-11-20"
version: "1"
---

# Formatters de tableaux

Liste des formatters permettant de manipuler et d’afficher des tableaux JSON dans les templates.

---

## :arrayJoin(separator, index, count)

Concatène les éléments d’un tableau en une chaîne de caractères.

### Paramètres

- `separator` : séparateur entre les éléments (String)
- `index` *(optionnel)* : index de départ (Number)
- `count` *(optionnel)* : nombre d’éléments à inclure (Number)

### Exemples

```text
['homer','bart','lisa']:arrayJoin() // "homer, bart, lisa"
['homer','bart','lisa']:arrayJoin(' | ') // "homer | bart | lisa"
['homer','bart','lisa']:arrayJoin('') // "homerbartlisa"
[10,50]:arrayJoin() // "10, 50"
[]:arrayJoin() // ""
null:arrayJoin() // null
{}:arrayJoin() // {}
20:arrayJoin() // 20
undefined:arrayJoin() // undefined
['homer','bart','lisa']:arrayJoin('', 1) // "bartlisa"
['homer','bart','lisa']:arrayJoin('', 1, 1) // "bart"
['homer','bart','lisa']:arrayJoin('', 1, 2) // "bartlisa"
['homer','bart','lisa']:arrayJoin('', 0, -1) // "homerbart"
```

---

## :arrayMap(objSeparator, attSeparator, attributes)

Transforme un tableau d’objets en texte.

### Paramètres

- `objSeparator` : séparateur entre les objets (String)
- `attSeparator` : séparateur entre les attributs (String)
- `attributes` : liste des attributs à afficher (Array)

### Exemples

```text
[{'id':2,'name':'homer'},{'id':3,'name':'bart'}]:arrayMap() // "2:homer, 3:bart"
[{'id':2,'name':'homer'},{'id':3,'name':'bart'}]:arrayMap(' - ') // "2:homer - 3:bart"
[{'id':2,'name':'homer'},{'id':3,'name':'bart'}]:arrayMap(' ; ', '|') // "2|homer ; 3|bart"
[{'id':2,'name':'homer'},{'id':3,'name':'bart'}]:arrayMap(' ; ', '|', 'id') // "2 ; 3"
[{'id':2,'name':'homer','obj':{'id':20},'arr':[12,23]}]:arrayMap() // "2:homer"
['homer','bart','lisa']:arrayMap() // "homer, bart, lisa"
[10,50]:arrayMap() // "10, 50"
[]:arrayMap() // ""
null:arrayMap() // null
{}:arrayMap() // {}
20:arrayMap() // 20
undefined:arrayMap() // undefined
```

---

## :count(start)

Affiche un compteur incrémental lors d’une répétition.

### Paramètres

- `start` *(optionnel)* : valeur de départ (Number)

### Exemples

```text
['a','b','c']:count() // 1 2 3
['a','b','c']:count(5) // 5 6 7
```

---

## Bonnes pratiques

- Utiliser `arrayJoin` pour des listes simples
- Utiliser `arrayMap` pour des tableaux d’objets
- Tester les tableaux vides
- Combiner avec filtres et tris si nécessaire

---

## Pour aller plus loin

-> [19 - Les conditions](../conditionner/19-conditions)
