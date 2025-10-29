---
title: "05 - Attribution des droits"
description: ""
date: "2025-07-29"
version: "1"
---
### 📚 Table des matières
1. [Attribution directe d’un rôle à un utilisateur](#attribution-directe-dun-rôle-à-un-utilisateur)  
2. [Attribution indirecte via groupe d’utilisateurs](#attribution-indirecte-via-groupe-dutilisateurs)

---

Cette section explique comment attribuer des rôles — et donc des permissions — à un utilisateur.

> Pour cela, les rôles et les groupes d'utilisateurs doivent avoir été préalablement créés dans le système.

---

## 🔒 Règles d'assignation à connaître

L'attribution des rôles et groupes suit des **règles métier strictes** basées sur la hiérarchie des organisations. Ces règles garantissent la cohérence et la sécurité des droits d'accès.

### Hiérarchie d'organisations - Exemple

Pour comprendre les règles, voici un exemple de hiérarchie typique :

```
Organisation Centre de Formation (CFA)
└── Organisation Parent
    ├── Organisation Enfant A
    └── Organisation Enfant B
```

**Relations** :
- `Organisation Centre de Formation` est **parent** de `Organisation Parent`
- `Organisation Parent` est **parent** de `Organisation Enfant A` et `Organisation Enfant B`
- Les organisations enfants peuvent voir "vers le haut" (parents) mais pas "vers le bas" (enfants d'autres branches)

---

### 📋 Règles pour Utilisateur → Rôle

Lorsque vous attribuez un rôle personnel à un utilisateur, **3 règles** doivent être respectées simultanément :

#### ✅ Règle 1 : Parentalité d'organisation du rôle

Le rôle **DOIT** provenir de l'organisation responsable de l'utilisateur ou d'une **organisation parente**.

**Exemple** : Si l'utilisateur appartient à `Organisation Parent`

| Rôle provenant de | Résultat | Explication |
|-------------------|----------|-------------|
| Organisation Centre de Formation | ✅ Autorisé | Organisation parente |
| Organisation Parent | ✅ Autorisé | Même organisation |
| Organisation Enfant A | ❌ Refusé | Organisation enfant (non autorisée) |

---

#### ✅ Règle 2 : Périmètre du sujet (utilisateur)

L'organisation assignée au rôle **DOIT** correspondre à l'organisation responsable de l'utilisateur ou à l'une de ses **organisations enfants**.

**Exemple** : Si l'utilisateur appartient à `Organisation Parent`

| Organisation assignée | Résultat | Explication |
|----------------------|----------|-------------|
| Organisation Parent | ✅ Autorisé | Organisation responsable de l'utilisateur |
| Organisation Enfant A | ✅ Autorisé | Organisation enfant de l'utilisateur |
| Organisation Centre de Formation | ❌ Refusé | Organisation parente (hors périmètre) |

> 💡 **Pourquoi ?** Un utilisateur ne peut pas se voir attribuer de droits sur des organisations "au-dessus" de lui dans la hiérarchie.

---

#### ✅ Règle 3 : Périmètre du rôle

L'organisation assignée **DOIT** appartenir au périmètre du rôle (organisation responsable du rôle ou ses organisations enfants).

**Exemple** : Si le rôle provient de `Organisation Parent`

| Organisation assignée | Résultat | Explication |
|----------------------|----------|-------------|
| Organisation Parent | ✅ Autorisé | Organisation responsable du rôle |
| Organisation Enfant A | ✅ Autorisé | Organisation enfant du rôle |
| Organisation Centre de Formation | ❌ Refusé | Organisation parente (hors périmètre du rôle) |

---

#### 🌳 Arbre de décision : Puis-je assigner ce rôle ?

```
┌─────────────────────────────────────────────────┐
│ Je veux assigner un rôle à un utilisateur       │
└─────────────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────┐
│ Le rôle provient-il de l'organisation de        │
│ l'utilisateur ou d'une organisation PARENTE ?   │
└─────────────────────────────────────────────────┘
         OUI │                          │ NON
             ▼                          ▼
┌──────────────────────────┐    ❌ REFUSÉ
│ L'organisation assignée  │    (Règle 1 non respectée)
│ est-elle l'organisation  │
│ de l'utilisateur ou      │
│ une organisation ENFANT? │
└──────────────────────────┘
         OUI │                          │ NON
             ▼                          ▼
┌──────────────────────────┐    ❌ REFUSÉ
│ L'organisation assignée  │    (Règle 2 non respectée)
│ appartient-elle au       │
│ périmètre du rôle ?      │
└──────────────────────────┘
         OUI │                          │ NON
             ▼                          ▼
    ✅ AUTORISÉ              ❌ REFUSÉ
                            (Règle 3 non respectée)
```

---

#### ⚠️ Règle 4 : Rôles non assignables

Certains rôles **ne peuvent pas être assignés** car ils sont administrés par Papaours.

| Rôle                       | Peut être assigné ? | Explication |
|----------------------------|---------------------|-------------|
| Administrateur Papaours    | ❌ | Rôle système réservé à Papaours |
| Gestionnaire administratif | ✅ | Rôle assignable normalement |
| Formateur                  | ✅ | Rôle assignable normalement |

---

### 📋 Règles pour Utilisateur → Groupe

Lorsque vous ajoutez un utilisateur à un groupe, des règles spécifiques s'appliquent :

#### ⚠️ Règle 1 : Groupes non modifiables

Certains groupes **ne peuvent pas être modifiés** car ils sont administrés par Papaours.

| Groupe                             | Peut ajouter des membres ? | Type |
|------------------------------------|---------------------------|------|
| Administrateur Papaours            | ❌ | Groupe système Papaours |
| Administrateur centre de formation | ✅ | Groupe standard Papaours |
| Formateurs CFA Paris               | ✅ | Groupe créé par le CFA |

---

#### 🚫 Règle 2 : Interdiction de s'auto-assigner

Un utilisateur **NE PEUT PAS** :
- S'ajouter lui-même à un groupe
- Se retirer lui-même d'un groupe
- Modifier les rôles d'un groupe auquel il appartient

**Exemples** :

| Action | Résultat |
|--------|----------|
| Alice s'ajoute au groupe "Formateurs" | ❌ Interdit |
| Alice ajoute Bob au groupe "Formateurs" | ✅ Autorisé |
| Alice (membre du groupe) modifie les rôles du groupe | ❌ Interdit |

> 💡 **Pourquoi ?** Cette règle empêche les utilisateurs de s'accorder eux-mêmes des droits supplémentaires.

---

#### ✅ Règle 3 : Périmètre via groupe

Lorsqu'un utilisateur est ajouté à un groupe, les **mêmes règles de périmètre** que pour Utilisateur → Rôle s'appliquent pour **tous les rôles du groupe**.

**Exemple** : Un groupe possède 2 rôles avec différents périmètres

| Utilisateur | Groupe | Rôles du groupe | Résultat | Explication |
|-------------|--------|-----------------|----------|-------------|
| Org Parent | Groupe Org Parent | Rôle Parent sur Org Parent | ✅ | Toutes les règles respectées |
| Org Parent | Groupe Org Enfant A | Rôle Enfant A sur Enfant A | ❌ | Rôle enfant invalide (Règle 1) |
| Org Enfant A | Groupe Org Parent | Rôle Parent sur Org Parent | ❌ | Organisation assignée hors périmètre (Règle 2) |

---

### 📖 Référence technique complète

> Pour une documentation exhaustive avec tous les cas d'usage, exemples détaillés et schémas, consultez l'[Annexe A - Référence technique des règles d'assignation](09-regles-assignation.md).

---

## Attribution directe d'un rôle à un utilisateur

L'attribution directe d'un rôle à un utilisateur est une méthode fondamentale pour la gestion des accès et des permissions au sein de notre système. Cette approche permet de définir précisément les actions qu'un utilisateur est autorisé à effectuer. En attribuant un rôle personnel, nous accordons à cet utilisateur un ensemble prédéfini de droits, facilitant ainsi le contrôle et la supervision de l'accès aux ressources et aux fonctionnalités de l'application.

### Étapes pour attribuer un rôle personnel à un utilisateur :

1. **Accéder à la modification de l’utilisateur**
   Pour modifier un utilisateur, vous devez disposer de la permission **Gestion des utilisateurs / Écriture**. Deux chemins sont possibles pour accéder à l’édition d’un utilisateur :
   - Depuis la **page de détail** de l’utilisateur, en cliquant sur le bouton **Modifier**
![Modifier un utilisateur depuis la page détail d'un utilisateur](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/utilisateur/modifier-utilisateur-depuis-detail.png "948*228")

   - Depuis la **liste des utilisateurs**, en cliquant sur le bouton **Modifier** situé sur la ligne correspondante
![Modifier un utilisateur depuis la liste des utilisateurs](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/utilisateur/modifier-utilisateur-depuis-liste.png "948*125")

2. **Choix du rôle** :  
   Dans la liste **Rôle personnel**, sélectionnez le rôle souhaité parmi les rôles disponibles dans le système en recherchant via le nom ou dans la liste déroulante.
![Choix du rôle](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/utilisateur/attribuer-role-personnel.png "980*210")
   
3. **Périmètre** :  
   Le rôle personnel est automatiquement attribué aux organisations de l’utilisateur qui effectue l’action.
![Rôle personnel attribué](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/utilisateur/role-personnel-attribue.png "980*174")

   Le périmetre de ce rôle est modifiable lorsque vous cliquez sur le bouton **Modifier le périmetre(x)**
   Retrouvez dans la section [06 - Modifier les droits d’accès](06-modifier-les-droits-dacces), Modifier un périmetre, la procédure pour modifier un périmètre.

4. **Confirmation** :  
   Cliquez sur **Modifier l'utilisateur** pour valider l'attribution.

Cette méthode offre une grande flexibilité et un contrôle précis sur les accès, permettant d'adapter les permissions en fonction des besoins spécifiques de chaque utilisateur et de garantir la sécurité et l'intégrité des données et des opérations du système.

---

## Attribution indirecte via groupe d’utilisateurs

Dans le cadre de la gestion des accès et des permissions, une méthode efficace consiste à attribuer des droits de manière **indirecte via des groupes d'utilisateurs**. Cela consiste à créer des groupes regroupant des utilisateurs ayant des besoins d’accès similaires, puis à attribuer les droits à ces groupes.

### Avantages :

- **Simplicité** : un seul paramétrage pour tous les membres du groupe
- **Maintenance facilitée** : ajout ou retrait rapide d’utilisateurs
- **Organisation claire** : regroupement par rôles, projets, départements…
- **Renforcement de la sécurité** : moins d’erreurs de configuration

### Deux méthodes d’attribution :

#### 1. Depuis la page de modification d’un utilisateur

1. Accédez à la modification de l’utilisateur
![Menu d'accès à la modification d'un utilisateur](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/utilisateur/modifier-utilisateur-depuis-detail.png "980*236")

2. **Choix du groupe** :  
   Dans la liste **groupe d’utilisateurs**, sélectionnez le groupe souhaité
![liste des groupes associables à un utilisateur](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/groupe/liste-groupe-utilisateur.png "")

3. **Périmètre** :  
   Hérité du groupe utilisateur sélectionné
4. **Confirmation** :  
   Cliquez sur **Modifier l'utilisateur**

#### 2. Depuis la page de modification d’un groupe utilisateur

1. Accédez à la modification du groupe utilisateur
![Menu d'accès à la modification d'un groupe](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/groupe/modifier-un-groupe.png "980*667")

2. **Choix de l’utilisateur** :  
   Recherchez l’utilisateur via son nom/prénom dans la section **Membres du groupe** puis cliquez sur **Ajouter au groupe**
![liste des utilisateurs associables à un groupe](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/groupe/ajouter-utilisateur-au-groupe.png "980*277")

3. **Confirmation** :  
   Cliquez sur **Modifier le groupe**
   L'utilisateur appartient à présent au groupe

---

### En résumé

L'attribution indirecte de permissions via des groupes utilisateurs est une **pratique recommandée** pour une gestion structurée et sécurisée des droits. Elle :

- Simplifie les opérations
- Facilite la maintenance
- Améliore l’organisation
- Renforce la sécurité globale du système

-> Retrouvez les bonnes pratiques de gestion dans la section [08 - Bonnes pratiques](08-bonnes-pratiques)


### Pour aller plus loin
- [Annexe A - Référence technique des règles d'assignation →](09-regles-assignation.md)
- [06 - Modifier les rôles, groupes et utilisateurs →](06-modifier-les-droits-dacces.md)

[Retour à l'Accueil](../accueil)
