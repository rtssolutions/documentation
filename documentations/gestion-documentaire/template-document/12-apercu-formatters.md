---
title: "12 - formater les données"
description: "Vue d’ensemble des moyens utilisés pour transformer et formater des données dans les templates"
date: "2025-11-20"
version: "1"
---

# Aperçu des transformateurs

Présentation générale des transformateurs

Cette page présente une **vue d’ensemble des transformateurs**.  
Un formatter permet de **transformer une donnée** directement dans un template, sans modifier les données sources.

Les transformateurs sont appliqués à l’aide du caractère `:` et peuvent être **chaînés**.

---

## Principe des transformateurs

Un formatter est appliqué à une valeur issue du JSON.

### Exemple

### data

```json
{
  "name": "JOHN",
  "birthday": "2000-01-31"
}
```

### template

```text
My name is {d.name:lowerCase:ucFirst}.
I was born on {d.birthday:formatD(LL)}.
```

### Document généré

```text
My name is John.
I was born on January 31, 2000.
```

Chaque formatter prend en entrée le résultat du formatter précédent.

---

## Chaînage des transformateurs

Plusieurs transformateurs peuvent être utilisés sur une même donnée :

```text
{d.name:lowerCase:ucFirst}
```

Dans cet exemple :
1. `lowerCase` transforme la chaîne en minuscules
2. `ucFirst` met la première lettre en majuscule

---

## Paramètres constants

Les transformateurs peuvent accepter des **paramètres constants**, placés entre parenthèses.

### Exemple

```text
{d.price:number(2)}
```

Si un paramètre contient des espaces ou des virgules, il doit être entouré de **guillemets simples**.

---

## Paramètres dynamiques

Les transformateurs peuvent aussi recevoir des **paramètres dynamiques** provenant du JSON.

- Paramètre relatif : commence par `.`
- Paramètre absolu : commence par `d.` ou `c.`

### Exemple

```text
{d.amount:number(.precision)}
```

Voici l'ensemble de données utilisé pour les exemples suivants :
```json
{
  "id" : 10,
  "qtyA" : 20,
  "subObject" : {
    "qtyB" : 5,
    "qtyC" : 3
  },
  "subArray" : [{
    "id" : 1000,
    "qtyE" : 3
  }]
}
```

Effectuez l'opération mathématique d.subObject.qtyB+ d.subObject.qtyC:
```text
{d.subObject.qtyB:add(d.subObject.qtyC)} // 8 (5 + 3)
```

Alternative plus courte, avec un chemin JSON relatif :
```text
{d.subObject.qtyB:add(.qtyC)} // 8 (5 + 3)
```
Plusieurs points peuvent être utilisés pour accéder aux attributs parents via un chemin JSON relatif :

```text
{d.subObject.qtyB:add(..qtyA):add(.qtyC)} // 28 (5 + 20 + 3)
```
Voici le même calcul utilisant un chemin JSON absolu :

```text
{d.subObject.qtyB:add(d.qtyA):add(d.subObject.qtyC)} // 28 (5 + 20 + 3)
```
Lire les objets parents et les attributs de leurs enfants (il n'y a pas de limite de profondeur) :

```text
{d.subArray[0].qtyE:add(..subObject.qtyC)} // 6 (3 + 3)
```
Accéder au premier élément d'une autre table (entiers positifs uniquement) :

```text
{d.subObject.qtyB:add(..subArray[0].qtyE)} // 8 (5 + 3)
```

---

###  Limitations connues :

L'utilisation d'itérateurs personnalisés ou de filtres de tableaux est interdite :
```text
{d.subObject.qtyB:add(..subArray[i].qtyE)} 
{d.subObject.qtyB:add(..subArray[index, something=3].qtyE)} 
{d.subObject.qtyB:add(d.subArray[i].qtyE)} 
{d.subObject.qtyB:add(d.subArray[index].qtyE)} 
```

---

## Ordre d’exécution

Les transformateurs sont exécutés **de gauche à droite**.  

---

## Bonnes pratiques

- Tester chaque transformateurs séparément
- Chaîner les transformateurs progressivement
- Utiliser les paramètres dynamiques lorsque le format dépend des données
- Garder les templates lisibles

---


