---
title: "04 - Qualité des données"
description: "Indicateurs et outils pour maintenir la qualité des données dans Papaours"
date: "2026-03-20"
version: "1"
---

# Qualité des données

## Importance de la qualité

La qualité des données est essentielle pour le bon fonctionnement de Papaours. Des données complètes et cohérentes permettent :

- Une **génération correcte des documents** (CERFA, attestations)
- Une **transmission fiable** aux organismes (OPCO, DECA)
- Un **suivi précis** des apprenants et des contrats

## Indicateurs de qualité

### Taux de complétion

Le taux de complétion indique le pourcentage de champs renseignés sur une fiche :

```
Taux = (Champs renseignés / Champs obligatoires) × 100
```

- **100%** : Fiche complète, prête à être utilisée
- **< 100%** : Champs manquants à compléter

### Visualisation

Papaours affiche visuellement l'état de complétion :

- **Indicateur vert** : fiche complète
- **Indicateur orange** : fiche partiellement complète
- **Indicateur rouge** : informations critiques manquantes

## Champs manquants

### Liste des champs à compléter

Pour chaque fiche incomplète, Papaours fournit :

- La **liste des champs manquants**
- Le **caractère obligatoire** de chaque champ
- Un **lien direct** vers la section concernée

### Types de champs

| Type | Description | Exemple |
|------|-------------|---------|
| **Obligatoire** | Indispensable au fonctionnement | NIR de l'apprenant |
| **Recommandé** | Important pour la qualité | Email de contact |
| **Optionnel** | Informatif | Commentaires |

## Champs invalides

### Détection automatique

Le système détecte automatiquement les erreurs de saisie :

- **Format incorrect** : email mal formaté, SIRET invalide
- **Incohérence** : date de fin avant date de début
- **Valeur hors plage** : âge négatif, montant aberrant

### Correction

Pour corriger un champ invalide :

1. Accédez à la fiche concernée
2. Localisez le champ signalé (généralement surligné en rouge)
3. Corrigez la valeur
4. Enregistrez les modifications

## Bonnes pratiques

### À la saisie

- **Renseignez tous les champs obligatoires** dès la création
- **Vérifiez les formats** avant d'enregistrer
- **Utilisez les valeurs suggérées** quand disponibles

### En maintenance

- **Contrôlez régulièrement** les indicateurs de qualité
- **Corrigez rapidement** les anomalies détectées
- **Formez les utilisateurs** aux bonnes pratiques de saisie

## Outils de contrôle

### Tableau de bord qualité

Un tableau de bord synthétise l'état de vos données :

- Nombre de fiches complètes / incomplètes
- Répartition par module (Apprenants, Employeurs, Contrats)
- Évolution dans le temps

### Exports de contrôle

Vous pouvez exporter la liste des fiches incomplètes pour :

- Planifier les actions de correction
- Répartir le travail entre les équipes
- Suivre l'avancement des corrections
