---
title: "Assignation de rôle"
description: "Types de rôles et règles d'assignation"
date: "2025-10-29"
version: "3.0"
---

# Assignation de rôle

Un **rôle** définit un ensemble de **permissions** applicables sur une **organisation** et ses **enfants**.

---

## Types de rôle

### Rôle système (administré par Papaours)

**Exemple** : `Administrateur Papaours`

**Restrictions** :
- ❌ Non modifiable
- ❌ Non assignable manuellement
- ❌ Non supprimable
- ✅ Géré uniquement par Papaours

---

### Rôle CFA (créé par le centre)

**Exemples** : `Directeur CFA`, `Responsable Pédagogique`, `Formateur`

**Permissions** :
- ✅ Modifiable
- ✅ Assignable
- ✅ Supprimable
- ✅ Permissions configurables

---

## Propriétés d'un rôle

### Organisation responsable et périmètre

L'**organisation responsable** détermine le **périmètre** du rôle.

**Calcul du périmètre** :
```
Périmètre = Organisation responsable + Tous les enfants (directs et éloignés)
```

**Exemples** :

| Rôle (org. resp.) | Périmètre | Peut être appliqué sur |
|-------------------|-----------|------------------------|
| Directeur CF (CF) | CF, OI, UF-A, UF-B, UF-D | Toutes les organisations |
| Responsable Pédago OI (OI) | OI, UF-A, UF-B | OI et ses enfants uniquement |
| Formateur UF-A (UF-A) | UF-A | UF-A uniquement |

---

## Assignation Sujet → Rôle

Les **3 règles fondamentales** s'appliquent (voir [Règles générales](03-regles-generales.md)).

### Matrice de validation rapide

| Sujet (org.) | Rôle CF | Rôle OI | Rôle UF-A |
|--------------|---------|---------|-----------|
| **Marie (CF)** | ✅ | ❌ | ❌ |
| **Pierre (OI)** | ✅ | ✅ | ❌ |
| **Sophie (UF-A)** | ✅ | ✅ | ✅ |

---

## Exemples concrets

### Exemple 1 : Rôle CF assigné à Pierre (OI)

**Contexte** : Pierre (OI) reçoit le rôle "Directeur CF"

**Organisations assignées possibles** : OI, UF-A, UF-B
**Organisations impossibles** : CF, UF-D

**Cas concret** :
```
Pierre (OI) → Rôle "Directeur CF" sur OI ✅
├─ Règle 1 : CF parent de OI ✅
├─ Règle 2 : OI = org de Pierre ✅
└─ Règle 3 : OI enfant de CF ✅

Pierre (OI) → Rôle "Directeur CF" sur CF ❌
├─ Règle 1 : CF parent de OI ✅
├─ Règle 2 : CF parent de OI ❌ (hors périmètre)
└─ INVALIDE
```

---

### Exemple 2 : Rôle OI assigné à Sophie (UF-A)

**Contexte** : Sophie (UF-A) reçoit le rôle "Responsable Pédagogique OI"

**Organisations assignées possibles** : UF-A uniquement
**Organisations impossibles** : CF, OI, UF-B, UF-D

**Cas concret** :
```
Sophie (UF-A) → Rôle "Responsable Pédago OI" sur UF-A ✅
├─ Règle 1 : OI parent de UF-A ✅
├─ Règle 2 : UF-A = org de Sophie ✅
└─ Règle 3 : UF-A enfant de OI ✅

Sophie (UF-A) → Rôle "Responsable Pédago OI" sur OI ❌
├─ Règle 1 : OI parent de UF-A ✅
├─ Règle 2 : OI parent de UF-A ❌ (hors périmètre)
└─ INVALIDE
```

---

### Exemple 3 : Rôle enfant refusé

**Contexte** : Pierre (OI) tente de recevoir le rôle "Formateur UF-A"

**Résultat** : ❌ INVALIDE

**Raison** :
```
Pierre (OI) → Rôle "Formateur UF-A" sur UF-A ❌
├─ Règle 1 : UF-A enfant de OI ❌ (rôle enfant interdit)
└─ INVALIDE (les autres règles ne sont pas vérifiées)
```

---

## Cas limites

### Rôle système non assignable

**Exemple** : `Administrateur Papaours`

| Sujet | Organisation | Résultat | Raison |
|-------|--------------|----------|--------|
| Marie (CF) | CF | ❌ | Règle T1 : Rôle système |
| Pierre (OI) | OI | ❌ | Règle T1 : Rôle système |

---

### Organisation sœur

**Exemple** : Pierre (OI) reçoit le rôle "Formateur UF-D" sur UF-D

| Règle | Vérification | Résultat |
|-------|--------------|----------|
| Règle 1 | UF-D et OI sont sœurs → ❌ | ❌ |

**Explication** : Pas de lien de parentalité entre organisations sœurs.

---

## Tableau récapitulatif

### Organisations assignées possibles par persona

| Persona | Rôle CF | Rôle OI | Rôle UF-A |
|---------|---------|---------|-----------|
| Marie (CF) | CF, OI, UF-A, UF-B, UF-D | - | - |
| Pierre (OI) | OI, UF-A, UF-B | OI, UF-A, UF-B | - |
| Sophie (UF-A) | UF-A | UF-A | UF-A |
| Lucas (UF-B) | UF-B | UF-B | - |
| Emma (UF-D) | UF-D | - | - |

---

## Navigation

- [← Règles générales](03-regles-generales.md)
- [← Retour à l'index](index.md)
- [Assignation de groupe →](05-assignation-groupe.md)

[Retour à la gestion des droits](../index.md)
