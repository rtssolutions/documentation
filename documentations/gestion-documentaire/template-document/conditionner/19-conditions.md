---
title: "19 - Conditions"
description: "Comment ajouter des conditions à vos templates ?"
date: "2025-11-20"
version: "1"
---

# Conditions

Comment ajouter des conditions à vos templates ?

**FONCTIONNALITÉ COMMUNAUTAIRE** — Disponible pour :
- Plateforme Cloud
- Plateforme On-premise
- Plateforme embarquée (JS) — v3.0+

---

## Overview

Il existe 3 méthodes pour écrire des conditions :

- **Conditions inline** : pour imprimer un mot ou une petite phrase en fonction de vos données
- **Blocs conditionnels** : pour masquer ou afficher une partie de votre document, incluant plusieurs tags de la plateforme, des paragraphes, des tableaux
- **Blocs conditionnels intelligents** : méthode simplifiée pour afficher ou masquer une ligne, un tableau, un paragraphe, une image

Chaque condition est précédée d’un formatter qui effectue le test logique (égal, supérieur à, ...). Voici la liste de tous les opérateurs logiques.

Opérateurs logiques :

- `ifEQ (value)` : correspond aux valeurs égales à une valeur spécifiée ; remplace `ifEqual`
- `ifNE (value)` : correspond à toutes les valeurs différentes d’une valeur spécifiée
- `ifGT (value)` : correspond aux valeurs strictement supérieures à une valeur spécifiée
- `ifGTE (value)` : correspond aux valeurs supérieures ou égales à une valeur spécifiée
- `ifLT (value)` : correspond aux valeurs strictement inférieures à une valeur spécifiée
- `ifLTE (value)` : correspond aux valeurs inférieures ou égales à une valeur spécifiée
- `ifIN (value)` : correspond à l’une des valeurs spécifiées dans un tableau ou une chaîne ; remplace `ifContain`
- `ifNIN (value)` : ne correspond à aucune des valeurs spécifiées dans un tableau ou une chaîne
- `ifEM ()` : correspond aux valeurs vides (chaînes, tableaux ou objets) ; remplace `ifEmpty`
- `ifNEM ()` : correspond aux valeurs non vides (chaînes, tableaux ou objets)
- `ifTE (value)` : correspond aux valeurs dont le type est égal à une valeur spécifiée
- `and (value)` : opérateur **AND** entre deux formatters conditionnels consécutifs
- `or (value)` : (par défaut) opérateur **OR** entre deux formatters conditionnels consécutifs

Suivi de l’un de ces formatters :

- `drop (element) / keep (element)` : supprimer ou conserver automatiquement certains éléments si la condition est vraie.
- `hideBegin / hideEnd` : masquer toute partie du document entre `hideBegin` et `hideEnd` si la condition est vraie
- `showBegin / showEnd` : afficher toute partie du document entre `showBegin` et `showEnd` si la condition est vraie
- `show (message)` : afficher un message si une condition est vraie
- `elseShow (message)` : afficher un message si une condition est fausse

Aucun formatter ne peut être chaîné après `drop`, `keep`, `hideBegin`, `hideEnd`, `showBegin`, `showEnd`.

---

## Basic example

### data

```json
{
  "val2" : 2,
  "val5" : 5
}
```

### template

```text
val2 = {d.val2:ifGT(3):show('high')}
val2 = {d.val2:ifGT(3):show('high'):elseShow('low')}
val5 = {d.val5:ifGT(3):show('high')}
```

### result

```text
val2 = 2
val2 = low
val5 = high
```

---

## Chain of conditions

Si une condition est vraie, le résultat **n’est pas** transmis au formatter conditionnel suivant (`ifEQ`, `show`, `elseShow`, etc.). La valeur de `show` ou `elseShow` est transmise directement au formatter suivant **non conditionnel** (`formatN`, `formatD`, etc.).

Pour voir clairement comment cela fonctionne, explorons comment écrire une **condition switch-case**.

---

## Multiple variables

Il est possible de tester plusieurs variables avec les opérateurs logiques `and` et `or` :

### data

```json
{
  "val2" : 2,
  "val5" : 5
}
```

### template

```text
and = {d.val2:ifEQ(1):and(.val5):ifEQ(5):show(OK):elseShow(KO)}
or = {d.val2:ifEQ(1):or(.val5):ifEQ(5):show(OK):elseShow(KO)}
```

### result

```text
and = KO
or = OK
```

Les parenthèses / priorités entre opérateurs logiques sont basées sur la position du formatter. Voici la représentation interne de la condition pour un tag de la plateforme donné :

```text
{d.A:ifEQ(1):and(.B):ifEQ(2):or(.C):ifEQ(3):and(.D):ifEQ(4)}
```

est équivalent à :

```text
(((A = 1) AND (B = 2)) OR (C = 3)) AND (D = 4)
```

---

## :and(value)

v2.0.0+

Changer l’opérateur par défaut entre des formatters conditionnels.

Par exemple :

```text
{d.car:ifEQ('delorean'):and(.speed):ifGT(80):show('TravelInTime'):elseShow('StayHere')}
```

signifie : « si ( (d.car est égal à 'delorean') AND d.speed est supérieur à 80 ), alors afficher 'TravelInTime', sinon afficher 'StayHere' ».

### Params

| Paramètre | Description | Type |
|---|---|---|
| `value` *(optionnel)* | nouvelle valeur à tester | Mixed |

---

## :or(value)

v2.0.0+

`OR` est l’opérateur par défaut entre les formatters conditionnels.

Par exemple :

```text
{d.car:ifEQ('delorean'):or(.speed):ifGT(80):show('TravelInTime'):elseShow('StayHere')}
```

signifie : « si ( (d.car est égal à 'delorean') OR d.speed est supérieur à 80 ), alors afficher 'TravelInTime', sinon afficher 'StayHere' ».

### Params

| Paramètre | Description | Type |
|---|---|---|
| `value` *(optionnel)* | nouvelle valeur à tester | Mixed |

---

## :ifEM

v2.0.0+

Correspond aux valeurs vides (null, undefined, [], {}, ...), pour les chaînes, tableaux ou objets ; remplace `ifEmpty`.

### Examples

```text
null:ifEM():show('Result true'):elseShow('Result false') // "Result true"
[]:ifEM():show('Result true'):elseShow('Result false') // "Result true"
{}:ifEM():show('Result true'):elseShow('Result false') // "Result true"
'':ifEM():show('Result true'):elseShow('Result false') // "Result true"
0:ifEM():show('Result true'):elseShow('Result false') // "Result false"
'homer':ifEM():show('Result true'):elseShow('Result false') // "Result false"
[23]:ifEM():show('Result true'):elseShow('Result false') // "Result false"
{'id':3}:ifEM():show('Result true'):elseShow('Result false') // "Result false"
```

---

## :ifNEM

v2.0.0+

Correspond aux valeurs non vides (chaînes, tableaux ou objets).

### Examples

```text
0:ifNEM():show('Result true'):elseShow('Result false') // "Result true"
'homer':ifNEM():show('Result true'):elseShow('Result false') // "Result true"
[23]:ifNEM():show('Result true'):elseShow('Result false') // "Result true"
{'id':3}:ifNEM():show('Result true'):elseShow('Result false') // "Result true"
null:ifNEM():show('Result true'):elseShow('Result false') // "Result false"
[]:ifNEM():show('Result true'):elseShow('Result false') // "Result false"
{}:ifNEM():show('Result true'):elseShow('Result false') // "Result false"
'':ifNEM():show('Result true'):elseShow('Result false') // "Result false"
```

---

## :ifEQ(value)

v2.0.0+

Correspond à toutes les valeurs égales à une valeur spécifiée. Peut être combiné avec d’autres formatters pour créer du contenu conditionnel. Il retourne le marqueur initial. L’état de la condition n’est pas retourné.

### Params

| Paramètre | Description | Type |
|---|---|---|
| `value` | valeur à tester | String, Integer |

### Examples

```text
100:ifEQ(100):show('Result true'):elseShow('Result false') // "Result true"
100:ifEQ(101):show('Result true'):elseShow('Result false') // "Result false"
'homer':ifEQ('homer'):show('Result true'):elseShow('Result false') // "Result true"
'homer':ifEQ('bart'):show('Result true'):elseShow('Result false') // "Result false"
'':ifEQ(''):show('Result true'):elseShow('Result false') // "Result true"
null:ifEQ(100):show('Result true'):elseShow('Result false') // "Result false"
null:ifEQ(null):show('Result true'):elseShow('Result false') // "Result true"
0:ifEQ(100):show('Result true'):elseShow('Result false') // "Result false"
```

---

## :ifNE(value)

v2.0.0+

Correspond à toutes les valeurs **différentes** d’une valeur spécifiée. Peut être combiné avec d’autres formatters pour créer du contenu conditionnel. Il retourne le marqueur initial. L’état de la condition n’est pas retourné.

### Params

| Paramètre | Description | Type |
|---|---|---|
| `value` | valeur à tester | String, Integer |

### Examples

```text
100:ifNE(100):show('Result true'):elseShow('Result false') // "Result false"
100:ifNE(101):show('Result true'):elseShow('Result false') // "Result true"
'homer':ifNE('homer'):show('Result true'):elseShow('Result false') // "Result false"
'homer':ifNE('bart'):show('Result true'):elseShow('Result false') // "Result true"
'':ifNE(''):show('Result true'):elseShow('Result false') // "Result false"
null:ifNE(100):show('Result true'):elseShow('Result false') // "Result true"
null:ifNE(null):show('Result true'):elseShow('Result false') // "Result false"
0:ifNE(100):show('Result true'):elseShow('Result false') // "Result true"
```

---

## :ifGT(value)

v2.0.0+

Correspond aux valeurs strictement supérieures à une valeur spécifiée.

### Params

| Paramètre | Description | Type |
|---|---|---|
| `value` | valeur à tester | Integer |

### Examples

```text
1234:ifGT(1):show('Result true'):elseShow('Result false') // "Result true"
'50':ifGT('-29'):show('Result true'):elseShow('Result false') // "Result true"
'32q':ifGT('4q2'):show('Result true'):elseShow('Result false') // "Result true"
'1234Hello':ifGT('1'):show('Result true'):elseShow('Result false') // "Result true"
'10':ifGT('8Hello1234'):show('Result true'):elseShow('Result false') // "Result true"
-23:ifGT(19):show('Result true'):elseShow('Result false') // "Result false"
1:ifGT(768):show('Result true'):elseShow('Result false') // "Result false"
0:ifGT(0):show('Result true'):elseShow('Result false') // "Result false"
-2891:ifGT('33Hello'):show('Result true'):elseShow('Result false') // "Result false"
```

---

## :ifGTE(value)

v2.0.0+

Correspond aux valeurs supérieures ou égales à une valeur spécifiée.

### Params

| Paramètre | Description | Type |
|---|---|---|
| `value` | valeur à tester | Integer |

### Examples

```text
50:ifGTE(-29):show('Result true'):elseShow('Result false') // "Result true"
1:ifGTE(1):show('Result true'):elseShow('Result false') // "Result true"
1290:ifGTE(768):show('Result true'):elseShow('Result false') // "Result true"
'1234':ifGTE('1'):show('Result true'):elseShow('Result false') // "Result true"
-23:ifGTE(19):show('Result true'):elseShow('Result false') // "Result false"
1:ifGTE(768):show('Result true'):elseShow('Result false') // "Result false"
'1':ifGTE('1234'):show('Result true'):elseShow('Result false') // "Result false"
```

---

## :ifLT(value)

v2.0.0+

Correspond aux valeurs strictement inférieures à une valeur spécifiée.

### Params

| Paramètre | Description | Type |
|---|---|---|
| `value` | valeur à tester | Integer |

### Examples

```text
-23:ifLT(19):show('Result true'):elseShow('Result false') // "Result true"
1:ifLT(768):show('Result true'):elseShow('Result false') // "Result true"
'1':ifLT('1234'):show('Result true'):elseShow('Result false') // "Result true"
'123dsf':ifLT('103123'):show('Result true'):elseShow('Result false') // "Result true"
-1299283:ifLT('-2891feihuwf'):show('Result true'):elseShow('Result false') // "Result true"
50:ifLT(-29):show('Result true'):elseShow('Result false') // "Result false"
0:ifLT(0):show('Result true'):elseShow('Result false') // "Result false"
1290:ifLT(768):show('Result true'):elseShow('Result false') // "Result false"
'1234':ifLT('1'):show('Result true'):elseShow('Result false') // "Result false"
```

---

## :ifLTE(value)

v2.0.0+

Correspond aux valeurs inférieures ou égales à une valeur spécifiée.

### Params

| Paramètre | Description | Type |
|---|---|---|
| `value` | valeur à tester | Integer |

### Examples

```text
-23:ifLTE(19):show('Result true'):elseShow('Result false') // "Result true"
1:ifLTE(768):show('Result true'):elseShow('Result false') // "Result true"
5:ifLTE(5):show('Result true'):elseShow('Result false') // "Result true"
'1':ifLTE('1234'):show('Result true'):elseShow('Result false') // "Result true"
1290:ifLTE(768):show('Result true'):elseShow('Result false') // "Result false"
'1234':ifLTE('1'):show('Result true'):elseShow('Result false') // "Result false"
```

---

## :ifIN(value)

v2.0.0+

Correspond à l’une des valeurs spécifiées dans un tableau ou une chaîne ; remplace `ifContain`.

### Params

| Paramètre | Description | Type |
|---|---|---|
| `value` | valeur à tester | Integer |

### Examples

```text
'car is broken':ifIN('is'):show('Result true'):elseShow('Result false') // "Result true"
[1,2,'toto']:ifIN(2):show('Result true'):elseShow('Result false') // "Result true"
'car is broken':ifIN('are'):show('Result true'):elseShow('Result false') // "Result false"
[1,2,'toto']:ifIN('titi'):show('Result true'):elseShow('Result false') // "Result false"
```

---

## :ifNIN(value)

v2.0.0+

Ne correspond à aucune des valeurs spécifiées dans un tableau ou une chaîne.

### Params

| Paramètre | Description | Type |
|---|---|---|
| `value` | valeur à tester | Integer |

### Examples

```text
'car is broken':ifNIN('are'):show('Result true'):elseShow('Result false') // "Result true"
[1,2,'toto']:ifNIN('titi'):show('Result true'):elseShow('Result false') // "Result true"
'car is broken':ifNIN('is'):show('Result true'):elseShow('Result false') // "Result false"
[1,2,'toto']:ifNIN(2):show('Result true'):elseShow('Result false') // "Result false"
```

---

## :ifTE(type)

NEW v4.4.0+

Teste le type de la valeur de l’opérande.

### Params

| Paramètre | Description | Type |
|---|---|---|
| `type` | peut être `"string"`, `"number"`, `"integer"`, `"boolean"`, `"binary"`, `"object"`, `"array"` | String |

### Examples

```text
0:ifTE('string'):show('Result true'):elseShow('Result false') // "Result false"
[23]:ifTE('string'):show('Result true'):elseShow('Result false') // "Result false"
{'id':3}:ifTE('string'):show('Result true'):elseShow('Result false') // "Result false"
null:ifTE('string'):show('Result true'):elseShow('Result false') // "Result false"
[]:ifTE('string'):show('Result true'):elseShow('Result false') // "Result false"
{}:ifTE('string'):show('Result true'):elseShow('Result false') // "Result false"
'10':ifTE('string'):show('Result true'):elseShow('Result false') // "Result true"
'homer':ifTE('string'):show('Result true'):elseShow('Result false') // "Result true"
'':ifTE('string'):show('Result true'):elseShow('Result false') // "Result true"
true:ifTE('boolean'):show('Result true'):elseShow('Result false') // "Result true"
false:ifTE('boolean'):show('Result true'):elseShow('Result false') // "Result true"
'0':ifTE('boolean'):show('Result true'):elseShow('Result false') // "Result false"
'false':ifTE('boolean'):show('Result true'):elseShow('Result false') // "Result false"
'0':ifTE('binary'):show('Result true'):elseShow('Result false') // "Result true"
'1':ifTE('binary'):show('Result true'):elseShow('Result false') // "Result true"
false:ifTE('binary'):show('Result true'):elseShow('Result false') // "Result true"
'false':ifTE('binary'):show('Result true'):elseShow('Result false') // "Result true"
10.5:ifTE('number'):show('Result true'):elseShow('Result false') // "Result true"
'10.5':ifTE('number'):show('Result true'):elseShow('Result false') // "Result false"
```

---

## Pour aller plus loin

-> [20 - Conditions en ligne](20-conditions-en-ligne)
