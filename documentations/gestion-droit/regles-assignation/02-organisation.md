---
title: "02 - Organisation"
description: "Présentation détaillée de la hiérarchie d'organisations utilisée dans tous les exemples"
date: "2025-10-29"
version: "2.0"
---

# 02 - Organisation

Cette page présente en détail la hiérarchie d'organisations utilisée comme référence dans tous les exemples de cette documentation.

---

## 📚 Table des matières

1. [Vue d'ensemble](#vue-densemble)
2. [Structure détaillée](#structure-détaillée)
3. [Relations hiérarchiques](#relations-hiérarchiques)
4. [Périmètres d'action](#périmètres-daction)
5. [Cas particuliers](#cas-particuliers)
6. [Personas utilisés](#personas-utilisés)

---

## Vue d'ensemble

### Schéma hiérarchique

```
Centre Formation (CF)
├── Org. Intermédiaire (OI)
│   ├── UF Enfant A (UF-A)
│   └── UF Enfant B (UF-B)
└── UF Direct (UF-D)
```

### Légende des abréviations

| Nom complet              | Abréviation | Niveau        |
|--------------------------|-------------|---------------|
| Centre Formation         | CF          | Racine        |
| Organisation Intermédiaire | OI        | Intermédiaire |
| UF Enfant A              | UF-A        | Feuille       |
| UF Enfant B              | UF-B        | Feuille       |
| UF Direct                | UF-D        | Feuille       |

---

## Structure détaillée

### Centre Formation (CF)

**Rôle** : Organisation racine, représente le centre de formation dans son ensemble.

**Position hiérarchique** :
- **Parent** : Aucun (racine)
- **Enfants directs** : Org. Intermédiaire (OI), UF Direct (UF-D)
- **Tous les enfants** : OI, UF-A (enfant éloigné), UF-B (enfant éloigné), UF-D

**Caractéristiques** :
- Niveau hiérarchique : 0 (racine)
- Visibilité : Toutes les organisations
- Responsabilité : Gestion globale du centre

**Exemple concret** : "Centre de Formation Professionnel Lyon"

---

### Organisation Intermédiaire (OI)

**Rôle** : Niveau intermédiaire, représente un département, un service ou un pôle de formation.

**Position hiérarchique** :
- **Parent direct** : Centre Formation (CF)
- **Enfants directs** : UF Enfant A (UF-A), UF Enfant B (UF-B)
- **Tous les enfants** : UF-A, UF-B
- **Tous les parents** : CF

**Caractéristiques** :
- Niveau hiérarchique : 1
- Visibilité : OI, UF-A, UF-B
- Responsabilité : Gestion d'un département ou pôle

**Exemple concret** : "Département Informatique"

---

### UF Enfant A (UF-A)

**Rôle** : Unité de Formation opérationnelle, représente une classe, un groupe ou une formation spécifique.

**Position hiérarchique** :
- **Parent direct** : Organisation Intermédiaire (OI)
- **Enfants directs** : Aucun (feuille)
- **Tous les enfants** : Aucun
- **Tous les parents** : OI (parent direct), CF (parent éloigné)

**Caractéristiques** :
- Niveau hiérarchique : 2
- Visibilité : UF-A uniquement
- Responsabilité : Gestion d'une formation/classe

**Exemple concret** : "Formation Développeur Web - Promotion 2025A"

---

### UF Enfant B (UF-B)

**Rôle** : Unité de Formation opérationnelle, sœur de UF-A.

**Position hiérarchique** :
- **Parent direct** : Organisation Intermédiaire (OI)
- **Enfants directs** : Aucun (feuille)
- **Tous les enfants** : Aucun
- **Tous les parents** : OI (parent direct), CF (parent éloigné)

**Caractéristiques** :
- Niveau hiérarchique : 2
- Visibilité : UF-B uniquement
- Responsabilité : Gestion d'une formation/classe

**Exemple concret** : "Formation Développeur Web - Promotion 2025B"

**⚠️ Relation avec UF-A** : UF-A et UF-B sont des organisations **sœurs** (même parent), elles n'ont aucune relation de parentalité entre elles.

---

### UF Direct (UF-D)

**Rôle** : Unité de Formation rattachée directement au Centre de Formation, sans organisation intermédiaire.

**Position hiérarchique** :
- **Parent direct** : Centre Formation (CF)
- **Enfants directs** : Aucun (feuille)
- **Tous les enfants** : Aucun
- **Tous les parents** : CF

**Caractéristiques** :
- Niveau hiérarchique : 1
- Visibilité : UF-D uniquement
- Responsabilité : Gestion d'une formation/classe

**Exemple concret** : "Formation Continue Management - Session 2025"

**⚠️ Cas particulier** : UF Direct est au **même niveau hiérarchique** que Organisation Intermédiaire. Elle n'est pas une sœur de UF-A et UF-B.

---

## Relations hiérarchiques

### Tableau récapitulatif des relations

| Organisation | Parent | Enfants directs | Tous les parents | Tous les enfants |
|--------------|--------|-----------------|-------------------|----------------------|
| **CF**       | -      | OI, UF-D        | -                 | OI, UF-A, UF-B, UF-D |
| **OI**       | CF     | UF-A, UF-B      | CF                | UF-A, UF-B           |
| **UF-A**     | OI     | -               | OI, CF            | -                    |
| **UF-B**     | OI     | -               | OI, CF            | -                    |
| **UF-D**     | CF     | -               | CF                | -                    |

---

### Relations détaillées par organisation

#### Centre Formation (CF)

```
CF
├─ Enfants directs:
│  ├─ Org. Intermédiaire (OI)
│  └─ UF Direct (UF-D)
│
├─ Enfants éloignés:
│  ├─ UF Enfant A (UF-A)
│  └─ UF Enfant B (UF-B)
│
└─ Tous les enfants: OI, UF-D, UF-A, UF-B
```

#### Organisation Intermédiaire (OI)

```
OI
├─ Parent direct: Centre Formation (CF)
│
├─ Enfants directs:
│  ├─ UF Enfant A (UF-A)
│  └─ UF Enfant B (UF-B)
│
├─ Organisations sœurs: UF Direct (UF-D)
│
└─ Tous les parents: CF
```

#### UF Enfant A (UF-A)

```
UF-A
├─ Parent direct: Org. Intermédiaire (OI)
│
├─ Parent éloigné: Centre Formation (CF)
│
├─ Organisation sœur: UF Enfant B (UF-B)
│
└─ Tous les parents: OI (parent direct), CF (parent éloigné)
```

#### UF Enfant B (UF-B)

```
UF-B
├─ Parent direct: Org. Intermédiaire (OI)
│
├─ Parent éloigné: Centre Formation (CF)
│
├─ Organisation sœur: UF Enfant A (UF-A)
│
└─ Tous les parents: OI (parent direct), CF (parent éloigné)
```

#### UF Direct (UF-D)

```
UF-D
├─ Parent direct: Centre Formation (CF)
│
├─ Organisation sœur: Org. Intermédiaire (OI)
│
└─ Tous les parents: CF
```

---

## Périmètres d'action

Le **périmètre d'action** d'une organisation correspond à l'organisation elle-même plus tous ses enfants (directs et éloignés).

### Tableau des périmètres

| Organisation responsable | Périmètre complet               | Nb organisations |
|--------------------------|---------------------------------|------------------|
| **Centre Formation**     | CF, OI, UF-A, UF-B, UF-D        | 5                |
| **Org. Intermédiaire**   | OI, UF-A, UF-B                  | 3                |
| **UF Enfant A**          | UF-A                            | 1                |
| **UF Enfant B**          | UF-B                            | 1                |
| **UF Direct**            | UF-D                            | 1                |

---

### Représentation visuelle des périmètres

#### Périmètre Centre Formation

```
┌─────────────────────────────────────┐
│ Centre Formation (CF)               │ ← Organisation responsable
│ ┌─────────────────────────────────┐ │
│ │ Org. Intermédiaire (OI)         │ │
│ │ ┌─────────────┐ ┌─────────────┐ │ │
│ │ │ UF-A        │ │ UF-B        │ │ │
│ │ └─────────────┘ └─────────────┘ │ │
│ └─────────────────────────────────┘ │
│ ┌─────────────────────────────────┐ │
│ │ UF Direct (UF-D)                │ │
│ └─────────────────────────────────┘ │
└─────────────────────────────────────┘
Périmètre = CF, OI, UF-A, UF-B, UF-D
```

#### Périmètre Organisation Intermédiaire

```
┌─────────────────────────────────────┐
│ Org. Intermédiaire (OI)             │ ← Organisation responsable
│ ┌─────────────┐ ┌─────────────┐    │
│ │ UF-A        │ │ UF-B        │    │
│ └─────────────┘ └─────────────┘    │
└─────────────────────────────────────┘
Périmètre = OI, UF-A, UF-B
```

#### Périmètre UF Enfant A

```
┌─────────────┐
│ UF-A        │ ← Organisation responsable
└─────────────┘
Périmètre = UF-A
```

---

### Impact des périmètres

**Règle générale** : Une entité (utilisateur, machine, rôle, groupe) dont l'organisation responsable est X ne peut agir que sur les organisations appartenant au périmètre de X.

**Exemples** :

| Organisation responsable | Peut agir sur                   | Ne peut PAS agir sur |
|--------------------------|---------------------------------|----------------------|
| Centre Formation         | CF, OI, UF-A, UF-B, UF-D        | (tout est accessible)|
| Org. Intermédiaire       | OI, UF-A, UF-B                  | CF, UF-D             |
| UF Enfant A              | UF-A                            | CF, OI, UF-B, UF-D   |
| UF Enfant B              | UF-B                            | CF, OI, UF-A, UF-D   |
| UF Direct                | UF-D                            | CF, OI, UF-A, UF-B   |

---

## Cas particuliers

### UF Direct vs UF Enfant A/B

**Différence fondamentale** :

```
CF
├── OI (niveau 1)
│   ├── UF-A (niveau 2)  ← 2 niveaux de séparation avec CF
│   └── UF-B (niveau 2)
└── UF-D (niveau 1)       ← 1 seul niveau de séparation avec CF
```

**Implications** :

| Aspect                  | UF-A / UF-B                      | UF-D                          |
|-------------------------|----------------------------------|-------------------------------|
| Parent direct           | OI                               | CF                            |
| Niveau hiérarchique     | 2                                | 1                             |
| Parents                 | OI (direct), CF (éloigné)        | CF                            |
| Organisations sœurs     | Sœurs entre elles (UF-A ↔ UF-B) | OI                            |

**⚠️ Attention** : UF-D et UF-A ne sont **pas des sœurs** car elles n'ont pas le même parent.

---

### Organisations sœurs

Deux organisations sont **sœurs** si elles ont le **même parent direct**.

**Dans notre hiérarchie** :

| Organisation | Sœurs                |
|--------------|----------------------|
| OI           | UF-D                 |
| UF-D         | OI                   |
| UF-A         | UF-B                 |
| UF-B         | UF-A                 |
| CF           | (aucune, c'est la racine) |

**Organisations qui ne sont PAS sœurs** :
- UF-A et UF-D (parents différents : OI vs CF)
- UF-B et UF-D (parents différents : OI vs CF)
- OI et UF-A (relation parent/enfant)

---

## Personas utilisés

Pour faciliter la compréhension des exemples, nous utilisons 5 personas représentant des utilisateurs de différentes organisations.

### Tableau des personas

| Persona    | Organisation responsable | Abréviation | Périmètre              | Rôle typique          |
|------------|-------------------------|-------------|------------------------|-----------------------|
| **Marie**  | Centre Formation        | CF          | CF, OI, UF-A, UF-B, UF-D | Directrice du centre  |
| **Pierre** | Org. Intermédiaire      | OI          | OI, UF-A, UF-B         | Responsable pédagogique |
| **Sophie** | UF Enfant A             | UF-A        | UF-A                   | Formatrice            |
| **Lucas**  | UF Enfant B             | UF-B        | UF-B                   | Formateur             |
| **Emma**   | UF Direct               | UF-D        | UF-D                   | Formatrice            |

---

### Relations entre personas

```
Marie (CF)
├── Supervise Pierre (OI)
│   ├── Supervise Sophie (UF-A)
│   └── Supervise Lucas (UF-B)
└── Supervise Emma (UF-D)
```

**Capacités de supervision** :

| Persona | Peut superviser       | Ne peut pas superviser |
|---------|-----------------------|------------------------|
| Marie   | Pierre, Sophie, Lucas, Emma | (tous accessibles) |
| Pierre  | Sophie, Lucas         | Marie, Emma            |
| Sophie  | (personne)            | Marie, Pierre, Lucas, Emma |
| Lucas   | (personne)            | Marie, Pierre, Sophie, Emma |
| Emma    | (personne)            | Marie, Pierre, Sophie, Lucas |

---

## Schéma récapitulatif complet

```
┌────────────────────────────────────────────────────────────────┐
│                    HIÉRARCHIE COMPLÈTE                         │
├────────────────────────────────────────────────────────────────┤
│                                                                │
│  Centre Formation (CF) - Niveau 0                              │
│  Persona: Marie                                                │
│  Périmètre: CF, OI, UF-A, UF-B, UF-D                           │
│                                                                │
│  ├── Org. Intermédiaire (OI) - Niveau 1                        │
│  │   Persona: Pierre                                           │
│  │   Périmètre: OI, UF-A, UF-B                                 │
│  │                                                             │
│  │   ├── UF Enfant A (UF-A) - Niveau 2                         │
│  │   │   Persona: Sophie                                       │
│  │   │   Périmètre: UF-A                                       │
│  │   │                                                         │
│  │   └── UF Enfant B (UF-B) - Niveau 2                         │
│  │       Persona: Lucas                                        │
│  │       Périmètre: UF-B                                       │
│  │                                                             │
│  └── UF Direct (UF-D) - Niveau 1                               │
│      Persona: Emma                                             │
│      Périmètre: UF-D                                           │
│                                                                │
└────────────────────────────────────────────────────────────────┘
```

---

## Navigation

- [← Concepts et relations](01-concepts-et-relations.md)
- [← Retour à l'index](index.md)
- [Règles générales →](03-regles-generales.md)

[Retour à la gestion des droits](../index.md)
