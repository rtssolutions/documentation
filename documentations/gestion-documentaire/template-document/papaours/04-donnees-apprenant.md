---
title: "04 - Données Apprenant"
description: "Variables de substitution disponibles pour l'entité Apprenant"
date: "2026-03-13"
version: "1"
---

# Données Apprenant

## Préfixe

Selon l'entité liée au template, les données de l'apprenant sont accessibles via :

| Entité liée | Préfixe |
|-------------|---------|
| `APPRENANT` | `{d.apprenant.xxx}` |
| `CONTRAT` | `{d.apprenant.xxx}` |

---

## Identité

| Variable | Description | Exemple |
|----------|-------------|---------|
| `nom` | Nom de famille | Dupont |
| `prenom` | Prénom | Jean |
| `nomDeNaissance` | Nom de naissance (si différent) | Martin |
| `sexe` | Sexe (H/F) | H |
| `dateDeNaissance` | Date de naissance | 1994-12-06 |
| `communeDeNaissance.nom` | Commune de naissance | Lille |
| `communeDeNaissance.codeInsee` | Code INSEE de la commune | 59350 |
| `communeDeNaissance.codeDepartement` | Code département | 62 |
| `communeDeNaissance.nomDepartement` | Nom du département | Pas-de-Calais |
| `paysDeNaissance.nom` | Pays de naissance | France |
| `paysDeNaissance.codeIso3` | Code ISO3 du pays | FRA |
| `paysDeNaissance.codeInseePays` | Code INSEE du pays | 99100 |
| `nationalite.nationalite` | Libellé de la nationalité | Française |
| `nationalite.codePaysIso2` | Code ISO2 du pays | FR |
| `nationalite.zoneGeographique` | Zone géographique | UNION_EUROPEENNE |
| `nir` | Numéro de sécurité sociale | 194126219345335 |
| `nirAffichable` | NIR formaté pour affichage | 1 94 12 62 193 453 35 |

### Exemple d'utilisation

```text
L'apprenant {d.apprenant.prenom} {d.apprenant.nom}, né(e) le {d.apprenant.dateDeNaissance:formatD(DD/MM/YYYY)}
à {d.apprenant.communeDeNaissance.nom}, de nationalité {d.apprenant.nationalite.nationalite}.
```

---

## Coordonnées

| Variable | Description | Exemple |
|----------|-------------|---------|
| `telephone` | Numéro de téléphone | 0750359597 |
| `courriel` | Adresse email | jean.dupont@example.com |

### Adresse postale

| Variable | Description | Exemple |
|----------|-------------|---------|
| `adressePostale.adresseComplete` | Adresse complète | 129 rue Solferino 59000 Lille |
| `adressePostale.numeroVoie` | Numéro de voie | 129 |
| `adressePostale.voie` | Nom de la voie | rue Solferino |
| `adressePostale.complement` | Complément d'adresse | Bâtiment A |
| `adressePostale.codePostal` | Code postal | 59000 |
| `adressePostale.ville` | Ville | Lille |

### Exemple d'utilisation

```text
Adresse : {d.apprenant.adressePostale.adresseComplete}
Téléphone : {d.apprenant.telephone}
Email : {d.apprenant.courriel}
```

---

## Situation

| Variable | Description | Type |
|----------|-------------|------|
| `estSousTutelle` | L'apprenant est sous tutelle | Booléen |
| `estEmancipe` | L'apprenant est émancipé | Booléen |
| `creationEntreprise` | Projet de création d'entreprise | Booléen |
| `nouveauContratApresEchecDiplome` | Nouveau contrat après échec | Booléen |

---

## Besoins spécifiques

| Variable | Description | Type |
|----------|-------------|------|
| `besoinSpecifique.estTravailleurHandicape` | Reconnu travailleur handicapé (RQTH) | Booléen |
| `besoinSpecifique.estSportifDeHautNiveau` | Sportif de haut niveau | Booléen |

### Exemple d'utilisation avec condition

```text
{d.apprenant.besoinSpecifique.estTravailleurHandicape:ifEQ(true):show(Bénéficie d'une RQTH)}
```

---

## Représentant légal

Pour les apprenants mineurs non émancipés ou sous tutelle/curatelle :

| Variable | Description | Exemple |
|----------|-------------|---------|
| `representantLegal.nom` | Nom du représentant | Dupont |
| `representantLegal.prenom` | Prénom du représentant | Marie |
| `representantLegal.courriel` | Email du représentant | marie.dupont@example.com |
| `representantLegal.telephone` | Téléphone du représentant | 0612345678 |
| `representantLegal.adresse.adresseComplete` | Adresse du représentant | 129 rue Solferino 59000 Lille |

---

## Code apprenant

| Variable | Description | Exemple |
|----------|-------------|---------|
| `code` | Code unique de l'apprenant | APP2025-000001 |

> Le code est généré automatiquement au format `APPYYYY-XXXXXX` lors de la création.

---

## Pour aller plus loin

-> [05 - Données Employeur](05-donnees-employeur)
