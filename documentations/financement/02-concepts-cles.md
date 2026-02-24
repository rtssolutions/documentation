---
title: "02 - Définitions et concepts clés"
description: "Concepts fondamentaux du module de financement dans Papaours"
date: "2025-01-08"
version: "1"
---

## Concepts fondamentaux

### Dossier de financement apprentissage

Le **dossier de financement** est l'entité centrale du module. Il est créé automatiquement lors du financement d'un
contrat d'apprentissage et regroupe :

- Le lien vers le **contrat** concerné
- La liste des **financeurs** associés
- Les **prestations vendues** à financer
- Les **ventilations** répartissant les montants
- Les **remises** applicables
- Le **récapitulatif** des montants

**Format du code** : `DFIAYYYY-XXXXXX`

- `DFIA` : Dossier Financement Apprentissage
- `YYYY` : Année de création
- `XXXXXX` : Compteur incrémental

### Statut du dossier

Un dossier de financement peut avoir les statuts suivants :

| Statut     | Description                                                                    |
|------------|--------------------------------------------------------------------------------|
| `EN_COURS` | Le dossier est en cours de traitement, les ventilations peuvent être modifiées |
| `CLOTURE`  | Le dossier est finalisé, aucune modification possible                          |

---

## Les financeurs

### Définition

Un **financeur** est une entité qui prend en charge tout ou partie du coût de la formation. Chaque financeur est
caractérisé par :

- Un **code** unique (ex: `FIN2025-000001`)
- Un **type de financeur** (voir ci-dessous)
- Une **dénomination** (nom du financeur)
- Un **statut** (actif/inactif)

### Types de financeurs

Papaours gère quatre types de financeurs :

| Code        | Intitulé                 | Description                                 |
|-------------|--------------------------|---------------------------------------------|
| `OPCO`      | Opérateur de compétences | Organisme collecteur des fonds de formation |
| `EMPLOYEUR` | Employeur                | L'entreprise qui emploie l'apprenti         |
| `REGION`    | Région                   | Financement régional complémentaire         |
| `AUTRE`     | Autre                    | Tout autre type de financeur                |

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

| Indicateur                | Description                                     |
|---------------------------|-------------------------------------------------|
| Montant total prestations | Somme des montants HT de toutes les prestations |
| Montant total ventilé     | Somme des montants attribués aux financeurs     |
| Reste à financer          | Différence entre le total et le ventilé         |
| Est complètement financé  | Vrai si le reste à financer est nul ou négatif  |
| Taux de couverture global | Pourcentage du montant ventilé sur le total     |

### Formules de calcul

```
Reste à financer = Montant total prestations - Montant total ventilé

Taux de couverture = (Montant ventilé / Montant total) × 100
```

---

## Les subventions

### Définition

Une **subvention** est un objet financier rattaché à un dossier de financement et proposé par un financeur. Elle représente une aide financière ou une réduction applicable au financement.

### Sens du montant

Le montant d'une subvention peut être :

| Sens | Signification | Exemple |
|------|---------------|---------|
| **Positif** | Aide financière, prise en charge | NPEC OPCO, Coût d'amorçage |
| **Négatif** | Réduction, minoration | Minoration formation à distance |

### Types de subventions système

Papaours gère plusieurs types de subventions créées automatiquement par le moteur de financement :

| Intitulé | Sens |
|----------|------|
| Niveau de prise en charge OPCO | Positif |
| Coût d'amorçage | Positif |
| Coût de carence | Positif |
| Minoration formation à distance | Négatif |
| Majoration contrat court | Positif |

Les subventions sont liées aux ventilations et impactent le récapitulatif de financement.

Pour en savoir plus, consultez la page dédiée : [08 - Les subventions](08-subventions)

---

## Contrat court

### Définition

Un **contrat court** est un contrat d'apprentissage dont la durée est **inférieure à 365 jours** et qui comporte une **dérogation de type 21**.

Les deux conditions doivent être réunies simultanément :

| Condition | Critère |
|-----------|---------|
| Durée du contrat | Strictement inférieure à 365 jours |
| Type de dérogation | Dérogation de type 21 |

### Impact sur le financement

Lorsqu'un contrat est identifié comme "court", une **majoration de 10 %** est appliquée sur la PEC proratisée (prise en charge pédagogie). Cette majoration se traduit par la création d'une subvention de type **Majoration contrat court**.

---

## RQTH (Reconnaissance de la Qualité de Travailleur Handicapé)

### Définition

Le financement **RQTH** concerne l'accompagnement des apprentis reconnus travailleurs handicapés. Il permet une prise en charge supplémentaire via la prestation de type `PAPAOURS-TPT-ACC-RQTH`.

### Conditions d'activation

Le champ **"Montant RQTH Annuel"** est visible sur le dossier de financement uniquement si l'apprenant est déclaré comme travailleur handicapé dans sa fiche. Ce montant est plafonné à **4 000 €** dans les calculs.

Si aucune prestation RQTH n'est présente ou si son montant est de 0 €, la PEC RQTH est automatiquement égale à 0 €.

Pour en savoir plus, consultez la page dédiée : [10 - Financement RQTH](10-financement-rqth)

---

## Règle de non-arrondi

Lors des calculs de financement (subventions, proratisation, majorations, plafonnements), le système **n'applique aucun arrondi** aux étapes intermédiaires. Les montants sont conservés avec une précision de **6 décimales** tout au long de la chaîne de calcul.

L'arrondi est appliqué uniquement à l'**affichage final** des montants. Cette règle garantit une précision maximale dans les calculs et évite les écarts cumulés.

---

### Pour aller plus loin

Poursuivez avec la page suivante :
[03 - Les types de prestations](03-types-prestations)
