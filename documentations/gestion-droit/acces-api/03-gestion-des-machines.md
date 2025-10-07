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

   ![Screenshot à placer : Menu de navigation avec "Gestion des droits" > "Machines"]

2. **Ouvrir le formulaire de création** : Cliquez sur le bouton **Créer une machine** (icône plus).

   ![Screenshot à placer : Page de liste des machines avec le bouton "Créer une machine"]

3. **Renseigner les informations de la machine** :
    - **Nom** : Saisissez un nom descriptif pour identifier la machine (exemple : "Service de facturation", "API
      Partenaire XYZ", etc.).
    - **Description** : Ajoutez une description détaillée expliquant le rôle et l'usage de cette machine.

   ![Screenshot à placer : Formulaire de création de machine avec les champs "Nom" et "Description"]

4. **Attribuer les rôles et groupes** : Sélectionnez les rôles et groupes qui définissent ce que la machine sera
   autorisée à
   faire sur la plateforme.

   ![Screenshot à placer : Section d'attribution des rôles avec liste de rôles disponibles]

5. **Définir le périmètre** : Associé l'organisation qui sera utilisée par la machine lors de son utilisation sur nos
   APIs.

   ![Screenshot à placer : Section de définition du périmètre avec sélection d'organisations]

6. **Créer la machine** : Cliquez sur le bouton **Créer** pour finaliser la création de la machine.

### Après la création

Une fois la machine créée, vous serez automatiquement redirigé vers sa page de détail. À partir de là, vous pourrez :

- Consulter les informations de la machine
- Modifier ses rôles et permissions si nécessaire
- **Créer des clés API** pour permettre à vos systèmes de s'authentifier avec les permissions de cette machine

> ℹ️ **Note** : Une machine nouvellement créée ne possède aucune clé API. Vous devrez en créer au moins une pour que vos
> systèmes puissent utiliser cette machine.

---

## Consulter une machine

Cette section explique comment visualiser les informations d'une machine existante.

### Accès à la liste des machines

1. **Accéder à la gestion des machines** : Naviguez vers la section *Machines* du menu *Gestion des droits*.
2. **Parcourir la liste** : La page affiche toutes les machines auxquelles vous avez accès.

![Screenshot à placer : Liste des machines avec colonnes Nom, Description, Date de création]

### Consulter le détail d'une machine

1. **Sélectionner une machine** : Cliquez sur la ligne de la machine que vous souhaitez consulter.
2. **Visualiser les informations** : La page de détail affiche :
    - **Informations générales** : Nom, description, date de création
    - **Rôles et groupes** : Liste des rôles et groupes attribués à la machine
    - **Périmètre** : Organisation à laquelle la machine est associée
    - **Clés API** : Liste des clés API associées à cette machine

![Screenshot à placer : Page de détail d'une machine avec toutes les sections]

### Informations disponibles

#### Informations générales

- **Nom** : Le nom de la machine
- **Description** : Description détaillée de son usage
- **Date de création** : Quand la machine a été créée
- **Créé par** : Utilisateur ayant créé la machine

#### Rôles et groupes

Cette section liste tous les rôles attribués à la machine. Chaque rôle définit un ensemble de permissions qui
déterminent
ce que la machine peut faire sur la plateforme au travers des droits d'accès.

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

2. **Ouvrir le formulaire de modification** : Cliquez sur le bouton **Modifier** (icône crayon).

   ![Screenshot à placer : Page de détail avec le bouton "Modifier"]

3. **Modifier les informations** : Vous pouvez modifier :
    - **Nom** : Changez le nom de la machine
    - **Description** : Mettez à jour la description
    - **Rôles** : Ajoutez ou retirez des rôles
    - **Périmètre** : Modifiez les organisations accessibles

   ![Screenshot à placer : Formulaire de modification avec tous les champs]

4. **Enregistrer les modifications** : Cliquez sur le bouton **Enregistrer** pour appliquer les changements.

### Conséquences de la modification

> ⚠️ **Attention** : Modifier les rôles ou le périmètre d'une machine affecte **toutes les clés API** associées à cette
> machine.

- **Ajout de permissions** : Toutes les clés API de la machine pourront effectuer de nouvelles actions.
- **Retrait de permissions** : Les clés API ne pourront plus effectuer certaines actions, ce qui peut entraîner des
  erreurs dans vos systèmes.

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
2. Les permissions restent configurées mais aucune clé ne peut être utilisée

#### Suppression définitive

> ⚠️ **Attention** : La suppression d'une machine est irréversible et supprime également toutes ses clés API.

Pour supprimer une machine :

1. Assurez-vous qu'aucun système n'utilise plus les clés API de cette machine
2. Sur la page de détail, cliquez sur **Supprimer**
3. Confirmez la suppression

---

### Pour aller plus loin

- [Créer des clés API pour votre machine →](04-gestion-des-cles-api.md)
- [Bonnes pratiques de sécurité →](05-securite-et-bonnes-pratiques.md)

[Retour à l'Accueil](../accueil)
