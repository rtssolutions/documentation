---
title: "08 - Suppression d'un employeur"
description: "Procédure et règles pour supprimer un employeur."
date: "2025-10-31"
version: "1"
---

## Table des matières

1. [Introduction](#introduction)
2. [Pré-requis et permissions](#pré-requis-et-permissions)
3. [Procédure de suppression](#procédure-de-suppression)
4. [Conséquences et historisation](#conséquences-et-historisation)
5. [Cas particuliers et bonnes pratiques](#cas-particuliers-et-bonnes-pratiques)

---

## Introduction

La suppression d’un employeur est une opération sensible.  
Elle est encadrée pour garantir la cohérence des données et la traçabilité des actions.

---

## Pré-requis et permissions

- **Permission requise** : Suppression des employeurs
- L’utilisateur doit être contextualisé sur le centre de formation ou l’organisation ayant la visibilité sur l’employeur
- La suppression n’est possible que si l’employeur n’est associé à aucun contrat valide ou brouillon

---

## Procédure de suppression

1. Accéder à la fiche de l’employeur
2. Vérifier que l’employeur n’a aucun contrat valide ou en brouillon associé
3. Cliquer sur **"Supprimer"**
4. Confirmer la suppression via la boîte de dialogue :

![Pop-up de confirmation de suppression](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/8/pop-up-suppression-employeur.png)

---

## Conséquences et historisation

- **Suppression physique** : les données sont supprimées définitivement
- **Traçabilité** : l’action est historisée avec :
    - Code employeur
    - Type d’action
    - Auteur
    - Date
- Les contacts associés sont également supprimés

---

## Cas particuliers et bonnes pratiques

- **Suppression impossible** :
    - Si un contrat est associé, la suppression est interdite
    - Message explicatif affiché à l’utilisateur
- **Bonnes pratiques** :
    - Privilégier l’archivage pour conserver l’historique
    - Supprimer uniquement en cas d’erreur manifeste ou doublon

---

### Pour aller plus loin

➡️ Consultez la page suivante :  
[09 - Statut personnalisé des employeurs](09-statut-personnalise-employeurs.md)
