# Guide d'Utilisation - Documentation et Release Notes

## 📚 Introduction

Ce guide explique comment utiliser et maintenir le système de documentation et de release notes de l'application
Papaours Gestion. Vous apprendrez à :

- Créer et organiser des documents de documentation
- Publier des notes de version
- Utiliser les fonctionnalités avancées du système
- Suivre les bonnes pratiques de rédaction

## 🎯 À qui s'adresse ce guide ?

- **Rédacteurs** : Création et maintenance de la documentation
- **Product Owners** : Publication des release notes
- **Équipe technique** : Maintenance et évolution du système

## 🏗️ Vue d'ensemble du système

### Documentation (`/dashboard/documentations/`)

La section documentation permet de consulter et naviguer dans l'ensemble des guides, tutoriels et références techniques
de l'application. Elle offre :

- **Navigation intuitive** avec une sidebar arborescente et tri intelligent
- **Interface optimisée** avec sidebar réduite par défaut pour plus d'espace de lecture
- **Icônes personnalisées** pour organiser visuellement les dossiers
- **Tri hiérarchique** : fichiers d'abord, puis dossiers, triés alphabétiquement
- **Affichage optimisé** avec mise en forme automatique
- **Support vidéo** pour les tutoriels multimédias
- **Liens intelligents** avec navigation Next.js optimisée

### Release Notes (`/dashboard/documentations/release-notes/`)

La section release notes présente l'historique des versions de l'application avec :

- **Liste chronologique** des versions publiées
- **Détails complets** de chaque version
- **Catégorisation** des changements (nouvelles fonctionnalités, corrections, etc.)
- **Navigation par version** avec recherche

## 📁 Organisation de la Documentation

### Structure des dossiers

Organisez vos documents dans le repository GitHub selon cette hiérarchie logique :

```
documentations/
├── index.md                          # 🏠 Page d'accueil
├── guides-utilisateur/               # 👥 Guides pour les utilisateurs finaux
│   ├── index.md                     # Titre : "Guides Utilisateur", Icon: "UserGroupIcon"
│   ├── premiers-pas.md              # Guide de démarrage
│   ├── gestion-contrats.md          # Gestion des contrats
│   └── formation/
│       ├── index.md                 # Titre : "Formation", Icon: "AcademicCapIcon"
│       ├── creation-formation.md    # Créer une formation
│       └── suivi-apprenants.md      # Suivre les apprenants
├── guides-technique/                # 🔧 Documentation technique
│   ├── index.md                     # Titre : "Guides Technique", Icon: "CogIcon"
│   ├── api/
│   │   ├── index.md                 # Titre : "API", Icon: "DocumentTextIcon"
│   │   ├── authentication.md       # Authentification
│   │   ├── endpoints.md             # Points d'entrée
│   │   └── exemples.md              # Exemples d'utilisation
│   ├── deployment/
│   │   ├── index.md                 # Titre : "Déploiement"
│   │   ├── docker.md                # Déploiement Docker
│   │   └── production.md            # Mise en production
│   └── troubleshooting.md           # Résolution de problèmes
└── processus/                       # 📋 Processus métier
    ├── index.md                     # Titre : "Processus", Icon: "ChartBarIcon"
    ├── onboarding.md                # Processus d'accueil
    └── validation.md                # Processus de validation
```

### Règles importantes

1. **Fichiers `index.md`** :
    - ⚠️ **Uniquement pour les titres de dossiers**
    - Ne s'affichent PAS comme des liens dans le menu
    - Définissent le nom affiché du dossier
    - Peuvent définir une icône avec la propriété `icon`

2. **Fichiers de documentation** :
    - Extension `.md` obligatoire
    - Nommage en `kebab-case` (ex: `gestion-contrats.md`)
    - S'affichent comme des liens cliquables dans le menu

## 📝 Format des documents

### Métadonnées obligatoires

Chaque fichier `.md` doit commencer par un bloc de métadonnées YAML :

```markdown
---
title: "Titre affiché dans le menu et en en-tête"
---

# Contenu du document

Votre contenu markdown commence ici...
```

### Métadonnées complètes disponibles

```markdown
---
# 🔵 OBLIGATOIRE
title: "Gestion des Contrats d'Apprentissage"

# 📝 MÉTADONNÉES UTILISABLES
icon: "DocumentTextIcon"                    # Icône pour les dossiers (index.md seulement)
description: "Guide complet pour créer et gérer les contrats d'apprentissage"
date: "2024-01-15"
author: "Marie Dupont"
version: "2.1"
tags: ["contrat", "formation", "guide"]
---

# Votre contenu ici
```

**Métadonnées officielles supportées** :

- `title?: string` - **Obligatoire** - Titre affiché dans le menu
- `icon?: string` - **Nouveau** - Nom de l'icône Heroicons
- `description?: string` - Description du document
- `date?: string` - Date de création/modification
- `author?: string` - Auteur du document
- `tags?: string[]` - Tags pour la recherche (tableau de chaînes)
- `version?: string` - Version du document

**Extensibilité** : L'interface permet d'ajouter des champs personnalisés grâce à `[key: string]: any`

### Métadonnées spécifiques par type de document

#### Pour les guides utilisateur :

```markdown
---
title: "Mon Guide Utilisateur"
description: "Guide d'utilisation pour les utilisateurs finaux"
author: "Équipe Documentation"
icon: "AcademicCapIcon"
tags: ["guide", "tutoriel"]
---
```

#### Pour la documentation technique :

```markdown
---
title: "Documentation API"
description: "Référence complète de l'API"
version: "1.0"
author: "Équipe Technique"
tags: ["api", "technique", "référence"]
---
```

#### Pour les processus métier :

```markdown
---
title: "Processus de Validation"
description: "Workflow de validation des documents"
date: "2024-01-15"
tags: ["processus", "workflow", "validation"]
---
```

## ✍️ Bonnes pratiques de rédaction

### Structure d'un document

1. **Introduction** : Présentation rapide du sujet
2. **Prérequis** : Ce qu'il faut savoir avant de commencer
3. **Étapes** : Guide pas à pas avec captures d'écran et/ou vidéos
4. **Exemples** : Cas d'usage concrets
5. **Dépannage** : Solutions aux problèmes courants
6. **Ressources** : Liens utiles et documentation complémentaire

### Style de rédaction

- **Structure** : Titres hiérarchiques (H1, H2, H3...) avec ancres automatiques
- **Lisibilité** : Paragraphes courts, listes à puces
- **Visuels** : Captures d'écran, vidéos, diagrammes, icônes
- **Navigation** : Liens internes avec composants Next.js optimisés

### Exemple de document bien structuré avec nouvelles fonctionnalités

```markdown
---
title: "Créer un Contrat d'Apprentissage"
description: "Comment créer un contrat d'apprentissage sur Papaours"
version: "2.0.0"
author: "Sebastien Buisine"
tags: ["contrat", "création", "tutoriel", "vidéo"]
---

# Créer un Contrat d'Apprentissage

## 📋 Introduction

Ce guide vous explique comment créer un nouveau contrat d'apprentissage dans l'application Papaours Gestion.

## 🎥 Tutoriel vidéo

<video controls>
  <source src="/videos/tutoriel-formation.webm" type="video/webm" />
  <source src="/videos/tutoriel-formation.mp4" type="video/mp4" />
</video>

## 🎯 Prérequis

Avant de commencer, assurez-vous de :

- Avoir un compte utilisateur actif
- Disposer des droits de création de contrats
- Avoir les informations de l'apprenant et de l'employeur

## 📝 Étapes de création

### 1. Accéder à la page de création

1. Connectez-vous à l'application
2. Allez dans **Contrats** > **Nouveau contrat**
3. Cliquez sur **"Créer un brouillon"**

<img src="/images/interface-creation-contrat.png" alt="Interface de création de contrat" width="800" height="500" />

### 2. Remplir les informations

#### Informations de l'apprenant

<video controls width="600">
  <source src="/videos/saisie-apprenant.webm" type="video/webm" />
  <source src="/videos/saisie-apprenant.mp4" type="video/mp4" />
</video>

- **Nom et prénom** : Saisir les données d'état civil
- **Date de naissance** : Format JJ/MM/AAAA
- **Adresse** : Adresse complète de résidence

#### Informations de l'employeur

- **Raison sociale** : Nom de l'entreprise
- **SIRET** : Numéro d'identification
- **Adresse** : Siège social ou lieu de travail

### 3. Valider et enregistrer

1. Vérifiez tous les champs obligatoires
2. Cliquez sur **"Enregistrer le brouillon"**
3. Le contrat passe en statut "En cours de rédaction"

## ✅ Résultat attendu

Après validation, vous devriez voir :

- Le nouveau contrat dans la liste
- Un statut "En cours de rédaction"
- Un identifiant unique généré

![Alt text](/images/contrat-cree-liste.png "WIDTHxHEIGHT") les tailles ne sont pas obligatoire

## 🔧 Dépannage

### Le bouton "Créer" est grisé

**Cause** : Champs obligatoires manquants  
**Solution** : Vérifier que tous les champs marqués * sont remplis

### Erreur "SIRET invalide"

**Cause** : Format incorrect du numéro SIRET  
**Solution** : Vérifier que le SIRET contient 14 chiffres

## 📚 Ressources complémentaires

- [Guide de validation des contrats](validation-contrats)
- [Gestion des apprenants](gestion-apprenants)
- [FAQ Contrats](faq-contrats)
- [Tutoriel vidéo avancé](tutoriel-contrat-avance)
```

### Sidebar optimisée
- **Mode réduit par défaut** sur les pages de documentation pour maximiser l'espace de lecture

### Navigation améliorée
- **Ancres automatiques** : Tous les titres H1-H4 génèrent des ancres pour les liens directs
- **Liens Next.js optimisés** : Navigation client-side rapide entre les documents

### Support multimédia
- **Composant vidéo natif** : Support HTML5 avec fallbacks multiples
- **Images optimisées** : Compression automatique et formats modernes (WebP, AVIF)

## 🚀 Release Notes - Guide Complet

### Vue d'ensemble

Les release notes sont générées automatiquement depuis les **releases GitHub** du projet. Chaque version publiée sur
GitHub apparaît dans l'interface sous `/dashboard/documentations/release-notes/`.

### Process de publication d'une release

#### 1. Créer une release sur GitHub

1. Allez dans **Releases** sur le repository GitHub
2. Cliquez sur **"Create a new release"**
3. Définissez le **tag version** (ex: `1.2.0`, `2.0.0-beta.1`)
4. Donnez un **titre** à la release (ex: "Version 1.2.0 - Nouvelles fonctionnalités de formation")
5. Rédigez la **description** selon le format recommandé ci-dessous

#### 2. Format recommandé pour les release notes

```markdown
---
title: "Version 1.2.0 - Nouvelles fonctionnalités de formation"
date: "2024-01-15"
version: "1.2.0"
description: "Cette version introduit de nouvelles fonctionnalités pour la gestion des formations"
author: "Équipe de développement"
tags: ["release", "feature", "formation"]
---

## 🎯 Résumé de la version

Cette version introduit de nouvelles fonctionnalités pour la gestion des formations et améliore l'expérience
utilisateur.

**Points clés :**

- Nouveau système de gestion des formations
- Interface utilisateur repensée
- Performances améliorées de 40%

## 🚀 Nouvelles fonctionnalités

### Formation

- **Création de formations personnalisées** : Possibilité de créer des parcours de formation sur mesure
- **Suivi des apprenants en temps réel** : Dashboard avec progression détaillée
- **Notifications automatiques** : Alertes pour les échéances importantes

### Interface utilisateur

- **Nouveau design system** : Interface plus moderne et intuitive
- **Mode sombre** : Disponible dans les paramètres utilisateur
- **Navigation améliorée** : Menu latéral repensé

### API

- **Nouveaux endpoints** : `/api/formations` et `/api/apprenants`
- **Authentification renforcée** : Support OAuth 2.0
- **Documentation interactive** : Swagger UI intégré

## 🐛 Corrections de bugs

### Critiques

- **Correction de la perte de données** lors de la sauvegarde des contrats
- **Résolution du problème de connexion** avec Auth0

### Importantes

- **Navigation** : Correction des liens brisés dans la sidebar
- **Validation** : Amélioration de la validation des formulaires
- **Performance** : Optimisation des requêtes à la base de données

### Mineures

- **Orthographe** : Correction des fautes dans l'interface
- **Affichage** : Alignement des éléments sur mobile
- **Traduction** : Mise à jour des textes en français

## 🔄 Améliorations

### Performance

- **Temps de chargement** réduit de 40% sur la page d'accueil
- **Optimisation** des images et ressources statiques
- **Cache** amélioré pour les données fréquemment consultées

### Accessibilité

- **Contraste** amélioré pour une meilleure lisibilité
- **Navigation au clavier** optimisée
- **Support des lecteurs d'écran** renforcé

### UX/UI

- **Animations** plus fluides lors des transitions
- **Feedback visuel** amélioré pour les actions utilisateur
- **Responsive design** optimisé pour tablettes

## ⚠️ Changements techniques

### API

- **Dépréciation** de l'endpoint `/api/v1/old-contracts` (suppression prévue en v2.0)
- **Nouveaux paramètres requis** pour `/api/formations/create`
- **Format de réponse modifié** pour `/api/users/profile`

### Base de données

- **Nouvelle table** `formation_progress` ajoutée
- **Index ajoutés** sur les tables `contracts` et `users` pour de meilleures performances
- **Migration automatique** lors du déploiement

### Configuration

- **Variables d'environnement** : Ajout de `FORMATION_MODULE_ENABLED`
- **Paramètres** : Nouveaux réglages dans le panneau d'administration

## 📦 Migration et mise à jour

### Pour les administrateurs

1. **Sauvegarde** : Effectuer une sauvegarde complète avant mise à jour
2. **Variables d'environnement** : Ajouter `FORMATION_MODULE_ENABLED=true`
3. **Base de données** : Les migrations se font automatiquement
4. **Cache** : Vider le cache après déploiement

### Pour les utilisateurs

1. **Déconnexion/reconnexion** : Recommandée après la mise à jour
2. **Cache navigateur** : Vider le cache si nécessaire (Ctrl+F5)
3. **Nouvelles fonctionnalités** : Consulter le guide utilisateur mis à jour

### Compatibilité

- **Navigateurs** : Chrome 90+, Firefox 88+, Safari 14+, Edge 90+
- **API** : Rétrocompatible avec la v1.1.x
- **Données** : Migration automatique, pas de perte de données

## 🔗 Ressources

- **Guide de migration** : [Lien vers le guide détaillé]
- **Documentation API** : [Lien vers la doc API]
- **Support** : Contacter l'équipe technique pour toute question
- **Formation** : Sessions de formation disponibles sur demande

## 👥 Contributeurs

Cette version a été développée par :

- **Marie Dupont** - Lead Developer
- **Jean Martin** - Frontend Developer
- **Alice Robert** - Backend Developer
- **Pierre Durand** - UX Designer

**Remerciements spéciaux** à l'équipe QA et aux bêta-testeurs pour leurs retours précieux.

---

**Date de publication** : 15 janvier 2024  
**Prochaine version prévue** : v1.3.0 (février 2024)  
**Support** : Cette version sera supportée jusqu'en janvier 2025
```

### Types de versions

#### Version majeure (ex: v2.0.0)

```markdown
---
title: "Version 2.0.0 - Refonte majeure"
version: "2.0.0"
date: "2024-02-01"
description: "Version majeure avec changements breaking"
author: "Équipe de développement"
tags: ["release", "major", "breaking"]
---

## ⚠️ ATTENTION - Version majeure avec changements breaking

Cette version introduit des changements importants qui nécessitent une migration...
```

#### Version mineure (ex: v1.2.0)

```markdown
---
title: "Version 1.2.0 - Nouvelles fonctionnalités"
version: "1.2.0"
date: "2024-01-15"
description: "Ajout de nouvelles fonctionnalités"
author: "Équipe de développement"
tags: ["release", "feature"]
---

## 🚀 Nouvelles fonctionnalités

Ajout de fonctionnalités sans impact sur l'existant...
```

#### Version de correction (ex: v1.1.1)

```markdown
---
title: "Version 1.1.1 - Corrections critiques"
version: "1.1.1"
date: "2024-01-10"
description: "Correction de bugs urgents"
author: "Équipe de développement"
tags: ["release", "bugfix"]
---

## 🐛 Corrections critiques

Correction de bugs urgents...
```

#### Version hotfix (ex: v1.1.2)

```markdown
---
title: "Version 1.1.2 - Corrections critiques"
version: "1.1.2"
date: "2024-01-10"
description: "Correction de bugs urgents"
author: "Équipe de développement"
tags: ["hotfix", "bugfix"]
---

## 🚨 Correctif de sécurité urgent

Correction d'une faille de sécurité...
```

### Conventions de nommage des versions

- **Format** : `v{major}.{minor}.{patch}[-{pre-release}]`
- **Exemples** :
    - `v1.0.0` (version stable)
    - `v1.2.0-beta.1` (version beta)
    - `v2.0.0-rc.1` (release candidate)
    - `v1.1.1` (correctif)



Pour toute question ou suggestion, contactez l'équipe de documentation à `contact@rtssolutions.fr`
