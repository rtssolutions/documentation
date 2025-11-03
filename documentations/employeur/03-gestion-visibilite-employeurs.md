---
title: "03 - Gestion de la visibilité des employeurs"
description: "Règles et fonctionnement de la visibilité des employeurs dans Papaours."
date: "2025-10-31"
version: "1"
---

## Table des matières

1. [Définition](#définition)
2. [Règles de visibilité à la création](#règles-de-visibilité-à-la-création)
3. [Extension automatique de visibilité](#extension-automatique-de-visibilité)
4. [Modification manuelle de la visibilité](#modification-manuelle-de-la-visibilité)
5. [Cas d’usage et exemples](#cas-dusage-et-exemples)
6. [Bonnes pratiques](#bonnes-pratiques)

---

## Définition

La **visibilité** détermine **quelles organisations** (centre de formation, unité, etc.) peuvent **consulter** un employeur.

Chaque fiche employeur est associée à un **ensemble d’organisations visibles** et une organisation propriétaire (actuellement le centre de formation).  
Cette visibilité peut être :
- **générée automatiquement** à la création de l’employeur, ou
- **modifiée manuellement** par un utilisateur disposant des droits adéquats.

---

## Règles de visibilité à la création

Lorsqu’un employeur est créé :

- L’employeur est automatiquement **visible par l’organisation créatrice** et devient la propriété du centre de formation.
- La visibilité s’étend **à toutes les organisations parentes** de celle-ci (hiérarchie ascendante).

## Extension automatique de visibilité

Certaines actions dans Papaours entraînent **une extension automatique** de la visibilité :

- **Lors du rattachement à un brouillon de contrat** :  
  L’organisation associée au brouillon (généralement l’unité de formation) obtient la visibilité sur l’employeur.
- **Lors de la création d’un contrat à partir d’un brouillon** :  
  Les organisations impliquées dans le contrat conservent ou obtiennent la visibilité.

---

## Modification manuelle de la visibilité

Si l’utilisateur dispose de la permission **écriture** sur les employeurs, il peut :

- Ajouter une ou plusieurs organisations à la liste des entités visibles ;
- Retirer une organisation (si elle n’est pas propriétaire de l’employeur) ;
- Consulter l’historique des modifications de visibilité.

Ces actions se réalisent depuis la fiche **Employeur > Encart Identité**.

> 💡 Astuce : une icône d’œil 👁️ indique le niveau d’accès actuel de chaque organisation.

---

## Cas d’usage et exemples

Lorsqu’une **unité de formation** crée un employeur, celui-ci devient automatiquement visible par l’unité créatrice et par ses organisations parentes, notamment le **centre de formation**.  
Cela permet à l’ensemble de la structure de travailler sur un référentiel commun.

Si un **employeur est ensuite rattaché à un contrat** d’une autre unité, cette nouvelle unité obtient **automatiquement la visibilité** sur l’employeur.  
Ainsi, chaque entité impliquée dans un contrat peut accéder à la fiche employeur correspondante.

En revanche, lorsqu’un **centre de formation met fin à un partenariat** avec une unité, il peut **retirer manuellement la visibilité** de cette unité, à condition qu’elle ne soit pas propriétaire de l’employeur.

Enfin, lorsqu’un **employeur devient commun à plusieurs entités**, par exemple à la suite d’une mutualisation ou d’un contrat inter-organisation, il est possible d’**ajouter explicitement ces organisations** à la visibilité pour partager la gestion.


---

## Bonnes pratiques

- **Créer les employeurs depuis le bon niveau hiérarchique** pour éviter une visibilité trop restreinte.
- **Ne pas multiplier inutilement les organisations visibles** afin de préserver la confidentialité des données.

---

### Pour aller plus loin

➡️ Poursuivez avec la page suivante :  
[04 - Lister les employeurs](04-lister-employeurs.md)
