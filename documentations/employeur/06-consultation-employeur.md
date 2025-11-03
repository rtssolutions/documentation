---
title: "06 - Consultation d'un employeur"
description: "Visualisation détaillée des informations et actions sur un employeur."
date: "2025-10-31"
version: "1"
---

## Table des matières
1. [Accéder au détail d'un employeur](#accéder-au-détail-dun-employeur)
2. [Organisation de la fiche détail](#organisation-de-la-fiche-détail)
3. [Blocs d’information](#blocs-dinformation)
4. [Actions disponibles](#actions-disponibles)

---

## Accéder au détail d'un employeur

### Depuis la liste principale
- Accédez via le menu **Employeurs > Liste**
- Utilisez la barre de recherche (Nom commercial, SIRET, IDCC, minimum 3 caractères)
- Cliquez sur la ligne de l’employeur ou le bouton **"Voir"**

### Navigation directe
- Accès via URL directe si le code employeur est connu
- Liens depuis d’autres modules (contrats, dossiers de formation)
- Favoris et raccourcis personnalisés

---

## Organisation de la fiche détail

![Vue détail employeur](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/6/vue-detail-employeur.png)

La fiche détail est organisée en plusieurs blocs pour faciliter la consultation et la gestion :

- **Bloc en-tête** : résumé de l’employeur et actions principales
- **Bloc Identité** : informations légales + gestion de la visiblité
- **Bloc Coordonnées** : téléphone, courriel, site internet
- **Bloc Qualifications** : informations administratives sur l'employeur
- **Bloc Fiscalité** : informations sur la fiscalité de l'enmployeur, TVA, etc
- **Bloc Contacts** : liste des contacts associés
- **Bloc Documents associés** : documents liés
- **Bloc Historique des actions** : actions réalisées sur l’employeur

---

## Blocs d’information

### Bloc En-tête

Ce bloc donne un aperçu rapide et synthétique de l’employeur.

- **Nom commercial** : désignation usuelle de l’entreprise, utilisée dans les communications commerciales.
- **Statut (tag)** : statut fonctionnel du dossier (ex. : *Actif*, *Archivé*, *Supprimé*).  
  Permet d’identifier d’un coup d’œil la situation actuelle de l’employeur dans la plateforme.
- **Statut personnalisé (chips)** : statuts secondaires ou spécifiques définis par les utilisateurs (ex. : *En attente de validation*).
- **Liste d’actions principales** :
    - **Modifier** : ouvre la fiche en mode édition.
    - **Supprimer** : supprime la fiche de manière définitive (selon les permissions).

---

### Bloc Identité

Regroupe les informations administratives et juridiques de l’employeur.

- **Visibilité** : liste des organisations ayant accès à la fiche (droits de consultation et de modification).
- **Nom commercial** : utilisé à des fins de communication externe.
- **Dénomination sociale** : nom juridique enregistré au RCS.
- **Code APE / NAF** : activité principale exercée (ex. : 8559A – Formation continue).
- **Type d’entreprise** : statut juridique (ex. : SARL, SASU, Association).
- **Secteur d’activité** : domaine professionnel de l’entreprise.
- **SIREN** : numéro d’identification unique de l’entreprise (9 chiffres).
- **SIRET** : numéro d’identification de l’établissement (14 chiffres, dont le SIREN).
- **Adresse postale** : adresse officielle associée au SIRET.

---

### Bloc Qualification de l’employeur

Contient les informations administratives et sociales principales.

- **Effectif total** : nombre de salariés (utile pour les obligations légales).
- **Convention collective principale** : texte de référence applicable à la majorité des salariés.
- **Autres conventions collectives applicables** : conventions additionnelles éventuelles.
- **Régime social** : type d’affiliation (URSSAF ou MSA).
- **Caisse de retraite** : organisme de rattachement pour les cotisations sociales.

---

### Bloc Fiscalité

Centralise les informations relatives à la TVA et au régime fiscal.

- **Soumis à la TVA ?** : indique si l’entreprise est assujettie à la TVA (*Oui / Non*).
- **Numéro de TVA** : numéro d’identification fiscal communautaire.
- **Régime de TVA** : régime d’imposition applicable (*franchise, réel, simplifié*).
- **Taux de TVA** : taux appliqué (*20 %, 10 %, 5,5 %, ou personnalisé*).
- **Taux de TVA personnalisé** : valeur libre comprise entre 0 % et 100 %.

---

### Bloc Coordonnées

Regroupe les moyens de contact principaux de l’employeur.

- **Téléphone** : numéro principal de l’entreprise.
- **Courriel** : adresse courriel générique ou de contact.
- **Site internet** : lien vers le site institutionnel ou commercial.

---

### Bloc Contacts

Liste les personnes liées à l’employeur et leurs coordonnées.

Chaque contact affiche :
- **Nom et prénom**
- **Fonction** (ex. : Responsable RH, Tuteur)
- **Coordonnées** : adresse mail professionnelle et téléphone direct

---

### Bloc Documents associés

Liste des fichiers liés à l’employeur (contrats, conventions, justificatifs…).

Chaque document peut être :
- **Consulté / Téléchargé**
- **Supprimé**
- **Téléversé**  
  Les actions disponibles dépendent des permissions de l’utilisateur.

---

### Bloc Historique des actions

Affiche l’ensemble des opérations effectuées sur la fiche employeur.  
Permet de tracer les modifications et d’identifier les responsables des mises à jour.

Caractéristiques :
- Liste paginée et filtrable
- Détail des actions : date, utilisateur, type d’action, anciennes et nouvelles valeurs

---

## Actions disponibles

- **Modifier** : accès conditionné par permission Écriture sur les employeurs
- **Supprimer** : accès conditionné par permission de suppression
- **Archiver** : alternative si suppression impossible (dans une future version)
- **Ajouter un document** : accès conditionné par permission d'écriture sur Document employeur
- **Modifier le statut personnalisé** : uniquement si permission Écriture
- **Gérer la visibilité** : uniquement pour le centre de formation propriétaire

![Actions disponibles](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/employeur/6/detail-employeur-actions.png)

---

### Pour aller plus loin

➡️ Poursuivez avec la page suivante :  
[07 - Modification d'un employeur](07-modification-employeur)
