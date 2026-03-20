---
title: "04 - Inscription d'un apprenant"
description: "Comment inscrire un apprenant depuis la page apprenant"
date: "2025-01-28"
version: "1"
---
## Inscription d'un apprenant

### Vue d'ensemble

L'inscription d'un apprenant dans Papaours permet de créer son dossier de formation et de l'associer à une session de formation.

### Procédure d'inscription depuis la page apprenant

Le processus d'inscription d'un apprenant est illustré dans cette vidéo tutorielle :

<video controls>
  <source src="https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/dossier-formation/dev.gestion.papaours.cloud_dashboard_apprenant_pageNumber%3D2.mp4" type="video/mp4" />
</video>

La vidéo montre comment :
1. Accéder à la page apprenant
2. Créer un nouveau dossier d'inscription
3. Associer l'apprenant à une session de formation
4. Choisir la date d'entrée en formation
  - Cette date doit être comprise entre le début et la fin de la session
  - **Important** : La date d'entrée ne peut pas être modifiée après la création du dossier
Le nombre de places disponible dans la session est incrémenté automatiquement.

### Prérequis

Avant de procéder à l'inscription :
- L'apprenant doit exister dans le système
- La session de formation doit être créée et active
- Vous devez disposer des droits nécessaires pour inscrire un apprenant

### Règle d'unicité de l'inscription
- Un apprenant **ne peut être inscrit** qu'une seule fois à une même session de formation.
- Un apprenant **ne peut être inscrit** qu'à une seule session de la même action de formation

Si vous tentez d'inscrire un apprenant déjà inscrit à la session, le système affichera un message d'erreur et l'inscription sera refusée.

### Après l'inscription

Une fois l'apprenant inscrit, plusieurs options s'offrent à vous :
- **Créer directement un contrat** si l'apprenant a trouvé un employeur
- **Déclarer l'apprenant en SFP avant contrat** (Stagiaire de la Formation Professionnelle avant contrat) s'il n'a pas encore de contrat
  - La création peut être manuelle ou automatique selon votre paramétrage
  - La période SFP avant contrat permet à l'apprenant de commencer sa formation en attendant la signature du contrat d'apprentissage
  - → [Voir le fonctionnement détaillé des SFP avant contrat](06-fonctionnement-sfp)

## Pour aller plus loin
→ [05 - Annulation d'une inscription](05-annulation-inscription)
→ [06 - Fonctionnement des SFP avant contrat](06-fonctionnement-sfp)