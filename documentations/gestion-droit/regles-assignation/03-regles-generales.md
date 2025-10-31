---
title: "03 - Règles générales"
description: "Les 3 règles fondamentales d'assignation des droits"
date: "2025-10-29"
version: "3.0"
---

# 03 - Règles générales

Cette page présente les **3 règles fondamentales** qui régissent toutes les assignations de droits.

---

## Les 3 règles fondamentales

Ces 3 règles **DOIVENT être respectées simultanément** pour qu'une assignation soit valide.

```
Assignation valide ✅ SI ET SEULEMENT SI :
├── Règle 1 : Parentalité du rôle ✅
├── Règle 2 : Périmètre du sujet ✅
└── Règle 3 : Périmètre du rôle ✅
```

---

### Règle 1 : Parentalité du rôle

**Le rôle DOIT provenir de l'organisation du sujet OU d'une organisation parente.**

| Sujet (org.) | Rôle (org.) | Relation | Résultat | Explication |
|--------------|-------------|----------|----------|-------------|
| Pierre (OI) | Rôle OI | Même org | ✅ | Même organisation |
| Pierre (OI) | Rôle CF | Parent direct | ✅ | CF est parent de OI |
| Sophie (UF-A) | Rôle UF-A | Même org | ✅ | Même organisation |
| Sophie (UF-A) | Rôle OI | Parent direct | ✅ | OI est parent de UF-A |
| Sophie (UF-A) | Rôle CF | Parent éloigné | ✅ | CF est parent éloigné de UF-A |
| Pierre (OI) | Rôle UF-A | Enfant direct | ❌ | Rôle d'organisation enfant interdit |
| Sophie (UF-A) | Rôle UF-B | Organisation sœur | ❌ | Pas de relation hiérarchique |
| Marie (CF) | Rôle OI | Enfant direct | ❌ | Rôle d'organisation enfant interdit |
| Marie (CF) | Rôle UF-A | Enfant éloigné | ❌ | Rôle d'organisation enfant interdit |

**Principe** : On ne peut pas recevoir un rôle d'une organisation "en dessous" de soi.

---

### Règle 2 : Périmètre du sujet

**L'organisation assignée DOIT être l'organisation du sujet OU une organisation enfant.**

| Sujet (org.) | Org. assignée | Relation | Résultat | Explication |
|--------------|---------------|----------|----------|-------------|
| Pierre (OI) | OI | Même org | ✅ | Même organisation |
| Pierre (OI) | UF-A | Enfant direct | ✅ | UF-A est enfant de OI |
| Pierre (OI) | UF-B | Enfant direct | ✅ | UF-B est enfant de OI |
| Marie (CF) | CF | Même org | ✅ | Même organisation |
| Marie (CF) | OI | Enfant direct | ✅ | OI est enfant de CF |
| Marie (CF) | UF-A | Enfant éloigné | ✅ | UF-A est enfant éloigné de CF |
| Pierre (OI) | CF | Parent direct | ❌ | Hors périmètre (organisation parente) |
| Sophie (UF-A) | OI | Parent direct | ❌ | Hors périmètre (organisation parente) |
| Sophie (UF-A) | CF | Parent éloigné | ❌ | Hors périmètre (organisation parente) |
| Sophie (UF-A) | UF-B | Organisation sœur | ❌ | Hors périmètre (pas d'enfant) |

**Principe** : On ne peut recevoir des rôles que sur son organisation ou ses enfants.

---

### Règle 3 : Périmètre du rôle

**L'organisation assignée DOIT appartenir au périmètre du rôle (organisation du rôle OU enfants).**

| Rôle (org.) | Org. assignée | Relation | Résultat | Explication |
|-------------|---------------|----------|----------|-------------|
| Rôle OI | OI | Même org | ✅ | Même organisation |
| Rôle OI | UF-A | Enfant direct | ✅ | UF-A est enfant de OI |
| Rôle OI | UF-B | Enfant direct | ✅ | UF-B est enfant de OI |
| Rôle CF | CF | Même org | ✅ | Même organisation |
| Rôle CF | OI | Enfant direct | ✅ | OI est enfant de CF |
| Rôle CF | UF-A | Enfant éloigné | ✅ | UF-A est enfant éloigné de CF |
| Rôle OI | CF | Parent direct | ❌ | Hors périmètre du rôle |
| Rôle UF-A | OI | Parent direct | ❌ | Hors périmètre du rôle |
| Rôle UF-A | CF | Parent éloigné | ❌ | Hors périmètre du rôle |
| Rôle UF-A | UF-B | Organisation sœur | ❌ | Hors périmètre du rôle |

**Principe** : Un rôle ne peut être appliqué que sur son organisation ou ses enfants.

---

## Validation complète

**Exemple valide** : Pierre (OI) reçoit Rôle CF sur OI

| Règle | Vérification | Résultat |
|-------|--------------|----------|
| **Règle 1** | Rôle CF vs Sujet OI → CF parent de OI | ✅ |
| **Règle 2** | Org OI vs Sujet OI → Même org | ✅ |
| **Règle 3** | Org OI vs Rôle CF → OI enfant de CF | ✅ |
| **RÉSULTAT** | Toutes les règles respectées | **✅ VALIDE** |

**Exemple invalide** : Pierre (OI) reçoit Rôle UF-A sur UF-A

| Règle | Vérification | Résultat |
|-------|--------------|----------|
| **Règle 1** | Rôle UF-A vs Sujet OI → UF-A enfant de OI | ❌ |
| **RÉSULTAT** | Règle 1 non respectée | **❌ INVALIDE** |

---

## Règles transversales

En plus des 3 règles fondamentales, des règles spécifiques s'appliquent :

- **T1 - Rôles système non assignables** → Voir [04 - Assignation de rôle](04-assignation-role#types-de-rôle)
- **T2 - Groupes non modifiables** → Voir [05 - Assignation de groupe](05-assignation-groupe#types-de-groupe)
- **T3 - Interdiction d'auto-assignation** → Voir [06 - Assignation utilisateur](06-assignation-utilisateur#utilisateur--groupe)
- **T4 - Machines système non modifiables** → Voir [07 - Assignation machine](07-assignation-machine#types-de-machine)

---

## Glossaire rapide

| Terme | Définition |
|-------|------------|
| **Parent direct** | Organisation immédiatement au-dessus (ex: OI est parent direct de UF-A) |
| **Parent éloigné** | Organisation plus haut dans la hiérarchie (ex: CF est parent éloigné de UF-A) |
| **Enfant direct** | Organisation immédiatement en-dessous (ex: UF-A est enfant direct de OI) |
| **Enfant éloigné** | Organisation plus bas dans la hiérarchie (ex: UF-A est enfant éloigné de CF) |
| **Organisation sœur** | Organisation avec le même parent direct (ex: UF-A et UF-B) |
| **Périmètre** | Organisation + tous ses enfants (directs et éloignés) |

---

## Navigation

- [02 - Organisation](02-organisation)
- [04 - Assignation de rôle](04-assignation-role)

[Retour à la gestion des droits](../index)
