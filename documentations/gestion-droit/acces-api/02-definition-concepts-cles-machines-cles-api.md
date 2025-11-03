---
title: "02 - Définition et concepts clés"
description: "Comprendre la différence entre machines et clés API dans Papaours"
date: "2025-10-07"
version: "1"
---

## Comprendre les machines et clés API

Avant de commencer la gestion des clés API, il est essentiel de comprendre la distinction entre une **machine** et une
**clé API**, ainsi que leur rôle respectif dans la sécurité et l'authentification au sein de la plateforme Papaours.

### Qu'est-ce qu'une machine ?

Une **machine** représente une entité système (serveur, application, service automatisé) qui a besoin d'accéder aux
ressources de la plateforme Papaours de manière programmatique.

**La machine définit les autorisations** :

- Elle possède des **rôles** et des **groupes** qui déterminent ce qu'elle peut faire sur la plateforme via des droits
  d'accès.
- Ces droits d'accès fonctionnent de la même manière que pour un utilisateur humain.
- Une machine est liée à **une seule organisation de rattachement** choisie à la création ou à la modification.
- Les rôles et groupes assignés peuvent avoir un périmètre multi-organisations, mais **les droits d'accès ne sont effectifs que si l'organisation de rattachement de la machine est incluse dans le périmètre** de ces rôles/groupes.
- C'est l'**identité fonctionnelle** qui porte les droits d'accès.

**Exemple** : Une machine "Service de facturation" pourrait avoir les permissions de lecture sur les contrats et
d'écriture sur les factures, mais aucun accès aux données de formation.

![Detail d'une machine](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/02/Detail%20d%27une%20machine.png)

### Qu'est-ce qu'une clé API ?

Une **clé API** est un **identifiant technique** qui permet d'authentifier la machine auprès de la plateforme Papaours
lors de ses appels API.

**La clé API assure l'identification** :

- C'est le **secret d'authentification** qui prouve l'identité de la machine.
- Une clé API est toujours rattachée à une machine spécifique.
- Elle hérite automatiquement de toutes les permissions de la machine à laquelle elle appartient.
- C'est l'équivalent d'un couple login/mot de passe pour une machine.

**Exemple** : La machine "Service de facturation" peut avoir plusieurs clés API :

- `Clé production` utilisée par le serveur de production
- `Clé test` utilisée par l'environnement de test
- `Clé développement` utilisée par les développeurs en local

![Liste cle api](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/02/Liste%20cle%CC%81%20api.png)

### Relation entre machine et clés API

Une **machine** est l'entité qui porte les droits d'accès, tandis que les **clés API** sont les identifiants techniques qui permettent d'utiliser ces droits.

**Fonctionnement** :
- Une machine peut posséder **plusieurs clés API**
- Chaque clé API hérite automatiquement de **tous les droits d'accès** de sa machine
- Toutes les clés d'une même machine ont donc exactement les **mêmes permissions**

**Exemple concret** :
La machine "Service Facturation" (rattachée au CFA Jean Bosco) possède les droits suivants via ses rôles/groupes :
- ✓ Lire les contrats
- ✓ Écrire les factures
- ✗ Accéder aux formations

Cette machine peut avoir deux clés API :
- **Clé "Production"** → utilisée par le serveur de production → mêmes droits que la machine
- **Clé "Test"** → utilisée par l'environnement de test → mêmes droits que la machine

Les deux clés donneront exactement les mêmes permissions, car elles appartiennent à la même machine.

### Pourquoi plusieurs clés API pour une même machine ?

La possibilité de créer plusieurs clés API pour une seule machine offre plusieurs avantages :

1. **Séparation des environnements** : Une clé pour la production, une autre pour le test, une autre pour le
   développement.

2. **Rotation de sécurité** : Permet de renouveler les clés sans interruption de service :
    - Créer une nouvelle clé
    - Mettre à jour progressivement les systèmes
    - Désactiver l'ancienne clé une fois la migration terminée

3. **Gestion des accès par service** : Si plusieurs applications différentes utilisent la même machine, chacune peut
   avoir sa propre clé pour faciliter le suivi et la révocation.

4. **Audit et traçabilité** : Chaque clé peut être nommée de manière explicite pour identifier son usage dans les logs.

### Analogie avec les utilisateurs humains

Pour mieux comprendre cette distinction, voici une analogie avec les utilisateurs humains :

| Concept              | Utilisateur humain                   | Machine                       |
|----------------------|--------------------------------------|-------------------------------|
| **Identité**         | Compte utilisateur (Jean Dupont)     | Machine (Service Facturation) |
| **Permissions**      | Rôles et droits attribués            | Rôles et droits attribués     |
| **Authentification** | Login + Mot de passe                 | Clé API                       |
| **Multi-sessions**   | Connexion depuis plusieurs appareils | Plusieurs clés API            |

Tout comme un utilisateur peut se connecter depuis son ordinateur de bureau, son laptop et son téléphone avec le même
compte (et donc les mêmes permissions), une machine peut avoir plusieurs clés API qui partagent toutes les mêmes
autorisations.

### Points clés à retenir

> 🔑 **Machine = Autorisations** : La machine définit **CE QUE** le système peut faire via les rôles et groupes qui lui sont assignés, générant des droits d'accès (combinaison de permission + opération + organisations).

> 🔐 **Clé API = Identification** : La clé API prouve **QUI** fait la requête (authentification).

> 🏢 **Organisation de rattachement** : Une machine appartient à **une seule organisation**. Les droits d'accès issus des rôles/groupes ne sont effectifs que si cette organisation est incluse dans leur périmètre.

> ⚠️ **Une clé compromise = droits d'accès compromis** : Si une clé API est volée, l'attaquant obtient tous les droits d'accès de la machine associée. D'où l'importance de bien sécuriser les clés et de les renouveler régulièrement.

---

### Pour aller plus loin

- [Créer une machine →](03-gestion-des-machines)
- [Générer une clé API →](04-gestion-des-cles-api)
- [Utiliser une clé API dans votre code →](06-utilisation-cle-api)

[Retour à l'Accueil](../../accueil)
