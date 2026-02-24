---
title: "11 - Échéancier de facturation"
description: "Gestion des échéanciers de facturation employeur et OPCO dans le module de financement"
date: "2025-01-08"
version: "1"
---

## Vue d'ensemble

Un **échéancier** est une liste ordonnée d'échéances rattachée à un dossier de financement. Il permet de planifier, suivre et piloter les échéances de facturation associées au financement d'un contrat d'apprentissage.

Papaours gère deux types d'échéanciers :

| Type | Financeur | Base de calcul du montant |
|------|-----------|---------------------------|
| Échéancier employeur | Employeur | Montant total dû par l'employeur |
| Échéancier OPCO | OPCO | Montant HT **avant remise** (somme des ventilations OPCO) |

---

## Échéancier employeur

### Principes

L'échéancier employeur permet de planifier les facturations à destination de l'employeur. Un financement dont le financeur est de type employeur peut posséder **un seul échéancier actif**, composé d'une ou plusieurs échéances.

### Création

L'échéancier employeur est créé **manuellement** par l'utilisateur à partir du financement employeur.

**Conditions de création** :
- Le financeur doit être de type **Employeur**
- Un montant total de financement doit être défini

### Structure d'une échéance

Chaque échéance est définie par les informations suivantes :

| Propriété | Description | Obligatoire |
|-----------|-------------|-------------|
| Numéro | Calculé automatiquement par ordre croissant de date de début (à partir de 1) | Auto |
| Date de début | Début de la période de l'échéance | Oui |
| Date de fin | Fin de la période de l'échéance | Oui |
| Date "À facturer" | Date prévue pour la facturation | Non |
| Date d'émission | Date d'émission de la facture | Non |
| Date de paiement | Date de paiement de la facture | Non |
| Intitulé | Libellé libre de l'échéance | Non |
| Type de montant | Pourcentage ou montant fixe | Oui |
| Valeur | Pourcentage (0 < valeur <= 100) ou montant (<= montant total) | Oui |
| Montant calculé | Montant réel de l'échéance, calculé automatiquement | Auto |

### Type de montant

Le montant d'une échéance peut être défini de deux façons :

| Type | Description | Calcul |
|------|-------------|--------|
| Pourcentage | Part du montant total | Montant total × (valeur / 100) |
| Montant fixe | Valeur directe en euros | Valeur saisie directement |

### États d'une échéance

Une échéance suit un cycle de vie à travers les états suivants :

| État | Description |
|------|-------------|
| `À facturer` | État initial par défaut à la création |
| `Facturée` | La facture a été émise (date d'émission renseignée) |
| `Payée` | La facture a été réglée (date de paiement renseignée) |
| `Annulée` | L'échéance a été annulée |
| `En retard` | L'échéance n'a pas été facturée à la date prévue |
| `Impayée` | La facture émise n'a pas été réglée |

---

## Règles de gestion de l'échéancier employeur

### Cohérence des montants

- La **somme des montants calculés** de toutes les échéances doit être égale au montant total du financement employeur
- Le montant d'une échéance individuelle ne peut pas dépasser le montant total du financement

### Cohérence des dates

- Les dates de début et de fin des échéances doivent être **cohérentes** avec la période du financement
- Les échéances **ne peuvent pas se chevaucher**
- Les échéances sont ordonnées par date de début

### Ajout d'une échéance

L'utilisateur peut ajouter des échéances en renseignant la période et le montant. Le numéro est recalculé automatiquement selon l'ordre des dates de début.

### Modification d'une échéance

Les propriétés d'une échéance peuvent être modifiées tant que les règles de cohérence sont respectées.

### Suppression d'une échéance

Une échéance peut être supprimée sous certaines conditions :

| État de l'échéance | Suppression autorisée |
|--------------------|-----------------------|
| `À facturer` | Oui |
| `En retard` | Oui |
| `Facturée` | Non |
| `Payée` | Non |
| `Annulée` | Oui |
| `Impayée` | Non |

La suppression d'une échéance déjà facturée ou payée est interdite car elle correspond à un engagement financier réel.

---

## Échéancier OPCO

### Principes

L'échéancier OPCO permet de planifier les facturations à destination de l'OPCO pour le financement des prestations prises en charge.

### Base de calcul

Le montant de l'échéancier OPCO est basé sur le **montant HT avant remise** du financement OPCO. Cela correspond à la somme des ventilations OPCO **avant application des remises**.

```
Montant total échéancier OPCO = Somme des ventilations OPCO (avant remise)
```

Les remises existantes (ex : POE) apparaissent ensuite dans l'échéancier, ce qui impose de partir du montant avant remise pour le calcul, puis de retirer la remise sur la première échéance.

### Différence avec l'échéancier employeur

| Aspect | Échéancier employeur | Échéancier OPCO |
|--------|---------------------|-----------------|
| Base de calcul | Montant dû par l'employeur | Montant HT avant remise des ventilations OPCO |
| Prise en compte des remises | Montant après remises | Montant avant remises (remises déduites dans les échéances) |

---

## Exemple d'échéancier

### Données

- Financement employeur : 2 000 € HT
- 4 échéances trimestrielles

| N° | Période | Type | Valeur | Montant calculé | État |
|----|---------|------|--------|-----------------|------|
| 1 | 01/09/2025 - 30/11/2025 | Pourcentage | 25 % | 500 € | À facturer |
| 2 | 01/12/2025 - 28/02/2026 | Pourcentage | 25 % | 500 € | À facturer |
| 3 | 01/03/2026 - 31/05/2026 | Pourcentage | 25 % | 500 € | À facturer |
| 4 | 01/06/2026 - 31/08/2026 | Pourcentage | 25 % | 500 € | À facturer |

**Total : 2 000 €** (= montant du financement employeur)

---

### Pour aller plus loin

Retour à l'introduction :
[01 - Introduction au financement](01-introduction)
