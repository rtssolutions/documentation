---
title: "01 - Introduction aux machines et clés API"
description: "Introduction à la gestion des machines et des clés API dans Papaours"
date: "2025-10-07"
version: "1"
---

## Introduction

Bienvenue dans la documentation de gestion des **machines** et des **clés API** de la plateforme Papaours.

Cette documentation vous guidera à travers les concepts, les procédures et les bonnes pratiques pour :

- Créer et gérer des machines
- Générer et administrer des clés API
- Sécuriser vos accès programmatiques à la plateforme

## À qui s'adresse cette documentation ?

Cette documentation est destinée aux **administrateurs système** et aux **responsables de la sécurité** qui ont besoin
de :

- Donner un accès programmatique à la plateforme Papaours à des services automatisés
- Intégrer des systèmes externes avec Papaours via API
- Gérer les permissions d'accès pour des applications tierces
- Sécuriser les communications entre systèmes

## Prérequis

Pour pouvoir créer et gérer des machines et des clés API, vous devez disposer des permissions suivantes dans la
plateforme Papaours :

- **Gestion des droits / Machines / Lecture** : Pour consulter les machines existantes
- **Gestion des droits / Machines / Écriture** : Pour créer et modifier des machines
- **Gestion des droits / Machines / Écriture** : Pour générer des clés API
- **Gestion des droits / Machines / Écriture** : Pour modifier ou désactiver des clés API

## Structure de la documentation

Cette documentation est organisée en plusieurs sections :

1. **Introduction** (cette page) : Vue d'ensemble et prérequis
2. **Définition et concepts clés** : Comprendre la différence entre machines et clés API
3. **Gestion des machines** : Créer, consulter et modifier des machines
4. **Gestion des clés API** : Créer, consulter et modifier des clés API
5. **Sécurité et bonnes pratiques** : Protéger et utiliser vos clés API en toute sécurité

## Cas d'usage courants

### Intégration d'un système de facturation

Vous développez un service de facturation qui doit accéder aux données de contrats et créer des factures dans Papaours.
Vous créerez une machine "Service de facturation" avec les permissions appropriées, puis générerez des clés API pour
chaque environnement (développement, test, production).

### Synchronisation avec un système externe

Votre organisation utilise un système RH externe qui doit lire les données d'apprentis depuis Papaours. Vous créerez une
machine "Système RH" avec les permissions de lecture nécessaires et générerez une clé API pour l'authentification.

### Automatisation de processus

Vous mettez en place des scripts automatisés pour extraire des rapports quotidiens depuis Papaours. Vous créerez une
machine "Scripts reporting" avec les permissions de lecture appropriées.

## Navigation rapide

- [Comprendre les machines et clés API →](02-definition-concepts-cles-machines-cles-api.md)
- [Créer votre première machine →](03-gestion-des-machines.md)
- [Générer une clé API →](04-gestion-des-cles-api.md)
- [Sécuriser vos clés →](05-securite-et-bonnes-pratiques.md)

---

[Retour à l'Accueil](../accueil)
