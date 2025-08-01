---
title: "07 - Supprimer les rôles, groupes et utilisateurs"
description: ""
date: "2025-08-01"
version: "1"
---

### 📚 Table des matières

1. [Supprimer un rôle](#supprimer-un-rôle)  
2. [Supprimer un groupe](#supprimer-un-groupe)  
3. [Supprimer un utilisateur](#supprimer-un-utilisateur)  

---

## Supprimer un rôle

La suppression d'un rôle est une action définitive qui retire le rôle et toutes ses permissions associées du système. Cette action ne peut être effectuée que par les utilisateurs disposant de la permission **Gestion des permissions / Rôle / Suppression**.

### Étapes de suppression

- **Accéder à la gestion des rôles :** Naviguez vers la section "Rôles" via le menu principal de l'interface de gestion des droits.
- **Rechercher le rôle :** Utilisez la barre de recherche ou les filtres disponibles pour localiser le rôle que vous souhaitez supprimer dans la liste des rôles.
- **Supprimer le rôle :** Une fois le rôle identifié, cliquez sur l'action "Supprimer" associée à celui-ci. Un message de confirmation s'affiche pour vous demander de valider cette action.
- **Confirmer la suppression :** Validez la suppression. Le rôle sera alors définitivement retiré de la liste des rôles actifs.

### Conséquences de la suppression

- Le rôle ne sera plus disponible dans le système.
- Tous les utilisateurs et groupes auxquels ce rôle était attribué perdront les permissions associées à ce rôle. Leurs droits seront alors recalculés en fonction de leurs autres rôles personnels ou de groupe.
- Les actions effectuées sous ce rôle avant sa suppression resteront tracées dans l’historique des actions.

---

## Supprimer un groupe

La suppression d'un groupe d'utilisateurs est une action définitive qui retire le groupe et toutes ses attributions de rôles et de périmètres du système. Cette action ne peut être effectuée que par les utilisateurs disposant de la permission **Gestion des permissions / Groupe / Suppression**.

### Étapes de suppression

- **Accéder à la gestion des groupes :** Naviguez vers la section "Groupes" via le menu principal de l'interface de gestion des droits.
- **Rechercher le groupe :** Utilisez la barre de recherche ou les filtres disponibles pour localiser le groupe que vous souhaitez supprimer dans la liste des groupes.
- **Supprimer le groupe :** Une fois le groupe identifié, cliquez sur l'action "Supprimer" associée à celui-ci. Un message de confirmation s'affiche pour vous demander de valider cette action.
- **Confirmer la suppression :** Validez la suppression. Le groupe sera alors définitivement supprimé du système.

### Conséquences de la suppression

- Le groupe ne sera plus visible dans le système.
- Tous les utilisateurs qui étaient membres de ce groupe perdront les rôles et permissions hérités de ce groupe. Leurs droits seront alors recalculés en fonction de leurs rôles personnels et des autres groupes auxquels ils pourraient appartenir.
- Les actions effectuées par les membres du groupe avant sa suppression resteront tracées dans l’historique des actions.

---

## Supprimer un utilisateur

La suppression d'un utilisateur est une action irréversible. Seuls les utilisateurs disposant de la permission **Gestion des permissions / Utilisateurs / Suppression** peuvent effectuer cette opération.

### Étapes de suppression

- **Accéder à la gestion des utilisateurs :** Naviguez vers la section des utilisateurs via le menu principal de l'interface de gestion des droits.
- **Rechercher l'utilisateur :** Utilisez la barre de recherche ou les filtres pour localiser l'utilisateur que vous souhaitez supprimer.
- **Supprimer l'utilisateur :** Une fois l'utilisateur identifié, cliquez sur l'action "Supprimer" associée à son profil. Un message de confirmation s'affichera pour valider cette action.
- **Confirmer la suppression :** Validez la suppression. L'utilisateur est alors retiré de la liste des utilisateurs actifs et ne pourra plus se connecter.

### Conséquences de la suppression

- L'utilisateur n'aura plus accès à la plateforme. 
- Toutes les permissions et les accès liés à cet utilisateur seront révoqués.
- Les actions effectuées par l'utilisateur avant sa suppression resteront tracées dans l’historique des actions



### Pour aller plus loin
-> [08 - Bonnes pratiques](08-bonnes-pratiques)
   
[Retour à l'Accueil](../accueil)
