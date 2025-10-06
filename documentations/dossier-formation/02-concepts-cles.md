---
title: "02 - Définition des concepts clés"
description: "Concepts fondamentaux pour comprendre les dossiers de formation"
date: "2025-09-29"
version: "1"
---

## Concepts fondamentaux

### Dossier de formation

Un dossier de formation est l'élément central qui matérialise le parcours d'un apprenant au sein d'une session de formation.
**Il est créé automatiquement** lors de l'inscription d'un apprenant à une formation et l'accompagne jusqu'à la fin de son parcours.

Le dossier de formation est caractérisé par :
- **Numéro unique** : Identifiant auto-généré pour chaque dossier
- **Apprenant** : La personne inscrite à la formation
- **Session de formation** : La session à laquelle l'apprenant est inscrit
- **État** : Situation actuelle du dossier (voir section dédiée)
- **Dates** : Date d'inscription, d'entrée en formation, de fin prévue
- **Documents** : Ensemble des pièces téléchargées et liées au dossier
- **Contrat** : Le ou les contrats d'apprentissage associés (si existant)

### État du dossier (Situation actuelle)

L'état du dossier est affiché visuellement dans l'interface sous le libellé **"Situation actuelle"**.
Cette information cruciale détermine les actions possibles et reflète l'avancement du parcours.

#### Les 5 états possibles

1. **Inscrit à la formation**
   - État initial après inscription
   - Permet la création d'un contrat
   - Aucun contrat actif

2. **SFP avant contrat**
   - Statut de Formation Professionnelle
   - Période transitoire avant signature du contrat

3. **Apprenti sous contrat**
   - Contrat d'apprentissage actif
   - Formation en cours

4. **Contrat terminé**
   - Fin normale ou rupture du contrat
   - Possibilité de nouveau contrat

5. **Inscription annulée**
   - Annulation de l'inscription
   - Aucune action possible

### Session de formation

La session de formation représente une période définie durant laquelle se déroule une formation.
Le dossier est obligatoirement rattaché à une session spécifique.

### Règles métier essentielles

#### Unicité de l'inscription
- **Un apprenant ne peut être inscrit qu'une seule fois** à une même session
- Tentative de double inscription = message d'erreur
- Contrôle automatique à la création

#### Conditions de création de contrat
Un brouillon de contrat ne peut être créé que si :
-  Le dossier est à l'état **"Inscrit à la formation"**
-  L'apprenant n'est pas en SFP
-  L'apprenant n'a pas de contrat actif
-  L'inscription n'est pas annulée

#### Transitions d'état automatiques
Les changements d'état se font automatiquement selon les événements :
- **Signature d'un contrat** → Passage à "Apprenti sous contrat"
- **Fin ou rupture de contrat** → Passage à "Contrat terminé"
- **Annulation de l'inscription** → Passage à "Inscription annulée"

### Liens avec les autres modules

#### Module Apprenant
- Le dossier est créé depuis la fiche apprenant
- Les informations personnelles sont synchronisées
- L'historique des dossiers est visible sur la fiche

#### Module Contrats
- Le contrat est créé depuis le dossier
- Les états sont synchronisés entre dossier et contrat

#### Module Formation
- Le dossier est lié à une session de formation spécifique

### Pour aller plus loin
→ [03 - Comprendre la situation actuelle](03-situation-actuelle.md)