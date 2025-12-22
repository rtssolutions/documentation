---
title: "03 - Les bases des substitutions"
description: "Comprendre comment utiliser les substitutions (balises) simples dans les templates de document"
date: "2025-11-20"
version: "1"
---

# Les bases des substitutions

## Objectif

Cette page décrit les **principes essentiels de substitution** dans un template de document utilisé avec la plateforme :  
comment écrire des balises simples pour **insérer des données JSON** à l’endroit voulu dans votre template.

Les balises permettent de faire correspondre les données de l'application avec le contenu du document final.

---

## Qu’est‑ce qu’une balise de substitution ?

Une **balise de substitution** est une instruction dans votre template indiquant à la plateforme **où et comment afficher les données** fournies via JSON.

Les balises sont écrites entre **accolades `{}`** et suivent une syntaxe spécifique comme `{d.…}`.

Lors de la génération du document, la plateforme **remplace** chaque balise par la donnée correspondante.

---

## Exemple simple

**Données JSON**

```json
{
  "firstname": "John",
  "lastname": "Doe"
}
```

**Template**

```
Hello {d.firstname} {d.lastname} !
```

**Document généré**

```
Hello John Doe !
```

---

## Accéder à des objets imbriqués

La plateforme permet d’accéder à des **objets imbriqués** à l’aide de la **notation pointée**.

**Données JSON**

```json
{
  "firstname": "John",
  "type": {
    "id": 1,
    "name": "human"
  }
}
```

**Template**

```
{d.firstname} est un {d.type.name}
```

---

## Accéder aux éléments d’un tableau

Les tableaux sont **indexés à partir de 0**.

**Données JSON**

```json
[
  { "movie": "Inception" },
  { "movie": "Matrix" },
  { "movie": "Back to the future" }
]
```

**Template**

```
Les films préférés sont {d[i=1].movie} et {d[2].movie}
```

---

## Bonnes pratiques

- Comprendre la structure JSON avant de créer le template
- Tester avec des données simples
- Construire progressivement des templates plus complexes

---

## Pour aller plus loin

→ Alias et raccourcis  
→ Recherche dans les tableaux  
→ Filtres et conditions
