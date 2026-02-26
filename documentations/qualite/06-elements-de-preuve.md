---
title: "Configurer les éléments de preuve"
description: "Lister, créer et consulter les éléments de preuve (documents et données) rattachés aux indicateurs qualité"
date: "2025-07-29"
version: "1"
---

## Accéder aux éléments de preuve

Depuis la fiche d'un indicateur, cliquez sur **Voir le paramétrage** pour accéder à la liste des éléments de preuve
configurés pour cet indicateur.

Les éléments de preuve sont organisés en **trois sections** distinctes :

| Section                               | Contenu                                                           |
|---------------------------------------|-------------------------------------------------------------------|
| Éléments de preuve de type **Donnée** | Données applicatives exploitées comme preuves                     |
| Documents — source **Indicateur**     | Documents attendus rattachés directement à l'indicateur           |
| Documents — source **Objet métier**   | Documents attendus recherchés sur les instances d'un objet métier |

### Informations affichées par section

**Type Donnée :**

| Colonne          | Description                                       |
|------------------|---------------------------------------------------|
| Objet métier     | L'objet métier source de la donnée                |
| Donnée(s)        | Les données associées (séparées par des virgules) |
| Fournisseur      | Groupe(s) d'utilisateurs fournisseurs             |
| Acceptation      | Taux ou nombre attendu                            |
| Période de dépôt | Période de collecte configurée                    |

**Type Document — source Indicateur :**

| Colonne          | Description                           |
|------------------|---------------------------------------|
| Type de document | Intitulé du type de document attendu  |
| Fournisseur      | Groupe(s) d'utilisateurs fournisseurs |
| Acceptation      | Taux ou nombre attendu                |
| Période de dépôt | Période de collecte configurée        |

**Type Document — source Objet métier :**

| Colonne          | Description                           |
|------------------|---------------------------------------|
| Objet métier     | L'objet métier source                 |
| Type de document | Intitulé du type de document attendu  |
| Fournisseur      | Groupe(s) d'utilisateurs fournisseurs |
| Acceptation      | Taux ou nombre attendu                |
| Période de dépôt | Période de collecte configurée        |


## Créer un élément de preuve de type Document

Un élément de preuve de type Document définit quel type de document est attendu et depuis quelle source il doit être
collecté.

### Champs à renseigner

| Champ                              | Obligatoire  | Description                                                 |
|------------------------------------|--------------|-------------------------------------------------------------|
| Indicateur                         | Oui          | Indicateur de rattachement                                  |
| Type de document attendu           | Oui          | Sélectionné dans la liste des types de documents paramétrés |
| Source du document                 | Oui          | **Indicateur** ou **Objet métier**                          |
| Objet métier source                | Conditionnel | Obligatoire si la source est « Objet métier »               |
| Groupe d'utilisateurs fournisseurs | Non          | Groupe(s) responsables de la fourniture du document         |
| Mode de volumétrie                 | Oui          | Taux attendu ou Nombre attendu                              |
| Taux attendu                       | Conditionnel | Entier de 0 à 100 (défaut : 100)                            |
| Nombre attendu                     | Conditionnel | Entier strictement positif                                  |
| Période de collecte                | Non          | Période durant laquelle le document doit être déposé        |
| Date butoir                        | Non          | Date limite de dépôt                                        |
| Durée de validité                  | Non          | Durée en mois                                               |

### Source Indicateur

Le document attendu est recherché parmi les documents rattachés directement à l'indicateur. Si au moins un document du
type attendu est présent, l'élément de preuve est considéré comme **collecté**.

### Source Objet métier

Un objet métier est sélectionné (par exemple, Apprenant ou Action de formation). Pour chaque instance de cet objet, le
système recherche un document du type attendu. L'élément de preuve est considéré comme **collecté pour chaque instance**
où le document est présent.

## Créer un élément de preuve de type Donnée

Un élément de preuve de type Donnée permet d'exploiter les données applicatives comme preuves de conformité.

### Champs à renseigner

| Champ                              | Obligatoire  | Description                                                 |
|------------------------------------|--------------|-------------------------------------------------------------|
| Indicateur                         | Oui          | Indicateur de rattachement                                  |
| Objet métier source                | Oui          | Objet métier dont les données seront exploitées             |
| Donnée(s) associée(s)              | Oui          | Au moins une donnée à sélectionner parmi celles disponibles |
| Groupe d'utilisateurs fournisseurs | Non          | Groupe(s) responsables                                      |
| Mode de volumétrie                 | Oui          | Taux attendu ou Nombre attendu                              |
| Taux attendu                       | Conditionnel | Entier de 0 à 100 (défaut : 100)                            |
| Nombre attendu                     | Conditionnel | Entier strictement positif                                  |
| Période de collecte                | Non          | Période durant laquelle la donnée est attendue              |
| Date butoir                        | Non          | Date limite                                                 |
| Durée de validité                  | Non          | Durée en mois                                               |

### Données accessibles par objet métier

Pour chaque objet métier, l'application expose une liste de données accessibles. Une donnée peut être :

- Un **attribut simple** (par exemple, la date de naissance d'un apprenant)
- Une **donnée calculée** (par exemple, le taux de réussite d'une action de formation)

Plusieurs données peuvent être associées à un même élément de preuve, à condition qu'elles appartiennent toutes au même
objet métier.

## Règles communes aux éléments de preuve

### Volumétrie : taux et nombre

Le taux attendu et le nombre attendu sont **mutuellement exclusifs**. Un seul des deux peut être renseigné.

| Mode               | Description                       | Valeur par défaut |
|--------------------|-----------------------------------|-------------------|
| **Taux attendu**   | Pourcentage entier entre 0 et 100 | 100 %             |
| **Nombre attendu** | Entier strictement positif        | —                 |

Un taux de 100 % signifie qu'une preuve est attendue pour chaque instance de la source.

### Périodicité et date butoir

L'élément de preuve peut avoir une contrainte temporelle parmi les suivantes (une seule à la fois) :

- **Période de collecte** : intervalle de dates durant lequel la preuve doit être collectée.
- **Date butoir** : date limite unique pour le dépôt de la preuve.
- **Aucune contrainte** : la preuve peut être collectée à tout moment.

### Durée de validité et renouvellement

Si une durée de validité (en mois) est renseignée, la date de renouvellement est calculée automatiquement :

| Cas                          | Calcul de la date de renouvellement                                                          |
|------------------------------|----------------------------------------------------------------------------------------------|
| Période de collecte définie  | Date de fin de période + durée de validité                                                   |
| Date butoir définie          | Date butoir + durée de validité                                                              |
| Aucune contrainte temporelle | Date de dépôt du document (ou date de dernière mise à jour de la donnée) + durée de validité |

## Consulter le détail d'un élément de preuve

Depuis la liste des éléments de preuve d'un indicateur, cliquez sur **Détails** pour ouvrir la fiche de l'élément en **lecture seule**.

La fenêtre affiche l'ensemble des champs de paramétrage préremplis avec les valeurs de l'élément de preuve. Aucune
modification n'est possible depuis cette vue.

Les informations affichées incluent :

- Intitulé, type, indicateur rattaché, description, statut
- Groupe(s) d'utilisateurs fournisseurs
- Mode d'acceptation (taux ou nombre) et valeur attendue
- Période de dépôt, durée de validité, date de renouvellement
- **Pour le type Donnée** : objet métier source et donnée(s) associée(s)
- **Pour le type Document** : type de document attendu, source (Indicateur ou Objet métier) et objet métier source le
  cas échéant

Cliquez sur **Fermer** pour revenir à la liste des éléments de preuve sans rechargement de la page.

## Pour aller plus loin

- [Suivre la conformité](07-suivi-conformite) : comprendre le taux de collecte et le statut de conformité.
