---
title: "01 - Historique des actions"
description: "Module de recherche et de visualisation des actions utilisateurs par entité"
date: "2025-07-31"
version: "1"
---
## 📚 Table des matières
1. [Objectif et bénéfices](#objectif-et-bénéfices)
2. [Présentation générale](#présentation-générale)  
3. [Description et règles de gestion](#description-et-règles-de-gestion)  
4. [Visibilité et périmètre](#visibilité-et-périmètre)  
5. [Affichage des résultats](#affichage-des-résultats)  
6. [Comportement en absence de résultat](#comportement-en-absence-de-résultat)  
7. [Objectif et bénéfices](#objectif-et-bénéfices)

---

## Objectif et bénéfices
L’objectif de cette fonctionnalité est de **conserver la mémoire des actions** liées à chaque entité. Elle permet :
- Aux utilisateurs habilités de **comprendre l’état actuel d’une entité**
- D’assurer une **traçabilité métier forte**

---
## Présentation générale
Le module **Historique des actions** permet de consulter toutes les actions réalisées par les utilisateurs sur les différentes entités manipulées dans la plateforme Papaours.  
Par entité, on entend tout objet métier structurant comme un **apprenant**, **contrat**, **dossier**, **formation**, etc.

Chaque action est historisée avec ses métadonnées (date, auteur, type d'action), permettant ainsi un suivi précis, utile à la fois pour la traçabilité, l'audit, et la compréhension métier.

---

## Accès à l'historique
L’utilisateur accède au module de recherche dédié à l’historique des actions via le menu **Historique** présent dans le menu contextuel.
Vous devez disposer de la permissions Gestion de l'historique / Historique / Lecture
![permissions historique](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/historique/permissions-historique.png)


Le module de recherche d'historique permet de rechercher en appliquant des filtres : 
- **Entité concernée** (ex. : Apprenant, Formation, Contrat, etc.)
- **Code de l’entité** (ex. : A2025-000123)  
  → Il s’agit d’un code fonctionnel, pas d’un identifiant technique.
- **Action réalisée** (ex. : création, modification, validation, suppression, etc.)
- **Intervalle de dates** (date de début et date de fin)  
  → La date de fin doit être supérieure ou égale à la date de début.
---

## Visibilité et périmètre
Seules les **entités visibles par l’utilisateur** sont affichées dans les résultats.  
La visibilité est déterminée par :
- Le **périmètre organisationnel** de l'utilisateur
- L’existence d’un droit d’accès à l’entité concernée

Une action est visible uniquement si l’utilisateur **a le droit de consulter l’entité concernée**.

---

## Affichage des résultats
Les résultats sont présentés dans un **tableau trié par date décroissante**. Chaque ligne affiche :
- Entité concernée
- Code de l’entité (ex. : A2025-XXXXXX)
- Numéro de version (compteur d’évolution de l’entité)
- Action réalisée
- Date de l’action
- Auteur de l’action
- une action **"Détails"**

---

## Comportement en absence de résultat
Si **aucune action** ne correspond aux critères OU n’est **visible** pour l’utilisateur :
- Le tableau est **masqué**
- Le message suivant est affiché :

> _"Aucun historique d’actions n’a été trouvé avec vos critères de recherche. Modifiez vos critères de recherche pour obtenir l’historique"_

---

[Retour à l'Accueil](../accueil)
