---
title: "Signature manuelle"
description: "Créer et gérer les signatures manuscrites sur papier"
date: "2026-02-26"
version: "1"
---

# Signature manuelle

La signature manuelle permet de gérer le processus de signature papier pour **tous les documents** de l'application, qu'ils soient générés depuis un template ou téléversés manuellement.

## Principe de fonctionnement

Le processus de signature manuelle se déroule hors de l'application :

1. **Création** : Vous créez une signature sur un document et définissez les signataires
2. **Envoi** : Vous envoyez la signature (le système passe en état "Envoyée en signature")
3. **Signature physique** : Le document est transmis aux signataires (par email ou impression papier) et signé par les parties
4. **Validation** : Vous téléversez le document signé (scan) et validez la signature

> La signature manuelle fonctionne toujours **sans ordonnancement** : tous les signataires sont considérés comme signant simultanément.

## Créer une signature manuelle

### Accéder à la création

![Bouton créer signature](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/creer-signature-btn.png)

1. Accédez au document concerné
2. Cliquez sur **Créer une signature**
3. Sélectionnez le canal **Manuelle**

### Configurer la signature

![Création signature manuelle](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/creation-manuelle.png)

1. **Canal** : Sélectionnez `Manuelle`
2. **Ordonnancement** : Automatiquement défini sur "Sans ordonnancement"
3. Validez la création

La signature est créée avec l'état **Créée**.

## Ajouter des signataires

Après la création de la signature, ajoutez les signataires requis.

### Ajouter une personne physique

![Ajout personne physique](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/ajout-personne-physique.png)

1. Cliquez sur **Ajouter un signataire**
2. Sélectionnez **Personne physique**
3. Renseignez :
   - **Nom** : Nom de famille
   - **Prénom** : Prénom
   - **Email** : Adresse email
   - **Profil** : Rôle du signataire (ex: "Apprenant", "Employeur")
4. Validez

### Ajouter une personne morale (visa)

![Ajout personne morale](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/ajout-personne-morale.png)

1. Cliquez sur **Ajouter un signataire**
2. Sélectionnez **Personne morale**
3. Renseignez :
   - **Code visa** : Identifiant de l'organisation
   - **Email** : Adresse email (optionnel si signature automatique)
   - **Mode de signature** : Automatique ou Manuel
4. Validez

## Envoyer en signature

Une fois les signataires définis :

![Envoyer en signature](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/envoyer-signature-btn.png)

1. Vérifiez la liste des signataires
2. Cliquez sur **Envoyer en signature**
3. Confirmez l'envoi

![Confirmation envoi](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/confirmation-envoi.png)

La signature passe à l'état **Envoyée en signature**.

> À ce stade, transmettez le document aux signataires (par email ou impression papier) et faites-le signer par toutes les parties.

## Valider la signature

Une fois le document signé sur papier et numérisé :

### Téléverser le document signé

![Validation signature manuelle](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/validation-manuelle.png)

1. Accédez au détail de la signature
2. Cliquez sur **Valider la signature**
3. Téléversez le document signé (scan PDF)
4. Confirmez la validation

### Résultat

Après validation :
- L'état passe à **Signée**
- **Tous les signataires** passent au statut "Signé" simultanément
- Le document signé est accessible depuis le détail de la signature

![Signature validée](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/signature-validee.png)

## Annuler une signature

Vous pouvez annuler une signature tant qu'elle n'est pas terminée (signée, refusée).

![Annuler signature](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/annuler-signature.png)

1. Accédez au détail de la signature
2. Cliquez sur **Annuler**
3. Confirmez l'annulation

**Conséquences de l'annulation :**
- L'état passe à **Annulée**
- Tous les signataires passent au statut "Annulé"
- La signature ne peut plus être modifiée ni envoyée
- Une signature annulée peut être **supprimée**

## Supprimer une signature

La suppression est possible uniquement si la signature est :
- À l'état **Créée** (jamais envoyée)
- À l'état **Annulée**

![Supprimer signature](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/supprimer-signature.png)

1. Accédez au détail de la signature
2. Cliquez sur **Supprimer**
3. Confirmez la suppression

> **Attention** : La suppression est **irréversible**.

## Visualiser les documents

Depuis le détail de la signature, accédez aux documents :

![Voir documents](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/voir-documents.png)

- **Document original** : Le document à signer (avant signature)
- **Document signé** : Le scan téléversé lors de la validation (après signature)

## Suivi et historique

### Détail de la signature

La page de détail affiche :

![Détail signature](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/detail-signature-manuelle.png)

| Information | Description |
|-------------|-------------|
| **Type** | Manuelle |
| **Canal** | Manuelle |
| **État** | État actuel de la signature |
| **Date de création** | Date et heure de création |
| **Date du dernier état** | Date du dernier changement d'état |

### Liste des signataires

Le tableau des signataires affiche pour chaque personne :

| Colonne | Description |
|---------|-------------|
| Signataire | Nom et email (ou code visa) |
| Type/Profil | Personne physique + profil / Visa |
| État | Statut actuel du signataire |
| Date d'envoi | Date d'envoi de la demande |
| Date du dernier état | Dernière mise à jour |
| Date de signature | Date de signature (si signé) |

### Historique des actions

L'historique retrace toutes les actions effectuées sur la signature :
- Création
- Ajout/modification/suppression de signataires
- Envoi en signature
- Validation
- Annulation

![Historique](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/signature/historique-actions.png)
