---
title: "22 - Conditions intelligentes"
description: "Afficher ou supprimer des éléments selon une condition avec une syntaxe simplifiée"
date: "2025-11-20"
version: "1"
---

# Conditions intelligentes

Cette page décrit les **blocs conditionnels intelligents** qui permettent de montrer ou masquer un élément entier (ligne de tableau, paragraphe, image, …) avec une seule balise simple.

---

## Pourquoi utiliser les conditions intelligentes ?

Pourquoi utiliser des blocs conditionnels intelligents plutôt que `hideBegin/hideEnd`, `showBegin/showEnd` ou des filtres de tableau ?

- Syntaxe plus courte : une seule balise au lieu de deux (Begin + End)
- Plus simple à utiliser : utile quand il est difficile de placer `hideBegin/hideEnd`, par exemple pour masquer une ligne de tableau
- Sortie plus propre : l’élément ciblé est supprimé **sans laisser d’espace vide**

Compatible avec les documents **DOCX, ODT, ODS, ODP, PDF, XLSX et HTML**.

Une balise utilisant `:drop` ou `:keep` ne produit rien dans le document généré. La balise est supprimée lors de l’exécution.

---

## :drop / :keep(element)

Utiliser le formatter `:drop` pour **supprimer des éléments** du document si la condition est vraie.  
Le formatter `:keep` fonctionne à l’inverse : il **conserve l’élément** si la condition est vraie.

| Élément | Description | Position |
|---|---|---|
| `row` | Ligne de tableau | Dans une ligne |
| `p` | Paragraphe | Dans un paragraphe |
| `img` | Image | Titre, description ou alt |
| `table` | Table | Dans une cellule |
| `chart` | Graphique | Texte alternatif |
| `shape` | Forme | Titre, description ou alt |
| `slide` | Diapositive | Zone de texte (ODP) |
| `item` | Élément de liste | Item de liste |
| `sheet` | Feuille | Cellule (ODS) |

Une **seconde valeur** peut être utilisée avec `p` et `row` pour supprimer ou conserver les **N éléments suivants**.

Exemples :
- `{d.text:ifEM:drop(p, 3)}`
- `{d.text:ifEM:drop(row, 3)}`

---

### Limitations connues

- ODS : supporte uniquement `row` et `img`
- HTML : supporte uniquement `table`, `row` et `p`
- XLSX : supporte uniquement `row`

---

## Exemples

### Supprimer des lignes contenant “Falcon”

#### data

```json
[
  { "name": "Falcon 9" },
  { "name": "Model S" },
  { "name": "Model 3" },
  { "name": "Falcon Heavy" }
]
```

#### template

```text
Planes{d[i].name}
{d[i].name:ifIN('Falcon'):drop(row)}{d[i+1].name}
```

#### Document généré

```text
Planes
Model S
Model 3
```

---

### Supprimer une table entière

#### data

```json
[
  { "name": "Bob" }
]
```

#### template

```text
Planes{d[i].name}
{d[i].name:ifIN('Falcon'):drop(table)}
```

#### Document généré

```text
Planes
```

---


