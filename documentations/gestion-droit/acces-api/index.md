---
title: "Gestion des accès API"
description: "Gestion des accès aux APIs en tant que machine"
date: "2025-10-07"
version: "1"
---

# Gestion des machines et des clés API

Cette section de la documentation vous guide dans la gestion des **machines** et des **clés API** pour permettre à vos systèmes automatisés d'accéder à la plateforme Papaours de manière sécurisée.

## Sommaire

1. [Introduction aux machines et clés API](01-introduction-machines-cles-api)
2. [Définition et concepts clés](02-definition-concepts-cles-machines-cles-api)
3. [Gestion des machines](03-gestion-des-machines)
4. [Gestion des clés API](04-gestion-des-cles-api)
5. [Sécurité et bonnes pratiques](05-securite-et-bonnes-pratiques)
6. [Utilisation d'une clé API](06-utilisation-cle-api)

## Démarrage rapide

### Pour créer votre première machine :
1. Accédez à **Gestion des droits > Machines**
2. Cliquez sur **Créer une machine**
3. Définissez le nom, l'organisation et les rôles/groupes
4. Créez une clé API pour cette machine
5. Utilisez la clé API dans vos applications

### Pour utiliser une clé API :
```bash
curl -X GET "https://api.papaours.fr/v1/contrats" \
  -H "X-API-KEY: votre_cle_api_ici" \
  -H "Content-Type: application/json"
```

[Retour à l'Accueil](../accueil)