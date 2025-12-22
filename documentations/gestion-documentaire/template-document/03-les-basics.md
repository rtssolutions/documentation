---
title: "03 - Les bases des substitutions"
description: "Utiliser les balises de substitution simples pour insérer des données dans les templates"
date: "2025-11-20"
version: "1"
---

# Les bases des substitutions

## Objectif

Cette page présente comment utiliser une **balise de substitution simple** dans un template de document avec la plateforme.  
Les balises `{d.…}` font référence aux données JSON qui seront injectées lors de la génération du document.

---

## Balises simples

Une balise de substitution est écrite entre **accolades `{}`** et commence par `d.` pour indiquer que la donnée vient du JSON fourni par l’application.

### Données JSON

```json
{
  "firstname": "John",
  "lastname": "Doe"
}
```

### Template

```text
Hello {d.firstname} {d.lastname} !
```

### Document généré

```text
Hello John Doe !
```

---

## Accéder aux sous-objets

Lorsque vos données JSON contiennent des objets imbriqués, vous pouvez utiliser la **notation pointée (`.`)** pour accéder aux propriétés internes.

### Données JSON

```json
{
  "firstname": "John",
  "type": {
    "id": 1,
    "name": "human"
  }
}
```

### Template

```text
{d.firstname} est un {d.type.name}
```

### Document généré

```text
John est un human
```

---

## Accéder aux tableaux

Si vos données JSON contiennent un **tableau**, vous pouvez accéder à un élément précis grâce à un **indice**.  
Les tableaux sont indexés à partir de **0**.

### Données JSON

```json
[
  { "movie": "Inception" },
  { "movie": "Matrix" },
  { "movie": "Back to the future" }
]
```

### Template

```text
Les films préférés sont {d[i=1].movie} et {d[2].movie}
```

### Document généré

```text
Les films préférés sont Matrix et Back to the future
```

---

## Accéder aux propriétés du parent

Il est possible d’accéder aux **propriétés d’un objet parent** en utilisant **deux points (`..`) ou plus**.

### Données JSON

```json
{
  "country": "France",
  "movie": {
    "name": "Inception",
    "sub": {
      "a": "test"
    }
  }
}
```

### Template

```text
{d.movie.sub..name}{d.movie.sub...country}
```

### Document généré

```text
Inception France
```

---

## Résumé

- `{d.…}` permet d’injecter une donnée JSON
- La notation `.` permet d’accéder aux objets imbriqués
- Les indices `[i]` permettent d’accéder aux tableaux
- Les double points `..` permettent de remonter au parent

## Pour aller plus loin

-> [04 - Recherche dans un tableau](04-recherche-tableau)
