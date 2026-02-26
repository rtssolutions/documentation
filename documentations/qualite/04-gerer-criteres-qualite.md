---
title: "Gérer les critères qualité"
description: "Créer, modifier et supprimer des critères qualité rattachés à un ensemble qualité"
date: "2025-07-29"
version: "1"
---

## Créer un critère qualité

Un critère est rattaché à un ensemble qualité existant. Pour créer un critère, renseignez les champs suivants :

| Champ | Obligatoire | Description |
|---|---|---|
| Intitulé | Oui | Nom du critère, unique au sein de l'ensemble qualité |
| Description | Non | Texte libre décrivant le critère |
| Date de début d'application | Oui | Initialisée avec la date de début de l'ensemble parent |
| Date de fin d'application | Non | Initialisée avec la date de fin de l'ensemble parent |
| Ensemble qualité | Oui | Ensemble de rattachement |

### Champs générés automatiquement

- **Code** : généré au format `CRT<AAAA>-<NNNNNN>` (non modifiable).
- **Statut** : positionné à **Activé** par défaut.

### Règles de dates

- La date de début d'application est **obligatoire** et initialisée par défaut avec celle de l'ensemble qualité parent.
- La date de fin d'application est **facultative** et initialisée par défaut avec celle de l'ensemble qualité parent.
- Si renseignée, la date de fin doit être **strictement postérieure** à la date de début.
- La période du critère doit être **incluse dans la période de l'ensemble qualité** parent.

### Unicité de l'intitulé

L'intitulé doit être unique **au sein de l'ensemble qualité**. Deux critères appartenant à des ensembles différents peuvent avoir le même intitulé.

## Modifier un critère qualité

Depuis la fiche d'un critère, cliquez sur **Modifier** pour accéder à l'écran de modification.

### Champs modifiables

| Champ | Règle |
|---|---|
| Intitulé | Doit rester unique au sein de l'ensemble qualité |
| Description | Peut être ajoutée, modifiée ou supprimée |
| Date de début d'application | Obligatoire, incluse dans la période de l'ensemble parent |
| Date de fin d'application | Facultative, strictement postérieure à la date de début |
| Statut | Activé ou Désactivé |

### Champs non modifiables

| Champ | Raison |
|---|---|
| Code | Identifiant unique généré à la création |
| Ensemble qualité | Le rattachement est définitif |

### Gestion du statut

| Statut | Comportement |
|---|---|
| **Activé** | Le critère est utilisable dans la démarche qualité |
| **Désactivé** | Le critère est temporairement non utilisable |

Toute modification est **historisée** (date, utilisateur, anciennes et nouvelles valeurs).

## Supprimer un critère qualité

La suppression d'un critère est une opération **définitive et irréversible**.

### Processus de suppression

1. Cliquez sur **Supprimer** depuis la fiche du critère.
2. Une alerte de confirmation s'affiche : _« Êtes-vous sûr de vouloir supprimer ce critère ? Cette action est irréversible. »_
3. Confirmez pour valider la suppression.

### Suppression en cascade

La suppression d'un critère entraîne automatiquement la suppression de tous les **indicateurs** rattachés à ce critère.

## Pour aller plus loin

- [Gérer les indicateurs qualité](05-gerer-indicateurs-qualite) : définir les points d'évaluation mesurables.
