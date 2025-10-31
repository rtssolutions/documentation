---
title: "02 - Définitions et concepts clés"
description: "Concepts fondamentaux et notions clés sur les employeurs dans Papaours."
date: "2025-10-31"
version: "1"
---

## Concepts fondamentaux

### Employeur

Un employeur représente une entité légale ou commerciale avec laquelle votre organisation a des relations contractuelles
ou administratives.  
Sa fiche regroupe l’ensemble des informations nécessaires au suivi administratif, juridique et contractuel.

Un employeur est caractérisé par :

- **Nom commercial**
- **Dénomination sociale**
- **SIREN / SIRET**
- **Adresse complète**
- **Code APE / NAF**
- **IDCC (Identifiant de Convention Collective)**
- **Statut entreprise** : actif, fermé, etc.
- **Statut personnalisé** : champs libre pour cas spécifiques
- **Régime social**
- **Caisse de retraite**
- **Coordonnées** : téléphone, mail, site internet
- **Effectif total**
- **Convention collective principale et autres conventions applicables**
- **Soumis à la TVA / régime et taux**

### Visibilité

La visibilité définit quelles organisations ou centres de formation peuvent consulter ou modifier un employeur.  
Elle est générée automatiquement lors de la création d’un employeur et peut être personnalisée depuis la fiche employeur
si l’utilisateur dispose des droits nécessaires.
A la création d'un employeur, celui-ci est visible par l'organisation créatrice ainsi que tout ses organisations
parents. Ainsi si l'employeur à tété créer par l'organisation centre de formation, seul le centre de formation aura la
visibilité sur celui-ci. En revanche si celui-ci est créé par une organisation unité de formation, celui-ci sera visible
par l'unité créatrice et le centre de formation.
Lors du rattachement d'un employeur à un brouillon de contrat, la visibilité est automatiquement augmenté pour y ajouté
l'organisation associé à ce brouillon de contrat (= l'unité de formation lié au brouillon de contrat).

### Code employeur

Chaque employeur possède un **code unique** généré automatiquement au moment de sa création, respectant le format :  
`EMPYYYY-XXXXXX`  
où `YYYY` est l’année de création et `XXXXXX` un compteur incrémental.

---

### Pour aller plus loin

➡️ Poursuivez avec la page suivante :  
[03 - Accéder à la gestion des employeurs](03-acceder-gestion-employeurs.md)
