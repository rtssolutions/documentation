---
title: "Règles d'assignation des droits d'accès"
description: "Documentation détaillée des règles métier qui régissent l'assignation des rôles et groupes aux utilisateurs et machines"
date: "2025-10-29"
version: "2.0"
---

# Règles d'assignation des droits d'accès

Cette documentation décrit les règles métier qui régissent l'assignation des rôles et groupes aux utilisateurs et machines dans l'application Papaours.

---

## 📚 Navigation

Cette documentation est divisée en 7 sections pour faciliter la compréhension :

1. **[Concepts et relations →](01-concepts-et-relations)**
   Définitions des entités, relations entre elles, notions de responsabilité et périmètre

2. **[Organisation →](02-organisation)**
   Hiérarchie de référence utilisée dans tous les exemples, relations parent/enfant

3. **[Règles générales →](03-regles-generales)**
   Les 3 règles fondamentales et règles transversales applicables à toutes les assignations

4. **[Assignation de rôle →](04-assignation-role)**
   Propriétés des rôles, rôles système vs CFA, exemples détaillés

5. **[Assignation de groupe →](05-assignation-groupe)**
   Composition des groupes, restrictions, règles spécifiques

6. **[Assignation utilisateur →](06-assignation-utilisateur)**
   Vue centrée utilisateur : Utilisateur → Rôle et Utilisateur → Groupe

7. **[Assignation machine →](07-assignation-machine)**
   Machine → Rôle et Machine → Groupe, machines système vs CFA

---

## 🏢 Hiérarchie d'organisations de référence

Tous les exemples de cette documentation utilisent la même hiérarchie d'organisations :

```
Centre Formation (CF)
├── Org. Intermédiaire (OI)
│   ├── UF Enfant A (UF-A)
│   └── UF Enfant B (UF-B)
└── UF Direct (UF-D)
```

### Relations hiérarchiques

| Organisation          | Parent                  | Enfants              |
|-----------------------|-------------------------|----------------------|
| Centre Formation (CF) | -                       | OI, UF-D             |
| Org. Intermédiaire (OI) | CF                     | UF-A, UF-B           |
| UF Enfant A (UF-A)    | OI                      | -                    |
| UF Enfant B (UF-B)    | OI                      | -                    |
| UF Direct (UF-D)      | CF                      | -                    |

**Point important** : `UF Direct` est au même niveau hiérarchique que `Org. Intermédiaire`, tous deux étant des enfants directs de `Centre Formation`.

---

## 👥 Personas utilisés dans les exemples

Pour faciliter la compréhension, les mêmes personas sont utilisés dans toute la documentation :

| Persona | Organisation responsable | Abréviation |
|---------|-------------------------|-------------|
| **Marie** | Centre Formation | CF |
| **Pierre** | Org. Intermédiaire | OI |
| **Sophie** | UF Enfant A | UF-A |
| **Lucas** | UF Enfant B | UF-B |
| **Emma** | UF Direct | UF-D |

---

## 🎯 Principes fondamentaux

Les règles d'assignation reposent sur **3 principes fondamentaux** :

1. **Parentalité d'organisation du rôle**
   Le rôle doit provenir de l'organisation responsable du sujet ou d'une organisation **parente**

2. **Périmètre du sujet**
   L'organisation assignée doit être l'organisation responsable du sujet ou une organisation **enfant**

3. **Périmètre du rôle**
   L'organisation assignée doit appartenir au périmètre du rôle (organisation responsable du rôle ou ses enfants)

Ces 3 règles **doivent être respectées simultanément** pour qu'une assignation soit valide.

---

## 🔒 Entités administrées par Papaours

Certaines entités sont **administrées par Papaours** et ne peuvent pas être modifiées :

- **Rôles système** : Administrateur Papaours
- **Groupes système** : Administrateur Papaours
- **Machines système** : Machines créées par Papaours

Ces entités sont marquées visuellement dans l'interface et leurs restrictions sont détaillées dans chaque section concernée.

---

## 📖 Comment utiliser cette documentation

1. **Découverte** : Commencez par [Concepts et relations](01-concepts-et-relations) pour comprendre les bases
2. **Référence** : Consultez [Organisation](02-organisation) pour la hiérarchie utilisée dans tous les exemples
3. **Apprentissage** : Lisez [Règles générales](03-regles-generales) pour maîtriser les 3 règles fondamentales
4. **Pratique** : Consultez les sections spécifiques selon votre besoin (Rôle, Groupe, Utilisateur, Machine)

---

## 🔗 Liens utiles

- [← Retour à la gestion des droits](../index.md)
- [Attribution des droits →](../05-attribution-des-droits.md)
- [Modifier les droits d'accès →](../06-modifier-les-droits-dacces.md)
- [Gestion des machines →](../acces-api/03-gestion-des-machines.md)

[Retour à l'Accueil](../../accueil)
