---
title: "08 - Processus d'approbation des unités de formation"
description: ""
date: "2025-09-01"
version: "1"
---

### Table des matières
1. [Principe du processus d'approbation](#principe-du-processus-dapprobation)
2. [États et workflow](#états-et-workflow)
3. [Accéder au module d'approbation](#accéder-au-module-dapprobation)
4. [Traitement des approbations individuelles](#traitement-des-approbations-individuelles)
5. [Approbations par lot](#approbations-par-lot)
6. [Gestion des rejets et corrections](#gestion-des-rejets-et-corrections)
7. [Suivi et reporting](#suivi-et-reporting)

---

## Principe du processus d'approbation

### Objectif
Le processus d'approbation garantit la qualité et la conformité des unités de formation avant leur mise en service. Il permet un contrôle qualité systématique et une validation métier des informations saisies.

### Acteurs du processus

**Créateurs/Modificateurs**
- **Gestionnaires de formation** : Saisie initiale des unités
- **Administrateurs fonctionnels** : Modifications et corrections
- **Utilisateurs métier** : Compléments d'informations

![Acteurs création](placeholder-acteurs-creation.png "Rôles de saisie")

**Approbateurs**
- **Responsables qualité** : Validation des conformités
- **Administrateurs système** : Contrôle technique
- **Référents métier** : Validation fonctionnelle

![Acteurs approbation](placeholder-acteurs-approbation.png "Rôles de validation")

### Déclenchement
L'approbation est requise dans les cas suivants :
- **Création** d'une nouvelle unité de formation
- **Modification majeure** d'une unité existante
- **Changement de statut** critique (réactivation)
- **Demande explicite** d'un gestionnaire

![Déclenchement approbation](placeholder-declenchement-approbation.png "Conditions d'entrée")

---

## États et workflow

### États d'approbation

**À compléter**
- **Données insuffisantes** : Champs obligatoires manquants
- **Informations incomplètes** : Détails nécessaires absents
- **Documentation manquante** : Pièces justificatives non fournies

![État à compléter](placeholder-etat-completer.png "Données insuffisantes")

**À corriger**
- **Erreurs détectées** : Incohérences dans les données
- **Format incorrect** : Non-respect des contraintes
- **Informations contradictoires** : Conflits entre champs

![État à corriger](placeholder-etat-corriger.png "Corrections nécessaires")

**À valider**
- **Données complètes** : Tous les champs requis renseignés
- **Conformité technique** : Formats respectés
- **Prêt pour validation** : En attente d'approbation finale

![État à valider](placeholder-etat-valider.png "Prêt pour validation")

**Validée**
- **Approbation accordée** : Unité validée par un approbateur
- **Mise en service** : Activation automatique de l'unité
- **Intégration complète** : Disponible dans tous les modules

![État validée](placeholder-etat-validee.png "Approbation accordée")

**Refusée**
- **Non-conformité majeure** : Problèmes bloquants identifiés
- **Critères non respectés** : Standards qualité non atteints
- **Décision de rejet** : Approbation explicitement refusée

![État refusée](placeholder-etat-refusee.png "Approbation refusée")

### Workflow de traitement

```mermaid
flowchart TD
    A[Création/Modification] --> B[À compléter]
    B --> C[Complément d'informations]
    C --> D[À corriger]
    D --> E[Corrections apportées]
    E --> F[À valider]
    F --> G{Décision approbateur}
    G -->|Approuve| H[Validée]
    G -->|Rejette| I[Refusée]
    G -->|Corrections nécessaires| D
    I --> J[Nouvelle soumission]
    J --> B
```

![Workflow approbation](placeholder-workflow-approbation.png "Flux de traitement")

---

## Accéder au module d'approbation

### Navigation principale
Le module d'approbation est accessible via :
- **Menu "Formation"** > **"Unités de Formation"** > **"Approbations"**
- **Onglet "Approbations"** depuis la liste des unités
- **Notifications** directes d'éléments en attente

![Navigation approbation](placeholder-navigation-approbation.png "Accès au module")

### Permissions requises
Pour accéder aux approbations :
- **"Consultation des approbations"** : Vue d'ensemble et détails
- **"Approbation des unités de formation"** : Actions de validation/rejet
- **Périmètre approprié** : Accès aux unités concernées

![Permissions approbation](placeholder-permissions-approbation.png "Contrôles d'accès")

### Vue d'ensemble

**Tableau de bord des approbations**
- **Compteurs par statut** : Nombre d'unités dans chaque état
- **Répartition temporelle** : Évolution des volumes
- **Alertes de délai** : Approbations en retard
- **Assignations** : Répartition par approbateur

![Dashboard approbations](placeholder-dashboard-approbations.png "Vue synthétique")

**Liste des unités en attente**
Organisation par colonnes :
- **Dénomination** : Nom de l'unité concernée
- **Statut** : État actuel dans le workflow
- **Date de soumission** : Ancienneté de la demande
- **Approbateur assigné** : Responsable du traitement
- **Priorité** : Niveau d'urgence

![Liste attente approbation](placeholder-liste-attente-approbation.png "Unités à traiter")

---

## Traitement des approbations individuelles

### Consultation d'une unité en attente

**Accès au détail**
- Cliquez sur l'unité dans la liste d'approbation
- **Vue spécialisée** avec focus sur les éléments à valider
- **Comparaison** avec la version précédente si modification

![Détail unité approbation](placeholder-detail-unite-approbation.png "Vue d'approbation")

**Informations spécifiques**
- **Historique des modifications** : Changements apportés
- **Commentaires** des versions précédentes
- **Points de vigilance** : Éléments nécessitant attention
- **Pièces justificatives** : Documents associés

![Infos spécifiques approbation](placeholder-infos-specifiques-approbation.png "Données de validation")

### Actions d'approbation

**Approuver l'unité**
1. **Vérification complète** : Contrôle de tous les éléments
2. **Validation métier** : Conformité aux standards
3. **Commentaire d'approbation** : Justification de la décision
4. **Confirmation** : Validation définitive

![Action approuver](placeholder-action-approuver.png "Processus d'approbation")

**Demander des corrections**
1. **Identification des problèmes** : Liste détaillée des points
2. **Catégorisation** : Bloquant, Amélioration, Information
3. **Instructions précises** : Explications pour les corrections
4. **Délai de correction** : Temps imparti pour les modifications

![Demander corrections](placeholder-demander-corrections.png "Retour pour correction")

**Refuser l'unité**
1. **Motifs de refus** : Raisons détaillées du rejet
2. **Références** : Standards ou règles non respectés
3. **Recommandations** : Pistes d'amélioration pour l'avenir
4. **Confirmation explicite** : Validation du refus définitif

![Action refuser](placeholder-action-refuser.png "Processus de rejet")

### Outils d'aide à la décision

**Check-list de validation**
- ✅ **Informations légales** : SIRET, dénomination, forme juridique
- ✅ **Données fiscales** : TVA, numéros officiels
- ✅ **Cohérence métier** : Secteur d'activité, formations proposées
- ✅ **Moyens de contact** : Accessibilité et validité
- ✅ **Lieux de formation** : Adresses et capacités réalistes

![Check-list validation](placeholder-checklist-validation.png "Points de contrôle")

**Référentiels de contrôle**
- **Base SIRET** : Vérification de l'existence et statut
- **Registres professionnels** : Validité des habilitations
- **Standards qualité** : Conformité aux exigences sectorielles
- **Règles internes** : Respect des procédures de l'organisation

![Référentiels contrôle](placeholder-referentiels-controle.png "Sources de vérification")

---

## Approbations par lot

### Sélection des unités

**Critères de groupement**
Traitement simultané possible pour :
- **Même type de problème** : Corrections similaires
- **Même créateur** : Unités saisies par la même personne
- **Même période** : Soumissions groupées
- **Même nature** : Organismes du même secteur

![Critères groupement](placeholder-criteres-groupement.png "Logique de lot")

**Interface de sélection**
- **Cases à cocher** : Sélection multiple dans la liste
- **Filtres avancés** : Critères de regroupement
- **Aperçu du lot** : Récapitulatif des unités sélectionnées
- **Vérification** : Contrôle de compatibilité

![Interface sélection lot](placeholder-interface-selection-lot.png "Sélection groupée")

### Actions par lot

**Approbation massive**
- **Pré-contrôles** : Vérification automatique de chaque unité
- **Validation globale** : Commentaire unique pour le lot
- **Traitement séquentiel** : Approbation une par une
- **Rapport de résultats** : Succès et échecs détaillés

![Approbation massive](placeholder-approbation-massive.png "Traitement groupé")

**Demande de corrections groupée**
- **Problème commun** : Même type de correction pour toutes
- **Instructions standardisées** : Message uniforme
- **Assignation** : Retour vers les créateurs respectifs
- **Suivi unifié** : Monitoring des corrections

![Corrections groupées](placeholder-corrections-groupees.png "Retours collectifs")

**Rejet par lot**
- **Motifs partagés** : Problèmes similaires identifiés
- **Documentation** : Justifications détaillées
- **Communication** : Notification aux parties prenantes
- **Archivage** : Conservation des décisions

![Rejet par lot](placeholder-rejet-par-lot.png "Refus collectifs")

### Gestion des exceptions
Dans un lot, traitement spécifique pour :
- **Unités non conformes** : Exclusion du traitement global
- **Cas particuliers** : Nécessitant une analyse individuelle
- **Problèmes techniques** : Erreurs système lors du traitement
- **Conflits de permissions** : Droits insuffisants sur certaines unités

![Gestion exceptions](placeholder-gestion-exceptions.png "Cas spéciaux")

---

## Gestion des rejets et corrections

### Traitement des unités refusées

**Communication du refus**
- **Notification automatique** : Email au créateur
- **Détail des motifs** : Explications précises des problèmes
- **Références** : Standards et règles applicables
- **Contact** : Coordonnées de l'approbateur pour clarifications

![Communication refus](placeholder-communication-refus.png "Information du créateur")

**Options post-refus**
- **Nouvelle soumission** : Correction et resoumission possible
- **Abandon** : Archivage de la demande
- **Escalade** : Remontée vers un niveau supérieur
- **Expertise externe** : Conseil spécialisé si nécessaire

![Options post-refus](placeholder-options-post-refus.png "Suite du processus")

### Corrections demandées

**Notification des corrections**
- **Liste détaillée** : Points à corriger avec priorités
- **Exemples** : Illustrations des bonnes pratiques
- **Délai** : Temps imparti pour les modifications
- **Assistance** : Contact pour aide si nécessaire

![Notification corrections](placeholder-notification-corrections.png "Guide de correction")

**Suivi des corrections**
- **Statut en temps réel** : Avancement des modifications
- **Alertes de délai** : Rappels avant échéance
- **Validation intermédiaire** : Contrôle partiel des corrections
- **Resoumission** : Nouveau cycle d'approbation

![Suivi corrections](placeholder-suivi-corrections.png "Monitoring des modifications")

### Escalade et résolution de conflits

**Procédure d'escalade**
En cas de désaccord :
1. **Dialogue direct** : Discussion entre créateur et approbateur
2. **Médiation** : Intervention d'un référent métier
3. **Arbitrage** : Décision d'un responsable hiérarchique
4. **Commission** : Examen collégial si nécessaire

![Procédure escalade](placeholder-procedure-escalade.png "Résolution de conflits")

**Documentation des décisions**
- **Historique complet** : Toutes les interactions documentées
- **Justifications** : Raisons détaillées de chaque décision
- **Précédents** : Constitution d'une base de référence
- **Amélioration continue** : Évolution des critères

![Documentation décisions](placeholder-documentation-decisions.png "Traçabilité complète")

---

## Suivi et reporting

### Métriques d'activité

**Indicateurs de performance**
- **Délai moyen d'approbation** : Temps de traitement par statut
- **Taux d'approbation** : Pourcentage de validations directes
- **Volume mensuel** : Évolution du nombre de demandes
- **Répartition par approbateur** : Charge de travail individuelle

![Métriques performance](placeholder-metriques-performance.png "Indicateurs clés")

**Tableaux de bord**
- **Vue temps réel** : Situation actuelle des approbations
- **Tendances** : Évolution sur plusieurs mois
- **Comparaisons** : Benchmarks avec périodes précédentes
- **Prévisions** : Charge de travail anticipée

![Tableaux de bord](placeholder-tableaux-de-bord.png "Vues synthétiques")

### Rapports de qualité

**Analyse des rejets**
- **Motifs récurrents** : Causes principales de refus
- **Organismes concernés** : Profils des unités rejetées
- **Actions préventives** : Mesures d'amélioration suggérées
- **Formation** : Besoins identifiés pour les créateurs

![Analyse rejets](placeholder-analyse-rejets.png "Étude des problèmes")

**Conformité globale**
- **Taux de conformité** : Evolution de la qualité générale
- **Standards respectés** : Niveau d'adhésion aux exigences
- **Points d'amélioration** : Axes de progression identifiés
- **Bonnes pratiques** : Exemples de réussites à diffuser

![Conformité globale](placeholder-conformite-globale.png "Qualité d'ensemble")

### Optimisation du processus

**Amélioration continue**
- **Feedback des utilisateurs** : Retours créateurs et approbateurs
- **Simplification** : Réduction des étapes non nécessaires
- **Automatisation** : Contrôles techniques automatisés
- **Formation** : Montée en compétence des acteurs

![Amélioration continue](placeholder-amelioration-continue.png "Evolution du processus")

**Évolution des critères**
- **Adaptation métier** : Prise en compte des évolutions sectorielles
- **Retours terrain** : Intégration de l'expérience utilisateur
- **Conformité réglementaire** : Mise à jour selon la législation
- **Benchmark externe** : Comparaison avec les meilleures pratiques

![Évolution critères](placeholder-evolution-criteres.png "Adaptation des standards")

### Pour aller plus loin
-> [09 - Bonnes pratiques et cas d'usage](09-bonnes-pratiques)