---
title: "09 - Règles d'assignation des droits d'accès"
description: "Documentation détaillée des règles métier qui régissent l'assignation des rôles et groupes aux utilisateurs et machines"
date: "2025-10-29"
version: "2.0"
---

# Règles d'assignation des droits d'accès

> **📢 Cette documentation a été restructurée pour plus de clarté**
>
> Le contenu a été divisé en plusieurs sections thématiques pour faciliter la navigation et la compréhension.
>
> **👉 [Accéder à la documentation complète →](regles-assignation/index.md)**

---

## 📚 Navigation rapide

La documentation est maintenant organisée en **7 sections** :

### 1. [Concepts et relations →](regles-assignation/01-concepts-et-relations.md)
Définitions des entités (Organisation, Utilisateur, Rôle, Groupe, Machine), relations entre elles, notions de responsabilité, périmètre et hiérarchie.

### 2. [Organisation →](regles-assignation/02-organisation.md)
Présentation détaillée de la hiérarchie d'organisations de référence utilisée dans tous les exemples, avec les personas associés.

### 3. [Règles générales →](regles-assignation/03-regles-generales.md)
Les **3 règles fondamentales** et les **règles transversales** qui s'appliquent à toutes les assignations de droits.

### 4. [Assignation de rôle →](regles-assignation/04-assignation-role.md)
Propriétés des rôles, types de rôles (système vs CFA), et exemples détaillés d'assignation par rôle.

### 5. [Assignation de groupe →](regles-assignation/05-assignation-groupe.md)
Composition des groupes, types de groupes, restrictions spécifiques et règles Groupe → Rôle.

### 6. [Assignation utilisateur →](regles-assignation/06-assignation-utilisateur.md)
Vue centrée utilisateur : Utilisateur → Rôle et Utilisateur → Groupe, avec exemples exhaustifs par persona.

### 7. [Assignation machine →](regles-assignation/07-assignation-machine.md)
Vue centrée machine : Machine → Rôle et Machine → Groupe, gestion des clés API, machines système vs CFA.

---

## 🎯 Accès rapide aux concepts clés

### Les 3 règles fondamentales

Toute assignation de rôle doit respecter **simultanément** ces 3 règles :

1. **Parentalité d'organisation du rôle**
   Le rôle doit provenir de l'organisation responsable du sujet ou d'une organisation **parente**

2. **Périmètre du sujet**
   L'organisation assignée doit être l'organisation responsable du sujet ou une organisation **enfant**

3. **Périmètre du rôle**
   L'organisation assignée doit appartenir au périmètre du rôle (organisation responsable du rôle ou ses enfants)

👉 [En savoir plus sur les règles générales →](regles-assignation/03-regles-generales.md)

---

## 🏢 Hiérarchie d'organisations de référence

Tous les exemples de la documentation utilisent cette hiérarchie :

```
Centre Formation (CF) - Marie
├── Org. Intermédiaire (OI) - Pierre
│   ├── UF Enfant A (UF-A) - Sophie
│   └── UF Enfant B (UF-B) - Lucas
└── UF Direct (UF-D) - Emma
```

👉 [Voir la documentation complète de la hiérarchie →](regles-assignation/02-organisation.md)

---

## 🔒 Entités administrées par Papaours

Certaines entités sont **administrées par Papaours** et ne peuvent pas être modifiées :

- **Rôles système** : Ex. Administrateur Papaours
- **Groupes système** : Ex. Administrateur Papaours
- **Groupes Papaours** : Nom et rôles non modifiables, membres modifiables
- **Machines système** : Machines créées par Papaours

👉 [En savoir plus sur les concepts →](regles-assignation/01-concepts-et-relations.md)

---

## 📖 Guide d'utilisation

### Pour découvrir
1. Commencez par [Concepts et relations](regles-assignation/01-concepts-et-relations.md)
2. Consultez [Organisation](regles-assignation/02-organisation.md) pour la hiérarchie de référence
3. Maîtrisez les [Règles générales](regles-assignation/03-regles-generales.md)

### Pour approfondir
- **Rôles** : [Assignation de rôle](regles-assignation/04-assignation-role.md)
- **Groupes** : [Assignation de groupe](regles-assignation/05-assignation-groupe.md)
- **Utilisateurs** : [Assignation utilisateur](regles-assignation/06-assignation-utilisateur.md)
- **Machines** : [Assignation machine](regles-assignation/07-assignation-machine.md)

---

## 🔗 Ancienne documentation

> **⚠️ Le contenu ci-dessous est conservé pour compatibilité mais n'est plus maintenu.**
>
> Pour la version à jour, consultez la [nouvelle documentation structurée](regles-assignation/index.md).

<details>
<summary>Cliquez pour afficher l'ancienne version (v1.0)</summary>

## Schéma récapitulatif (ancien)

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

</details>

---

## 🔗 Liens connexes

- [← Retour à la gestion des droits](index.md)
- [Attribution des droits →](05-attribution-des-droits.md)
- [Modifier les droits d'accès →](06-modifier-les-droits-dacces.md)

[Retour à l'Accueil](../accueil)
