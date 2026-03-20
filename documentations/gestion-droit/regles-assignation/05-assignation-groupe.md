---
title: "05 - Assignation de groupe"
description: "Types de groupes et règles d'assignation"
date: "2025-10-29"
version: "3.0"
---

# 05 - Assignation de groupe

Un **groupe** est un ensemble d'**utilisateurs** et/ou de **machines** partageant les mêmes **rôles**.

**Avantage** : Gestion centralisée des permissions (modifier le groupe affecte tous les membres).

---

## Types de groupe

### Groupe système (administré par Papaours)

**Exemple** : `Administrateur Papaours`

**Restrictions** :
- ❌ Nom non modifiable
- ❌ Rôles non modifiables
- ❌ Membres non modifiables
- ✅ Géré uniquement par Papaours

---

### Groupe Papaours (partiellement modifiable)

**Exemple** : `Administrateur Centre de Formation`

**Restrictions** :
- ❌ Nom non modifiable
- ❌ Rôles non modifiables
- ✅ Membres modifiables par le CFA

---

### Groupe CFA (totalement modifiable)

**Exemples** : `Équipe Pédagogique OI`, `Formateurs UF-A`

**Permissions** :
- ✅ Nom modifiable
- ✅ Rôles modifiables
- ✅ Membres modifiables
- ✅ Supprimable

---

## Groupe → Rôle

Les **3 règles fondamentales** s'appliquent au **groupe** (et non aux membres individuels).

**Important** : Tous les rôles du groupe doivent être valides pour le groupe lui-même.

### Exemple : Groupe OI avec rôles

**Groupe** : Équipe Pédagogique OI (org. responsable : OI)

| Rôle (org. resp.) | Org. assignée | Règle 1 | Règle 2 | Règle 3 | Résultat |
|-------------------|---------------|---------|---------|---------|----------|
| Rôle CF | OI | ✅ | ✅ | ✅ | ✅ |
| Rôle OI | OI | ✅ | ✅ | ✅ | ✅ |
| Rôle OI | UF-A | ✅ | ✅ | ✅ | ✅ |
| Rôle UF-A | UF-A | ❌ | ✅ | ✅ | ❌ |

---

## Groupe → Membres

### Héritage automatique

Lorsqu'un membre est ajouté au groupe, il **hérite de TOUS les rôles** du groupe.

**Validation** : Chaque rôle du groupe doit être valide pour chaque membre.

```
Pour chaque rôle du groupe:
  Pour chaque membre:
    └─ Les 3 règles doivent être respectées
```

---

### Exemple : Ajout de Pierre au groupe

**Groupe** : Équipe Pédagogique OI (org. resp : OI)
**Rôles du groupe** :
- Responsable Pédagogique OI sur OI
- Formateur OI sur UF-A

**Membre** : Pierre (org. resp : OI)

**Validation** :

| Rôle | Org. assignée | Règle 1 | Règle 2 | Règle 3 | Résultat |
|------|---------------|---------|---------|---------|----------|
| Responsable Pédago OI | OI | ✅ | ✅ | ✅ | ✅ |
| Formateur OI | UF-A | ✅ | ✅ | ✅ | ✅ |

**Résultat** : Pierre peut être ajouté ✅

---

### Exemple : Ajout de Marie refusé

**Groupe** : Équipe Pédagogique OI (org. resp : OI)
**Rôles du groupe** : Responsable Pédagogique OI sur OI

**Membre** : Marie (org. resp : CF)

**Validation** :

| Rôle | Org. assignée | Règle 1 | Règle 2 | Résultat |
|------|---------------|---------|---------|----------|
| Responsable Pédago OI | OI | ❌ | ❌ | ❌ |

**Explication** :
- Règle 1 : OI est enfant de CF ❌
- Règle 2 : OI n'est pas dans le périmètre de Marie ❌

**Résultat** : Marie ne peut PAS être ajoutée ❌

---

## Restrictions spécifiques

### Règle T2 : Groupes non modifiables

| Type de groupe | Modifier nom | Modifier rôles | Modifier membres |
|----------------|--------------|----------------|------------------|
| Groupe système | ❌ | ❌ | ❌ |
| Groupe Papaours | ❌ | ❌ | ✅ |
| Groupe CFA | ✅ | ✅ | ✅ |

---

### Règle T3 : Interdiction d'auto-assignation

Un utilisateur **NE PEUT PAS** :
- S'ajouter lui-même à un groupe
- Se retirer lui-même d'un groupe
- Modifier les rôles d'un groupe auquel il appartient

**Exemples** :

| Utilisateur | Action | Résultat |
|-------------|--------|----------|
| Pierre | S'ajouter au groupe "Direction" | ❌ |
| Pierre | Ajouter Sophie au groupe "Direction" | ✅ |
| Pierre (membre) | Modifier rôles du groupe | ❌ |
| Pierre (non-membre) | Modifier rôles du groupe | ✅ |

---

## Exemple complet : Groupe Papaours

**Groupe** : Administrateur Centre de Formation
**Type** : Groupe Papaours
**Organisation responsable** : CF

### Restrictions

| Action | Autorisé ? |
|--------|-----------|
| Modifier le nom | ❌ |
| Modifier les rôles | ❌ |
| Ajouter un utilisateur | ✅ |
| Supprimer le groupe | ❌ |

### Rôles du groupe

| Rôle | Org. assignée | Modifiable ? |
|------|---------------|--------------|
| Administrateur du centre de formation | CF | ❌ |

### Membres possibles

| Utilisateur | Peut être ajouté ? | Raison |
|-------------|-------------------|--------|
| Marie (CF) | ✅ | Toutes les règles respectées |
| Pierre (OI) | ❌ | Règle 2 : ne peut recevoir rôle sur CF |
| Sophie (UF-A) | ❌ | Règle 2 : ne peut recevoir rôle sur CF |

---

## Navigation

- [04 - Assignation de rôle](04-assignation-role)
- [06 - Assignation utilisateur](06-assignation-utilisateur)

[Retour à la gestion des droits](../index)
