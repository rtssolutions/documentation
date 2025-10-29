---
title: "01 - Concepts et relations"
description: "Définitions des entités et relations dans le système de gestion des droits"
date: "2025-10-29"
version: "2.0"
---

# 01 - Concepts et relations

Cette page présente les concepts fondamentaux et les relations entre les différentes entités du système de gestion des droits.

---

## 📚 Table des matières

1. [Entités du système](#entités-du-système)
2. [Relations entre entités](#relations-entre-entités)
3. [Notions clés](#notions-clés)
4. [Sources d'assignation](#sources-dassignation)
5. [Entités administrées par Papaours](#entités-administrées-par-papaours)

---

## Entités du système

### 🏢 Organisation

Une **organisation** représente une structure administrative dans la hiérarchie du centre de formation.

**Caractéristiques** :
- Possède un nom unique
- Peut avoir une organisation **parente**
- Peut avoir des organisations **enfants**
- Forme une hiérarchie arborescente

**Types d'organisation** :
- **Centre de Formation (CF)** : Racine de la hiérarchie
- **Organisation intermédiaire** : Niveau intermédiaire (groupement d'UF non obligatoire)
- **Unité de Formation (UF)** : Niveau opérationnel

---

### 👤 Utilisateur

Un **utilisateur** est une personne physique ayant accès à l'application.

**Caractéristiques** :
- Possède une **organisation responsable** unique
- Peut avoir plusieurs **rôles** (directs ou via groupes)
- Peut appartenir à plusieurs **groupes**
- Peut effectuer des actions selon ses droits

**Exemple** :
```
Sophie
├── Organisation responsable: UF Enfant A
├── Rôles directs: Formateur sur UF-A
└── Groupes: Groupe Équipe Pédagogique
```

---

### 🎭 Rôle

Un **rôle** définit un ensemble de permissions applicables sur une organisation.

**Caractéristiques** :
- Possède un nom (ex: Directeur CFA, Formateur, Assistant)
- Provient d'une **organisation responsable**
- Définit un **périmètre** d'action (organisation + enfants)
- Peut être assigné directement ou via un groupe

**Structure d'un rôle** :
```
Rôle: Gestionnaire administratif
├── Organisation responsable: Org. Intermédiaire
├── Périmètre: OI, UF-A, UF-B
└── Permissions: Gestion apprenants, gestion des contrats, etc.
```

**Types de rôle** :
- **Rôle système** : Créé et géré par Papaours (non modifiable)
- **Rôle CFA** : Créé et géré par le centre de formation

---

### 👥 Groupe

Un **groupe** est un ensemble d'utilisateurs partageant les mêmes rôles.

**Caractéristiques** :
- Possède un nom unique
- Provient d'une **organisation responsable**
- Contient une **liste d'utilisateurs**
- Contient une **liste de rôles**

**Structure d'un groupe** :
```
Groupe: Équipe Pédagogique
├── Organisation responsable: Org. Intermédiaire
├── Utilisateurs: Pierre, Sophie, Lucas
└── Rôles:
    ├── Gestionnaire pédagogique sur OI
    └── Formateur sur UF-A, UF-B
```

**Types de groupe** :
- **Groupe système** : Créé et géré par Papaours, non modifiable
- **Groupe Papaours** : Créé par Papaours, utilisateurs modifiables
- **Groupe CFA** : Créé et géré par le centre de formation

---

### 🖥️ Machine

Une **machine** représente un système automatisé accédant à l'API.

**Caractéristiques** :
- Possède une **organisation responsable** unique
- Possède une ou plusieurs **clés API**
- Peut avoir plusieurs **rôles** (directs ou via groupes)
- Peut appartenir à plusieurs **groupes**

**Exemple** :
```
Machine API: Export Données
├── Organisation responsable: Centre Formation
├── Clé API: pk_prod_export_xxxxx
├── Rôles directs: Lecteur sur CF
└── Groupes: Groupe API Export
```

**Types de machine** :
- **Machine système** : Créée et gérée par Papaours (non modifiable)
- **Machine CFA** : Créée et gérée par le centre de formation

---

## Relations entre entités

### Diagramme général

```
┌─────────────────────────────────────────────────────────────┐
│                     SYSTÈME DE DROITS                       │
└─────────────────────────────────────────────────────────────┘
                              │
                ┌─────────────┴─────────────┐
                │                           │
         ┌──────▼──────┐            ┌──────▼──────┐
         │ UTILISATEUR │            │   MACHINE   │
         └──────┬──────┘            └──────┬──────┘
                │                           │
                │ org. responsable          │ org. responsable
                │                           │
         ┌──────▼───────────────────────────▼──────┐
         │          ORGANISATION                    │
         │  (hiérarchie parent/enfant)              │
         └──────────────────────────────────────────┘
                │
                │
    ┌───────────┴───────────┐
    │                       │
┌───▼────┐              ┌───▼────┐
│  RÔLE  │              │ GROUPE │
└───┬────┘              └───┬────┘
    │                       │
    │ org. responsable      │ org. responsable
    │ + périmètre           │ + liste rôles
    │                       │ + liste utilisateurs/machines
    └───────────────────────┘
```

### Relations détaillées

#### Utilisateur ↔ Organisation
- Un utilisateur appartient à **UNE SEULE** organisation responsable
- Cette organisation définit les roles et groupes assignables à l'utilisateur.

**Exemple** : Sophie appartient à UF Enfant A

---

#### Machine ↔ Organisation
- Une machine appartient à **UNE SEULE** organisation responsable
- Cette organisation définit les roles et groupes assignables à la machine.

**Exemple** : Machine API Pédagogie appartient à Org. Intermédiaire

---

#### Utilisateur ↔ Rôle
- Un utilisateur peut avoir **plusieurs rôles directs**
- Chaque rôle est assigné sur une **organisation spécifique**

**Exemple** :
```
Sophie
├── Formateur ( Org. Responsable UF-A ) sur UF-A
└── Gestion des contrats ( Org. Responsable CF ) sur UF-A
```

---

#### Machine ↔ Rôle
- Une machine peut avoir **plusieurs rôles directs**
- Chaque rôle est assigné sur une **organisation spécifique**

**Exemple** :
```
Machine API Export
├── Lecteur ( Org. Responsable CF ) sur CF
└── Lecteur ( Org. Responsable CF ) sur OI
```

---

#### Utilisateur ↔ Groupe
- Un utilisateur peut appartenir à **plusieurs groupes**
- L'utilisateur **hérite automatiquement** des rôles de tous ses groupes

**Exemple** :
```
Pierre
├── Groupe "Équipe Pédagogique" → hérite de ses rôles
└── Groupe "Validation" → hérite de ses rôles
```

---

#### Machine ↔ Groupe
- Une machine peut appartenir à **plusieurs groupes**
- La machine **hérite automatiquement** des rôles de tous ses groupes

**Exemple** :
```
Machine API Consultation
└── Groupe "API Lecture" → hérite de ses rôles
```

---

#### Groupe ↔ Rôle
- Un groupe contient **plusieurs rôles**
- Chaque rôle est assigné sur une **organisation spécifique**

**Exemple** :
```
Groupe "Équipe Pédagogique"
├── Responsable Pédagogique sur OI
├── Formateur sur UF-A
└── Formateur sur UF-B
```

---

#### Organisation ↔ Organisation
- Les organisations forment une **hiérarchie arborescente**
- Une organisation peut avoir **UN parent** et **plusieurs enfants**

**Exemple** :
```
Org. Intermédiaire
├── Parent : Centre Formation
└── Enfants : UF-A, UF-B
```

---

## Notions clés

### Organisation responsable

L'**organisation responsable** est l'organisation à laquelle appartient une entité (utilisateur, machine, rôle, groupe).

**Rôles de l'organisation responsable** :

1. **Appartenance** : Définit à qui appartient la donnée
   - Sophie appartient à UF Enfant A

2. **Droits de modification** : Définit qui peut modifier l'entité
   - CF peut modifier les utilisateurs de UF
   - UF ne peut PAS modifier les utilisateurs de CF

3. **Cohérence des relations** : Garantit la logique hiérarchique
   - Un utilisateur CF ne peut pas avoir un rôle d'apprenant à UF
   - Les assignations doivent respecter la hiérarchie

**Exemples** :
- Sophie a pour organisation responsable : `UF Enfant A`
  - Elle est "gérée" par UF-A
  - CF, OI et UF-A peuvent la modifier
  - UF-B et UF-D ne peuvent pas la modifier

- Le rôle "Gestionnaire administratif" a pour organisation responsable : `Org. Intermédiaire`
  - Il appartient à OI
  - CF et OI peuvent le modifier
  - UF-A et UF-B ne peuvent pas le modifier

- Le groupe "Équipe Pédagogique" a pour organisation responsable : `Centre Formation`
  - Il appartient à CF
  - Seul CF peut le modifier

---

### Périmètre

Le **périmètre** définit l'ensemble des organisations sur lesquelles une entité **peut recevoir des assignations**.

**⚠️ Important** : Le périmètre découle des **assignations**, pas de l'organisation responsable seule.

**Pour un utilisateur ou une machine** :
Le périmètre est limité par l'organisation responsable ET ses enfants (Règle 2).

**Exemples** :

| Utilisateur / Machine | Organisation responsable | Périmètre possible (Règle 2)           |
|-----------------------|--------------------------|----------------------------------------|
| Marie                 | Centre Formation (CF)    | CF, OI, UF-A, UF-B, UF-D               |
| Pierre                | Org. Intermédiaire (OI)  | OI, UF-A, UF-B                         |
| Sophie                | UF Enfant A (UF-A)       | UF-A seulement                         |
| Emma                  | UF Direct (UF-D)         | UF-D seulement                         |

**Pour un rôle** :
Le périmètre définit sur quelles organisations le rôle peut être appliqué (Règle 3).

**Exemples** :

| Rôle                        | Organisation responsable | Périmètre du rôle (Règle 3)            |
|-----------------------------|--------------------------|----------------------------------------|
| Directeur CF                | Centre Formation (CF)    | CF, OI, UF-A, UF-B, UF-D               |
| Gestionnaire administratif  | Org. Intermédiaire (OI)  | OI, UF-A, UF-B                         |
| Formateur UF-A              | UF Enfant A (UF-A)       | UF-A seulement                         |

---

### Hiérarchie et parentalité

Les organisations forment une **hiérarchie arborescente**.

**Concepts** :
- **Parent** : Organisation au-dessus dans la hiérarchie
  - **Parent direct** : Organisation immédiatement au-dessus
  - **Parent éloigné** : Organisation plus haut dans la hiérarchie (ex: CF est parent éloigné de UF-A)

- **Enfant** : Organisation en-dessous dans la hiérarchie
  - **Enfant direct** : Organisation immédiatement en-dessous
  - **Enfant éloigné** : Organisation plus bas dans la hiérarchie (ex: UF-A est enfant éloigné de CF)

**Exemple avec UF Enfant A** :
```
Parents de UF-A:
├── Parent direct: Org. Intermédiaire
└── Parent éloigné: Centre Formation

Enfants de UF-A:
└── (aucun)
```

**Exemple avec Centre Formation** :
```
Parents de CF:
└── (aucun, c'est l'organisation racine)

Enfants de CF:
├── Enfants directs: Org. Intermédiaire, UF Direct
└── Enfants éloignés: UF Enfant A, UF Enfant B
```

---

### Organisation assignée

L'**organisation assignée** est l'organisation sur laquelle un rôle est appliqué lors d'une assignation.

**Exemple** :
```
Sophie (UF Enfant A) reçoit le rôle "Formateur" sur l'organisation "UF Enfant A"
                                                              └─── Organisation assignée
```

**Important** : L'organisation assignée doit respecter les règles de périmètre (voir [Règles générales](03-regles-generales.md)).

---

## Sources d'assignation

Les rôles peuvent être attribués de **deux manières** :

### 1. Assignation directe

Un rôle est directement attribué à un utilisateur ou une machine.

**Exemple** :
```
Sophie → Rôle "Formateur" sur UF-A
         └─── Assignation directe
```

### 2. Assignation via groupe

Un utilisateur ou une machine hérite des rôles d'un groupe auquel il/elle appartient.

**Exemple** :
```
Sophie → Groupe "Équipe Pédagogique"
         └─── Le groupe possède le rôle "Formateur" sur UF-A
              └─── Sophie hérite automatiquement de ce rôle
```

**Avantages de l'assignation via groupe** :
- Gestion centralisée des droits
- Facilite les modifications en masse
- Réduit les erreurs de configuration

---

## Entités administrées par Papaours

Certaines entités sont **créées et gérées par Papaours** et ne peuvent pas être modifiées par les utilisateurs du centre de formation.

### Rôles système

**Rôle système** : **Administrateur Papaours**

**Restrictions** :
- ❌ Ne peut pas être modifié
- ❌ Ne peut pas être assigné manuellement
- ❌ Ne peut pas être supprimé
- ✅ Géré uniquement par Papaours

**Description** : Administrateur de la plateforme Papaours avec tous les droits sur toutes les ressources.

---

### Rôles Papaours (assignables)

**Rôle Papaours** : **Administrateur du centre de formation**

**Caractéristiques** :
- ✅ Peut être assigné aux utilisateurs du centre
- ❌ Permissions non modifiables (définies par Papaours)
- ❌ Ne peut pas être supprimé
- ✅ Donne accès complet à la gestion du centre de formation

**Description** : Administrateur du centre de formation avec tous les droits de gestion.

---

### Groupes système

**Groupe système** : **Administrateur Papaours**

**Restrictions** :
- ❌ Nom non modifiable
- ❌ Rôles non modifiables
- ❌ Liste utilisateurs non modifiable
- ✅ Géré uniquement par Papaours

**Composition** :
- Contient le rôle : **Administrateur Papaours**
- Uniquement assignable au niveau Centre de Formation

---

### Groupes Papaours (partiellement modifiables)

**Groupe Papaours** : **Administrateur Centre de Formation**

**Restrictions** :
- ❌ Nom non modifiable
- ❌ Rôles non modifiables
- ✅ Liste utilisateurs modifiable par le centre

**Composition** :
- Contient le rôle : **Administrateur du centre de formation**
- Uniquement assignable au niveau Centre de Formation

---

### Machines système

**Machine système** : **Administrateur Papaours**

**Restrictions** :
- ❌ Ne peut pas être modifiée
- ❌ Rôles non modifiables
- ❌ Groupes non modifiables
- ❌ Clés API non modifiables
- ❌ Ne peut pas être désactivée/supprimée
- ✅ Gérée uniquement par Papaours

**Composition** :
- Appartient au groupe : **Administrateur Papaours**
- Dispose de tous les droits d'administration

---

## Schéma récapitulatif

```
┌──────────────────────────────────────────────────────────────┐
│                    CONCEPTS FONDAMENTAUX                     │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  🏢 ORGANISATION                                             │
│     ├─ Hiérarchie parent/enfant                              │
│     ├─ Organisation responsable                              │
│     └─ Périmètre (org + enfants)                             │
│                                                              │
│  👤 UTILISATEUR / 🖥️ MACHINE                                 │
│     ├─ Appartient à UNE organisation                         │
│     ├─ Peut avoir plusieurs rôles (direct ou groupe)         │
│     └─ Peut appartenir à plusieurs groupes                   │
│                                                              │
│  🎭 RÔLE                                                      │
│     ├─ Provient d'une organisation responsable               │
│     ├─ Définit un périmètre d'action                         │
│     ├─ Assigné sur une organisation spécifique               │
│     └─ Système (Papaours) ou CFA (modifiable)                │
│                                                              │
│  👥 GROUPE                                                    │
│     ├─ Provient d'une organisation responsable               │
│     ├─ Contient des utilisateurs/machines                    │
│     ├─ Contient des rôles                                    │
│     └─ Système, Papaours ou CFA                              │
│                                                              │
│  📋 SOURCES D'ASSIGNATION                                    │
│     ├─ Directe : Rôle → Utilisateur/Machine                  │
│     └─ Via Groupe : Groupe → Utilisateur/Machine             │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

## Navigation

- [← Retour à l'index](index.md)
- [Organisation →](02-organisation.md)
- [Règles générales →](03-regles-generales.md)

[Retour à la gestion des droits](../index.md)
