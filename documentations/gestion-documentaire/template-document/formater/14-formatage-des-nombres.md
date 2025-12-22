---
title: "14 - Formatage des nombres"
description: "Liste des fonctions (formatters) pour manipuler et transformer des nombres dans les templates"
date: "2025-11-20"
version: "1"
---

# Formatage des nombres

Liste des fonctions pour manipuler et transformer des nombres JSON.

---

## :formatN(precision)

Formate un nombre selon la **locale**.

L’application du nombre de décimales dépend du type de rapport :

- Pour **ODS/XLSX**, le nombre de décimales doit être formaté via l’éditeur (mise en forme du tableur).
- Pour les autres types de fichiers, le nombre de décimales dépend du paramètre `precision` passé au formatter.

### Paramètres

- `precision` : nombre de décimales (Number)

### Exemples

```text
// With API options: {
//   "lang": "en-us"
// }
'10':formatN() // "10.000"
'1000.456':formatN() // "1,000.456"
```

---

## :round(precision)

Arrondit un nombre.

Identique à `toFixed(2)` mais arrondit correctement, par exemple : `round(1.05, 1) = 1.1`.

### Paramètres

- `precision` : nombre de décimales (Number)

### Exemples

```text
10.05123:round(2) // 10.05
1.05:round(1) // 1.1
```

---

## :add(value)

Additionne deux nombres.

### Paramètres

- `value` : valeur à ajouter (Number)

### Exemples

```text
1000.4:add(2) // 1002.4
'1000.4':add('2') // 1002.4
```

---

## :sub(value)

Soustrait deux nombres.

### Paramètres

- `value` : valeur à soustraire (Number)

### Exemples

```text
1000.4:sub(2) // 998.4
'1000.4':sub('2') // 998.4
```

---

## :mul(value)

Multiplie deux nombres.

### Paramètres

- `value` : valeur par laquelle multiplier (Number)

### Exemples

```text
1000.4:mul(2) // 2000.8
'1000.4':mul('2') // 2000.8
```

---

## :div(value)

Divise deux nombres.

### Paramètres

- `value` : valeur par laquelle diviser (Number)

### Exemples

```text
1000.4:div(2) // 500.2
'1000.4':div('2') // 500.2
```

---

## :mod(value)

Calcule le modulo.

### Paramètres

- `value` : Y (Number)

### Exemples

```text
4:mod(2) // 0
3:mod(2) // 1
```

---

## :abs

Retourne la valeur absolue.

### Exemples

```text
-10:abs() // 10
-10.54:abs() // 10.54
10.54:abs() // 10.54
'-200':abs() // 200
```

---

## :ceil

Arrondit vers l’entier **supérieur** le plus proche.

### Exemples

```text
10.05123:ceil() // 11
1.05:ceil() // 2
-1.05:ceil() // -1
```

---

## :floor

Arrondit vers l’entier **inférieur** le plus proche.

### Exemples

```text
10.05123:floor() // 10
1.05:floor() // 1
-1.05:floor() // -2
```

---
## Pour aller plus loin

-> [15 - Formatage des devises](15-formatage-des-devises)

