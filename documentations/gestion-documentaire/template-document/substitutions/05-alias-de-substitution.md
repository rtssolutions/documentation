---
title: "05 - Alias de substitution"
description: "Utiliser des alias pour simplifier et factoriser les balises de substitution dans les templates"
date: "2025-11-20"
version: "1"
---

# Alias de substitution

## Objectif

Cette page décrit l’utilisation des **alias** dans les templates de document avec la plateforme.
Les alias permettent de **simplifier l’écriture des balises**, d’améliorer la lisibilité des templates et d’éviter la répétition de chemins complexes.

---

## Définition d’un alias

Un alias est défini à l’aide de la syntaxe suivante :

```text
{#alias = expression}
```

- `alias` est le nom de l’alias
- `expression` correspond à une balise ou à une partie de balise

Pour utiliser un alias, on emploie la syntaxe :

```text
{$alias}
```

Les alias peuvent être définis **n’importe où dans le document**.
Ils sont supprimés du document final lors de la génération.

---

## Exemple simple

### Données (JSON)

```json
{
  "name": "Cars",
  "wheels": 4
}
```

### Template

```text
{#myAlias = d.wheels}
{d.name} need {$myAlias} wheels!
```

### Document généré

```text
Cars need 4 wheels!
```

Dans cet exemple :
- `{#myAlias = d.wheels}` définit un alias nommé `myAlias`
- `{$myAlias}` est remplacé par la valeur de `d.wheels`

> Un alias **ne stocke pas de valeur** : il agit uniquement comme un raccourci textuel.

---

## Alias avec paramètres

Un alias peut accepter **un nombre illimité de paramètres**.
Les paramètres sont définis entre parenthèses et doivent commencer par `$`.

### Exemple

### Données (JSON)

```json
[
  { "name": "chicken", "weekday": 1 },
  { "name": "fish", "weekday": 2 }
]
```

### Template

```text
{#mealOf($weekday) = d[weekday = $weekday]}
Tuesday, we eat {$mealOf(2).name}.
```

### Document généré

```text
Tuesday, we eat fish.
```

Dans cet exemple :
- L’alias `mealOf` prend un paramètre `$weekday`
- Il permet de retrouver dynamiquement un élément du tableau

---

## Limitations des alias

- Les alias ne permettent pas de stocker des valeurs intermédiaires
- Ils ne remplacent pas les formatters de type `set`
- Certains cas complexes peuvent ne pas être supportés (boucles, chemins dynamiques)

Les alias doivent être considérés comme un **préprocesseur**, comparable à un `#define`.

---

## Bonnes pratiques

- Utiliser des alias pour les chemins longs ou répétés
- Donner des noms d’alias explicites
- Éviter les alias trop complexes
- Préférer la préparation des données côté application

---

## Pour aller plus loin

-> [06 - Répétitions avec des tableaux](06-repetitions-with-arrays)