---
title: "04 - Consulter et télécharger"
description: "Guide pour consulter, télécharger et gérer les documents associés"
date: "2026-03-20"
version: "1"
---

# Consulter et télécharger

## Consultation des documents

### Accéder aux documents

Pour consulter les documents associés à une entité :

1. Ouvrez la fiche de l'entité (Apprenant, Employeur, Contrat, etc.)
2. Naviguez vers la section **Documents** ou l'onglet **Documents associés**
3. La liste des documents s'affiche

### Informations affichées

Pour chaque document, vous pouvez voir :

| Information | Description |
|-------------|-------------|
| **Nom** | Intitulé du document |
| **Type** | Catégorie du document |
| **Date d'ajout** | Date de téléversement |
| **Ajouté par** | Utilisateur ayant téléversé le document |
| **Taille** | Poids du fichier |

### Aperçu rapide

Pour certains types de fichiers (PDF, images), un aperçu est disponible :

1. Cliquez sur le nom du document
2. Un aperçu s'affiche dans une fenêtre modale
3. Utilisez les contrôles pour zoomer ou naviguer

## Téléchargement

### Télécharger un document

Pour télécharger un document sur votre ordinateur :

1. Localisez le document dans la liste
2. Cliquez sur l'icône de téléchargement (flèche vers le bas) ou sur **"Télécharger"**
3. Le fichier est téléchargé dans votre dossier de téléchargements

### Téléchargement groupé

Si plusieurs documents sont disponibles, vous pouvez les télécharger en lot :

1. Sélectionnez les documents souhaités (cases à cocher)
2. Cliquez sur **"Télécharger la sélection"**
3. Un fichier ZIP contenant tous les documents est téléchargé

## Gestion des documents

### Supprimer un document

Pour supprimer un document :

1. Localisez le document dans la liste
2. Cliquez sur l'icône de suppression (corbeille)
3. Confirmez la suppression dans la fenêtre de dialogue

> La suppression est définitive mais l'action reste tracée dans l'historique.

### Permissions requises

| Action | Permission nécessaire |
|--------|----------------------|
| **Consulter** | Lecture sur l'entité |
| **Télécharger** | Lecture sur l'entité |
| **Ajouter** | Écriture sur l'entité |
| **Supprimer** | Suppression sur l'entité |

## Historique des documents

### Traçabilité

Chaque action sur les documents est enregistrée :

- **Ajout** : date, utilisateur, nom du fichier
- **Suppression** : date, utilisateur, nom du fichier supprimé
- **Téléchargement** : date, utilisateur (si configuré)

### Consulter l'historique

Pour voir l'historique des actions :

1. Accédez à la fiche de l'entité
2. Ouvrez la section **Historique**
3. Filtrez par type d'action **"Document"**

## Documents générés automatiquement

### Identification

Les documents générés par Papaours (CERFA, attestations) sont identifiables par :

- Une icône spécifique
- La mention **"Généré automatiquement"**
- Le type de document (CERFA FA13, CERFA P2S, etc.)

### Caractéristiques

Ces documents :

- Ne peuvent pas être supprimés manuellement
- Sont regénérés si les données source changent
- Conservent un historique des versions

## Bonnes pratiques

### Organisation

- **Vérifiez régulièrement** les documents présents
- **Supprimez les doublons** pour maintenir la clarté
- **Mettez à jour** les documents périmés

### Sécurité

- **Ne partagez pas** les documents sensibles en dehors de Papaours
- **Respectez la confidentialité** des données personnelles
- **Signalez** tout document inapproprié à votre administrateur

## Résolution de problèmes

### Impossible de télécharger

- Vérifiez que vous disposez des droits de lecture
- Essayez avec un autre navigateur
- Vérifiez votre connexion internet

### Document corrompu

- Essayez de télécharger à nouveau
- Contactez l'utilisateur ayant téléversé le document original
- Demandez un nouveau fichier source

### Document non visible

- Vérifiez vos permissions sur l'entité
- Actualisez la page
- Vérifiez les filtres actifs dans la liste
