# Gestion des droits

# 

# Table des matières

[**1\. Introduction	4**](#introduction)

[1.1 Objectifs de l’application	4](#1.1-objectifs-de-l’application)

[1.2 Public visé par la documentation	4](#1.2-public-visé-par-la-documentation)

[**2\. Prise en main du système	5**](#prise-en-main-du-système)

[2.1 Accès à l’application	5](#2.1-accès-à-l’application)

[2.2 Première connexion	5](#2.2-première-connexion)

[Étapes de la première connexion :	5](#étapes-de-la-première-connexion-:)

[**3\. Définition des concepts clés	6**](#définition-des-concepts-clés)

[3.1. Diagramme conceptuel	6](#diagramme-conceptuel)

[3.2. Définitions	7](#définitions)

[3.3. Description des relations	8](#description-des-relations)

[3.4  Gestion des permissions	9](#3.4-gestion-des-permissions)

[3.4.1 Liste des permissions	9](#3.4.1-liste-des-permissions)

[3.4.2 Consultations des permissions	9](#3.4.2-consultations-des-permissions)

[3.4.3 Non modifiable par l’utilisateur	9](#3.4.3-non-modifiable-par-l’utilisateur)

[**4\. Accéder à la gestion des droits	10**](#accéder-à-la-gestion-des-droits)

[4.1 Où trouver la gestion des droits ?	10](#4.1-où-trouver-la-gestion-des-droits-?)

[4.2 Conditions d’accès	10](#4.2-conditions-d’accès)

[4.3 Que permet le menu "Gestion des droits" ?	11](#4.3-que-permet-le-menu-"gestion-des-droits"-?)

[4.4 Visibilité des entités	11](#4.4-visibilité-des-entités)

[4.4.1 Visibilité des rôles	11](#4.4.1-visibilité-des-rôles)

[4.4.2 Visibilité des groupes	11](#4.4.2-visibilité-des-groupes)

[4.4.3 Visibilité des utilisateurs	11](#4.4.3-visibilité-des-utilisateurs)

[4.4 Sécurité et traçabilité	11](#4.4-sécurité-et-traçabilité)

[**5\. Création des entités	13**](#création-des-entités)

[5.1  Créer un rôle	13](#5.1-créer-un-rôle)

[5.1.1 Accéder à la création de rôle	13](#5.1.1-accéder-à-la-création-de-rôle)

[5.1.2 Informations à renseigner	13](#5.1.2-informations-à-renseigner)

[5.1.3 Finaliser la création	14](#5.1.3-finaliser-la-création)

[5.2 Créer un groupe d’utilisateurs	15](#5.2-créer-un-groupe-d’utilisateurs)

[5.3 Créer un utilisateur	16](#5.3-créer-un-utilisateur)

[5.3.1 Informations à renseigner	16](#5.3.1-informations-à-renseigner)

[5.3.2 Gestion du mot de passe	16](#5.3.2-gestion-du-mot-de-passe)

[5.3.3 Association à un ou plusieurs groupes	17](#5.3.3-association-à-un-ou-plusieurs-groupes)

[5.3.4 Attribution de rôles personnels	18](#5.3.4-attribution-de-rôles-personnels)

[5.3.5 Enregistrement de l’utilisateur	18](#5.3.5-enregistrement-de-l’utilisateur)

[5.3.6 Cumul de rôle(s) et groupe(s) pour un utilisateur	18](#5.3.6-cumul-de-rôle\(s\)-et-groupe\(s\)-pour-un-utilisateur)

[5.4  Attribuer un périmètre	20](#5.4-attribuer-un-périmètre)

[**6\. Attribution des droits	21**](#attribution-des-droits)

[6.1 Attribution directe d’un rôle à un utilisateur	21](#6.1-attribution-directe-d’un-rôle-à-un-utilisateur)

[6.2 Attribution indirecte via groupe d’utilisateurs	21](#6.2-attribution-indirecte-via-groupe-d’utilisateurs)

[**7\. Modification des entités	24**](#modification-des-entités)

[7.1. Modifier un rôle	24](#modifier-un-rôle)

[7.2. Modifier un groupe	25](#modifier-un-groupe)

[7.3. Modifier un utilisateur	25](#modifier-un-utilisateur)

[7.4. Modifier un périmètre	25](#modifier-un-périmètre)

[7.5. Modifier ses droits	25](#modifier-ses-droits)

[**8\. Suppression des entités	26**](#suppression-des-entités)

[8.1. Supprimer un rôle	26](#supprimer-un-rôle)

[8.2. Supprimer un groupe	26](#supprimer-un-groupe)

[8.3. Supprimer un utilisateur	26](#supprimer-un-utilisateur)

[**9\. Bonnes pratiques	27**](#bonnes-pratiques)

# 

1. # **Introduction** {#introduction}

## 1.1 Objectifs de l’application {#1.1-objectifs-de-l’application}

Cette application de gestion des identités et des accès (IAM) a pour objectif de centraliser et sécuriser la gestion des droits d’accès aux ressources de votre plateforme Papaours. Elle permet de créer des utilisateurs, de les regrouper en groupes, de leur attribuer des rôles définis par un ensemble de permissions, et d’appliquer ces rôles sur des périmètres organisationnels définis.

L’approche par rôles et groupes facilite la gestion des droits à grande échelle, tout en permettant une gouvernance fine et traçable des accès au sein de votre plateforme Papaours.

L'application de gestion des identités et des accès (IAM) vise à centraliser et sécuriser la gestion des droits d'accès à votre plateforme Papaours. Elle offre la possibilité de créer des utilisateurs, de les organiser en groupes, de leur attribuer des rôles (définis par un ensemble de permissions) et d'appliquer ces rôles à des périmètres organisationnels spécifiques. 

Cette approche, basée sur les rôles et les groupes, simplifie la gestion des droits à grande échelle tout en assurant une gouvernance précise et une traçabilité des accès au sein de votre plateforme Papaours.

## 1.2 Public visé par la documentation {#1.2-public-visé-par-la-documentation}

Ce document est destiné aux administrateurs, gestionnaires de sécurité, responsables d’organisation, ou toute personne ayant la responsabilité de configurer et gérer les droits d’accès dans l’application. Il contient les informations essentielles pour comprendre le fonctionnement du système et l’utiliser de manière optimale.

## 

# 

2. # **Prise en main du système** {#prise-en-main-du-système}

## 2.1 Accès à l’application {#2.1-accès-à-l’application}

L’accès à l’application se fait via un navigateur web à l’adresse fournie par votre administrateur Papaours. Il n’existe pas de mot de passe initialement attribué par l’administrateur. Lorsqu’un utilisateur est créé, il reçoit un lien d’activation par e-mail lui permettant d’accéder à l’application après initialisation de son mot de passe.

Ce lien permet de :

* **Définir un mot de passe personnel**, en respectant les règles de sécurité définies (longueur minimale, complexité, etc.),  
* **Accéder directement à son tableau de bord**, avec les permissions et périmètres qui lui ont été attribués.

## 2.2 Première connexion {#2.2-première-connexion}

Lorsqu’un utilisateur reçoit son lien d’invitation à la plateforme Papaours, il est redirigé vers une page sécurisée permettant de définir son mot de passe. Ce mot de passe doit respecter les exigences minimales de sécurité définies par la plateforme (longueur minimale, complexité, caractères spéciaux, etc.).

#### **Étapes de la première connexion :** {#étapes-de-la-première-connexion-:}

* **Cliquez sur le lien reçu par e-mail**  
* **Choisissez un mot de passe personnel** en respectant les règles affichées à l’écran.  
* **Validez** pour finaliser la création de votre compte.  
* Vous êtes automatiquement redirigé vers la page d’accueil de Papaours, avec vos accès personnalisés.

💡 *Important : tant que le mot de passe n’est pas défini, l’utilisateur ne peut pas se connecter.* 

# 

3. # **Définition des concepts clés** {#définition-des-concepts-clés}

   1. ## Diagramme conceptuel {#diagramme-conceptuel}

![][image1]

## 

2. ## Définitions {#définitions}

Dans le cadre de la gestion des droits, il est crucial de clarifier et de définir avec précision les concepts fondamentaux qui sous-tendent l'ensemble du processus. 

Ces définitions servent de base commune à tous les acteurs impliqués, garantissant ainsi une compréhension uniforme et une application cohérente des règles et procédures.

* **Permission** : Dans la plateforme Papaours, une autorisation permet d'effectuer une action spécifique, comme créer un utilisateur ou modifier un groupe.

* **Rôle** : Un rôle est un ensemble de permissions spécifiques regroupées sous une désignation unique. Cet ensemble de permissions est destiné à être attribué à un utilisateur individuel ou à un groupe d'utilisateurs.

* **Utilisateur** : Personne ayant un accès personnel à la plateforme. Ses droits sont déterminés par ses rôles directs et ceux des groupes auxquels il appartient.

* **Groupe** : Ensemble d’utilisateurs partageant un ou plusieurs rôles communs.

* **Périmètre** : Domaine d’application d’un rôle (ex. : une organisation, un ensemble d'organisations). Permet de restreindre les droits à une zone précise.

* **Organisation** : Entité représentant une structure opérationnelle de votre réseau (ex. : un centre de formation, une unité de formation ou un regroupement d’unités de formation). Elle constitue la base sur laquelle les périmètres sont définis.

3. ## Description des relations {#description-des-relations}

**Permission → Rôle** : Un rôle regroupe plusieurs permissions.  
Chaque rôle au sein du système est méticuleusement conçu comme un ensemble cohérent de permissions. Lorsqu'un rôle est attribué à un utilisateur ou à un groupe, cela confère de facto l'intégralité des permissions associées. 

**Rôle → Utilisateur** : Un utilisateur peut se voir attribuer un ou plusieurs rôles directement.  
Il est loisible d'octroyer directement un ou plusieurs rôles à un utilisateur. Cette méthode d'attribution s'avère particulièrement pertinente dans les cas où un utilisateur requiert des accès spécifiques et personnalisés. Elle confère une grande flexibilité dans la configuration des droits d'accès individuels.

**Rôle → Groupe** : Un rôle peut aussi être affecté à un groupe d’utilisateurs.  
Alternativement, un rôle peut être assigné à un groupe d'utilisateurs. Cette approche est préconisée pour gérer les accès de manière collective, simplifiant ainsi l'administration des droits pour des équipes ou départements entiers. Tous les membres du groupe hériteront des permissions inhérentes au rôle attribué.

**Utilisateur → Groupe** : Un utilisateur peut appartenir à un ou plusieurs groupes.  
Un utilisateur peut être membre de plusieurs groupes simultanément. Cette fonctionnalité permet de cumuler les permissions émanant des différents rôles assignés aux groupes auxquels l'utilisateur appartient. Elle offre une gestion granulaire et complexe des accès, adaptée aux organisations aux structures multidimensionnelles.

**Rôle → Périmètre** : Chaque attribution de rôle est contextualisée par un périmètre.  
Chaque attribution de rôle est définie dans un contexte spécifique, désigné sous le terme de périmètre. Le périmètre détermine l'étendue de l'application du rôle, assurant que les permissions ne sont valides que dans les limites établies. Cela permet de prévenir des accès non intentionnels ou excessifs en restreignant l'influence du rôle à des zones ou entités spécifiques.

**Périmètre → Organisation** : Le périmètre définit sur quelle(s) organisation(s) le rôle est valable.  
Le périmètre est intrinsèquement lié à l'organisation. Il spécifie avec précision sur quelle(s) entité(s) organisationnelle(s) le rôle est applicable. Cette granularité permet de refléter fidèlement la structure de l'organisation dans la gestion des droits d'accès, garantissant ainsi une sécurité et une conformité optimales.

## 3.4  Gestion des permissions {#3.4-gestion-des-permissions}

 Les permissions sont gérées exclusivement par la plateforme Papaours.  
Elles représentent les droits techniques élémentaires (ex. : consulter une fiche, modifier un contrat, etc.) et sont maintenues à jour automatiquement par l’équipe Papaours.

### 3.4.1 Liste des permissions {#3.4.1-liste-des-permissions}

Lors de la création ou de la consultation d'un rôle, la plateforme permet de visualiser la liste des permissions disponibles. L'ensemble des permissions est affiché au moment de la création d'un rôle. Rendez-vous dans le menu Gestion des droits, section rôles puis cliquez soit sur un rôle existant soit sur l’action Ajouter un rôle.

### 3.4.2 Consultations des permissions {#3.4.2-consultations-des-permissions}

Les utilisateurs ont la possibilité de consulter les permissions qui leur sont attribuées. Cette fonction permet une transparence totale sur les accès dont dispose chaque utilisateur.

### 3.4.3 Non modifiable par l’utilisateur {#3.4.3-non-modifiable-par-l’utilisateur}

Les permissions ne peuvent pas être modifiées directement par l'utilisateur final. Toute modification des permissions doit être effectuée par un administrateur ou une personne autorisée ayant les droits nécessaires. Cette restriction assure la sécurité et l'intégrité du système.

4. # **Accéder à la gestion des droits** {#accéder-à-la-gestion-des-droits}

La gestion des droits d’accès dans votre plateforme Papaours est une interface dédiée permettant aux utilisateurs autorisés de créer, modifier ou consulter les entités liées à la sécurité et aux autorisations : utilisateurs, groupes, rôles, périmètres, et organisations.

### **4.1 Où trouver la gestion des droits ?** {#4.1-où-trouver-la-gestion-des-droits-?}

L’accès à la gestion des droits se fait via le menu principal de l’application Papaours.

* Dans la barre de navigation à gauche de l’écran, un menu intitulé **Gestion des droits** est affiché.

* Ce menu donne accès à l’ensemble des fonctionnalités liées à la gestion des accès et permissions.

* Le menu est **conditionnel** : il n’apparaît que pour les utilisateurs autorisés (voir point suivant).

### **4.2 Conditions d’accès** {#4.2-conditions-d’accès}

L’accès à la gestion des droits est restreint aux utilisateurs disposant des permissions techniques nécessaires. Ces permissions sont attribuées via les rôles associés à l’utilisateur ou à son groupe.

Les permissions requises sont celles liés à la catégorie gestion des permissions, qui regroupent les permissions suivantes : 

- Lire un utilisateur  
- Ecrire un utilisateur  
- Supprimer un utilisateur  
- Lire un rôle  
- Ecrire un rôle  
- Supprimer un rôle  
- Lire un groupe  
- Ecrire un groupe  
- Supprimer un groupe

Ces permissions ne peuvent pas être attribuées directement : elles doivent être regroupées au sein d’un **rôle** actif, lui-même affecté à un utilisateur ou à un groupe auquel l’utilisateur appartient.

### **4.3 Que permet le menu "Gestion des droits" ?** {#4.3-que-permet-le-menu-"gestion-des-droits"-?}

Une fois le menu accessible, l’utilisateur peut :

* Visualiser la liste des utilisateurs, groupes, rôles, périmètres, et organisations  
* Créer de nouvelles entités (selon les permissions dont il dispose) ;  
* Modifier les utilisateurs, groupes, rôles et périmètre  
* Supprimer un utilisateur, un rôle ou un groupe  
* Modifier les attributions de rôles et périmètres pour les utilisateurs et groupes (selon les permissions dont il dispose) ;  
* Visualiser les droits effectifs d’un utilisateur donné, en prenant en compte les rôles directs et ceux hérités de groupes (selon les permissions dont il dispose)


### **4.4 Visibilité des entités** {#4.4-visibilité-des-entités}

Afin d'assurer la gestion de votre organisation et la protection de vos données entre les différentes organisations, les éléments de gestion des droits bénéficient d'une visibilité spécifique.

### 4.4.1 Visibilité des rôles {#4.4.1-visibilité-des-rôles}

### 4.4.2 Visibilité des groupes {#4.4.2-visibilité-des-groupes}

### 4.4.3 Visibilité des utilisateurs {#4.4.3-visibilité-des-utilisateurs}

### **4.4 Sécurité et traçabilité** {#4.4-sécurité-et-traçabilité}

L’ensemble des actions réalisées dans la gestion des droits est enregistré pour assurer une traçabilité complète. En cas d’incident ou d’audit, il est possible de consulter l’historique des modifications de rôles et d’autorisations.

# 

# 

5. # **Création des entités** {#création-des-entités}

## 5.1  Créer un rôle {#5.1-créer-un-rôle}

Les rôles sont des regroupements de permissions permettant de structurer les droits d’accès des utilisateurs et des groupes dans votre plateforme **Papaours**. Chaque rôle correspond à un ensemble d’actions autorisées dans le système.

### **5.1.1 Accéder à la création de rôle** {#5.1.1-accéder-à-la-création-de-rôle}

La gestion des rôles se fait depuis la section **"Gestion des droits"**, dans le **sous-menu "Rôles"**.

Pour créer un nouveau rôle :

* Cliquez sur le **sous-menu "Rôles"** : Vous devez disposez de la permission rôle / Lecture pour accéder à ce sous-menu.  
* Cliquez sur le bouton **"Ajouter un rôle"** : Vous devez disposez de la permission rôle / Écriture pour accéder à ce bouton.

  ### **5.1.2 Informations à renseigner** {#5.1.2-informations-à-renseigner}

La création d’un rôle nécessite les éléments suivants :

* **Nom du rôle** *(obligatoire)*  
   Ce nom doit être explicite pour refléter le rôle métier ou fonctionnel (ex. : *Responsable CFA*, *Gestionnaire des contrats*).  
* **Description du rôle** *(obligatoire)*  
   Elle permet d’expliquer à quoi sert ce rôle, à quelles permissions il correspond, et à qui il est destiné.  
* **Liste de permissions associées**  
   Une liste complète des permissions disponibles est affichée sous forme de cases à cocher.  
   Il suffit de cocher les permissions souhaitées pour composer le rôle.

📌 **Les permissions disponibles sont définies et maintenues par la plateforme Papaours**. Elles ne peuvent pas être modifiées par les utilisateurs.

### **5.1.3 Finaliser la création** {#5.1.3-finaliser-la-création}

Une fois le rôle configuré :

* Cliquez sur le bouton "Ajouter le rôle".  
* Le rôle est alors enregistré et devient disponible pour l’attribution à des utilisateurs ou groupes.  
* Il est visible dans la liste des rôles existants, avec ses permissions listées dans le détail.

## 

## 5.2 Créer un groupe d’utilisateurs {#5.2-créer-un-groupe-d’utilisateurs}

Afin de faciliter la gestion des accès et des permissions au sein de notre système, il est possible de structurer les utilisateurs en groupes distincts. La création de ces groupes permet d'attribuer des rôles et des droits spécifiques à un ensemble d'utilisateurs de manière efficace et centralisée.

Voici les étapes à suivre pour créer un nouveau groupe d'utilisateurs :

* **Accès à l'Interface de Gestion des Droits:** Connectez-vous à l'interface de gestion des droits avec un compte disposant des privilèges nécessaires pour créer et gérer les groupes.  
* **Navigation vers la Section Groupes**: Accédez à la section “Groupes”  dédiée à la gestion des groupes d'utilisateurs.  
* **Création d'un Nouveau Groupe:** Cliquez sur le bouton "Ajouter un Groupe"  
* La page de création d’un groupe utilisateur s’ouvre  
  1. **Nommage du Groupe:** Attribuez un nom descriptif et pertinent au nouveau groupe. Ce nom doit refléter clairement la fonction ou le rôle des utilisateurs qui seront inclus dans ce groupe. Par exemple, "Administrateurs Système", "Utilisateurs Standard", "Équipe Marketing", etc.  
  2. **Sélection des rôles:** Définissez les permissions et les droits d'accès spécifiques pour le groupe. Ces permissions détermineront les actions que les membres du groupe seront autorisés à effectuer au sein du système. Pour cela, sélectionnez le ou les rôles que vous souhaitez affecter à ce groupe d'utilisateurs.  
  3. **Choix des périmètres**: Pour chaque rôle affecté, choisissez la ou les organisations souhaitées via l’action Modifier le périmètre. Une fenêtre s’affiche avec la liste des organisations disponibles.  
  4. **Ajout des Utilisateurs au Groupe:** Associez les utilisateurs concernés au groupe nouvellement créé. Vous pouvez ajouter des utilisateurs en les sélectionnant dans la liste Ajouter un membre au groupe ou en utilisant la barre de recherche  
  5. **Validation et Sauvegarde:** Vérifiez attentivement les informations et les configurations du groupe, puis validez et sauvegardez les modifications via l’action Créer le groupe. Le nouveau groupe sera alors créé et les utilisateurs ajoutés hériteront des permissions définies.

## 5.3 Créer un utilisateur {#5.3-créer-un-utilisateur}

La création d’un utilisateur dans Papaours permet d’enregistrer une personne habilitée à se connecter à la plateforme et à bénéficier de droits d’accès selon ses rôles. Cette étape est essentielle pour intégrer un collaborateur, un formateur ou un gestionnaire au système.

### 5.3.1 Informations à renseigner {#5.3.1-informations-à-renseigner}

Pour créer un utilisateur, les champs suivants doivent être renseignés :

* **Prénom** *(obligatoire)*  
* **Nom** *(obligatoire)*  
* **Adresse e-mail** *(obligatoire)*  
   L’adresse e-mail est utilisée comme identifiant de connexion et pour l’envoi du lien de création de mot de passe.  
* **Numéro de téléphone** *(optionnel)*  
  * Un champ dédié permet de saisir le numéro.

  * Un sélecteur d’indicatif international (liste déroulante) permet de choisir le bon indicatif (ex. : \+33 pour la France).

### 5.3.2 Gestion du mot de passe {#5.3.2-gestion-du-mot-de-passe}

Papaours ne permet pas la création manuelle d’un mot de passe pour des raisons de sécurité.

* Une fois l’utilisateur créé, un lien d’accès temporaire lui est envoyé automatiquement à l’adresse e-mail renseignée.   
* Le mail envoyé à pour titre : *Définir le mot de passe de votre compte Papaours*

Il est de la forme suivante : 

![][image2]

* L’utilisateur peut définir lui-même son mot de passe en cliquant sur **Définir mon mot de passe**

### 5.3.3 Association à un ou plusieurs groupes {#5.3.3-association-à-un-ou-plusieurs-groupes}

Une fois les informations de base renseignées, l’utilisateur peut être ajouté à un ou plusieurs groupes existants.

* Cette étape est facultative, mais recommandée pour faciliter la gestion collective des rôles.  
* L’ajout à un groupe permet à l’utilisateur d’hériter automatiquement des rôles et périmètres attribués à ce groupe.

### 5.3.4 Attribution de rôles personnels {#5.3.4-attribution-de-rôles-personnels}

Il est également possible d’associer directement des rôles à l’utilisateur en tant que rôles personnels (en complément ou indépendamment des groupes).

Pour chaque rôle personnel ajouté :

* Le rôle doit être sélectionné dans la liste des rôles disponibles.  
* Un périmètre doit être spécifié pour définir les organisations sur lesquelles le rôle s’applique.

⚠️ Un rôle personnel **doit toujours être associé à un périmètre**. Par défaut, c’est les périmètres de l’utilisateur créant l’affectation qui sont pris en compte.

### 5.3.5 Enregistrement de l’utilisateur {#5.3.5-enregistrement-de-l’utilisateur}

Une fois toutes les informations saisies :

* Cliquer sur Ajouter et envoyer l'invitation pour finaliser la création de l’utilisateur.  
* Un e-mail d’invitation est automatiquement envoyé.  
* L’utilisateur s'affiche alors dans la liste des utilisateurs

### 5.3.6 Cumul de rôle(s) et groupe(s) pour un utilisateur {#5.3.6-cumul-de-rôle(s)-et-groupe(s)-pour-un-utilisateur}

L'attribution de permissions à un utilisateur au sein du système, qu'elle soit effectuée individuellement via des rôles personnels ou de manière collective par le biais de groupes, est conçue comme un processus cumulatif et additif. Cela signifie que les permissions globales dont bénéficie un utilisateur ne sont pas déterminées par un seul rôle, mais plutôt par l'ensemble des rôles qui lui sont associés, qu'ils soient personnels ou liés à des groupes.

Concrètement, chaque rôle attribue un ensemble spécifique de permissions, définissant ce que l'utilisateur est autorisé à faire ou à ne pas faire dans le système. Lorsqu'un utilisateur se voit attribuer plusieurs rôles, les permissions de chaque rôle s'additionnent. Il n'y a pas de mécanisme de remplacement ou de priorité qui ferait que les permissions d'un rôle prévaudraient sur celles d'un autre. Au contraire, l'utilisateur bénéficie de la somme totale des permissions accordées par tous les rôles qui lui sont attribués.

Cette approche cumulative garantit une grande flexibilité dans la gestion des droits. Elle permet de construire des profils d'utilisateurs complexes en combinant différents rôles, chacun apportant son lot de permissions spécifiques. Par exemple, un utilisateur pourrait avoir un rôle personnel lui donnant accès à certaines données spécifiques, tout en appartenant à un groupe qui lui accorde des permissions plus générales sur l'ensemble du système. Les permissions finales de cet utilisateur seraient alors la combinaison de ces deux ensembles de permissions.

Il est donc crucial de bien comprendre que la gestion des droits est un processus d'accumulation. L'utilisateur n'a pas seulement les permissions du dernier rôle qui lui a été attribué, mais bien celles de tous les rôles qui lui ont été attribués à un moment donné. Cette caractéristique est essentielle pour concevoir une architecture de permissions efficace et adaptée aux besoins spécifiques de chaque utilisateur et de chaque organisation.

## 

## 5.4  Attribuer un périmètre {#5.4-attribuer-un-périmètre}

L'attribution d'un périmètre définit les limites et l'étendue des accès pour un utilisateur ou un groupe au sein du système. Cette étape est cruciale pour garantir la sécurité, l'efficacité et la clarté dans la gestion des droits.

* **Importance de l'Attribution de Périmètre:** L'attribution d'un périmètre est une pratique essentielle pour une gestion efficace et sécurisée des droits d'accès. En suivant ces directives, vous pouvez assurer une organisation plus structurée, sécurisée et productive, permettant de traduire votre organisation en droit d’accès.

* **Choix du périmètre:** Cliquez sur l'action “Modifier le périmètre” accessible lors de l’affectation d’un rôle à un utilisateur ou un groupe. Le périmètre est défini par défaut avec le périmètre de l'utilisateur effectuant l'action. Sélectionnez ensuite une ou plusieurs organisations au sein de la plateforme que vous souhaitez ajouter au périmètre. Cette sélection détermine les entités spécifiques sur lesquelles les droits seront appliqués.




# 

6. # **Attribution des droits** {#attribution-des-droits}

## 6.1 Attribution directe d’un rôle à un utilisateur {#6.1-attribution-directe-d’un-rôle-à-un-utilisateur}

L'attribution directe d'un rôle à un utilisateur est une méthode fondamentale pour la gestion des accès et des permissions au sein de notre système. Cette approche permet de définir précisément les actions qu'un utilisateur est autorisé à effectuer. En attribuant un rôle personnel, nous accordons à cet utilisateur un ensemble prédéfini de droits, facilitant ainsi le contrôle et la supervision de l'accès aux ressources et aux fonctionnalités de l'application.

Pour attribuer un rôle personnel à un utilisateur : 

* Rendez-vous en modification sur un utilisateur

* Choix du rôle : Dans la liste Rôle personnel, Sélectionner le rôle personnel souhaité parmi les rôles disponibles dans le système en recherchant via le nom du rôle ou dans la liste déroulante qui s’affiche. 

* Périmètre : Le rôle personnel est automatiquement attribué aux organisations de l’utilisateur qui effectue l’action.

* Confirmation : Cliquez sur Modifier l'utilisateur pour que le système prenne en compte l'attribution

L'attribution directe de rôles offre une grande flexibilité et un contrôle précis sur les accès, permettant d'adapter les permissions en fonction des besoins spécifiques de chaque utilisateur et de garantir la sécurité et l'intégrité des données et des opérations du système.

## 

## 6.2 Attribution indirecte via groupe d’utilisateurs {#6.2-attribution-indirecte-via-groupe-d’utilisateurs}

Dans le cadre de la gestion des accès et des permissions, une méthode efficace consiste à attribuer des droits de manière indirecte via des groupes d'utilisateurs. Au lieu d'assigner des droits individuellement à chaque utilisateur, il est possible de créer des groupes d'utilisateurs, regroupant des individus ayant des besoins d'accès similaires, puis d'attribuer les droits nécessaires à ces groupes.

Cette approche présente plusieurs avantages significatifs. Tout d'abord, elle simplifie grandement la gestion des droits, en réduisant le nombre d'opérations nécessaires. Au lieu de configurer des droits pour chaque utilisateur individuellement, il suffit de gérer les droits au niveau des groupes, ce qui est beaucoup plus rapide et moins sujet aux erreurs.

De plus, l'attribution indirecte via des groupes facilite la maintenance des accès. Lorsque de nouveaux utilisateurs rejoignent une équipe ou un service, il suffit de les ajouter au groupe approprié pour qu'ils héritent automatiquement des droits nécessaires. De même, lorsqu'un utilisateur quitte une équipe ou change de rôle, il suffit de le retirer du groupe concerné. Cette méthode garantit une mise à jour rapide et précise des droits, en évitant les oublis et les erreurs humaines.

En outre, l'utilisation de groupes permet de mieux structurer et organiser les accès. Les groupes peuvent être créés en fonction des rôles, des départements, des projets ou de toute autre classification pertinente pour l'organisation. Cela permet de visualiser clairement qui a accès à quelles ressources et facilite l'audit et la vérification des droits.

Enfin, l'attribution indirecte via des groupes améliore la sécurité en réduisant la complexité de la gestion des accès. Moins il y a de configurations individuelles, moins il y a de risques d'erreurs de configuration ou d'oublis qui pourraient compromettre la sécurité des systèmes et des données.

Deux possibilités s’offrent à vous pour attribuer un utilisateur à un groupe.

- Depuis la page de modification d’un utilisateur : 

  1. Rendez-vous en modification sur un utilisateur

  2. Choix du groupe: Dans la liste groupe d’utilisateur, Sélectionner le groupe souhaité parmi les groupes disponibles dans le système en recherchant via le nom ou dans la liste déroulante qui s’affiche. 

  3. Périmètre : Le périmètre est celui affecté au groupe utilisateur choisi. 

  4. Confirmation : Cliquez sur Modifier l'utilisateur pour que le système prenne en compte l'attribution

- Depuis la page de modification d’un groupe utilisateur : 

  5. Rendez-vous en modification sur un groupe utilisateur

  6. Choix de l’utilisateur : rechercher l’utilisateur via son nom et / ou  prénom dans le champ Ajouter un membre au groupe

  7. Périmètre : Le périmètre est celui affecté au groupe en cours de modification

  8. Confirmation : Cliquez sur Modifier le groupe pour que le système prenne en compte l'attribution

En résumé, l'attribution indirecte de droits via des groupes d'utilisateurs est une pratique recommandée pour une gestion efficace, structurée et sécurisée des accès et des permissions. Elle simplifie les opérations, facilite la maintenance, améliore l'organisation et renforce la sécurité globale du système.

### 

### 

### 

### 

# 

# 

7. # **Modification des entités** {#modification-des-entités}

   1. ## Modifier un rôle {#modifier-un-rôle}

Cette section détaille la procédure à suivre pour modifier un rôle existant au sein du système. La modification des rôles est une fonction cruciale pour la gestion des accès et des permissions, garantissant que les utilisateurs disposent des droits appropriés pour accomplir leurs tâches.

Avant de procéder à la modification d'un rôle, assurez-vous d'avoir les privilèges d'administrateur nécessaires. Seuls les utilisateurs disposant de la permissions Ecrire un rôle sont autorisés à modifier les rôles et leurs permissions associées. 

1. Étapes de modification  
* **Accéder à la gestion des rôles :** Naviguez vers la section rôles du menu gestion des rôles dans l'interface.  
* **Sélectionner le rôle à modifier :** Identifiez et sélectionnez le rôle que vous souhaitez modifier dans la liste des rôles disponibles. Vous pouvez utiliser les options de recherche pour localiser rapidement le rôle souhaité.  
* **Éditer les permissions du rôle :** Une fois le rôle sélectionné, vous aurez la possibilité de modifier le rôle en cliquant sur l’action Modifier  
* **Sauvegarder les modifications :** Après avoir apporté les modifications nécessaires, assurez-vous de les sauvegarder. Un bouton de sauvegarde ou d'enregistrement sera généralement disponible pour confirmer les changements.


  2. Conséquences de la modification

Il est important de noter que la modification d'un rôle peut avoir des impacts sur les utilisateurs qui y sont associés. Assurez-vous de bien comprendre les conséquences de vos modifications avant de les appliquer, et communiquez les changements aux utilisateurs concernés si nécessaire.Conseils additionnels

* **Documenter les modifications :** Prenez le temps de documenter les modifications apportées aux rôles. Cela facilitera la gestion future des accès et permettra de retracer l'historique des changements.  
* **Tester les modifications :** Après avoir modifié un rôle, testez les changements avec un compte utilisateur affecté à ce rôle pour vous assurer que les permissions fonctionnent comme prévu.

  ## 

  2. ## Modifier un groupe {#modifier-un-groupe}

  3. ## Modifier un utilisateur {#modifier-un-utilisateur}

  4. ## Modifier un périmètre {#modifier-un-périmètre}

  5. ## Modifier ses droits {#modifier-ses-droits}

# 

8. # **Suppression des entités** {#suppression-des-entités}

   1. ## Supprimer un rôle {#supprimer-un-rôle}

   2. ## Supprimer un groupe {#supprimer-un-groupe}

   3. ## Supprimer un utilisateur {#supprimer-un-utilisateur}

   

   # 

9. # **Bonnes pratiques** {#bonnes-pratiques}

* Centralisation des rôles via les groupes

* Utilisation raisonnée des périmètres pour segmenter les accès

* Documentation des rôles métiers avec descriptions compréhensibles

* Gestion des comptes inactifs et audit des accès

Conseils Pratiques

* **Revoir Régulièrement les Périmètres :** Les besoins et les rôles peuvent évoluer. Il est donc essentiel de revoir régulièrement les périmètres attribués et de les ajuster si nécessaire.  
* **Utiliser des Groupes :** L'attribution de périmètres à des groupes plutôt qu'à des individus peut simplifier la gestion des droits dans les grandes organisations.  
* **Appliquer le Principe du Moindre Privilège :** N'accorder que les droits strictement nécessaires pour accomplir les tâches assignées.

[image1]: <data:image/png;base64,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>

[image2]: <data:image/png;base64,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>