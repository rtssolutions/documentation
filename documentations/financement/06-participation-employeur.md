---
title: "06 - Participation obligatoire employeur"
description: "Règles de participation obligatoire de l'employeur pour les diplômes de niveau supérieur à 5"
date: "2025-01-08"
version: "1"
---

## Contexte réglementaire

La réforme du financement de l'apprentissage introduit une **participation obligatoire de l'employeur** pour les formations préparant à des diplômes de niveau supérieur à 5 (nomenclature européenne).

Cette mesure vise à faire participer les employeurs au financement des formations de niveau supérieur (Licence, Master, Ingénieur, etc.).

---

## Conditions d'éligibilité

La participation obligatoire employeur est ajoutée automatiquement lorsque **toutes** les conditions suivantes sont réunies :

| Critère | Condition |
|---------|-----------|
| Niveau du diplôme | Supérieur à 5 (niveaux 6, 7, 8) |
| Date de conclusion | Contrat conclu **après le 30 juin 2025** |
| Voie d'accès | Apprentissage |

### Niveaux de diplôme concernés

| Niveau | Intitulé | Exemples |
|--------|----------|----------|
| 6 | Licence | Licence professionnelle, Bachelor |
| 7 | Master | Master, Diplôme d'ingénieur |
| 8 | Doctorat | Doctorat |

### Niveaux non concernés

| Niveau | Intitulé | Exemples |
|--------|----------|----------|
| 3 | CAP | CAP, BEP |
| 4 | Baccalauréat | Bac Pro, BP |
| 5 | BTS/DUT | BTS, DUT, DEUST |

---

## Montant de la participation

Le montant de la participation obligatoire employeur est fixé à :

| Montant HT | TVA | Unité de vente |
|------------|-----|----------------|
| **750,00 €** | 0% | Forfait |

Ce montant est défini au niveau système et s'applique uniformément à tous les contrats éligibles.

---

## Mécanisme d'application

### Création automatique

Lors du financement d'un contrat éligible, le système :

1. **Vérifie** les conditions d'éligibilité
2. **Ajoute** la prestation "Participation Employeur – Diplôme niveau supérieur à 5"
3. **Crée** la ventilation correspondante sur le financeur Employeur
4. **Marque** la prestation et la ventilation comme obligatoires

### Caractéristiques de la prestation

| Propriété | Valeur |
|-----------|--------|
| Code | `PAPAOURS-TPT-PARTICIPATION-OBLIGATOIRE-EMPLOYEUR` |
| Intitulé | Participation Employeur – Diplôme niveau supérieur à 5 |
| Montant | 750,00 € HT |
| Obligatoire | Oui |
| Supprimable | Non |

---

## Impact sur le dossier de financement

### Financeur Employeur

Si l'employeur n'est pas déjà présent comme financeur dans le dossier, il est automatiquement ajouté lors de l'application de la participation obligatoire.

### Exemple de dossier avec participation

**Contrat d'apprentissage** :
- Formation : Master Management
- Niveau RNCP : 7
- Date de conclusion : 01/09/2025

**Dossier de financement** :

| Prestation | Montant | Financeur | Ventilé |
|------------|---------|-----------|---------|
| Pédagogie | 8 000 € | OPCO | 8 000 € |
| **Participation employeur** | **750 €** | **Employeur** | **750 €** |
| **Total** | **8 750 €** | | **8 750 €** |

---

## Cas de non-éligibilité

La participation obligatoire **n'est pas appliquée** dans les cas suivants :

### Niveau insuffisant

```
Exemple : Contrat pour un BTS (niveau 5)
→ Pas de participation obligatoire
```

### Date de conclusion antérieure

```
Exemple : Contrat conclu le 15/06/2025
→ Pas de participation obligatoire (avant le 30/06/2025)
```

### Autre voie d'accès

```
Exemple : Contrat de professionnalisation niveau 6
→ Règle spécifique à l'apprentissage, non applicable
```

---

## Vérification dans le système

Le système affiche clairement :

- La présence de la participation obligatoire dans la liste des prestations
- Le caractère **obligatoire** de la prestation (non supprimable)
- La ventilation automatique vers le financeur Employeur

---

## Règles de gestion

| Règle | Comportement |
|-------|--------------|
| Suppression de la prestation | Interdite (erreur) |
| Suppression de la ventilation | Interdite (erreur) |
| Modification du montant | Non applicable (montant fixe système) |
| Ajout de remise sur cette ventilation | Autorisé |

---

### Pour aller plus loin

Poursuivez avec la page suivante :
[07 - Dates et durée du financement](07-dates-duree)
