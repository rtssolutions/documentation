---
title: "20 - Conditions en ligne"
description: "Conditions utilisées directement dans une ligne de texte"
date: "2025-11-20"
version: "1"
---

# Conditions en ligne

Cette page décrit comment utiliser des **conditions en ligne** dans les templates.

Les conditions en ligne sont utiles lorsque vous souhaitez **imprimer un mot ou une courte phrase** selon vos données, sans utiliser de blocs conditionnels.

---

## :show(text) / :elseShow(text)

Les conditions en ligne utilisent généralement les formatters `show` et `elseShow`.

### Exemple

#### data

```json
{
  "val2" : 2,
  "val5" : 5
}
```

#### template

```text
val2 = {d.val2:ifGT(3):show('high')}
val5 = {d.val5:ifGT(3):show('high')}
val2 = {d.val2:ifGT(3):show('high'):elseShow('low')}
```

#### Document généré

```text
val2 = 2
val5 = high
val2 = low
```

---

## Switch / Case

Les conditions en ligne peuvent être chaînées pour créer un comportement de type **switch / case**.

### data

```json
{
  "val1" : 1,
  "val2" : 2,
  "val3" : 3
}
```

### template

```text
val1 = {d.val1:ifEQ(1):show(A):ifEQ(2):show(B):elseShow(C)}
val2 = {d.val2:ifEQ(1):show(A):ifEQ(2):show(B):elseShow(C)}
val3 = {d.val3:ifEQ(1):show(A):ifEQ(2):show(B):elseShow(C)}
```

### Document généré

```text
val1 = A
val2 = B
val3 = C
```

Lorsqu’une condition est vraie, les suivantes **ne sont pas évaluées**.

---

## Avec des filtres de tableau

Les conditions en ligne peuvent être combinées avec des filtres de tableau.

### data

```text
{d.products:arraySearch(.price, '>', 100):count():ifGT(0):show('Expensive'):elseShow('Cheap')}
```

### template

```text
People
{d[i].name}: {d[i, age > 19].age}
{d[i+1].name}
```

### Document généré

```text
People
John: 20
Eva: 
Bob: 25
Charly: 30
```
---

## :ifEmpty(textIfTrue, continueOnSuccess)

Ce formatter affiche un texte si la valeur est vide.

### Exemple

```text
null:ifEmpty('D'oh!') // "D'oh!"
[]:ifEmpty('D'oh!') // "D'oh!"
{}:ifEmpty('D'oh!') // "D'oh!"
'':ifEmpty('D'oh!') // "D'oh!"
0:ifEmpty('D'oh!') // 0
'homer':ifEmpty('D'oh!') // "homer"
[23]:ifEmpty('D'oh!') // [23]
{'id':3}:ifEmpty('D'oh!') // {"id":3}

```

---

## :ifEqual(value, textIfTrue, continueOnSuccess)

Affiche un texte si la valeur est égale à la valeur attendue.

### Exemple

```text
100:ifEqual(100, 'bingo') // "bingo"
100:ifEqual(101, 'bingo') // 100
'homer':ifEqual('homer', 'bingo') // "bingo"
'homer':ifEqual('bart', 'bingo') // "homer"
'':ifEqual('', 'bingo') // "bingo"
null:ifEqual(100, 'bingo') // null
null:ifEqual(null, 'bingo') // "bingo"
0:ifEqual(100, 'bingo') // 0
```

---

## :ifContain(value, textIfTrue, continueOnSuccess)

Affiche un texte si la valeur contient l’élément spécifié.

### Exemples

```text
'your beautiful eyes':ifContain('beauti', 'bingo') // "bingo"
'your beautiful eyes':ifContain('leg', 'bingo') // "your beautiful eyes"
'your beautiful eyes':ifContain('eyes', 'bingo') // "bingo"
'':ifContain('eyes', 'bingo') // ""
'your beautiful eyes':ifContain('', 'bingo') // "bingo"
[100,120,20]:ifContain(120, 'bingo') // "bingo"
[100,120,20]:ifContain(99, 'bingo') // [100,120,20]
['your','eyes']:ifContain('eyes', 'bingo') // "bingo"
[]:ifContain('eyes', 'bingo') // []
```

---

## Pour aller plus loin

-> [21 - Blocs conditionnels](21-blocs-conditionnels)
