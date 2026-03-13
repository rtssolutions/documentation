---
title: "06 - Données Contrat"
description: "Variables de substitution disponibles pour l'entité Contrat"
date: "2026-03-13"
version: "1"
---

# Données Contrat

## Vue d'ensemble

L'entité **Contrat** est la plus complète car elle agrège les données de plusieurs sources :
- Le contrat lui-même
- L'apprenant
- L'employeur
- Le maître d'apprentissage
- Le dossier de formation
- Le centre de formation (CFA)

---

## Données du contrat

### Identification

| Variable | Description | Exemple |
|----------|-------------|---------|
| `code` | Code unique du contrat | CTR2025-000001 |
| `numeroContrat` | Numéro officiel du contrat | |
| `typeContrat` | Type de contrat | APPRENTISSAGE |
| `modeContractuel` | Mode contractuel | INITIAL |

### Dates

| Variable | Description | Format |
|----------|-------------|--------|
| `dateDebutContrat` | Date de début du contrat | YYYY-MM-DD |
| `dateFinContrat` | Date de fin du contrat | YYYY-MM-DD |
| `dateDebutFormation` | Date de début de la formation | YYYY-MM-DD |
| `dateFinFormation` | Date de fin de la formation | YYYY-MM-DD |
| `dateSignature` | Date de signature | YYYY-MM-DD |

### Exemple d'utilisation

```text
Contrat d'apprentissage n° {d.code}
Du {d.dateDebutContrat:formatD(DD/MM/YYYY)} au {d.dateFinContrat:formatD(DD/MM/YYYY)}
```

### Durée et horaires

| Variable | Description | Exemple |
|----------|-------------|---------|
| `dureeHebdomadaireTravail` | Durée hebdomadaire de travail | 35 |
| `dureeContratEnMois` | Durée du contrat en mois | 24 |

---

## Rémunération

| Variable | Description | Exemple |
|----------|-------------|---------|
| `remuneration.salaireMinimum` | Salaire minimum légal | 1747.20 |
| `remuneration.pourcentageSmic` | Pourcentage du SMIC | 100 |
| `remuneration.salaireNegocie` | Salaire négocié | 1800.00 |

---

## Apprenant

Les données de l'apprenant sont accessibles via le préfixe `apprenant` :

```text
{d.apprenant.nom}
{d.apprenant.prenom}
{d.apprenant.dateDeNaissance}
```

Voir [04 - Données Apprenant](04-donnees-apprenant) pour la liste complète.

---

## Employeur

Les données de l'employeur sont accessibles via le préfixe `employeur` :

```text
{d.employeur.denominationSociale}
{d.employeur.siret}
{d.employeur.adresse.adresseComplete}
```

Voir [05 - Données Employeur](05-donnees-employeur) pour la liste complète.

---

## Maître d'apprentissage

| Variable | Description | Exemple |
|----------|-------------|---------|
| `maitreApprentissage.nom` | Nom du maître d'apprentissage | Martin |
| `maitreApprentissage.prenom` | Prénom | Sophie |
| `maitreApprentissage.dateDeNaissance` | Date de naissance | 1980-05-15 |
| `maitreApprentissage.courriel` | Email | sophie.martin@acme.com |

---

## Formation

Les données de la formation sont accessibles via les préfixes suivants :

### Diplôme et certification

| Variable | Description | Exemple |
|----------|-------------|---------|
| `codeRncp` | Code RNCP de la formation | RNCP12345 |
| `codeDiplome` | Code du diplôme | 12345678 |
| `diplomeOuTitreVise.code` | Code du type de diplôme | 50 |
| `diplomeOuTitreVise.libelle` | Libellé du diplôme | BTS |
| `diplomeOuTitreVise.libellePersonnalise` | Libellé personnalisé | BTS Commerce International |

### Lieu de formation

| Variable | Description | Exemple |
|----------|-------------|---------|
| `lieuFormationPrincipal.adresseComplete` | Adresse du lieu de formation | 15 rue de la Formation 59000 Lille |
| `lieuFormationPrincipal.codePostal` | Code postal | 59000 |
| `lieuFormationPrincipal.ville` | Ville | Lille |

---

## Centre de formation (CFA)

| Variable | Description | Exemple |
|----------|-------------|---------|
| `denominationCfa` | Dénomination du CFA | CFA des Métiers |
| `numeroSiretCfa` | SIRET du CFA | 98765432109876 |
| `lieuSignature` | Lieu de signature (ville du CFA) | Lille |
| `cfaEntreprise` | Est un CFA d'entreprise | Booléen |

---

## Attestations

| Variable | Description | Type |
|----------|-------------|------|
| `employeurAttesteConformiteCerfa` | L'employeur atteste la conformité | Booléen |

---

## Exemple complet

```text
CONTRAT D'APPRENTISSAGE

Entre :
L'employeur : {d.employeur.denominationSociale}
SIRET : {d.employeur.siret}
Adresse : {d.employeur.adresse.adresseComplete}

Et :
L'apprenti(e) : {d.apprenant.prenom} {d.apprenant.nom}
Né(e) le : {d.apprenant.dateDeNaissance:formatD(DD/MM/YYYY)}
Adresse : {d.apprenant.adressePostale.adresseComplete}

Formation préparée : {d.diplomeOuTitreVise.libellePersonnalise}
Code RNCP : {d.codeRncp}

Durée du contrat : du {d.dateDebutContrat:formatD(DD/MM/YYYY)} au {d.dateFinContrat:formatD(DD/MM/YYYY)}

Maître d'apprentissage : {d.maitreApprentissage.prenom} {d.maitreApprentissage.nom}

Fait à {d.lieuSignature}, le {d.dateSignature:formatD(DD/MM/YYYY)}
```

---

## Pour aller plus loin

-> [07 - Données Dossier de formation](07-donnees-dossier-formation)
