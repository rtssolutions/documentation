---
title: "08 - Les subventions"
description: "Gestion des subventions associées à un dossier de financement : NPEC OPCO, coût d'amorçage, minorations et majorations"
date: "2025-01-08"
version: "1"
---

## Vue d'ensemble

Une **subvention** est un objet financier rattaché à un dossier de financement et proposé par un financeur. Elle représente une aide financière ou une réduction applicable au financement d'un contrat d'apprentissage.

Les subventions sont au coeur du mécanisme de calcul de la prise en charge (PEC) par l'OPCO. Elles sont créées automatiquement par le moteur de financement lors du traitement du dossier.

### Caractéristiques d'une subvention

Chaque subvention est définie par :

| Propriété | Description |
|-----------|-------------|
| Type de subvention | Catégorie fonctionnelle (NPEC OPCO, coût d'amorçage, minoration, majoration) |
| Type de prestation subventionnée | Le type de prestation concerné (ex : `PAPAOURS-TPT-PEDAGOGIE`) |
| Montant | Montant de la subvention, positif ou négatif |
| Intitulé | Libellé descriptif de la subvention |

### Sens du montant

| Sens | Signification | Exemples |
|------|---------------|----------|
| **Positif** | Aide financière, prise en charge | NPEC OPCO, Coût d'amorçage, Majoration contrat court |
| **Négatif** | Réduction, minoration | Minoration formation à distance |

---

## Types de subventions système

Le moteur de financement crée automatiquement les subventions suivantes selon les règles métier :

| Intitulé | Sens | Description |
|----------|------|-------------|
| Niveau de prise en charge OPCO | Positif | Niveau de prise en charge annuel défini par France Compétences |
| Coût d'amorçage | Positif | Montant de secours lorsqu'aucun NPEC OPCO n'est trouvé |
| Coût de carence | Positif | NPEC avec statut "D" dans le référentiel France Compétences |
| Minoration formation à distance | Négatif | Réduction de 10 % proportionnelle aux heures à distance |
| Majoration contrat court | Positif | Majoration de 10 % pour les contrats de moins de 365 jours avec dérogation 21 |

---

## NPEC OPCO

### Définition

Le **NPEC (Niveau de Prise En Charge)** est le montant annuel de financement défini par France Compétences pour une certification donnée. Il constitue la base principale du calcul de la prise en charge OPCO.

### Recherche automatique

Le système recherche le NPEC dans le référentiel OPCO à partir de :

- L'**IDCC** (Identifiant de la Convention Collective) du contrat
- Le **code RNCP** de la certification préparée
- La **date de conclusion** du contrat

La recherche retourne le NPEC dont l'intervalle de validité couvre la date de conclusion du contrat.

### Subvention créée

Lorsqu'un NPEC est trouvé :

| Propriété | Valeur |
|-----------|--------|
| Type | NPEC OPCO (ou Coût de carence si statut "D") |
| Prestation | `PAPAOURS-TPT-PEDAGOGIE` |
| Montant | Montant du NPEC annuel trouvé |
| Intitulé | NPEC Annuel France Compétences |

---

## Coût d'amorçage

### Définition

Le **coût d'amorçage** est un mécanisme de secours utilisé lorsqu'aucun NPEC OPCO n'est trouvé dans le référentiel. Il permet de garantir un niveau minimum de prise en charge.

### Condition de déclenchement

La recherche du coût d'amorçage n'est déclenchée **que si** la recherche de NPEC OPCO n'a retourné aucun résultat. Les deux subventions sont **mutuellement exclusives**.

### Recherche automatique

Le système recherche le coût d'amorçage dans le référentiel pédagogie à partir de :

- Le **niveau de la certification** préparée
- La **date de conclusion** du contrat

### Subvention créée

Lorsqu'un coût d'amorçage est trouvé :

| Propriété | Valeur |
|-----------|--------|
| Type | Coût d'amorçage |
| Prestation | `PAPAOURS-TPT-PEDAGOGIE` |
| Montant | Montant du coût d'amorçage |
| Intitulé | Coût d'amorçage France Compétences |

---

## Minoration formation à distance

### Condition

La minoration s'applique uniquement si le contrat comporte un **volume horaire à distance supérieur à 0**.

### Formule

```
Minoration = NPEC annuel × (heures à distance / heures totales) × 0.10
```

La subvention créée a un **montant négatif** (elle réduit le NPEC). Si le contrat ne comporte pas d'heures à distance, la minoration est de 0.

---

## Majoration contrat court

### Conditions

La majoration s'applique uniquement si **les deux conditions** sont réunies :

| Condition | Critère |
|-----------|---------|
| Durée du contrat | Strictement inférieure à 365 jours |
| Type de dérogation | Dérogation de type 21 |

### Formule

```
Majoration = PEC proratisée × 0.10
```

La subvention créée a un **montant positif** (elle augmente la prise en charge de 10 %).

---

## Subventions obligatoires et personnalisées

### Subventions obligatoires

Les subventions créées automatiquement par le moteur de financement sont **obligatoires**. Elles ne peuvent pas être supprimées par l'utilisateur.

### Subventions personnalisées

L'utilisateur peut ajouter des subventions supplémentaires manuellement pour couvrir des cas spécifiques non gérés par le moteur de financement.

---

## Règles de gestion

| Règle | Comportement |
|-------|--------------|
| Suppression d'une subvention obligatoire | Interdite |
| Suppression d'une subvention personnalisée | Autorisée |
| Modification du montant | Autorisée pour les subventions personnalisées |
| Exclusivité NPEC / Coût d'amorçage | Une seule des deux peut exister sur un dossier |

---

## Impact sur le récapitulatif

Les subventions sont prises en compte dans le calcul de la ventilation OPCO. Le montant total des subventions (positives et négatives) détermine le niveau de prise en charge du financeur OPCO pour chaque type de prestation.

Le détail des subventions est visible dans l'écran de financement du dossier, avec leur type, intitulé et montant.

---

### Pour aller plus loin

Poursuivez avec la page suivante :
[09 - Moteur de financement pédagogie](09-moteur-financement-pedagogie)
