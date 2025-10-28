---
title: "09 - Règles d'assignation des droits d'accès"
description: "Documentation détaillée des règles métier qui régissent l'assignation des rôles et groupes aux utilisateurs et machines"
date: "2025-10-28"
version: "1"
---

# Règles d'assignation des droits d'accès

Cette documentation décrit les règles métier qui régissent l'assignation des rôles et groupes aux utilisateurs et machines dans l'application.

## 📚 Table des matières

1. [Concepts généraux](#concepts-généraux)
2. [Hiérarchie d'organisations](#hiérarchie-dorganisations)
3. [Utilisateur → Rôle](#utilisateur--rôle)
4. [Utilisateur → Groupe](#utilisateur--groupe)
5. [Groupe → Rôle](#groupe--rôle)
6. [Machine → Rôle](#machine--rôle)
7. [Machine → Groupe](#machine--groupe)
8. [Schéma récapitulatif](#schéma-récapitulatif)

---

## Concepts généraux

### Sources d'assignation

Les rôles peuvent être assignés de deux manières :

- **Direct** : Assignation directe d'un rôle à un utilisateur ou une machine
- **Via Groupe** : Assignation indirecte via l'appartenance à un groupe

### Caractéristiques importantes

#### Rôles et groupes

Certains rôles et groupes sont **administrés par Papaours** (par exemple : le rôle et le groupe "Administrateur Papaours"). Ces éléments :
- Ne peuvent pas être modifiés par les utilisateurs
- Sont réservés à des usages internes spécifiques
- Leur assignation est contrôlée directement par le système

#### Machines

Certaines machines sont également **administrées par Papaours** (machines système). Ces machines ne peuvent pas être modifiées.

---

## Hiérarchie d'organisations

Pour les exemples suivants, nous utilisons cette hiérarchie :

```
Organisation Centre de Formation
└── Organisation Parent
    ├── Organisation Enfant A
    └── Organisation Enfant B
```

**Relations** :

- `Organisation Centre de Formation` est **parent** de `Organisation Parent`
- `Organisation Parent` est **parent** de `Organisation Enfant A` et `Organisation Enfant B`
- `Organisation Parent` est **enfant** de `Organisation Centre de Formation`
- `Organisation Enfant A` et `Organisation Enfant B` sont **enfants** de `Organisation Parent`

---

## Utilisateur → Rôle

### Règle 1 : Parentalité d'organisation du rôle

Le rôle **DOIT** provenir de l'organisation responsable de l'utilisateur ou d'une organisation **parente**.

#### Exemples avec Utilisateur Organisation Parent

| Utilisateur          | Rôle (org responsable)                   | Organisation assignée | Résultat | Explication                                 |
|----------------------|------------------------------------------|-----------------------|----------|---------------------------------------------|
| Organisation Parent  | Rôle Organisation Parent                 | Organisation Parent   | ✅        | Le rôle provient de la même organisation    |
| Organisation Parent  | Rôle Organisation Centre de Formation    | Organisation Parent   | ✅        | Le rôle provient d'une organisation parente |
| Organisation Parent  | Rôle Organisation Enfant A               | Organisation Parent   | ❌        | Le rôle provient d'une organisation enfant  |
| Organisation Parent  | Rôle Organisation Enfant B               | Organisation Parent   | ❌        | Le rôle provient d'une organisation enfant  |

#### Exemples avec Utilisateur Organisation Enfant A

| Utilisateur            | Rôle (org responsable)                   | Organisation assignée | Résultat | Explication                                       |
|------------------------|------------------------------------------|-----------------------|----------|---------------------------------------------------|
| Organisation Enfant A  | Rôle Organisation Enfant A               | Organisation Enfant A | ✅        | Le rôle provient de la même organisation          |
| Organisation Enfant A  | Rôle Organisation Parent                 | Organisation Enfant A | ✅        | Le rôle provient d'une organisation parente       |
| Organisation Enfant A  | Rôle Organisation Centre de Formation    | Organisation Enfant A | ✅        | Le rôle provient d'une organisation grand-parente |
| Organisation Enfant A  | Rôle Organisation Enfant B               | Organisation Enfant A | ❌        | Le rôle provient d'une organisation sœur          |

---

### Règle 2 : Périmètre du sujet

L'organisation assignée au rôle **DOIT** correspondre à l'organisation responsable de l'utilisateur ou à l'une de ses **organisations enfants**.

#### Exemples avec Utilisateur Organisation Parent

| Utilisateur         | Rôle            | Organisation assignée            | Résultat | Explication                               |
|---------------------|-----------------|----------------------------------|----------|-------------------------------------------|
| Organisation Parent | Rôle quelconque | Organisation Parent              | ✅        | Organisation responsable de l'utilisateur |
| Organisation Parent | Rôle quelconque | Organisation Enfant A            | ✅        | Organisation enfant de l'utilisateur      |
| Organisation Parent | Rôle quelconque | Organisation Enfant B            | ✅        | Organisation enfant de l'utilisateur      |
| Organisation Parent | Rôle quelconque | Organisation Centre de Formation | ❌        | Organisation parente (hors périmètre)     |

#### Exemples avec Utilisateur Organisation Enfant A

| Utilisateur           | Rôle            | Organisation assignée              | Résultat | Explication                                 |
|-----------------------|-----------------|------------------------------------|----------|---------------------------------------------|
| Organisation Enfant A | Rôle quelconque | Organisation Enfant A              | ✅        | Organisation responsable de l'utilisateur   |
| Organisation Enfant A | Rôle quelconque | Organisation Parent                | ❌        | Organisation parente (hors périmètre)       |
| Organisation Enfant A | Rôle quelconque | Organisation Enfant B              | ❌        | Organisation sœur (hors périmètre)          |
| Organisation Enfant A | Rôle quelconque | Organisation Centre de Formation   | ❌        | Organisation grand-parente (hors périmètre) |

#### Exemples avec Utilisateur Organisation Centre de Formation

| Utilisateur                      | Rôle            | Organisation assignée              | Résultat | Explication               |
|----------------------------------|-----------------|------------------------------------|----------|---------------------------|
| Organisation Centre de Formation | Rôle quelconque | Organisation Centre de Formation   | ✅        | Organisation responsable  |
| Organisation Centre de Formation | Rôle quelconque | Organisation Parent                | ✅        | Organisation enfant       |
| Organisation Centre de Formation | Rôle quelconque | Organisation Enfant A              | ✅        | Organisation petit-enfant |
| Organisation Centre de Formation | Rôle quelconque | Organisation Enfant B              | ✅        | Organisation petit-enfant |

---

### Règle 3 : Périmètre du rôle

L'organisation assignée **DOIT** appartenir au périmètre du rôle (organisation responsable du rôle ou ses enfants).

#### Exemples avec Rôle Organisation Parent

| Utilisateur | Rôle (org responsable)   | Organisation assignée            | Résultat | Explication                                   |
|-------------|--------------------------|----------------------------------|----------|-----------------------------------------------|
| quelconque  | Rôle Organisation Parent | Organisation Parent              | ✅        | Organisation responsable du rôle              |
| quelconque  | Rôle Organisation Parent | Organisation Enfant A            | ✅        | Organisation enfant du rôle                   |
| quelconque  | Rôle Organisation Parent | Organisation Enfant B            | ✅        | Organisation enfant du rôle                   |
| quelconque  | Rôle Organisation Parent | Organisation Centre de Formation | ❌        | Organisation parente (hors périmètre du rôle) |

#### Exemples avec Rôle Organisation Enfant A

| Utilisateur | Rôle (org responsable)     | Organisation assignée            | Résultat | Explication                                         |
|-------------|----------------------------|----------------------------------|----------|-----------------------------------------------------|
| quelconque  | Rôle Organisation Enfant A | Organisation Enfant A            | ✅        | Organisation responsable du rôle                    |
| quelconque  | Rôle Organisation Enfant A | Organisation Parent              | ❌        | Organisation parente (hors périmètre du rôle)       |
| quelconque  | Rôle Organisation Enfant A | Organisation Enfant B            | ❌        | Organisation sœur (hors périmètre du rôle)          |
| quelconque  | Rôle Organisation Enfant A | Organisation Centre de Formation | ❌        | Organisation grand-parente (hors périmètre du rôle) |

#### Exemples avec Rôle Organisation Centre de Formation

| Utilisateur | Rôle (org responsable)                   | Organisation assignée              | Résultat | Explication                       |
|-------------|------------------------------------------|------------------------------------|----------|-----------------------------------|
| quelconque  | Rôle Organisation Centre de Formation    | Organisation Centre de Formation   | ✅        | Organisation responsable du rôle  |
| quelconque  | Rôle Organisation Centre de Formation    | Organisation Parent                | ✅        | Organisation enfant du rôle       |
| quelconque  | Rôle Organisation Centre de Formation    | Organisation Enfant A              | ✅        | Organisation petit-enfant du rôle |
| quelconque  | Rôle Organisation Centre de Formation    | Organisation Enfant B              | ✅        | Organisation petit-enfant du rôle |

---

### Règle 4 : Rôles non assignables

Certains rôles **ne peuvent pas être assignés** car ils sont administrés par Papaours.

**⚠️ Cas particulier - Rôle système** :

Le rôle **Administrateur Papaours** est un rôle système qui ne peut pas être assigné. Il est géré uniquement par Papaours et réservé à des usages internes spécifiques.

#### Exemples

| Rôle                    | Peut être assigné ? | Explication                                  |
|-------------------------|---------------------|----------------------------------------------|
| Administrateur Papaours | ❌                   | Rôle système administré par Papaours         |
| Directeur CFA           | ✅                   | Rôle assignable normalement                  |
| Formateur               | ✅                   | Rôle assignable normalement                  |

---

### Exemples combinés : Utilisateur → Rôle

Les **3 règles** (Parentalité + Périmètre Sujet + Périmètre Rôle) doivent être respectées simultanément.

#### Cas 1 : Utilisateur Organisation Parent

| Rôle (org resp.)                         | Org. assignée                    | Règle 1    | Règle 2    | Règle 3          | Résultat |
|------------------------------------------|----------------------------------|------------|------------|------------------|----------|
| Rôle Organisation Centre de Formation    | Organisation Parent              | ✅ Parente  | ✅ Même org | ✅ Enfant du rôle | ✅        |
| Rôle Organisation Parent                 | Organisation Parent              | ✅ Même org | ✅ Même org | ✅ Même org       | ✅        |
| Rôle Organisation Parent                 | Organisation Enfant A            | ✅ Même org | ✅ Enfant   | ✅ Enfant du rôle | ✅        |
| Rôle Organisation Enfant A               | Organisation Enfant A            | ❌ Enfant   | ✅ Enfant   | ✅ Même org       | ❌        |
| Rôle Organisation Parent                 | Organisation Centre de Formation | ✅ Même org | ❌ Parent   | ❌ Parent du rôle | ❌        |

#### Cas 2 : Utilisateur Organisation Enfant A

| Rôle (org resp.)                         | Org. assignée         | Règle 1        | Règle 2    | Règle 3          | Résultat |
|------------------------------------------|-----------------------|----------------|------------|------------------|----------|
| Rôle Organisation Centre de Formation    | Organisation Enfant A | ✅ Grand-parent | ✅ Même org | ✅ Petit-enfant   | ✅        |
| Rôle Organisation Parent                 | Organisation Enfant A | ✅ Parent       | ✅ Même org | ✅ Enfant du rôle | ✅        |
| Rôle Organisation Enfant A               | Organisation Enfant A | ✅ Même org     | ✅ Même org | ✅ Même org       | ✅        |
| Rôle Organisation Enfant B               | Organisation Enfant A | ❌ Sœur         | ✅ Même org | ❌ Sœur           | ❌        |
| Rôle Organisation Enfant A               | Organisation Parent   | ✅ Même org     | ❌ Parent   | ❌ Parent du rôle | ❌        |

#### Cas 3 : Utilisateur Organisation Centre de Formation

| Rôle (org resp.)                         | Org. assignée                    | Règle 1    | Règle 2        | Règle 3          | Résultat |
|------------------------------------------|----------------------------------|------------|----------------|------------------|----------|
| Rôle Organisation Centre de Formation    | Organisation Centre de Formation | ✅ Même org | ✅ Même org     | ✅ Même org       | ✅        |
| Rôle Organisation Centre de Formation    | Organisation Parent              | ✅ Même org | ✅ Enfant       | ✅ Enfant du rôle | ✅        |
| Rôle Organisation Centre de Formation    | Organisation Enfant A            | ✅ Même org | ✅ Petit-enfant | ✅ Petit-enfant   | ✅        |
| Rôle Organisation Parent                 | Organisation Parent              | ❌ Enfant   | ✅ Enfant       | ✅ Même org       | ❌        |
| Rôle Organisation Parent                 | Organisation Enfant A            | ❌ Enfant   | ✅ Petit-enfant | ✅ Enfant du rôle | ❌        |

---

## Utilisateur → Groupe

### Règle 1 : Groupes non modifiables

Certains groupes **ne peuvent pas modifier leur liste d'utilisateurs** car ils sont administrés par Papaours.

**⚠️ Cas particulier - Groupe système** :

Le groupe **Administrateur Papaours** est un groupe système géré uniquement par Papaours. Il n'est pas possible d'ajouter ou retirer des utilisateurs de ce groupe.

#### Exemples

| Groupe                  | Action              | Résultat | Explication                                      |
|-------------------------|---------------------|----------|--------------------------------------------------|
| Administrateur Papaours | Ajouter utilisateur | ❌        | Groupe système administré par Papaours           |
| Groupe Formateurs       | Ajouter utilisateur | ✅        | Groupe modifiable normalement                    |
| Groupe Validation       | Retirer utilisateur | ✅        | Groupe modifiable normalement                    |

---

### Règle 2 : Interdiction de s'auto-assigner

Un utilisateur **NE PEUT PAS** :

- S'ajouter lui-même à un groupe
- Se retirer lui-même d'un groupe
- Modifier les rôles d'un groupe auquel il appartient

#### Exemples

| Utilisateur connecté     | Utilisateur cible | Action                           | Résultat |
|--------------------------|-------------------|----------------------------------|----------|
| Alice                    | Alice             | S'ajouter au groupe Formateurs   | ❌        |
| Alice                    | Bob               | Ajouter Bob au groupe Formateurs | ✅        |
| Alice (membre du groupe) | Carol             | Modifier rôles du groupe         | ❌        |
| Alice (non membre)       | Carol             | Modifier rôles du groupe         | ✅        |
| Bob                      | Bob               | Se retirer du groupe Direction   | ❌        |

---

### Règle 3 : Restrictions sur les groupes administrés par Papaours

Les groupes administrés par Papaours ont des restrictions spécifiques :

- Le **nom** du groupe ne peut jamais être modifié
- Les **rôles** du groupe ne peuvent jamais être modifiés
- Seule la **liste des utilisateurs** peut parfois être modifiée (selon le groupe)

#### Exemples

| Groupe                  | Type                     | Action              | Résultat |
|-------------------------|--------------------------|---------------------|----------|
| Administrateur Papaours | Groupe système           | Ajouter utilisateur | ❌        |
| Administrateur Papaours | Groupe système           | Modifier nom        | ❌        |
| Administrateur Papaours | Groupe système           | Modifier rôles      | ❌        |
| Groupe Validation       | Groupe Papaours          | Ajouter utilisateur | ✅        |
| Groupe Validation       | Groupe Papaours          | Modifier nom        | ❌        |
| Groupe Validation       | Groupe Papaours          | Modifier rôles      | ❌        |
| Groupe Custom CFA       | Groupe créé par le CFA   | Modifier nom        | ✅        |
| Groupe Custom CFA       | Groupe créé par le CFA   | Modifier rôles      | ✅        |

---

### Règle 4 : Périmètre via groupe

Lorsqu'un utilisateur est ajouté à un groupe, les **mêmes règles de périmètre** que pour Utilisateur → Rôle s'appliquent pour **tous les rôles du groupe**.

#### Exemples

| Utilisateur           | Groupe (org resp.)                 | Rôles du groupe                                        | Résultat | Explication                                    |
|-----------------------|------------------------------------|--------------------------------------------------------|----------|------------------------------------------------|
| Organisation Parent   | Groupe Parent (Parent)             | Rôle Parent sur Parent                                 | ✅        | Toutes les règles respectées                   |
| Organisation Parent   | Groupe Parent (Parent)             | Rôle Centre de Formation sur Parent                    | ✅        | Rôle parental valide                           |
| Organisation Parent   | Groupe Enfant A (Enfant A)         | Rôle Enfant A sur Enfant A                             | ❌        | Rôle enfant invalide (Règle 1)                 |
| Organisation Enfant A | Groupe Parent (Parent)             | Rôle Parent sur Parent                                 | ❌        | Organisation assignée hors périmètre (Règle 2) |
| Organisation Enfant A | Groupe Enfant A (Enfant A)         | Rôle Parent sur Enfant A                               | ✅        | Toutes les règles respectées                   |

---

## Groupe → Rôle

Les **mêmes règles** que pour Utilisateur → Rôle s'appliquent :

1. **Règle de parentalité d'organisation** : Le rôle doit provenir de l'organisation responsable du groupe ou d'une organisation parente
2. **Règle de périmètre du sujet** : L'organisation assignée doit être dans le périmètre du groupe
3. **Règle de périmètre du rôle** : L'organisation assignée doit être dans le périmètre du rôle
4. **Rôles non assignables** : Les rôles administrés par Papaours (ex: Administrateur Papaours) ne peuvent pas être assignés

### Exemples

| Groupe (org resp.)    | Rôle (org resp.)                  | Org. assignée         | Règle 1 | Règle 2 | Règle 3 | Résultat |
|-----------------------|-----------------------------------|-----------------------|---------|---------|---------|----------|
| Organisation Parent   | Rôle Parent                       | Organisation Parent   | ✅       | ✅       | ✅       | ✅        |
| Organisation Parent   | Rôle Centre de Formation          | Organisation Parent   | ✅       | ✅       | ✅       | ✅        |
| Organisation Parent   | Rôle Parent                       | Organisation Enfant A | ✅       | ✅       | ✅       | ✅        |
| Organisation Parent   | Rôle Enfant A                     | Organisation Enfant A | ❌       | ✅       | ✅       | ❌        |
| Organisation Enfant A | Rôle Enfant A                     | Organisation Enfant A | ✅       | ✅       | ✅       | ✅        |
| Organisation Enfant A | Rôle Parent                       | Organisation Enfant A | ✅       | ✅       | ✅       | ✅        |
| Organisation Enfant A | Rôle Parent                       | Organisation Parent   | ✅       | ❌       | ✅       | ❌        |

---

## Machine → Rôle

Les **mêmes règles** que pour Utilisateur → Rôle s'appliquent avec une règle supplémentaire.

### Règle supplémentaire : Machines administrées par Papaours

Les machines administrées par Papaours (machines système) **ne peuvent pas être modifiées**.

### Exemples

#### Machines créées par le CFA

| Machine (org resp.)   | Rôle (org resp.)             | Org. assignée         | Règle 1 | Règle 2 | Règle 3 | Résultat |
|-----------------------|------------------------------|-----------------------|---------|---------|---------|----------|
| Organisation Parent   | Rôle Parent                  | Organisation Parent   | ✅       | ✅       | ✅       | ✅        |
| Organisation Parent   | Rôle Centre de Formation     | Organisation Parent   | ✅       | ✅       | ✅       | ✅        |
| Organisation Parent   | Rôle Parent                  | Organisation Enfant A | ✅       | ✅       | ✅       | ✅        |
| Organisation Parent   | Rôle Enfant A                | Organisation Enfant A | ❌       | ✅       | ✅       | ❌        |
| Organisation Enfant A | Rôle Enfant A                | Organisation Enfant A | ✅       | ✅       | ✅       | ✅        |
| Organisation Enfant A | Rôle Parent                  | Organisation Enfant A | ✅       | ✅       | ✅       | ✅        |
| Organisation Enfant A | Rôle Parent                  | Organisation Parent   | ✅       | ❌       | ✅       | ❌        |

#### Machines administrées par Papaours

| Machine               | Type             | Action         | Résultat |
|-----------------------|------------------|----------------|----------|
| Machine Système       | Machine Papaours | Ajouter rôle   | ❌        |
| Machine Système       | Machine Papaours | Modifier rôle  | ❌        |
| Machine Système       | Machine Papaours | Supprimer rôle | ❌        |
| Machine API CFA       | Machine du CFA   | Ajouter rôle   | ✅        |

---

## Machine → Groupe

Lorsqu'un groupe est associé à une machine, les **mêmes règles de périmètre** que pour Utilisateur → Groupe s'appliquent pour **tous les rôles du groupe**.

### Exemples

| Machine (org resp.)                    | Groupe (org resp.)         | Rôles du groupe                     | Résultat | Explication                                    |
|----------------------------------------|----------------------------|-------------------------------------|----------|------------------------------------------------|
| Organisation Parent                    | Groupe Parent (Parent)     | Rôle Parent sur Parent              | ✅        | Toutes les règles respectées                   |
| Organisation Parent                    | Groupe Parent (Parent)     | Rôle Centre de Formation sur Parent | ✅        | Rôle parental valide                           |
| Organisation Parent                    | Groupe Enfant A (Enfant A) | Rôle Enfant A sur Enfant A          | ❌        | Rôle enfant invalide (Règle 1)                 |
| Organisation Enfant A                  | Groupe Parent (Parent)     | Rôle Parent sur Parent              | ❌        | Organisation assignée hors périmètre (Règle 2) |
| Organisation Enfant A                  | Groupe Enfant A (Enfant A) | Rôle Parent sur Enfant A            | ✅        | Toutes les règles respectées                   |
| Machine Système (administrée Papaours) | Groupe quelconque          | Rôles quelconques                   | ❌        | Machine non modifiable                         |

---

## Schéma récapitulatif

```
┌─────────────────────────────────────────────────────────────┐
│                  Règles d'assignation                       │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  1. Parentalité organisation du rôle                        │
│     ► Le rôle provient de l'organisation responsable        │
│       ou d'une organisation PARENTE                         │
│                                                             │
│  2. Périmètre du sujet                                      │
│     ► L'organisation assignée est l'organisation            │
│       responsable ou une organisation ENFANT                │
│                                                             │
│  3. Périmètre du rôle                                       │
│     ► L'organisation assignée appartient au périmètre       │
│       du rôle (organisation responsable ou enfants)         │
│                                                             │
│  4. Rôles et groupes non assignables                        │
│     ► Certains rôles et groupes administrés par Papaours    │
│       ne peuvent pas être assignés                          │
│                                                             │
│  5. Restrictions spécifiques                                │
│     ► Pas d'auto-assignation utilisateur                    │
│     ► Groupes/rôles Papaours non modifiables                │
│     ► Machines Papaours non modifiables                     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

### Pour aller plus loin

- [05 - Attribution des droits →](05-attribution-des-droits.md)
- [06 - Modifier les droits d'accès →](06-modifier-les-droits-dacces.md)
- [03 - Gestion des machines →](acces-api/03-gestion-des-machines.md)

[Retour à l'Accueil](../accueil)
