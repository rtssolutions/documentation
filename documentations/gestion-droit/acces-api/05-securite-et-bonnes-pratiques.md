---
title: "05 - Sécurité et bonnes pratiques"
description: "Protéger et utiliser vos clés API en toute sécurité"
date: "2025-10-07"
version: "1"
---

## Sécurité et bonnes pratiques

La protection de vos clés API est essentielle pour garantir la sécurité de vos accès à la plateforme Papaours. Voici
les bonnes pratiques à suivre lors de l'utilisation de vos clés API.

---

## Conservation sécurisée des clés

Lorsque vous créez une clé API, celle-ci s'affiche une seule fois. Il est crucial de la conserver de manière sécurisée :

- **Copiez immédiatement la clé** et sauvegardez-la dans un endroit sûr avant de fermer la fenêtre.
- **Ne partagez jamais vos clés** par email, messagerie instantanée ou tout autre moyen non sécurisé.
- **Utilisez un gestionnaire de mots de passe** ou un coffre-fort numérique pour stocker vos clés.
- **Ne notez pas les clés sur papier** ou dans des fichiers non protégés sur votre ordinateur.

---

## Protection de vos clés dans vos applications

Si vous développez des applications utilisant les clés API Papaours :

- **N'incluez jamais les clés directement dans votre code** : Elles seraient visibles par toute personne ayant accès au
  code source.
- **Utilisez des variables d'environnement** : Stockez vos clés dans des fichiers de configuration séparés du code.
- **Ne versionnez pas vos clés** : Assurez-vous que les fichiers contenant des clés ne sont pas enregistrés dans votre
  système de contrôle de version (Git, SVN, etc.).

### Exemple de mauvaise pratique ❌

```javascript
// ❌ Ne faites JAMAIS cela
const API_KEY = "pk_prod_abc123def456ghi789";

fetch("https://api.papaours.fr/contrats", {
  headers: {
    "Authorization": `Bearer ${API_KEY}`
  }
});
```

### Exemple de bonne pratique ✅

```javascript
// ✅ Utilisez des variables d'environnement
const API_KEY = process.env.PAPAOURS_API_KEY;

fetch("https://api.papaours.fr/contrats", {
  headers: {
    "Authorization": `Bearer ${API_KEY}`
  }
});
```

---

## Renouvellement régulier des clés

Il est recommandé de changer vos clés API régulièrement, même si vous ne suspectez aucun problème de sécurité :

1. **Créez une nouvelle clé** avec un nom explicite (exemple : "Clé production 2025").
2. **Testez la nouvelle clé** dans votre environnement de test avant de l'utiliser en production.
3. **Remplacez l'ancienne clé** dans tous vos systèmes.
4. **Désactivez l'ancienne clé** une fois que vous êtes certain que tous vos systèmes utilisent la nouvelle.

Cette pratique limite les risques en cas de fuite accidentelle d'une clé.

---

## Utilisation de clés distinctes par environnement

Créez des clés API différentes pour vos différents environnements :

- Une clé pour votre **environnement de production**
- Une clé pour votre **environnement de test**
- Une clé pour votre **environnement de développement**

### Avantages de cette séparation

✅ **Désactiver uniquement la clé de test** sans affecter la production
✅ **Identifier plus facilement l'origine des appels** dans les logs
✅ **Limiter l'impact** en cas de compromission d'une clé

### Exemple d'organisation

```
Machine : Service de Facturation
├── Clé API : Production - Service Facturation (Active)
├── Clé API : Test - Service Facturation (Active)
└── Clé API : Dev - Service Facturation (Active)
```

---

## Nommage clair de vos clés

Donnez des noms explicites à vos clés pour les retrouver facilement :

### ✅ Exemples de noms clairs

- `Production - Service Facturation`
- `Test - Intégration Partenaire`
- `Développement - Application Mobile`
- `Staging - API Externe v2`

### ❌ Évitez les noms vagues

- `Clé 1`
- `Ma clé`
- `Test`
- `API`

Un bon nom de clé devrait vous permettre de répondre à ces questions :

- **Quel environnement ?** (Production, Test, Dev)
- **Quel système utilise cette clé ?** (Service, Application, Script)
- **Quelle version ?** (v1, v2, 2025, etc.)

---

## Que faire si vous pensez qu'une clé a été compromise ?

Si vous suspectez qu'une de vos clés API a été vue ou utilisée par une personne non autorisée :

### Actions immédiates

1. **Désactivez immédiatement la clé** via le bouton Modifier dans l'interface Papaours.
2. **Créez une nouvelle clé** pour la remplacer.
3. **Mettez à jour vos systèmes** avec la nouvelle clé.
4. **Informez votre administrateur** si vous pensez que des données sensibles ont pu être consultées.

> ⚠️ **Réagissez rapidement** : Tant que la clé compromise reste active, elle peut être utilisée par des personnes non
> autorisées.
> N'hésitez pas à contacter les équipes Papaours pour vous accompagner sur ce point.

### Signes de compromission

Soyez vigilant si vous observez :

- Des appels API depuis des adresses IP inhabituelles
- Une augmentation soudaine du nombre d'appels API
- Des erreurs d'authentification répétées
- Des accès à des ressources inhabituelles

---

## Suppression des clés inutilisées

Si vous n'utilisez plus une clé API :

- **Désactivez-la** plutôt que de la laisser active sans utilisation.
- **Conservez l'historique** : Une clé désactivée reste visible dans la liste pour référence, mais ne peut plus être
  utilisée.
- 
---

## Ce que Papaours gère pour vous

Pour vous aider à maintenir la sécurité, **Papaours s'occupe automatiquement de** :

### 🔍 L'historique d'utilisation

Tous les appels effectués avec vos clés sont enregistrés. Vous pouvez ainsi :

- Consulter quand une clé a été utilisée pour la dernière fois
- Identifier les clés actives vs inactives
- Détecter des usages anormaux

### 🔐 La sécurité du système

Le code de génération et de validation des clés est :

- Maintenu et mis à jour par l'équipe Papaours
- Protégé selon les standards de sécurité les plus élevés
- Régulièrement audité

---

### Pour aller plus loin

- [Créer une machine →](03-gestion-des-machines.md)
- [Créer une clé API →](04-gestion-des-cles-api.md)
- [Comprendre les concepts →](02-definition-concepts-cles-machines-cles-api.md)

[Retour à l'Accueil](../accueil)
