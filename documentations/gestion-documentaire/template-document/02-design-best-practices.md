---
title: "02 - Bonnes pratiques de conception"
description: "Bonnes pratiques pour concevoir des templates de document avec la plateforme"
date: "2025-11-20"
version: "1"
---

# Bonnes pratiques de conception

## Objectif

Cette page présente les **bonnes pratiques recommandées** pour concevoir des templates de document avec la plateforme.

Elle est la **traduction fidèle** de la documentation originale et vise à aider à :
- Créer des templates plus lisibles
- Faciliter leur maintenance
- Réduire les erreurs lors de la génération de documents

---

## Concevoir d’abord le document

La première étape consiste à **concevoir le document sans aucune balise**.

- Créez la structure complète du document
- Travaillez la mise en page, les styles, les tableaux
- Vérifiez que le document est correct avec du contenu statique

👉 Le template doit être valide **avant** l’ajout de la moindre substitution.

---

## Ajouter les substitutions ensuite

Une fois la structure validée :
- Remplacez progressivement le contenu statique par des balises
- Ajoutez les substitutions **une par une**
- Testez régulièrement le rendu généré

Cela permet d’identifier rapidement l’origine d’une erreur.

---

## Limiter la logique dans les templates

Les templates ne doivent pas contenir de **logique métier complexe**.

Recommandations :
- Préparer les données côté application
- Fournir un JSON aussi proche que possible du rendu attendu
- Éviter les calculs ou règles complexes dans le template

---

## Utiliser des alias pour améliorer la lisibilité

Lorsque les chemins de données deviennent longs ou répétitifs, il est recommandé d’utiliser des **alias**.

### Exemple

```text
{#movie = d.movie}
{movie.title}
{movie.year}
```

Les alias permettent de :
- Rendre le template plus lisible
- Réduire les erreurs de saisie
- Faciliter la maintenance

---

## Travailler avec des données réelles

Il est fortement recommandé de tester les templates avec :
- Des données complètes
- Des données partielles
- Des tableaux vides
- Des valeurs nulles

Cela permet de s’assurer que le document reste cohérent dans tous les cas.

---

## Gérer les données manquantes

Si certaines données sont optionnelles :
- Prévoir des valeurs par défaut
- Utiliser des conditions pour masquer des sections
- Éviter l’affichage de champs vides

La plateforme fournit des mécanismes permettant de sécuriser l’affichage.

---

## Versionner les templates

Les templates évoluent avec le temps.

Bonnes pratiques :
- Conserver l’historique des versions
- Tester chaque nouvelle version
- Éviter de modifier un template déjà utilisé en production sans validation

---

## Tester régulièrement

Tester fréquemment permet de :
- Détecter rapidement les erreurs
- Vérifier la cohérence des données
- Garantir un rendu stable dans le temps

---

## Résumé des bonnes pratiques

- Concevoir le document avant d’ajouter des balises
- Ajouter les substitutions progressivement
- Limiter la logique dans les templates
- Utiliser des alias pour plus de lisibilité
- Tester avec des données réelles
- Versionner et tester régulièrement

## Pour aller plus loin

-> [03 - Les bases des substitutions](03-les-bascis)

