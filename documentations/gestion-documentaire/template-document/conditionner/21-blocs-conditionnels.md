---
title: "21 - Blocs conditionnels"
description: "Afficher ou masquer des parties d’un document selon une condition"
date: "2025-11-20"
version: "1"
---

# Blocs conditionnels

Cette page explique comment **afficher ou masquer une partie d’un document** selon une condition dans un template de la plateforme.


---

## :showBegin / :showEnd

Afficher un bloc de texte entre `showBegin` et `showEnd` **si une condition est vraie**.

Il est recommandé d’utiliser uniquement des **sauts de ligne (Shift + Entrée)** entre `showBegin` et `showEnd`.

> **NOUVEAU**  
> Utiliser les formatters `drop / keep` si vous souhaitez masquer un paragraphe, une ligne de tableau, une image, un graphique ou une forme.

### Exemple

#### data

```json
{
  "toBuy": true
}
```

#### template

```text
Banana{d.toBuy:ifEQ(true):showBegin}
Apple
Pineapple
{d.toBuy:showEnd}
Grapes
```

#### Document généré

```text
Banana
Apple
Pineapple
Grapes
```

---

## :hideBegin / :hideEnd

Masquer un bloc de texte entre `hideBegin` et `hideEnd` **si une condition est vraie**.

Il est recommandé d’utiliser uniquement des **sauts de ligne (Shift + Entrée)** entre `hideBegin` et `hideEnd`.

> **NOUVEAU**  
> Utiliser les formatters `drop / keep` si vous souhaitez supprimer un paragraphe, une ligne de tableau, une image, un graphique ou une forme.

### Exemple

#### data

```json
{
  "toBuy": true
}
```

#### template

```text
Banana{d.toBuy:ifEQ(true):hideBegin}
Apple
Pineapple
{d.toBuy:hideEnd}
Grapes
```

#### Document généré

```text
Banana
Grapes
```

---

## Bonnes pratiques

- Pour **supprimer complètement** des éléments structurés (lignes de tableau, images, graphiques, formes), préférer les formatters **`drop / keep`**
- Réserver `showBegin / showEnd` et `hideBegin / hideEnd` aux contenus textuels
- Toujours utiliser des sauts de ligne simples entre les balises de bloc conditionnel

---

## Pour aller plus loin

-> [22 - Conditions intelligentes](22-blocs-conditions-intelligentes)