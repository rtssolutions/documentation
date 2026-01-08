---
title: "02 - Définitions et concepts clés"
description: "Concepts fondamentaux du module de financement dans Papaours"
date: "2025-01-08"
version: "1"
---

## Concepts fondamentaux

### Dossier de financement apprentissage

Le **dossier de financement** est l'entité centrale du module. Il est créé automatiquement lors du financement d'un contrat d'apprentissage et regroupe :

- Le lien vers le **contrat** concerné
- La liste des **financeurs** associés
- Les **prestations vendues** à financer
- Les **ventilations** répartissant les montants
- Les **remises** applicables
- Le **récapitulatif** des montants

**Format du code** : `DFA-YYYY-XXXXXX`
- `DFA` : Dossier Financement Apprentissage
- `YYYY` : Année de création
- `XXXXXX` : Compteur incrémental

### Statut du dossier

Un dossier de financement peut avoir les statuts suivants :

| Statut | Description |
|--------|-------------|
| `EN_COURS` | Le dossier est en cours de traitement, les ventilations peuvent être modifiées |
| `CLOTURE` | Le dossier est finalisé, aucune modification possible |

---

## Les financeurs

### Définition

Un **financeur** est une entité qui prend en charge tout ou partie du coût de la formation. Chaque financeur est caractérisé par :

- Un **code** unique (ex: `OPCO-2025-000001`)
- Un **type de financeur** (voir ci-dessous)
- Une **dénomination** (nom du financeur)
- Un **statut** (actif/inactif)

### Types de financeurs

Papaours gère quatre types de financeurs :

| Code | Intitulé | Description |
|------|----------|-------------|
| `OPCO` | Opérateur de compétences | Organisme collecteur des fonds de formation |
| `EMPLOYEUR` | Employeur | L'entreprise qui emploie l'apprenti |
| `REGION` | Région | Financement régional complémentaire |
| `AUTRE` | Autre | Tout autre type de financeur |

### Association automatique des financeurs

Lors de la création d'un dossier de financement, le système associe automatiquement :

1. **L'OPCO** : récupéré depuis la fiche employeur du contrat
2. **L'Employeur** : systématiquement associé pour gérer les éventuels restes à charge

---

## Les prestations vendues

### Définition

Une **prestation vendue** représente un service facturé dans le cadre de la formation. Elle est caractérisée par :

- Un **type de prestation** (pédagogie, hébergement, etc.)
- Un **montant HT**
- Un **taux de TVA**
- Une **unité de vente** (forfait, heure, nuitée, etc.)
- Un caractère **obligatoire** ou non

### Prestation obligatoire

Certaines prestations sont marquées comme **obligatoires**. Elles :
- Sont ajoutées automatiquement au dossier de financement
- Ne peuvent pas être supprimées
- Ont une ventilation créée automatiquement

---

## Le récapitulatif de financement

Le système calcule automatiquement un récapitulatif comprenant :

| Indicateur | Description |
|------------|-------------|
| Montant total prestations | Somme des montants HT de toutes les prestations |
| Montant total ventilé | Somme des montants attribués aux financeurs |
| Reste à financer | Différence entre le total et le ventilé |
| Est complètement financé | Vrai si le reste à financer est nul ou négatif |
| Taux de couverture global | Pourcentage du montant ventilé sur le total |

### Formules de calcul

```
Reste à financer = Montant total prestations - Montant total ventilé

Taux de couverture = (Montant ventilé / Montant total) × 100
```

---

### Pour aller plus loin

Poursuivez avec la page suivante :
[03 - Les types de prestations](03-types-prestations)
