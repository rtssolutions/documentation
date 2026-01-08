---
title: "04 - La ventilation des prestations"
description: "Répartition des montants des prestations entre les différents financeurs"
date: "2025-01-08"
version: "1"
---

## Qu'est-ce que la ventilation ?

La **ventilation** est le mécanisme qui permet de répartir le montant d'une prestation entre un ou plusieurs financeurs. Elle définit "qui paie quoi" dans le dossier de financement.

### Caractéristiques d'une ventilation

Chaque ventilation est définie par :

| Propriété | Description |
|-----------|-------------|
| Financeur | Le financeur qui prend en charge ce montant |
| Prestation vendue | La prestation concernée |
| Montant ventilé | Le montant attribué à ce financeur pour cette prestation |
| Remises | Liste des remises applicables sur cette ventilation |

---

## Règles de ventilation

### Contrainte d'unicité

Une seule ventilation peut exister pour un couple **(financeur, prestation)**. Si une ventilation existe déjà, le système propose de modifier le montant existant plutôt que d'en créer une nouvelle.

### Contrainte de montant

Le montant ventilé ne peut pas dépasser le **reste à financer** pour la prestation concernée.

```
Montant maximum ventilable = Montant prestation - Montants déjà ventilés
```

**Exemple** :
- Prestation pédagogie : 5 000 €
- Ventilation OPCO existante : 4 000 €
- Montant maximum pour une nouvelle ventilation : 1 000 €

### Ventilations obligatoires

Certaines ventilations sont créées automatiquement et ne peuvent pas être supprimées :

- Ventilations liées à des **prestations obligatoires**
- Ventilation de la **participation obligatoire employeur** (si applicable)

Toute tentative de suppression d'une ventilation obligatoire génère une erreur.

---

## Création d'une ventilation

### Ventilation automatique

Lors de la création du dossier de financement, le système crée automatiquement :

1. Les ventilations pour les **prestations obligatoires**
2. La ventilation pour la **participation employeur** (si éligible)

### Ventilation manuelle

L'utilisateur peut créer des ventilations supplémentaires en spécifiant :

1. Le financeur concerné
2. La prestation à ventiler
3. Le montant à attribuer

---

## Modification d'une ventilation

Le montant d'une ventilation peut être modifié, sous réserve de respecter la contrainte de montant maximum.

**Calcul du montant disponible lors de la modification** :
```
Montant disponible = Reste à financer + Montant actuel de la ventilation
```

Cela permet de réattribuer le montant déjà ventilé vers un autre financeur ou de l'ajuster.

---

## Suppression d'une ventilation

Une ventilation peut être supprimée sauf si :

- Elle est liée à une **prestation obligatoire**
- Elle concerne une **participation obligatoire employeur**

Lors de la suppression, le montant ventilé est réintégré au "reste à financer".

---

## Calculs automatiques

### Montant dû par financeur

Pour chaque financeur, le système calcule :

```
Montant dû = Somme des montants ventilés - Somme des remises de ventilation
```

### Exemple de répartition

| Prestation | Montant | Financeur | Ventilé | Remise | Dû |
|------------|---------|-----------|---------|--------|-----|
| Pédagogie | 5 000 € | OPCO | 4 000 € | 400 € (10%) | 3 600 € |
| Pédagogie | 5 000 € | Employeur | 1 000 € | 0 € | 1 000 € |
| Hébergement | 500 € | OPCO | 500 € | 0 € | 500 € |

**Totaux** :
- Total prestations : 5 500 €
- Total ventilé : 5 500 €
- Reste à financer : 0 €
- Total dû OPCO : 4 100 €
- Total dû Employeur : 1 000 €

---

## États du financement

En fonction de la ventilation, le dossier peut être dans différents états :

| État | Condition | Signification |
|------|-----------|---------------|
| Partiellement financé | Reste à financer > 0 | Des montants restent à attribuer |
| Complètement financé | Reste à financer = 0 | Toutes les prestations sont couvertes |
| Sur-financé | Reste à financer < 0 | Le total ventilé dépasse le montant des prestations |

---

### Pour aller plus loin

Poursuivez avec la page suivante :
[05 - Les remises](05-remises)
