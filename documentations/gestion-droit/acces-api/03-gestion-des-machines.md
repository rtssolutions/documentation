---
title: "03 - Gestion des machines"
description: "Créer, consulter et modifier des machines dans Papaours"
date: "2025-10-07"
version: "1"
---

## 📚 Table des matières

1. [Créer une machine](#créer-une-machine)
2. [Consulter une machine](#consulter-une-machine)
3. [Modifier une machine](#modifier-une-machine)

---

## Créer une machine

Avant de pouvoir créer des clés API, vous devez d'abord créer une machine. Cette section explique comment créer une
nouvelle machine dans le système.

### Prérequis

Seuls les utilisateurs disposant de la permission **Gestion des droits / Machines / Écriture** peuvent créer de
nouvelles machines.

### Étapes de création

1. **Accéder à la gestion des machines** : Naviguez vers la section *Machines* du menu *Gestion des droits*.
   ![Menu machine](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/03/menu%20machine.png "319×211")

2. **Ouvrir le formulaire de création** : Cliquez sur le bouton **Créer une machine** (icône plus).

   ![Bouton création](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/03/Creation%20machine%20bouton%20liste.png)

3. **Renseigner les informations de la machine** :
    - **Nom** : Saisissez un nom descriptif pour identifier la machine (exemple : "Service de facturation", "API
      Partenaire XYZ", etc.).
    - **Description** : Ajoutez une description détaillée expliquant le rôle et l'usage de cette machine.

4. **Définir l'organisation de rattachement** : Choisissez l'organisation unique à laquelle la machine sera rattachée.
   Cette organisation peut être modifiée ultérieurement si nécessaire. Par défaut, l'organisation est celle que l'utilisateur a sélectionnée.

   ![Modification organisation](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/03/Modification%20organisation.png "656×343")

5. **Attribuer les rôles et groupes** : Sélectionnez les rôles et groupes qui déterminent les droits d'accès de la
   machine sur la plateforme. Les droits d'accès sont automatiquement calculés à partir des permissions et opérations
   contenues dans ces rôles et groupes.

   > ⚠️ **Important** : Les droits d'accès issus d'un rôle ou groupe ne seront effectifs que si l'organisation de
   > rattachement de la machine est incluse dans le périmètre de ce rôle/groupe.

---

### 🔒 Règles d'assignation pour les machines

L'attribution des rôles et groupes aux machines suit les **mêmes règles** que pour les utilisateurs, avec des restrictions supplémentaires.

#### 📋 Règles Machine → Rôle

Les **3 règles** de l'assignation Utilisateur → Rôle s'appliquent également aux machines :

1. **Parentalité d'organisation du rôle** : Le rôle DOIT provenir de l'organisation de la machine ou d'une organisation parente
2. **Périmètre du sujet (machine)** : L'organisation assignée DOIT être l'organisation de la machine ou une organisation enfant
3. **Périmètre du rôle** : L'organisation assignée DOIT appartenir au périmètre du rôle

**Exemple** : Si la machine appartient à `Organisation Parent`

| Rôle provenant de | Organisation assignée | Résultat | Explication |
|-------------------|----------------------|----------|-------------|
| Organisation Centre de Formation | Organisation Parent | ✅ | Toutes les règles respectées |
| Organisation Parent | Organisation Enfant A | ✅ | Machine peut agir sur org enfant |
| Organisation Enfant A | Organisation Enfant A | ❌ | Rôle enfant non autorisé |

---

#### ⚠️ Règle supplémentaire : Machines administrées par Papaours

Certaines machines **système** sont administrées par Papaours et **ne peuvent pas être modifiées**.

| Type de machine | Peut être modifiée ? | Peut assigner des rôles ? |
|-----------------|---------------------|---------------------------|
| Machine système Papaours | ❌ | ❌ |
| Machine créée par votre CFA | ✅ | ✅ |

**Exemples** :

| Machine | Type | Actions possibles |
|---------|------|-------------------|
| "Machine Système" | Machine Papaours | ❌ Aucune modification possible |
| "API CFA Production" | Machine du CFA | ✅ Tous droits modifiables |
| "Service Facturation" | Machine du CFA | ✅ Tous droits modifiables |

---

#### 📋 Règles Machine → Groupe

Lorsqu'une machine est ajoutée à un groupe, les **mêmes règles de périmètre** que pour Machine → Rôle s'appliquent pour **tous les rôles du groupe**.

| Machine | Groupe | Rôles du groupe | Résultat | Explication |
|---------|--------|-----------------|----------|-------------|
| Org Parent | Groupe Org Parent | Rôle Parent sur Parent | ✅ | Toutes les règles respectées |
| Org Parent | Groupe Org Enfant A | Rôle Enfant A sur Enfant A | ❌ | Rôle enfant invalide |
| Machine Système (Papaours) | Groupe quelconque | Rôles quelconques | ❌ | Machine non modifiable |

---

### 📖 Référence technique complète

> Pour une documentation exhaustive sur les règles d'assignation des machines avec tous les cas d'usage et exemples détaillés, consultez l'[Annexe A - Référence technique des règles d'assignation](../09-regles-assignation.md#machine--rôle).

---

6. **Créer la machine** : Cliquez sur le bouton **Créer** pour finaliser la création de la machine.

![Page de creation](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/03/Cre%CC%81ation%20d%27une%20machine.png)


### Après la création

Une fois la machine créée, vous serez automatiquement redirigé vers sa page de détail. À partir de là, vous pourrez :

- Consulter les informations de la machine
- Modifier ses rôles et groupes si nécessaire
- Modifier son organisation de rattachement si nécessaire
- **Créer des clés API** pour permettre à vos systèmes de s'authentifier avec les droits d'accès de cette machine

> ℹ️ **Note** : Une machine nouvellement créée ne possède aucune clé API. Vous devrez en créer au moins une pour que vos
> systèmes puissent utiliser cette machine.

---

## Consulter une machine

Cette section explique comment visualiser les informations d'une machine existante.

### Accès à la liste des machines

1. **Accéder à la gestion des machines** : Naviguez vers la section *Machines* du menu *Gestion des droits*.
2. **Parcourir la liste** : La page affiche toutes les machines auxquelles vous avez accès.

![Liste des machines](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/03/Liste%20machines.png)

### Consulter le détail d'une machine

1. **Sélectionner une machine** : Cliquez sur la ligne de la machine que vous souhaitez consulter.
2. **Visualiser les informations** : La page de détail affiche :
    - **Informations générales** : Nom, description, date de création
    - **Organisation de rattachement** : Organisation unique à laquelle la machine est rattachée
    - **Rôles et groupes** : Liste des rôles et groupes attribués à la machine (avec leur périmètre d'organisations)
    - **Clés API** : Liste des clés API associées à cette machine

![Détail d'une machine](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/03/Detail%20d%27une%20machine.png)

### Informations disponibles

#### Informations générales

- **Nom** : Le nom de la machine
- **Description** : Description détaillée de son usage
- **Date de création** : Quand la machine a été créée
- **Créé par** : Utilisateur ayant créé la machine

#### Rôles et groupes

Cette section liste tous les rôles et groupes attribués à la machine :
- Les **rôles** contiennent des permissions avec des opérations (lecture, écriture, suppression, archivage)
- Les **groupes** rassemblent plusieurs rôles
- Chaque rôle/groupe a un **périmètre** (liste d'organisations sur lesquelles il s'applique)
- Les **droits d'accès** sont automatiquement générés en combinant : organisation(s) du périmètre + permission + opération

> ⚠️ **Important** : Un rôle ou groupe n'accorde des droits d'accès effectifs que si l'organisation de rattachement de la machine est incluse dans son périmètre.

> ℹ️ **À noter** : Certains rôles et groupes sont administrés par Papaours et ne peuvent pas être assignés (ex: "Administrateur Papaours"). De même, certaines machines système administrées par Papaours ne peuvent pas être modifiées. Consultez l'[Annexe A - Référence technique](../09-regles-assignation.md) pour plus de détails.

#### Clés API

Cette section affiche toutes les clés API associées à la machine. Pour chaque clé, vous pouvez voir :

- Son libellé
- Son statut (Active ou Inactive)

Consultez la section [Gestion des clés API](04-gestion-des-cles-api.md) pour plus de détails.

---

## Modifier une machine

Cette section détaille comment modifier les informations et les permissions d'une machine existante.

### Prérequis

Seuls les utilisateurs disposant de la permission **Gestion des droits / Machines / Écriture** peuvent modifier des
machines.

### Étapes de modification

1. **Accéder à la page de détail** : Depuis la liste des machines, cliquez sur la machine que vous souhaitez modifier.

2. **Ouvrir le formulaire de modification** : Cliquez sur le bouton **Modifier** en haut à droite de la page (icône crayon).

3. **Modifier les informations** : Vous pouvez modifier :
    - **Nom** : Changez le nom de la machine
    - **Description** : Mettez à jour la description
    - **Organisation de rattachement** : Modifiez l'organisation unique de rattachement
    - **Rôles et groupes** : Ajoutez ou retirez des rôles et groupes

   > ⚠️ **Machines administrées par Papaours** : Les machines système administrées par Papaours ne peuvent pas être modifiées. Seules les machines créées par votre organisation peuvent être modifiées.

4. **Enregistrer les modifications** : Cliquez sur le bouton **Enregistrer** pour appliquer les changements.

![Modification machine](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/03/Modification%20machine.png)


### Conséquences de la modification

> ⚠️ **Attention** : Modifier les rôles, groupes ou l'organisation de rattachement d'une machine affecte **toutes les clés API** associées à cette machine, car cela modifie les droits d'accès disponibles.

- **Ajout de rôles/groupes** : Toutes les clés API de la machine pourront effectuer de nouvelles actions (si l'organisation de rattachement est dans le périmètre).
- **Retrait de rôles/groupes** : Les clés API ne pourront plus effectuer certaines actions, ce qui peut entraîner des erreurs dans vos systèmes.
- **Changement d'organisation** : Les droits d'accès issus des rôles/groupes peuvent devenir inactifs si la nouvelle organisation de rattachement n'est plus dans leur périmètre.

### Conseils avant modification

- **Identifiez les impacts** : Listez tous les systèmes utilisant les clés API de cette machine.
- **Testez dans un environnement de test** : Si possible, testez les changements avec une clé de test avant de modifier
  la machine de production.
- **Communiquez les changements** : Informez les équipes techniques concernées des modifications de permissions.
- **Documentez** : Conservez une trace des modifications effectuées et de leur raison.

### Désactivation vs Suppression

#### Désactivation temporaire

Pour désactiver temporairement une machine sans perdre sa configuration :

1. Désactivez toutes ses clés API (voir [Modifier une clé API](04-gestion-des-cles-api.md#modifier-une-clé-api))
2. Les rôles et groupes restent configurés mais aucune clé ne peut être utilisée

#### Suppression définitive

> ⚠️ **Attention** : La suppression d'une machine est irréversible et supprime également toutes ses clés API.

Pour supprimer une machine :

1. Assurez-vous qu'aucun système n'utilise plus les clés API de cette machine
2. Sur la page de détail, cliquez sur **Supprimer**
3. Confirmez la suppression

---

### Pour aller plus loin

- [Annexe A - Référence technique des règles d'assignation →](../09-regles-assignation.md)
- [Créer des clés API pour votre machine →](04-gestion-des-cles-api.md)
- [Bonnes pratiques de sécurité →](05-securite-et-bonnes-pratiques.md)

[Retour à l'Accueil](../../accueil)
