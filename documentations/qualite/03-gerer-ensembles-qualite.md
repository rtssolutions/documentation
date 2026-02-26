---
title: "Gérer les ensembles qualité"
description: "Créer, visualiser, modifier et supprimer un ensemble qualité dans Papaours"
date: "2025-07-29"
version: "1"
---

## Créer un ensemble qualité

Pour créer un nouvel ensemble qualité, renseignez les champs suivants :

| Champ | Obligatoire | Description |
|---|---|---|
| Intitulé | Oui | Nom de l'ensemble, unique parmi tous les ensembles qualité |
| Description | Non | Texte libre décrivant l'ensemble |
| Date de début d'application | Oui | Début de la période d'application |
| Date de fin d'application | Non | Fin de la période d'application (si renseignée, strictement postérieure à la date de début) |

### Champs générés automatiquement

- **Code** : généré au format `ESQ<AAAA>-<NNNNNN>` (non modifiable).
- **Statut** : positionné à **Activé** par défaut.

### Règle de non-chevauchement des dates

Les périodes d'application des ensembles qualité utilisent des bornes inclusives `[date début ; date fin]` : deux ensembles ne peuvent pas partager un jour commun.

**Exemple :**
- Ensemble A : 01/01/2026 au 31/12/2026
- Ensemble B commençant le 31/12/2026 : refusé (chevauchement)
- Ensemble B commençant le 01/01/2027 : accepté

## Visualiser un ensemble qualité

Depuis la liste des ensembles qualité, cliquez sur un ensemble pour afficher sa fiche de consultation. L'affichage est structuré de manière hiérarchique :

**Ensemble qualité** > **Critères** > **Indicateurs**

### Informations affichées

Pour chaque niveau, les éléments suivants sont présentés :

| Niveau | Informations |
|---|---|
| Ensemble qualité | Intitulé, description, statut |
| Critère | Intitulé, description, dates d'application, statut |
| Indicateur | Intitulé, code, description, dates d'application, statut |

### Navigation dans l'arbre

- Les critères sont affichés sous l'ensemble qualité.
- Les indicateurs sont affichés sous leur critère parent.
- Vous pouvez **développer ou replier** chaque critère pour afficher ou masquer ses indicateurs.
- Par défaut, l'ensemble qualité est affiché **replié**.
- Les critères et indicateurs sont triés par **intitulé croissant**.

### Affichage des dates

- Si seule la date de début est renseignée : **À partir du JJ/MM/AAAA**
- Si les deux dates sont renseignées : **Du JJ/MM/AAAA au JJ/MM/AAAA**

### Éléments désactivés

Les ensembles et critères désactivés restent visibles mais apparaissent **grisés**.

## Modifier un ensemble qualité

Depuis la fiche d'un ensemble qualité, cliquez sur **Modifier** pour accéder à l'écran de modification.

### Champs modifiables

| Champ | Règle |
|---|---|
| Intitulé | Doit rester unique parmi tous les ensembles qualité |
| Description | Peut être ajoutée, modifiée ou supprimée |
| Date de début d'application | Obligatoire |
| Date de fin d'application | Facultative, strictement postérieure à la date de début si renseignée |

### Champs non modifiables

| Champ | Raison |
|---|---|
| Code | Identifiant unique généré à la création |

### Contrôle de non-chevauchement

Lors de la modification des dates, le système vérifie que la nouvelle période ne chevauche aucun autre ensemble qualité.

Toute modification est **historisée** (date, utilisateur, anciennes et nouvelles valeurs).

## Supprimer un ensemble qualité

La suppression d'un ensemble qualité est une opération **définitive et irréversible**.

### Processus de suppression

1. Cliquez sur **Supprimer** depuis la fiche de l'ensemble qualité.
2. Une alerte de confirmation s'affiche : _« Êtes-vous sûr de vouloir supprimer cet ensemble Qualité ? Cette action est irréversible. »_
3. Confirmez pour valider la suppression.

### Suppression en cascade

La suppression d'un ensemble entraîne automatiquement la suppression de :

- Tous les **critères** rattachés à l'ensemble
- Tous les **indicateurs** rattachés à ces critères

## Pour aller plus loin

- [Gérer les critères qualité](04-gerer-criteres-qualite) : structurer les exigences au sein d'un ensemble.
