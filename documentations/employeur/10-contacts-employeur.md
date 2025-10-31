---
title: "10 - Bloc Contacts employeur"
description: "Gestion des contacts liés à un employeur et règles d'accès."
date: "2025-10-31"
version: "1"
---

## Table des matières

1. [Introduction](#introduction)
2. [Description des contacts employeur](#description-des-contacts-employeur)
3. [Accès et permissions](#acces-et-permissions)
4. [Création et modification](#creation-et-modification)
5. [Suppression et cascade](#suppression-et-cascade)
6. [Utilisation des contacts](#utilisation-des-contacts)

---

## Introduction

Les contacts employeur sont des **personnes physiques** rattachées à un employeur, permettant de faciliter la
communication pour la gestion administrative, pédagogique et contractuelle.  
Ils sont gérés directement depuis la fiche détail de l’employeur dans un bloc dédié.

![Bloc Contacts employeur](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/10/bloc-contacts.png)

---

## Description des contacts employeur

Chaque contact dispose des informations suivantes:

- **Nom** (obligatoire)
- **Prénom** (obligatoire)
- **Courriel** (obligatoire, pas de contrainte d’unicité)
- **Téléphone** (optionnel)
- **Nom de naissance** (optionnel)
- **Fonction** (optionnelle)

Les contacts sont affichés sous forme de liste dans le bloc Contacts de la fiche employeur.

---

## Accès et permissions

L’accès au bloc Contacts dépend des permissions attribuées:

- **Lecture**: si non attribuée, le bloc Contacts n’apparaît pas dans la fiche employeur
- **Création / Écriture**: si non attribuée, le bouton **Créer un contact** n’est pas visible en haut à droite du bloc,
  et les boutons de modification des contacts existants ne sont pas affichés

Cette gestion garantit que seuls les utilisateurs habilités peuvent créer ou modifier des contacts.

---

## Création et modification

- La création d’un contact se fait via le bouton **Créer un contact** si l’utilisateur dispose des permissions.
- La modification d’un contact existant se fait en cliquant sur le bouton **Modifier** correspondant dans la liste.
- Dans les deux cas, un formulaire s’ouvre dans une **pop-up** permettant de saisir ou éditer les informations du
  contact.

![Création et modification d'un contact employeur](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/10/formulaire-contact-popup.png)

---

## Suppression et cascade

- Les contacts sont supprimés automatiquement **en cascade** lors de la suppression de l’employeur correspondant.
- Cette suppression assure que les contacts orphelins n’existent pas dans la base.

---

## Utilisation des contacts

Les contacts employeur sont utilisés dans le cadre des contrats pour:

- Choisir un **maître d’apprentissage**
- Définir un **contact**

Ces informations étant obligatoire sur le CERFA.

Ils permettent donc d’assurer la liaison entre l’employeur et le suivi administratif et pédagogique des apprentis.

![Contacts utilisés dans le contrat](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/10/contacts-contrat.png)

---
