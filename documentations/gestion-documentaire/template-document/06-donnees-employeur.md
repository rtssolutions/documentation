---
title: "6 - Données Employeur"
description: "Variables de substitution disponibles pour l'entité Employeur"
date: "2026-03-13"
version: "1"
---

# Données Employeur

## Préfixe

Selon l'entité liée au template, les données de l'employeur sont accessibles via :

| Entité liée | Préfixe |
|-------------|---------|
| `EMPLOYEUR` | `{d.employeur.xxx}` |
| `CONTRAT` | `{d.employeur.xxx}` |

---

## Identification

| Variable | Description | Exemple |
|----------|-------------|---------|
| `siret` | Numéro SIRET | 12345678901234 |
| `denominationSociale` | Dénomination sociale | ACME SARL |
| `code` | Code unique employeur | EMP2025-000001 |

> Le code est généré automatiquement au format `EMPYYYY-XXXXXX` lors de la création.

---

## Adresse

| Variable | Description | Exemple |
|----------|-------------|---------|
| `adresse.adresseComplete` | Adresse complète | 10 avenue des Champs 1000 Bruxelles |
| `adresse.numeroVoie` | Numéro de voie | 10 |
| `adresse.voie` | Nom de la voie | avenue des Champs |
| `adresse.complement` | Complément d'adresse | Bâtiment B |
| `adresse.codePostal` | Code postal | 59000 |
| `adresse.ville` | Ville / Commune | Lille |

### Exemple d'utilisation

```text
Employeur : {d.employeur.denominationSociale}
SIRET : {d.employeur.siret}
Adresse : {d.employeur.adresse.adresseComplete}
```

---

## Activité et effectif

| Variable | Description | Exemple |
|----------|-------------|---------|
| `activitePrincipale` | Code NAF / APE | 6201Z |
| `effectifTotal` | Effectif total de l'entreprise | 10 |
| `secteurActivite.code` | Code du secteur d'activité | 1 |
| `secteurActivite.libelle` | Libellé du secteur | Industrie |

---

## Type et régime

| Variable | Description | Exemple |
|----------|-------------|---------|
| `typeEmployeur` | Type d'employeur | PRIVE |
| `regimeSocial` | Régime social | URSSAF |
| `employeurSpecifique.code` | Code employeur spécifique | 3 |
| `employeurSpecifique.libelle` | Libellé employeur spécifique | Employeur saisonnier |

---

## Convention collective

| Variable | Description | Exemple |
|----------|-------------|---------|
| `conventionCollective.code` | Code IDCC | 1486 |
| `conventionCollective.libelle` | Libellé de la convention | Bureaux d'études techniques |

### Exemple d'utilisation

```text
Convention collective applicable : {d.employeur.conventionCollective.libelle} (IDCC {d.employeur.conventionCollective.code})
```

---

## Coordonnées

| Variable | Description | Exemple |
|----------|-------------|---------|
| `coordonnees.telephone` | Téléphone | 0123456789 |
| `coordonnees.courriel` | Email | contact@acme.com |
| `coordonnees.siteInternet` | Site web | http://www.acme.com |

---

## Informations complémentaires

| Variable | Description | Type |
|----------|-------------|------|
| `estSiege` | Est le siège social | Booléen |
| `dateCreation` | Date de création de l'établissement | Date |
| `etatAdministratif` | État administratif (actif/fermé) | Texte |
| `caisseDeRetraite` | Caisse de retraite | Texte |
| `accepteSignatureElectronique` | Accepte la signature électronique | Booléen |
| `tauxCompletion` | Taux de complétion de la fiche | Nombre |

---

## Nature juridique

| Variable | Description | Exemple |
|----------|-------------|---------|
| `natureJuridique.code` | Code de la forme juridique | 5710 |
| `natureJuridique.description` | Libellé de la forme juridique | SARL |

---

## Opérateur de compétences (OPCO)

| Variable | Description | Exemple |
|----------|-------------|---------|
| `operateurCompetence.code` | Code de l'OPCO | OPCO2I |
| `operateurCompetence.libelle` | Nom de l'OPCO | OPCO 2i |

---

## TVA

| Variable | Description | Exemple |
|----------|-------------|---------|
| `tva.regime` | Régime de TVA | REGIME_REEL_NORMAL |
| `tva.numero` | Numéro de TVA intracommunautaire | FR14123456789 |
| `tva.taux` | Taux de TVA applicable | 20.0 |
| `assujettiAlaTVA` | Assujetti à la TVA | Booléen |

---

## Liste des UAI

Pour les employeurs ayant des établissements d'enseignement :

| Variable | Description |
|----------|-------------|
| `listeUai` | Liste des codes UAI associés |

---

## Pour aller plus loin

-> [06 - Données Contrat](06-donnees-contrat)
