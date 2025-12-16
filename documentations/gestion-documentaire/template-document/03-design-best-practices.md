---
title: "03 - Bonnes pratiques de conception des templates"
description: "Recommandations et bonnes pratiques pour concevoir des templates de document efficaces et maintenables"
date: "2025-11-20"
version: "1"
---

# Bonnes pratiques de conception des templates

## Objectif

Cette page présente les **bonnes pratiques de conception** pour créer des templates de document robustes, lisibles et faciles à maintenir lorsqu’ils sont utilisés avec la plateforme.

Ces recommandations visent à :
- Améliorer la lisibilité des templates
- Réduire les erreurs lors de la génération
- Faciliter l’évolution des documents dans le temps

---

## Séparer la mise en forme et les données

Un template doit avant tout se concentrer sur :
- La **structure du document**
- La **mise en page**
- La **présentation visuelle**

Les données, quant à elles, doivent rester dans le **JSON fourni par l’application**.

👉 Évitez de coder de la logique métier complexe directement dans le template.

---

## Garder les templates simples

Un template simple est :
- Plus facile à comprendre
- Plus rapide à maintenir
- Moins sujet aux erreurs

Recommandations :
- Limiter l’imbrication excessive de balises
- Préférer plusieurs petits templates plutôt qu’un seul très complexe
- Ajouter la logique progressivement, par itérations

---

## Utiliser des alias pour améliorer la lisibilité

Les **alias** permettent de définir des raccourcis pour des chemins de données longs ou répétés.

### Exemple

Au lieu d’écrire plusieurs fois :
```
{d.customer.address.street}
```

Déclarez un alias :
```
{#address = d.customer.address}
{address.street}
```

Avantages :
- Template plus lisible
- Moins de répétition
- Maintenance facilitée

---

## Structurer clairement les sections

Utilisez la structure naturelle du document (titres, tableaux, sections) pour :
- Identifier clairement les zones dynamiques
- Regrouper les données liées
- Faciliter la compréhension pour toute personne reprenant le template

---

## Tester avec des données réalistes

Toujours tester les templates avec :
- Des données complètes
- Des données partielles
- Des cas limites (valeurs nulles, listes vides)

Cela permet d’anticiper :
- Les erreurs de génération
- Les rendus inattendus
- Les problèmes de mise en page

---

## Gérer les valeurs manquantes

Il est recommandé de :
- Prévoir des valeurs par défaut
- Gérer les champs optionnels
- Éviter d’afficher des champs vides dans le document final

La plateforme fournit des mécanismes pour sécuriser l’affichage lorsque certaines données sont absentes.

---

## Versionner les templates

Les templates évoluent dans le temps.

Bonnes pratiques :
- Versionner les fichiers de template
- Documenter les changements majeurs
- Tester chaque nouvelle version avant mise en production

Cela facilite :
- Le retour arrière
- La traçabilité
- La maintenance à long terme

---

## Bonnes pratiques générales

- Nommer clairement les fichiers de template
- Commenter les sections complexes si nécessaire
- Éviter les dépendances implicites entre données
- Documenter les structures JSON attendues

---

## Pour aller plus loin

→ [Les bases des substitutions](02-les-basics)  
→ [Gestion des listes et tableaux dynamiques](#)  
→ [Conditions et logique avancée](#)
