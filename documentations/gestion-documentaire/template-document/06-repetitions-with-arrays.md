---
title: "06 - Répétitions avec des tableaux"
description: "Répéter n’importe quelle partie d’un document en parcourant un tableau JSON"
date: "2025-11-20"
version: "1"
---

# Répétitions avec des tableaux

Répéter n’importe quelle partie d’un document

---

## Overview

La plateforme peut répéter n’importe quelle partie d’un document (lignes, titres, pages…).

Il suffit d’indiquer où se trouvent les lignes `i` et `i+1` : la plateforme déduit automatiquement le motif à répéter, en utilisant la première ligne (`i`) comme exemple.

La seconde ligne (`i+1`) est supprimée avant le rendu final.

Une seule balise `[i+1]` suffit pour identifier le motif de répétition : il n’est pas nécessaire de dupliquer toute la partie `[i+1]`.

---

## Tableau simple

Dans cet exemple, on souhaite parcourir un tableau de voitures.

### data

```json
{
  "cars" : [
    {"brand" : "Toyota" , "id" : 1 },
    {"brand" : "Hyundai", "id" : 2 },
    {"brand" : "BMW"    , "id" : 3 },
    {"brand" : "Peugeot", "id" : 4 }
  ]
}
```

### template

```text
Cars id{d.cars[i].brand}{d.cars[i].id}{d.cars[i+1].brand}
```

### Résultat

```text
Cars id Toyota 1 Hyundai 2 BMW 3 Peugeot 4
```

---

## Tableaux imbriqués

La plateforme gère les tableaux imbriqués (profondeur illimitée). Voici un exemple où une portion entière du document est répétée.

### data

```json
[
  {
    "brand": "Toyota",
    "models": [{ "size": "Prius 4", "power": 125 }, { "size": "Prius 5", "power": 139  }]
  },
  {
    "brand": "Kia",
    "models": [{ "size": "EV4", "power": 450  }, { "size": "EV6", "power": 500  }]
  }
]
```

### template

```text
{d[i].brand}Models{d[i].models[i].size} - {d[i].models[i].power}{d[i].models[i+1].size}{d[i+1].brand}
```

### Résultat

```text
Toyota Models Prius 4 - 125 Prius 5 - 139 Kia Models EV4 - 450 EV6 - 500
```

Comme on peut le voir, il est inutile de répéter deux fois le premier paragraphe dans le template : seul le titre du second paragraphe est nécessaire pour aider la plateforme à reconnaître où se termine le motif de répétition du tableau principal `{d.cars[i+1].brand}`.

---

## Boucle bidirectionnelle

**v4.8.0+**

La boucle bidirectionnelle effectue des itérations dans **2 directions**, créant des colonnes et des lignes supplémentaires.

Quelques restrictions :
- Le tableau parent JSON doit être utilisé pour les **lignes**, et le tableau imbriqué pour les **colonnes**. Cette limitation sera levée en v5.
- Support officiel pour les templates **DOCX, HTML, MD**. En plus, Word peut redimensionner automatiquement la table pour s’adapter à la largeur de la page. Les boucles bidirectionnelles avec d’autres formats de template sont encore expérimentales.

### data

```json
{
  "titles" : [{ "name": "Kia" }, { "name": "Toyota" }, { "name": "Hopium" }],
  "cars"   : [
    { "models" : [ "EV3", "Prius 1", "Prototype" ] },
    { "models" : [ "EV4", "Prius 2", "" ]          },
    { "models" : [ "EV6", "Prius 3", "" ]          }
  ]
}
```

### template

```text
{d.titles[i].name}{d.titles[i+1].name}{d.cars[i].models[i]}{d.cars[i].models[i+1]}{d.cars[i+1].models[i]}
```

### Résultat

```text
Kia Toyota Hopium EV3 Prius 1 Prototype EV4 Prius 2 EV6 Prius 3
```
---

## Accéder à la valeur de l’itérateur de boucle

**v4.0.0+**

Accéder à la valeur de l’itérateur lorsqu’une liste est imprimée dans un document. Exemple :  
`{d[i].cars[i].other.wheels[i].tire.subObject:add(.i):add(..i):add(...i)}`

Le nombre de points correspond à la position de `i` dans la hiérarchie :
- `...i` se réfère à l’index de `wheels[i]`
- `..i` se réfère à l’index de `cars[i]`
- `.i` se réfère à l’index de `d[i]`

⚠️ Le nombre de points est actuellement inversé. Il devrait être `...i` pour `d[i]` et `.i` pour `wheels[i]`. C’est un bug connu. Beaucoup d’utilisateurs s’appuient sur le comportement actuel et le corriger casserait certains rapports. Ce point sera traité plus tard avec compatibilité ascendante.

---

## Boucle parallèle

Parcourir **deux tableaux distincts** en même temps en utilisant la même variable d’itération.

Comme vu précédemment, l’itérateur `i` peut être utilisé dans des formatters. En le combinant avec l’accès par chemin relatif, on peut remonter dans la hiérarchie JSON en utilisant deux points (`..`).  
Cela permet d’imprimer le contenu d’un autre tableau, `brands`, avec le même itérateur que le tableau `cars`.

### data

```json
{
  "cars" : [
    { "id" : 1 },
    { "id" : 2 },
    { "id" : 3 },
    { "id" : 4 }
  ],
  "brands" : [
    { "name" : "Toyota" },
    { "name" : "Hyundai"},
    { "name" : "BMW"    }
  ]
}
```

### template

```text
Cars id{d.cars[i].id}{d.cars[i].id:print(..brands[.i].name)}{d.cars[i+1].id}
```

### Résultat

```text
Cars id 1 Toyota 2 Hyundai 3 BMW 4
```
