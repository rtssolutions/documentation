---
title: "09 - Générer un document"
description: "Comment générer un document depuis l'application Papaours"
date: "2026-03-13"
version: "1"
---

# Générer un document

## Vue d'ensemble

Une fois votre template créé et configuré, vous pouvez générer des documents depuis les différentes fiches de l'application. Le contexte de génération dépend des **entités liées** définies dans le template.

---

## Génération selon l'entité liée

| Entité liée | Génération depuis |
|-------------|-------------------|
| `CONTRAT` | Fiche contrat |
| `APPRENANT` | Fiche apprenant |
| `EMPLOYEUR` | Fiche employeur |
| `DOSSIER_FORMATION` | Fiche dossier de formation |

---

## Processus de génération

### Étape 1 : Accéder à la fiche

Ouvrez la fiche correspondant à l'entité liée du template :
- Fiche Contrat pour un template lié à `CONTRAT`
- Fiche Apprenant pour un template lié à `APPRENANT`
- etc.

### Étape 2 : Sélectionner le template

1. Accédez à l'onglet **Documents** de la fiche
2. Cliquez sur **Générer un document**
3. Sélectionnez le template souhaité dans la liste

> Seuls les templates compatibles avec l'entité en cours sont proposés.

### Étape 3 : Prévisualiser (optionnel)

Avant de générer le document final, vous pouvez prévisualiser le résultat pour vérifier que les données sont correctement substituées.

### Étape 4 : Générer le document

1. Cliquez sur **Générer**
2. Le document est créé au format défini (PDF généralement)
3. Il est automatiquement stocké dans l'onglet Documents de la fiche

---

## Documents générés

### Stockage

Les documents générés sont stockés dans Papaours et accessibles depuis :
- L'onglet **Documents** de la fiche source
- Le module **Gestion documentaire** (recherche globale)

### Nommage

Le nom du document généré suit le format :
```
[Type de document] - [Date de génération]
```

Exemple : `Attestation de formation - 13-03-2026.pdf`

### Téléchargement

Les documents générés peuvent être :
- Téléchargés individuellement
- Envoyés par email
- Utilisés dans les processus de signature électronique

---

## Cas particuliers

### Documents réservés (CERFA)

Les documents CERFA (FA13, P2S) sont générés automatiquement par Papaours lors de certaines actions :
- Le CERFA FA13 est généré depuis le contrat d'apprentissage
- Le CERFA P2S est généré depuis le dossier de formation

Ces templates réservés ne peuvent pas être modifiés.

### Signature électronique

Certains documents générés peuvent être envoyés en signature électronique via DocuSeal. Consultez la documentation [Signature de documents](../../signature-documents/index) pour plus d'informations.

---

## Résolution de problèmes

### Le template n'apparaît pas dans la liste

Vérifiez que :
- Le template est bien associé à l'entité correspondante
- Votre organisation a accès au template
- Le template n'est pas désactivé

### Les données ne s'affichent pas

Vérifiez que :
- La syntaxe des balises est correcte (`{d.xxx}`)
- Le chemin vers la donnée existe dans l'entité
- La donnée est renseignée dans la fiche

### Le document est vide ou mal formaté

Vérifiez que :
- Le fichier template est au bon format (DOCX ou HTML)
- Les balises ne contiennent pas d'erreurs de syntaxe
- Les formatters utilisés sont compatibles avec le type de donnée

---

## Pour aller plus loin

- [Syntaxe des substitutions](carbone/substituer/03-les-bases-des-substitutions)
- [Formatters disponibles](carbone/formater/index)
- [Conditions](carbone/conditionner/index)
- [Boucles sur tableaux](carbone/tableau/06-repetitions-with-arrays)
