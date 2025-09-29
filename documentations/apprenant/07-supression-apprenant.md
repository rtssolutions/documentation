---
title: "07 - Suppression d'un apprenant"
description: "Procédure et impacts de la suppression d'un apprenant."
date: "2025-09-26"
version: "1"
---

## 📚 Table des matières
1. [Introduction](#introduction)
2. [Pré-requis et permissions](#pré-requis-et-permissions)
3. [Procédure de suppression](#procédure-de-suppression)
4. [Conséquences et gestion des données](#conséquences-et-gestion-des-données)
5. [Cas particuliers et bonnes pratiques](#cas-particuliers-et-bonnes-pratiques)
6. [Pour aller plus loin](#pour-aller-plus-loin)

---

## Introduction
La suppression d’un apprenant est une opération sensible, encadrée par des règles strictes pour garantir la traçabilité, la sécurité et la cohérence des données. Cette action est généralement réservée aux utilisateurs disposant de droits avancés.

## Pré-requis et permissions
- **Permission requise** : "Suppression des apprenants".
- L’utilisateur doit être contextualisé sur le centre de formation ou une unité de formation qui possède la visibilite sur l’apprenant.
- La suppression n’est possible que si l’apprenant n’est pas engagé dans un processus bloquant (ex : formation en cours, inscription validée, etc.).

## Procédure de suppression
1. **Accéder à la fiche de l’apprenant** :
   - Depuis la liste des apprenants, cliquer sur l’apprenant concerné.
2. **Vérifier l’état de l’apprenant** :
   - S’assurer qu’aucune formation en cours ou dossier administratif bloquant n’est rattaché à l’apprenant.
   - Un message d’alerte s’affiche si la suppression est impossible.
3. **Cliquer sur le bouton "Supprimer"** :
   - Le bouton est visible uniquement pour les utilisateurs autorisés et si l’apprenant est éligible à la suppression.
4. **Confirmer la suppression** :
   - Une fenêtre de confirmation détaille les conséquences de la suppression (perte d’accès, archivage des données, etc.).
   - L’utilisateur doit valider explicitement l’action.

![Suppression d'un apprenant](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/7/supression-apprenant.png)

## Conséquences et gestion des données
- **Supression définitive** : Les données de l’apprenant sont supprimées physiquement de la base de données.
- **Traçabilité** : L’opération est historisée (date, utilisateur, entite concernée).
- **Unicité** : Le code apprenant reste réservé et ne pourra pas être réattribué à un autre apprenant, même après suppression
- **Effet sur les documents liés** : Les documents administratifs ou pédagogiques associés à l’apprenant sont également archivés.

## Cas particuliers et bonnes pratiques
- **Suppression impossible** :
  - Si l’apprenant est inscrit à une session de formation en cours, la suppression est bloquée.
  - Un message explicite indique la raison du blocage.
- **Bonnes pratiques** :
  - Privilégier l’archivage plutôt que la suppression définitive, sauf en cas d’erreur manifeste de saisie.

