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

## Attribution directe d’un rôle à un utilisateur

L'attribution directe d'un rôle à un utilisateur est une méthode fondamentale pour la gestion des accès et des permissions au sein de notre système. Cette approche permet de définir précisément les actions qu'un utilisateur est autorisé à effectuer. En attribuant un rôle personnel, nous accordons à cet utilisateur un ensemble prédéfini de droits, facilitant ainsi le contrôle et la supervision de l'accès aux ressources et aux fonctionnalités de l'application.

### Étapes pour attribuer un rôle personnel à un utilisateur :

1. **Accéder à la modification de l’utilisateur**
   Pour modifier un utilisateur, vous devez disposer de la permission **Gestion des utilisateurs / Écriture**. Deux chemins sont possibles pour accéder à l’édition d’un utilisateur :
   - Depuis la **page de détail** de l’utilisateur, en cliquant sur le bouton **Modifier**
   <img src="https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/gestion-des-droits/utilisateur/modifier-utilisateur-depuis-detail.png" height="200" />
![Menu d'accès à la création d'un rôle](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/role/acces-creer-un-role.png)

   - Depuis la **liste des utilisateurs**, en cliquant sur le bouton **Modifier** situé sur la ligne correspondante
   <img src="https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/gestion-des-droits/utilisateur/modifier-utilisateur-depuis-liste.png" height="200" />
![Menu d'accès à la création d'un rôle](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/role/acces-creer-un-role.png)

2. **Choix du rôle** :  
   Dans la liste **Rôle personnel**, sélectionnez le rôle souhaité parmi les rôles disponibles dans le système en recherchant via le nom ou dans la liste déroulante.
   <img src="https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/gestion-des-droits/utilisateur/attribuer-role-personnel.png" height="200" />
![Menu d'accès à la création d'un rôle](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/role/acces-creer-un-role.png)
   
3. **Périmètre** :  
   Le rôle personnel est automatiquement attribué aux organisations de l’utilisateur qui effectue l’action.
   <img src="https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/gestion-des-droits/utilisateur/role-personnel-attribue.png" height="200" />
![Menu d'accès à la création d'un rôle](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/role/acces-creer-un-role.png)

   Le périmetre de ce rôle est modifiable lorsque vous cliquez sur le bouton **Modifier le périmetre(x)**
   Retrouvez dans la section [06 - Modifier les droits d’accès](06-modifier-les-droits-dacces), Modifier un périmetre

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
![Menu d'accès à la modification d'un utilisateur](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/utilisateur/modifier-utilisateur-depuis-detail.png)

2. **Choix du groupe** :  
   Dans la liste **groupe d’utilisateur**, sélectionnez le groupe souhaité
![liste des groupes associables à un utilisateur](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/groupe/liste-groupe-utilisateur.png)

3. **Périmètre** :  
   Hérité du groupe utilisateur sélectionné
4. **Confirmation** :  
   Cliquez sur **Modifier l'utilisateur**

#### 2. Depuis la page de modification d’un groupe utilisateur

1. Accédez à la modification du groupe utilisateur
![Menu d'accès à la modification d'un groupe](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/groupe/modifier-un-groupe.png)

2. **Choix de l’utilisateur** :  
   Recherchez l’utilisateur via son nom/prénom dans la section **Membres du groupe** puis cliquez sur **Ajouter au groupe**
![liste des utilisateurs associables à un groupe](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/groupe/ajouter-utilisateur-au-groupe.png)

3. **Confirmation** :  
   Cliquez sur **Modifier le groupe**
   L'utilisateur possède les rôles du groupe auquel il appartient

---

### En résumé

L'attribution indirecte via groupes est une **pratique recommandée** pour une gestion structurée et sécurisée des droits. Elle :

- Simplifie les opérations
- Facilite la maintenance
- Améliore l’organisation
- Renforce la sécurité globale du système

### Pour aller plus loin
-> [06 - Modifier les rôles, groupes et utilisateurs](06-modifier-les-droits-dacces)
   
[Retour à l'Accueil](../accueil)
