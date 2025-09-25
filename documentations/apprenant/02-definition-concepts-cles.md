---
title: "02 - Définitions des concepts clés"
description: ""
date: "2025-09-25"
version: "1"
---

## Concepts fondamentaux

### Apprenant
Un apprenant représente une personne physique inscrite ou en cours d'inscription dans un parcours de formation.  
Sa fiche regroupe l’ensemble des informations nécessaires au suivi administratif, pédagogique et contractuel.  
Un apprenant est caractérisé par :
- **Code** : Identifiant auto-généré unique pour chaque apprenant (l'unicité est garantie dans le temps même en cas de suppression)
- **Identité** : Nom, Prénom, Date de naissance, Lieu de naissance, Nationalité, NIR, Sexe
- **Moyens de contact** : Adresse postale, Téléphone, Courriel
- **Parcours scolaire** : Informations relatives au parcours scolaire que l'apprenant a réalisé
- **Besoins spécifiques** : Informations relatives aux besoins spécifiques de l'apprenant (RQTH, Sportif de haut niveau, etc.)
- **Représentants légaux** : Informations sur le représentant légal de l'apprenant (si mineur non émancipé ou sous curatelle/tutelle)

### Représentant légal
Un représentant légal est une personne physique agissant au nom et pour le compte d'un apprenant mineur non émancipé ou sous curatelle/tutelle.  
Il est caractérisé par :
- **Identité** : Nom, Prénom
- **Moyens de contact** : Adresse postale, Téléphone, Courriel
- **Lien de parenté** : Nature du lien avec l'apprenant (parent, tuteur, père, mère, etc.)
Le représentant légal posséde sa propre permission décorrélée de celle de l'apprenant.

### Besoins spécifiques
Les besoins spécifiques sont un ensemble d'informations relatives aux besoins particuliers d'un apprenant, tels que la Reconnaissance de la Qualité de Travailleur Handicapé (RQTH), le statut de sportif de haut niveau, ou d'autres besoins nécessitant des aménagements spécifiques dans le cadre de la formation.  
Ces données sont particulièrement sensibles et nécessitent une gestion spécifique, hors du parcours classique d'un apprenant, pour garantir la confidentialité et le respect des droits de l'apprenant.
Les besoins spécifiques sont gérés via des permissions dédiées, assurant que seules les personnes autorisées peuvent accéder et modifier ces informations.

### Pour aller plus loin
-> [03 - Accéder à la gestion des apprenants](03-acceder-gestion-apprenants)
