
---
title: "04 - Recherche dans un tableau"
description: "Rechercher un élément dans un tableau JSON sans boucle, en utilisant des filtres dans les balises"
date: "2025-11-20"
version: "1"
---

# Recherche dans un tableau

## Objectif

Cette page explique comment **rechercher un élément dans un tableau JSON sans créer de boucle explicite**, en appliquant **des filtres directement dans les balises de substitution**.

---

## Filtres simples

Au lieu d’utiliser le mot réservé `i` pour accéder au i‑ème élément d’un tableau, la plateforme accepte des **filtres basés sur les attributs des objets** du tableau.  
Si le filtre renvoie plusieurs éléments, **seule la première occurrence est conservée**.  
Utilisez des **apostrophes simples** pour filtrer du texte contenant des espaces.

### Données (JSON)

```json
[
  { "name": "Inception", "year": 2010 },
  { "name": "Matrix", "year": 1999 },
  { "name": "Back to the future", "year": 1985 }
]
```

### Template

```text
The movie of 1999 was {d[year=1999].name}
Back to the future: {d[name='Back to the future'].year}
```

### Document généré

```text
The movie of 1999 was Matrix
Back to the future: 1985
```

---

## Filtre avec variable

Si le **second opérande commence par un point (`.`)**, la plateforme considère que cet opérande est une **variable provenant du JSON**.

### Données (JSON)

```json
{
  "parent": {
    "qty": 2
  },
  "subArray": [
    {
      "text": 1000,
      "other": 1,
      "sub": { "b": { "c": 1 } }
    },
    {
      "text": 2000,
      "other": 1,
      "sub": { "b": { "c": 2 } }
    }
  ]
}
```

### Template

```text
{d.subArray[sub.b.c = .other].text}
{d.subArray[sub.b.c = ..parent.qty].text}
```

### Document généré

```text
1000
2000
```

---

## Plusieurs filtres sur un tableau

La plateforme accepte **plusieurs filtres combinés**, y compris sur des sous‑objets.  
Si le filtre renvoie plusieurs éléments, **seule la première occurrence est conservée**.

### Données (JSON)

```json
[
  { "name": "Interstellar",   "year": 2014, "meta": { "type": "SF" } },
  { "name": "Matrix",         "year": 1999, "meta": { "type": "SF" } },
  { "name": "The Green Mile", "year": 1999, "meta": { "type": "Drama" } }
]
```

### Template

```text
{d[year=1999, meta.type='SF'].name}
```

### Document généré

```text
Matrix
```

---

## Dernier élément

Vous pouvez récupérer le **dernier élément d’un tableau** à l’aide d’un **indice négatif** :

- Dernier élément : `[i=-1]`
- Avant‑dernier élément : `[i=-2]`

> Ce filtre peut aussi être utilisé dans une boucle de répétition.

### Données (JSON)

```json
[
  { "name": "Inception", "year": 2010 },
  { "name": "Matrix", "year": 1999 },
  { "name": "BTTF", "year": 1985 }
]
```

### Template

```text
The oldest movie was {d[i=-1].name}.
```

### Document généré

```text
The oldest movie was BTTF.
```

---

## Filtrer et afficher une donnée du parent

Il est possible d’accéder aux **propriétés de l’objet parent** en utilisant **deux points (`..`)** ou plus, lorsque vous appliquez un filtre dans un tableau imbriqué.

### Données (JSON)
```json
{
  "country": "USA",
  "movies": [
    { "name": "Inception", "year": 2010 },
    { "name": "Matrix", "year": 1999 },
    { "name": "BTTF", "year": 1985 }
  ]
}
```

### Template
```text
{d.movies[year=1999]..country}
```

### Document généré
```text
USA
```

## Pour aller plus loin
-> [05 - Alias de substitution](05-alias-de-substitution)
