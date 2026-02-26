---
title: "Gérer les indicateurs qualité"
description: "Créer, modifier et supprimer des indicateurs qualité rattachés à un critère"
date: "2025-07-29"
version: "1"
---

## Créer un indicateur qualité

Un indicateur est rattaché à un critère existant. Pour créer un indicateur, renseignez les champs suivants :

| Champ | Obligatoire | Description |
|---|---|---|
| Intitulé | Oui | Nom de l'indicateur, unique au sein du critère |
| Description | Non | Texte libre décrivant l'indicateur |
| Date de début d'application | Oui | Initialisée avec la date de début du critère parent |
| Date de fin d'application | Non | Initialisée avec la date de fin du critère parent |
| Critère | Oui | Critère de rattachement |

### Champs générés automatiquement

- **Code** : généré au format `IND<AAAA>-<NNNNNN>` (non modifiable).
- **Statut** : positionné à **Activé** par défaut.

### Héritage et règles de dates

À la création d'un indicateur, les dates de début et de fin d'application sont **initialisées par défaut avec celles du critère de rattachement**. Ces dates sont affichées automatiquement dans le formulaire de création.

L'utilisateur peut modifier ces dates, sous réserve de respecter les règles suivantes :

- La date de début est **obligatoire**.
- La date de fin est **facultative**.
- Si renseignée, la date de fin doit être **strictement postérieure** à la date de début.
- La période de l'indicateur doit être **incluse dans la période du critère** parent.

### Unicité de l'intitulé

L'intitulé doit être unique **au sein du critère** auquel l'indicateur appartient.

## Modifier un indicateur qualité

Depuis la fiche d'un indicateur, cliquez sur **Modifier** pour accéder à l'écran de modification.

### Champs modifiables

| Champ | Règle |
|---|---|
| Intitulé | Doit rester unique au sein du critère |
| Description | Peut être ajoutée, modifiée ou supprimée |
| Date de début d'application | Obligatoire, incluse dans la période du critère parent |
| Date de fin d'application | Facultative, strictement postérieure à la date de début |
| Statut | Activé ou Désactivé |

### Champs non modifiables

| Champ | Raison |
|---|---|
| Code | Identifiant unique généré à la création |
| Critère de rattachement | Le rattachement est définitif |

### Gestion du statut

| Statut | Comportement |
|---|---|
| **Activé** | L'indicateur est utilisable dans la démarche qualité |
| **Désactivé** | L'indicateur est temporairement non utilisable |

Toute modification est **historisée** (date, utilisateur, anciennes et nouvelles valeurs).

## Supprimer un indicateur qualité

La suppression d'un indicateur est une opération **définitive et irréversible**.

### Processus de suppression

1. Cliquez sur **Supprimer** depuis la fiche de l'indicateur.
2. Une alerte de confirmation s'affiche : _« Êtes-vous sûr de vouloir supprimer cet indicateur ? Cette action est irréversible. »_
3. Confirmez pour valider la suppression.

## Pour aller plus loin

- [Configurer les éléments de preuve](06-elements-de-preuve) : définir les preuves attendues pour chaque indicateur.
