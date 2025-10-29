---
title: "04 - Créer des rôles, groupes et utilisateurs"
description: ""
date: "2025-07-29"
version: "1"
---
### Tables des matières
1. [Créer un rôle](#créer-un-rôle)  
2. [Accéder à la création de rôle](#accéder-à-la-création-de-rôle)  
3. [Informations à renseigner pour un rôle](#informations-à-renseigner-pour-un-rôle)  
4. [Finaliser la création](#finaliser-la-création)  
5. [Créer un groupe d’utilisateurs](#créer-un-groupe-dutilisateurs)  
6. [Créer un utilisateur](#créer-un-utilisateur)  
7. [Informations à renseigner pour un utilisateur](#informations-à-renseigner-pour-un-utilisateur)  
8. [Gestion du mot de passe](#gestion-du-mot-de-passe)  
9. [Association à un ou plusieurs groupes](#association-à-un-ou-plusieurs-groupes)  
10. [Attribution de rôles personnels](#attribution-de-rôles-personnels)  
11. [Enregistrement de l’utilisateur](#enregistrement-de-lutilisateur)  
12. [Cumul de rôle(s) et groupe(s) pour un utilisateur](#cumul-de-rôles-et-groupes-pour-un-utilisateur)  
13. [Attribuer un périmètre](#attribuer-un-périmètre)
---
## Créer un rôle
Les rôles sont des regroupements de permissions permettant de structurer les droits d'accès des utilisateurs et des groupes dans votre plateforme **Papaours**. Chaque rôle correspond à un ensemble d'actions autorisées dans le système.

---

### 🔒 Règles à connaître avant de créer un rôle

> **💡 Important** : Certains rôles sont administrés par Papaours et ne peuvent pas être modifiés ou supprimés. Ces rôles système sont réservés à des usages internes spécifiques.

#### Rôles non modifiables

| Type de rôle | Peut être créé/modifié ? | Exemple                                   |
|--------------|--------------------------|-------------------------------------------|
| Rôle système Papaours | ❌ Non modifiable | "Administrateur Papaours"                 |
| Rôle créé par votre CFA | ✅ Modifiable | "Gestionnaire administratif", "Formateur" |

> ⚠️ **Attention** : Le rôle **"Administrateur Papaours"** est un rôle système. Il ne peut pas être créé, modifié ou assigné par les utilisateurs. Il est géré uniquement par Papaours.

---

### 🎥 Tutoriel vidéo

<video controls>
  <source src="https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/role/creer-role.mov" type="video/mp4" />
</video>

---

### Accéder à la création de rôle
La gestion des rôles se fait depuis la section **"Gestion des droits"**, dans le **sous-menu "Rôles"**.

Pour créer un nouveau rôle :

* Cliquez sur le **sous-menu "Rôles"** : Vous devez disposez de la permission rôle / Lecture pour accéder à ce sous-menu.  
* Cliquez sur le bouton **"Ajouter un rôle"** : Vous devez disposez de la permission rôle / Écriture pour accéder à ce bouton.

![Menu d'accès à la création d'un rôle](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/role/acces-creer-un-role.png "1012*252")

  ### Informations à renseigner pour un rôle
La création d’un rôle nécessite les éléments suivants :

* **Nom du rôle** *(obligatoire)*  
   Ce nom doit être explicite pour refléter le rôle métier ou fonctionnel (ex. : *Responsable CFA*, *Gestionnaire des contrats*).  
* **Description du rôle** *(obligatoire)*  
   Elle permet d’expliquer à quoi sert ce rôle, à quelles permissions il correspond, et à qui il est destiné.  
* **Liste de permissions associées**  
   Une liste complète des permissions disponibles est affichée sous forme de cases à cocher.  
   Il suffit de cocher les permissions souhaitées pour composer le rôle.

![Renseigner les informations du rôle](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/gestion-des-droits/role/ajouter-un-role.png "1012*715")

> Les permissions disponibles sont définies et maintenues par la plateforme Papaours. Elles ne peuvent pas être modifiées par les utilisateurs.

### Finaliser la création
Une fois le rôle configuré :

* Cliquez sur le bouton "Ajouter le rôle".  
* Le rôle est alors enregistré et devient disponible pour l’attribution à des utilisateurs ou groupes.  
* Il est visible dans la liste des rôles existants, avec ses permissions listées dans le détail.

![nouveau rôle créé](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/role/nouveau-role-cree.png "1012*351")

---

## Créer un groupe d'utilisateurs
Afin de faciliter la gestion des accès et des permissions au sein de notre système, il est possible de structurer les utilisateurs en groupes distincts. La création de ces groupes permet d'attribuer des rôles et des droits spécifiques à un ensemble d'utilisateurs de manière efficace et centralisée.

### 🔒 Règles à connaître avant de créer un groupe

> **💡 Important** : Certains groupes sont administrés par Papaours. Ces groupes système ont des restrictions spécifiques.

#### Groupes non modifiables

| Type de groupe | Nom modifiable ? | Rôles modifiables ? | Membres modifiables ? |
|----------------|------------------|---------------------|----------------------|
| Groupe système Papaours | ❌ | ❌ | ❌ |
| Groupe standard Papaours | ❌ | ❌ | ✅ |
| Groupe créé par votre CFA | ✅ | ✅ | ✅ |

**Exemples** :

| Groupe                               | Type | Actions possibles |
|--------------------------------------|------|-------------------|
| "Administrateur Papaours"            | Groupe système | ❌ Aucune modification possible |
| "Administrateur centre de formation" | Groupe Papaours | ✅ Ajouter/retirer des membres uniquement |
| "Formateurs CFA Paris"               | Groupe créé par le CFA | ✅ Toutes modifications possibles |

> ⚠️ **Attention** : Le groupe **"Administrateur Papaours"** est un groupe système. Il ne peut pas être modifié et vous ne pouvez pas ajouter ou retirer des utilisateurs de ce groupe.

---

Voici les étapes à suivre pour créer un nouveau groupe d'utilisateurs :

* **Navigation vers la Section Groupes**: Accédez à la section “Groupes”  dédiée à la gestion des groupes d'utilisateurs.  
![Menu d'accès à l'ajout d'un groupe](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/groupe/acces-nouveau-groupe.png "980*217")

* **Création d'un Nouveau Groupe:** Cliquez sur le bouton "Ajouter un Groupe"  
Vous devez disposez de la permission gestion des groupes / Écriture pour accéder à ce bouton.

* La page de création d’un groupe utilisateur s’ouvre  
  1. **Nommage du Groupe:** Attribuez un nom descriptif et pertinent au nouveau groupe. Ce nom doit refléter clairement la fonction ou le rôle des utilisateurs qui seront inclus dans ce groupe. Par exemple, "Administrateurs Système", "Utilisateurs Standard", "Équipe Marketing", etc.  
  2. **Sélection des rôles:** Définissez les permissions et les droits d'accès spécifiques pour le groupe. Ces permissions détermineront les actions que les membres du groupe seront autorisés à effectuer au sein du système. Pour cela, sélectionnez le ou les rôles que vous souhaitez affecter à ce groupe d'utilisateurs.  
  3. **Choix des périmètres**: Pour chaque rôle affecté, choisissez la ou les organisations souhaitées via l’action Modifier le périmètre. Une fenêtre s’affiche avec la liste des organisations disponibles.  
  4. **Ajout des Utilisateurs au Groupe:** Associez les utilisateurs concernés au groupe nouvellement créé. Vous pouvez ajouter des utilisateurs en les sélectionnant dans la liste Ajouter un membre au groupe ou en utilisant la barre de recherche  
  5. **Validation et Sauvegarde:** Vérifiez attentivement les informations et les configurations du groupe, puis validez et sauvegardez les modifications via l’action Créer le groupe. Le nouveau groupe sera alors créé et les utilisateurs ajoutés hériteront des permissions définies.

![Création d'un nouveau groupe](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/groupe/nouveau-groupe.png "1012*372")

---

## Créer un utilisateur
La création d’un utilisateur dans Papaours permet d’enregistrer une personne habilitée à se connecter à la plateforme et à bénéficier de droits d’accès selon ses rôles. Cette étape est essentielle pour intégrer un collaborateur, un formateur ou un gestionnaire au système.

Pour créer un nouveau membre :

* Cliquez sur le **sous-menu "Utilisateurs"** puis 
* Cliquez sur le bouton **"Ajouter un Membre"** : Vous devez disposez de la permission gestion des utilisateurs / Écriture pour accéder à ce bouton.
![Menu d'accès à l'ajout d'un utilisateur](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/utilisateur/acces-nouvel-utilisateur.png "980*243")

### Informations à renseigner pour un utilisateur
Pour créer un utilisateur, les champs suivants doivent être renseignés :

* **Prénom** *(obligatoire)*  
* **Nom** *(obligatoire)*  
* **Adresse e-mail** *(obligatoire)*  
   L’adresse e-mail est utilisée comme identifiant de connexion et pour l’envoi du lien de création de mot de passe.  
* **Numéro de téléphone** *(optionnel)*  
  * Un champ dédié permet de saisir le numéro.
  * Un sélecteur d’indicatif international (liste déroulante) permet de choisir le bon indicatif (ex. : \+33 pour la France).
![creation d'un utilisateur](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/utilisateur/creer-utilisateur.png "1012*230")

### Association à un ou plusieurs groupes
Une fois les informations de base renseignées, l’utilisateur peut être ajouté à un ou plusieurs groupes existants.

* Cette étape est facultative, mais recommandée pour faciliter la gestion collective des rôles.  
* L’ajout à un groupe permet à l’utilisateur d’hériter automatiquement des rôles et périmètres attribués à ce groupe.
![liste des groupes associables à un utilisateur](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/utilisateur/liste-groupe-creer-utilisateur.png "980*186")

### Attribution de rôles personnels
Il est également possible d’associer directement des rôles à l’utilisateur en tant que rôles personnels (en complément ou indépendamment des groupes).

Pour chaque rôle personnel ajouté :

* Le rôle doit être sélectionné dans la liste des rôles disponibles.  
* Un périmètre doit être spécifié pour définir les organisations sur lesquelles le rôle s’applique.

⚠️ Un rôle personnel **doit toujours être associé à un périmètre**. Par défaut, ce sont les périmètres de l’utilisateur créant l’affectation qui sont pris en compte.
![Liste des rôles associables à un utilisateur](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/utilisateur/liste-role-creer-utilisateur.png "1012*230")

### Enregistrement de l’utilisateur
Une fois toutes les informations saisies :

* Cliquer sur Ajouter et envoyer l'invitation pour finaliser la création de l’utilisateur.  
* Un e-mail d’invitation est automatiquement envoyé.  
* L’utilisateur s'affiche alors dans la liste des utilisateurs

### Cumul de rôle(s) et groupe(s) pour un utilisateur
L'attribution de permissions à un utilisateur au sein du système, qu'elle soit effectuée individuellement via des rôles personnels ou de manière collective par le biais de groupes, est conçue comme un processus cumulatif et additif. Cela signifie que les permissions globales dont bénéficie un utilisateur ne sont pas déterminées par un seul rôle, mais plutôt par l'ensemble des rôles qui lui sont associés, qu'ils soient personnels ou liés à des groupes.

Concrètement, chaque rôle attribue un ensemble spécifique de permissions, définissant ce que l'utilisateur est autorisé à faire ou à ne pas faire dans le système. Lorsqu'un utilisateur se voit attribuer plusieurs rôles, les permissions de chaque rôle s'additionnent. Il n'y a pas de mécanisme de remplacement ou de priorité qui ferait que les permissions d'un rôle prévaudraient sur celles d'un autre. Au contraire, l'utilisateur bénéficie de la somme totale des permissions accordées par tous les rôles qui lui sont attribués.

Cette approche cumulative garantit une grande flexibilité dans la gestion des droits. Elle permet de construire des profils d'utilisateurs complexes en combinant différents rôles, chacun apportant son lot de permissions spécifiques. Par exemple, un utilisateur pourrait avoir un rôle personnel lui donnant accès à certaines données spécifiques, tout en appartenant à un groupe qui lui accorde des permissions plus générales sur l'ensemble du système. Les permissions finales de cet utilisateur seraient alors la combinaison de ces deux ensembles de permissions.

Il est donc crucial de bien comprendre que la gestion des droits est un processus d'accumulation. L'utilisateur n'a pas seulement les permissions du dernier rôle qui lui a été attribué, mais bien celles de tous les rôles qui lui ont été attribués à un moment donné. Cette caractéristique est essentielle pour concevoir une architecture de permissions efficace et adaptée aux besoins spécifiques de chaque utilisateur et de chaque organisation.

### Gestion du mot de passe
Papaours ne permet pas la création manuelle d’un mot de passe pour des raisons de sécurité.

* Une fois l’utilisateur créé, un lien d’accès temporaire lui est envoyé automatiquement à l’adresse e-mail renseignée.   
* Le mail envoyé à pour titre : *Définir le mot de passe de votre compte Papaours*

Il est de la forme suivante : 
![mail d'initialiation de compte Papaours](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/utilisateur/mail-initialiser-mot-de-passe.png "528*479")

* L’utilisateur peut définir lui-même son mot de passe en cliquant sur **Définir mon mot de passe**

---

## Attribuer un périmètre
L'attribution d'un périmètre définit les limites et l'étendue des accès pour un utilisateur ou un groupe au sein du système. Cette étape est cruciale pour garantir la sécurité, l'efficacité et la clarté dans la gestion des droits.

* **Importance de l'Attribution de Périmètre:** L'attribution d'un périmètre est une pratique essentielle pour une gestion efficace et sécurisée des droits d'accès. En suivant ces directives, vous pouvez assurer une organisation plus structurée, sécurisée et productive, permettant de traduire votre organisation en droit d’accès.

* **Choix du périmètre:** Cliquez sur l'action “Modifier le périmètre” accessible lors de l’affectation d’un rôle à un utilisateur ou un groupe. Le périmètre est défini par défaut avec le périmètre de l'utilisateur effectuant l'action. Sélectionnez ensuite une ou plusieurs organisations au sein de la plateforme que vous souhaitez ajouter au périmètre. Cette sélection détermine les entités spécifiques sur lesquelles les droits seront appliqués.

### Pour aller plus loin
-> [05 - Attribution des droits](05-attribution-des-droits)

---

[Retour à l'Accueil](../accueil)
