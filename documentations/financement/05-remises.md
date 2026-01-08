---
title: "05 - Les remises"
description: "Gestion des remises sur les ventilations et les financeurs"
date: "2025-01-08"
version: "1"
---

## Les types de remises

Papaours gère deux niveaux de remises dans le module Financement :

| Type | Niveau d'application | Description |
|------|---------------------|-------------|
| Remise de ventilation | Sur une ventilation spécifique | Réduit le montant dû pour une prestation donnée |
| Remise financeur | Sur l'ensemble d'un financeur | S'applique au total dû par le financeur |

---

## Remises de ventilation

### Définition

Une **remise de ventilation** s'applique à une ventilation spécifique, c'est-à-dire à l'attribution d'un montant d'une prestation à un financeur.

### Caractéristiques

| Propriété | Description |
|-----------|-------------|
| Type | Pourcentage ou montant fixe |
| Valeur | Le pourcentage ou le montant de la remise |
| Libellé | Description optionnelle de la remise |
| Ordre | Position dans la chaîne de calcul |

### Types de remise

| Type | Code | Calcul |
|------|------|--------|
| Pourcentage | `POURCENTAGE` | Montant × (Valeur / 100) |
| Montant fixe | `FIXE` | Valeur directe |

### Exemple de calcul

**Ventilation** : 1 000 € sur OPCO pour la prestation pédagogie

| Remise | Type | Valeur | Montant remise | Montant restant |
|--------|------|--------|----------------|-----------------|
| Remise fidélité | Pourcentage | 10% | 100 € | 900 € |
| Remise exceptionnelle | Fixe | 50 € | 50 € | 850 € |

**Montant dû après remises** : 850 €

### Ordre d'application

Les remises sont appliquées dans l'ordre défini. Le montant d'une remise en pourcentage est calculé sur le montant restant après application des remises précédentes.

---

## Remises financeur

### Définition

Une **remise financeur** s'applique à l'ensemble des ventilations d'un financeur. Elle est calculée après les remises de ventilation.

### Base de calcul

La remise financeur est calculée sur le **montant dû après remises de ventilation** :

```
Base = Somme des montants ventilés - Somme des remises de ventilation
Remise financeur = Base × (Pourcentage / 100) [ou valeur fixe]
```

### Exemple complet

**Financeur OPCO** avec 2 ventilations :

| Prestation | Ventilé | Remise ventilation | Montant dû |
|------------|---------|-------------------|------------|
| Pédagogie | 1 000 € | 100 € (10%) | 900 € |
| Hébergement | 500 € | 50 € (fixe) | 450 € |

**Sous-total avant remise financeur** : 1 350 €

**Remise financeur** : 5% = 67,50 €

**Total dû par l'OPCO** : 1 282,50 €

---

## Récapitulatif des montants

### Par financeur

Pour chaque financeur, le système affiche :

| Indicateur | Calcul |
|------------|--------|
| Montant total ventilé | Somme des montants des ventilations |
| Montant total remises | Remises ventilation + Remise financeur |
| Montant total dû | Ventilé - Remises totales |

### Global

Au niveau du dossier :

| Indicateur | Calcul |
|------------|--------|
| Montant total prestations | Somme des montants HT des prestations |
| Montant total ventilé | Somme de tous les montants ventilés |
| Montant total remises ventilation | Somme des remises de ventilation |
| Montant total remises financeurs | Somme des remises financeur |
| Reste à ventiler | Total prestations - Total ventilé |

---

## Scénario complet

Voici un exemple illustrant l'ensemble des mécanismes de remises :

### Données initiales

- **Prestation pédagogie** : 3 000 € HT
- **Prestation hébergement** : 600 € HT
- **Total prestations** : 3 600 €

### Financeur OPCO

**Ventilations :**

| Prestation | Montant ventilé | Remise | Type remise | Montant dû |
|------------|-----------------|--------|-------------|------------|
| Pédagogie (1) | 1 000 € | 100 € | 10% | 900 € |
| Pédagogie (2) | 500 € | 50 € | Fixe | 450 € |
| **Sous-total ventilations** | **1 500 €** | **150 €** | - | **1 350 €** |

**Remise financeur :** 5% sur 1 350 € = **67,50 €**

**Total dû par l'OPCO :** 1 350 € - 67,50 € = **1 282,50 €**

**Récapitulatif OPCO :**

| Indicateur | Montant |
|------------|---------|
| Montant ventilé | 1 500 € |
| Remises ventilation | 150 € |
| Remise financeur | 67,50 € |
| Total remises | 217,50 € |
| Montant dû | 1 282,50 € |

### Financeur Employeur

**Ventilations :**

| Prestation | Montant ventilé | Remise | Type remise | Montant dû |
|------------|-----------------|--------|-------------|------------|
| Hébergement | 300 € | 0 € | - | 300 € |

**Remise financeur :** 20 € (fixe)

**Total dû par l'Employeur :** 300 € - 20 € = **280 €**

**Récapitulatif Employeur :**

| Indicateur | Montant |
|------------|---------|
| Montant ventilé | 300 € |
| Remises ventilation | 0 € |
| Remise financeur | 20 € |
| Total remises | 20 € |
| Montant dû | 280 € |

### Récapitulatif global

| Indicateur | Montant |
|------------|---------|
| Total prestations | 3 600 € |
| Total ventilé | 1 800 € |
| Total remises ventilation | 150 € |
| Total remises financeurs | 87,50 € |
| Reste à ventiler | 1 800 € |

---

### Pour aller plus loin

Poursuivez avec la page suivante :
[06 - Participation obligatoire employeur](06-participation-employeur)
