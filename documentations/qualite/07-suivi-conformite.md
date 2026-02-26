---
title: "Suivre la conformité"
description: "Taux de collecte par indicateur et statut de conformité par indicateur et critère qualité"
date: "2025-07-29"
version: "1"
---

## Taux de collecte par indicateur

Le module Qualité calcule automatiquement le **taux de collecte** pour chaque indicateur qualité. Ce taux mesure
l'avancement de la collecte des preuves par rapport aux éléments de preuve paramétrés.

### Principe de calcul

Pour chaque indicateur, le système évalue l'ensemble des éléments de preuve configurés et détermine la proportion de
ceux qui sont effectivement collectés.

| Élément                | Description                                                          |
|------------------------|----------------------------------------------------------------------|
| **Éléments attendus**  | Nombre total d'éléments de preuve paramétrés pour l'indicateur       |
| **Éléments collectés** | Nombre d'éléments de preuve dont la collecte est effective           |
| **Taux de collecte**   | Ratio éléments collectés / éléments attendus, exprimé en pourcentage |

### Critères de collecte selon le type

| Type de preuve                     | Condition de collecte                                                                  |
|------------------------------------|----------------------------------------------------------------------------------------|
| **Document — source Indicateur**   | Au moins un document du type attendu est rattaché à l'indicateur                       |
| **Document — source Objet métier** | Le taux ou le nombre de documents collectés sur les instances atteint le seuil attendu |
| **Donnée**                         | La donnée est renseignée sur le nombre ou le pourcentage d'instances requis            |

Le taux de collecte prend en compte la volumétrie configurée (taux attendu ou nombre attendu) pour chaque élément de
preuve.

## Statut de conformité

Le statut de conformité permet de disposer d'une vue synthétique de l'état d'avancement de la démarche qualité, à deux
niveaux : **indicateur** et **critère**.

### Conformité par indicateur

Le statut de conformité d'un indicateur est déterminé par le taux de collecte de ses éléments de preuve. Un indicateur
est considéré comme **conforme** lorsque tous ses éléments de preuve atteignent le seuil de volumétrie attendu.

| Statut           | Condition                                                               |
|------------------|-------------------------------------------------------------------------|
| **Conforme**     | Tous les éléments de preuve sont collectés selon la volumétrie attendue |
| **Non conforme** | Au moins un élément de preuve n'atteint pas le seuil attendu            |

### Conformité par critère

Le statut de conformité d'un critère est déterminé par la conformité de l'ensemble de ses indicateurs.

| Statut           | Condition                                          |
|------------------|----------------------------------------------------|
| **Conforme**     | Tous les indicateurs du critère sont conformes     |
| **Non conforme** | Au moins un indicateur du critère est non conforme |

Cette approche ascendante permet de visualiser rapidement les points de non-conformité et d'identifier les actions
correctives nécessaires.

## Pour aller plus loin

- [Vue d'ensemble du module Qualité](01-introduction) : revenir aux objectifs et au périmètre du module.
- [Concepts clés et définitions](02-concepts-cles) : revoir la hiérarchie qualité et les règles fondamentales.
