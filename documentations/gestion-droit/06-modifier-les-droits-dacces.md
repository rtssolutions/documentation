---
title: "06 - Modifier des rôles, groupes et utilisateurs"
description: "Modification des rôles, groupes, utilisateurs et périmètres dans Papaours"
date: "2025-08-01"
version: "1"
---

## 📚 Table des matières

1. [Modifier un rôle](#modifier-un-rôle)  
2. [Modifier un groupe](#modifier-un-groupe)  
3. [Modifier un utilisateur](#modifier-un-utilisateur)  
4. [Modifier un périmètre](#modifier-un-périmètre)  
5. [Modifier ses droits](#modifier-ses-droits)

---

## Modifier un rôle

Cette section détaille la procédure à suivre pour modifier un rôle existant au sein du système. La modification des rôles est une fonction cruciale pour la gestion des accès et des permissions, garantissant que les utilisateurs disposent des droits appropriés pour accomplir leurs tâches.

Avant de procéder à la modification d'un rôle, assurez-vous d'avoir les privilèges d'administrateur nécessaires. Seuls les utilisateurs disposant de la permission **Écrire un rôle** sont autorisés à modifier les rôles et leurs permissions associées.

> ⚠️ **Rôles administrés par Papaours** : Certains rôles sont administrés par Papaours (ex: "Administrateur Papaours") et ne peuvent pas être modifiés. Consultez la section [09 - Règles d'assignation](09-regles-assignation.md#règle-4--rôles-non-assignables) pour plus de détails.

### Étapes de modification

1. **Accéder à la gestion des rôles** : Naviguez vers la section rôles du menu Gestion des droits.
2. **Sélectionner le rôle à modifier** : Recherchez le rôle souhaité dans la liste. Utilisez les options de recherche pour le localiser rapidement.
3. **Éditer les permissions** : Cliquez sur l’action **Modifier**. Vous pourrez alors cocher/décocher les permissions attribuées.
4. **Sauvegarder les modifications** : Cliquez sur le bouton de confirmation pour enregistrer les changements.

### Conséquences de la modification

Modifier un rôle peut impacter tous les utilisateurs et groupes auxquels il est rattaché. Il est donc essentiel d’informer les utilisateurs concernés et de vérifier les effets des modifications sur leurs accès.

### Conseils additionnels

- **Documenter les modifications** pour assurer un bon suivi.
- **Tester les droits modifiés** avec un utilisateur concerné pour s’assurer du bon fonctionnement.

---

## Modifier un groupe

Cette section détaille la procédure à suivre pour modifier un groupe existant au sein du système. La modification des groupes est une fonction cruciale pour la gestion des accès et des permissions, garantissant que les utilisateurs disposent des droits appropriés pour accomplir leurs tâches.

Avant de procéder à la modification d'un groupe, assurez-vous d'avoir les privilèges d'administrateur nécessaires. Seuls les utilisateurs disposant de la permissions Gestion des permissions / Groupe / Écriture sont autorisés à modifier les groupes et les données associées.

> ⚠️ **Groupes administrés par Papaours** : Certains groupes sont administrés par Papaours et ont des restrictions spécifiques. Par exemple, le groupe "Administrateur Papaours" ne peut pas être modifié. D'autres groupes administrés par Papaours permettent de modifier uniquement la liste des utilisateurs, mais pas le nom ni les rôles. Consultez la section [09 - Règles d'assignation](09-regles-assignation.md#règle-3--restrictions-sur-les-groupes-administrés-par-papaours) pour plus de détails.

### Étapes de modification

- **Accéder à la gestion des groupes** : Naviguez vers la section groupes du menu gestion des groupes dans l'interface.  
- **Sélectionner le groupe à modifier** : Identifiez et sélectionnez le groupe que vous souhaitez modifier dans la liste des groupes disponibles. Vous pouvez utiliser les options de recherche pour localiser rapidement le groupe souhaité.  
- **Éditer les informations du groupe** : Une fois le groupe sélectionné, vous avez la possibilité de modifier le groupe en cliquant sur l’action Modifier. Vous pouvez modifier tous les attributs du groupe :  
  - Le nom  
  - La description  
  - Les rôles associés  
  - Les utilisateurs constituant le groupe  
- **Sauvegarder les modifications** : Après avoir apporté les modifications nécessaires, assurez-vous de les sauvegarder. Un bouton “Modifier le groupe” est disponible pour confirmer les changements.

### Conséquences de la modification

Il est important de noter que la modification d'un groupe peut avoir des impacts sur les utilisateurs qui y sont associés. Assurez-vous de bien comprendre les conséquences de vos modifications avant de les appliquer, et de communiquer les changements aux utilisateurs concernés si nécessaire.

Il n'est pas nécessaire pour les utilisateurs concernés de se déconnecter et de se reconnecter à l'application pour que les permissions soient prises en compte ; un simple rafraîchissement de la page suffit.

### Tester les modifications

Après avoir modifié un groupe, testez les changements avec un compte utilisateur affecté à ce groupe pour vous assurer que les permissions fonctionnent comme prévu. 

---

## Modifier un utilisateur

Cette section détaille la procédure à suivre pour modifier un utilisateur existant au sein du système.

Avant de procéder à la modification d'un utilisateur, assurez-vous d'avoir les privilèges d'administrateur nécessaires. Seuls les utilisateurs disposant de la permission **Gestion des permissions / Utilisateurs / Écriture** sont autorisés à modifier les utilisateurs et les données associées.

### Étapes de modification

- **Accéder à la gestion des utilisateurs** : Naviguez vers la section *Utilisateurs* du menu *Gestion des utilisateurs* dans l'interface.  
- **Sélectionner l’utilisateur à modifier** : Identifiez et sélectionnez l’utilisateur que vous souhaitez modifier dans la liste des utilisateurs disponibles. Vous pouvez utiliser les options de recherche pour localiser rapidement l’utilisateur souhaité.  
- **Éditer les informations de l’utilisateur** : Une fois l’utilisateur sélectionné, vous avez la possibilité de modifier l’utilisateur en cliquant sur l’action **Modifier**. Vous pouvez modifier les attributs suivants :  
  - Courriel  
  - Nom  
  - Prénom  
  - Téléphone  
  - Les groupes associés  
  - Les rôles personnels et leurs périmètres  
- **Sauvegarder les modifications** : Après avoir apporté les modifications nécessaires, assurez-vous de les sauvegarder. Un bouton **Modifier l’utilisateur** est disponible pour confirmer les changements.

### Conséquences de la modification

Il est important de noter que la modification d'un utilisateur peut avoir des impacts. Assurez-vous de bien comprendre les conséquences de vos modifications avant de les appliquer, et de communiquer les changements à l’utilisateur concerné si nécessaire.

>Il n'est pas nécessaire pour l’utilisateur concerné de se déconnecter et de se reconnecter à l'application pour que les permissions soient prises en compte ; un simple rafraîchissement de la page suffit.

---

## Modifier un périmètre

Cette section détaille la procédure à suivre pour modifier le périmètre d’application d’un rôle existant au sein du système.

Avant de procéder à la modification d'un périmètre, assurez-vous d'avoir les privilèges d'administrateur nécessaires.  

- Pour modifier le périmètre d’un rôle personnel attribué à un utilisateur, il faut disposer de la permission **Gestion des permissions / Utilisateurs / Écriture**  
- Pour modifier le périmètre d’un rôle attribué à un groupe, il faut disposer de la permission **Gestion des permissions / Groupe / Écriture**

### Étapes de modification

- **Accéder à la modification d’un périmètre** : Naviguer vers la modification d’un groupe ou d’un utilisateur, puis dans la section *Rôles du groupe* ou *Rôles personnels*.  
- **Sélectionner le périmètre à modifier** : Identifiez et sélectionnez le périmètre que vous souhaitez modifier dans la liste des périmètres disponibles. Cliquez sur le bouton **Modifier le périmètre** du rôle que vous souhaitez modifier.  
- **Éditer le périmètre** :  
  - Utilisez la barre de recherche pour rechercher une organisation en particulier puis cliquez sur l’organisation de la liste déroulante pour l’ajouter au périmètre.  
  - Utilisez les petites croix à côté de chaque organisation pour la retirer du périmètre.  
  - Si vous souhaitez positionner l’organisation mère de votre organisation dans le périmètre, utilisez l’interrupteur à côté du nom de cette organisation.  
  - Positionner l’organisation mère dans le périmètre revient à donner l’accès à toutes les organisations.  
    Vous ne pouvez associer d’autres organisations dans le périmètre si vous l’associez à l’organisation mère.  
  - Veuillez noter qu’un périmètre doit avoir **au moins une organisation associée**.  
- **Sauvegarder les modifications** : Après avoir apporté les modifications nécessaires, assurez-vous de les sauvegarder.  
  Un bouton **Enregistrer** est disponible pour confirmer les changements.  
  Après enregistrement, le bouton **Modifier le périmètre** vous indique entre parenthèses le **nombre d’organisations associées** au périmètre du rôle.

### Conséquences de la modification

Il est important de noter que la modification d'un périmètre peut avoir des impacts.  
Assurez-vous de bien comprendre les conséquences de vos modifications avant de les appliquer, et de communiquer les changements aux utilisateurs concernés si nécessaire.

>Il n'est pas nécessaire pour les utilisateurs concernés de se déconnecter et de se reconnecter à l'application pour que les permissions soient prises en compte ; un simple rafraîchissement de la page suffit.

---

## Modifier ses droits

L’application de gestion des droits au sein de la plateforme **Papaours** ne permet pas de modifier ses propres permissions.  
Elle est conçue avec une restriction fondamentale : **elle n'autorise pas les utilisateurs à modifier leurs propres droits**.  
Cette limitation est une **mesure de sécurité essentielle** et une pratique courante dans la gestion des accès et des identités (*IAM - Identity and Access Management*) au sein des systèmes d'information robustes.

### Cette approche garantit plusieurs points critiques :

- **Prévention des escalades de privilèges non autorisées**  
  Si un utilisateur pouvait modifier ses propres droits, il pourrait potentiellement s'attribuer des permissions plus élevées (administrateur, super-utilisateur, etc.) sans supervision ou validation. Cela créerait une faille de sécurité majeure.

- **Maintien de l'intégrité du système**  
  La modification des droits est une opération sensible qui doit être effectuée par des entités (administrateurs désignés, processus automatisés) distinctes de l'utilisateur concerné, afin d'éviter des configurations erronées ou malveillantes qui pourraient compromettre la stabilité ou la sécurité de la plateforme.

- **Conformité et auditabilité**  
  Dans de nombreux cadres réglementaires (RGPD), il est crucial de pouvoir tracer qui a modifié quels droits et quand.  
  Permettre l'auto-modification rendrait cette traçabilité plus complexe et moins fiable.  
  La séparation des rôles (*separation of duties*) est un principe clé ici.

- **Simplification de l'administration**  
  En centralisant la gestion des droits via des administrateurs dédiés ou des workflows prédéfinis, le système devient plus facile à maintenir et les erreurs sont réduites.  
  Les demandes de modification de permissions doivent donc passer par un circuit de validation spécifique, impliquant généralement un responsable hiérarchique ou un administrateur système.

---

En somme, cette restriction dans l'application de gestion des droits de la plateforme **Papaours** n'est **pas une lacune**, mais bien **une fonctionnalité délibérée** visant à renforcer la sécurité, la fiabilité et la gouvernance des accès au sein de l'environnement applicatif.  

Les modifications des permissions des utilisateurs doivent ainsi être **gérées par une autorité externe et habilitée**, garantissant que chaque changement est intentionnel, justifié et enregistré.

-> Retrouvez les bonnes pratiques de gestion dans la section [08 - Bonnes pratiques](08-bonnes-pratiques)


### Pour aller plus loin
- [09 - Règles d'assignation des droits d'accès →](09-regles-assignation.md)
- [07 - Supprimer les rôles, groupes et utilisateurs →](07-suppression-des-entites.md)

[Retour à l'Accueil](../accueil)
