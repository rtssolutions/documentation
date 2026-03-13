---
title: "8 - Données Dossier de formation"
description: "Variables de substitution disponibles pour l'entité Dossier de formation"
date: "2026-03-13"
version: "1"
---

# Données Dossier de formation

## Vue d'ensemble

L'entité **Dossier de formation** contient les informations relatives à l'inscription d'un apprenant dans une session de formation. Elle donne accès aux données :
- Du dossier lui-même
- De la session de formation
- De l'action de formation
- De la formation (diplôme, RNCP)
- Des lieux de formation

---

## Préfixe

Selon l'entité liée au template, les données sont accessibles via :

| Entité liée | Préfixe |
|-------------|---------|
| `DOSSIER_FORMATION` | `{d.dossierFormation.xxx}` |
| `CONTRAT` | `{d.dossierFormation.xxx}` |

---

## Données du dossier

### Identification

| Variable | Description | Exemple |
|----------|-------------|---------|
| `code` | Code unique du dossier | DOS2025-000001 |
| `situationActuelle` | État actuel du dossier | EN_COURS |

### Exemple d'utilisation

```text
Dossier de formation n° {d.dossierFormation.code}
Situation : {d.dossierFormation.situationActuelle}
```

---

## Session de formation

Les données de la session sont accessibles via le préfixe `sessionFormation` :

| Variable | Description | Exemple |
|----------|-------------|---------|
| `sessionFormation.code` | Code de la session | SES2025-001 |
| `sessionFormation.dateDebut` | Date de début | 2025-09-01 |
| `sessionFormation.dateFin` | Date de fin | 2027-06-30 |

---

## Action de formation

| Variable | Description | Exemple |
|----------|-------------|---------|
| `sessionFormation.actionDeFormation.code` | Code de l'action | ACT2025-001 |
| `sessionFormation.actionDeFormation.intitule` | Intitulé de l'action | BTS Commerce International |

---

## Formation

Les données de la formation sont accessibles via le chemin complet :

### Identification

| Variable | Description | Exemple |
|----------|-------------|---------|
| `sessionFormation.actionDeFormation.formation.code` | Code de la formation | FOR2025-001 |
| `sessionFormation.actionDeFormation.formation.intitule` | Intitulé | BTS Commerce International |

### RNCP et diplôme

| Variable | Description | Exemple |
|----------|-------------|---------|
| `sessionFormation.actionDeFormation.formation.rncp.code` | Code RNCP | RNCP12345 |
| `sessionFormation.actionDeFormation.formation.diplome.code` | Code diplôme | 12345678 |
| `sessionFormation.actionDeFormation.formation.typeDiplome.code` | Code type diplôme | 50 |
| `sessionFormation.actionDeFormation.formation.typeDiplome.libelle` | Libellé type diplôme | BTS |
| `sessionFormation.actionDeFormation.formation.typeDiplome.libellePersonnalise` | Libellé personnalisé | BTS Commerce International |

### Exemple d'utilisation

```text
Formation : {d.dossierFormation.sessionFormation.actionDeFormation.formation.intitule}
Code RNCP : {d.dossierFormation.sessionFormation.actionDeFormation.formation.rncp.code}
Diplôme préparé : {d.dossierFormation.sessionFormation.actionDeFormation.formation.typeDiplome.libelle}
```

---

## Lieux de formation

Les lieux de formation sont accessibles via le chemin `sessionFormation.lieuxDeFormation` :

### Lieu principal

| Variable | Description | Exemple |
|----------|-------------|---------|
| `sessionFormation.lieuxDeFormation[i=0].adresse.adresseComplete` | Adresse du lieu principal | 15 rue de la Formation 59000 Lille |
| `sessionFormation.lieuxDeFormation[i=0].adresse.codePostal` | Code postal | 59000 |
| `sessionFormation.lieuxDeFormation[i=0].adresse.ville` | Ville | Lille |

### Parcourir tous les lieux

```text
{d.dossierFormation.sessionFormation.lieuxDeFormation[i].adresse.adresseComplete}
```

> Utilisez la syntaxe `[i]` pour créer une boucle sur les lieux de formation.

---

## Centre de formation

Lorsque l'entité `CENTRE_DE_FORMATION` est également liée, les données du CFA sont accessibles :

| Variable | Description | Exemple |
|----------|-------------|---------|
| `centreDeFormation.denominationSociale` | Nom du CFA | CFA des Métiers |
| `centreDeFormation.siret` | SIRET du CFA | 98765432109876 |
| `centreDeFormation.adresse.ville` | Ville du CFA | Lille |
| `centreDeFormation.adresse.adresseComplete` | Adresse complète | 20 avenue du CFA 59000 Lille |

---

## Exemple complet (CERFA P2S)

Le template CERFA P2S utilise les entités `DOSSIER_FORMATION` et `CENTRE_DE_FORMATION` :

```text
DEMANDE DE PRISE EN CHARGE

Centre de formation : {d.centreDeFormation.denominationSociale}
SIRET : {d.centreDeFormation.siret}
Adresse : {d.centreDeFormation.adresse.adresseComplete}

Formation : {d.dossierFormation.sessionFormation.actionDeFormation.formation.intitule}
Code RNCP : {d.dossierFormation.sessionFormation.actionDeFormation.formation.rncp.code}

Période : du {d.dossierFormation.sessionFormation.dateDebut:formatD(DD/MM/YYYY)}
          au {d.dossierFormation.sessionFormation.dateFin:formatD(DD/MM/YYYY)}

Lieu de formation principal :
{d.dossierFormation.sessionFormation.lieuxDeFormation[i=0].adresse.adresseComplete}
```

---

## Pour aller plus loin

-> [08 - Générer un document](08-generer-document)
