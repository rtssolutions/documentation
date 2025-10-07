---
title: "06 - Utilisation d'une clé API"
description: "Comment utiliser une clé API pour accéder aux services Papaours"
date: "2025-10-07"
version: "1"
---

## 📚 Table des matières

1. [Authentification via clé API](#authentification-via-clé-api)
2. [Format de la requête](#format-de-la-requête)
3. [Exemples de code](#exemples-de-code)
4. [Gestion des erreurs](#gestion-des-erreurs)
5. [Bonnes pratiques d'utilisation](#bonnes-pratiques-dutilisation)

---

## Authentification via clé API

Pour accéder aux services de la plateforme Papaours de manière programmatique, vous devez authentifier votre machine en utilisant une clé API générée pour celle-ci.

### Prérequis

Avant d'utiliser une clé API, assurez-vous que :
- Une **machine** a été créée avec les rôles et groupes appropriés
- Une **clé API** a été générée pour cette machine
- La clé API est **active**
- L'organisation de rattachement de la machine est incluse dans le périmètre des rôles/groupes assignés

---

## Format de la requête

Pour authentifier vos appels API, vous devez inclure votre clé API dans le **header HTTP** de chaque requête.

### Header d'authentification

```
X-API-KEY: votre_cle_api_ici
```

### Format complet d'une requête

```http
GET /v1/contrats HTTP/1.1
Host: api.papaours.fr
X-API-KEY: pk_prod_abc123def456ghi789
Content-Type: application/json
```

> ⚠️ **Important** : Le header doit être nommé exactement `X-API-KEY` (sensible à la casse).

---

## Exemples de code

Voici des exemples concrets d'utilisation de votre clé API dans différents langages de programmation.

### JavaScript / Node.js

#### Avec fetch (native)

```javascript
const API_KEY = process.env.PAPAOURS_API_KEY;

async function recupererContrats() {
  try {
    const response = await fetch('https://api.papaours.fr/v1/contrats', {
      method: 'GET',
      headers: {
        'X-API-KEY': API_KEY,
        'Content-Type': 'application/json'
      }
    });

    if (!response.ok) {
      throw new Error(`Erreur HTTP: ${response.status}`);
    }

    const data = await response.json();
    console.log('Contrats récupérés:', data);
    return data;
  } catch (error) {
    console.error('Erreur lors de la récupération des contrats:', error);
    throw error;
  }
}
```

#### Avec axios

```javascript
const axios = require('axios');

const api = axios.create({
  baseURL: 'https://api.papaours.fr/v1',
  headers: {
    'X-API-KEY': process.env.PAPAOURS_API_KEY,
    'Content-Type': 'application/json'
  }
});

// Récupérer des contrats
api.get('/contrats')
  .then(response => {
    console.log('Contrats:', response.data);
  })
  .catch(error => {
    console.error('Erreur:', error.response?.data || error.message);
  });

// Créer une facture
api.post('/factures', {
  contratId: 'abc-123',
  montant: 1500.00,
  dateEmission: '2025-10-01'
})
  .then(response => {
    console.log('Facture créée:', response.data);
  })
  .catch(error => {
    console.error('Erreur:', error.response?.data || error.message);
  });
```

---

### Python

#### Avec requests

```python
import os
import requests

API_KEY = os.environ.get('PAPAOURS_API_KEY')
BASE_URL = 'https://api.papaours.fr/v1'

headers = {
    'X-API-KEY': API_KEY,
    'Content-Type': 'application/json'
}

# Récupérer des contrats
def recuperer_contrats():
    try:
        response = requests.get(
            f'{BASE_URL}/contrats',
            headers=headers
        )
        response.raise_for_status()
        contrats = response.json()
        print('Contrats récupérés:', contrats)
        return contrats
    except requests.exceptions.HTTPError as error:
        print(f'Erreur HTTP: {error}')
        raise
    except Exception as error:
        print(f'Erreur: {error}')
        raise

# Créer une facture
def creer_facture(contrat_id, montant, date_emission):
    try:
        response = requests.post(
            f'{BASE_URL}/factures',
            headers=headers,
            json={
                'contratId': contrat_id,
                'montant': montant,
                'dateEmission': date_emission
            }
        )
        response.raise_for_status()
        facture = response.json()
        print('Facture créée:', facture)
        return facture
    except requests.exceptions.HTTPError as error:
        print(f'Erreur HTTP: {error}')
        print(f'Détails: {error.response.text}')
        raise
```

---

### Java / Kotlin

#### Avec Spring WebClient (Kotlin)

```kotlin
import org.springframework.http.HttpHeaders
import org.springframework.web.reactive.function.client.WebClient
import org.springframework.web.reactive.function.client.awaitBody

class PapaoursApiClient(
    private val apiKey: String
) {
    private val webClient = WebClient.builder()
        .baseUrl("https://api.papaours.fr/v1")
        .defaultHeader("X-API-KEY", apiKey)
        .defaultHeader(HttpHeaders.CONTENT_TYPE, "application/json")
        .build()

    suspend fun recupererContrats(): List<Contrat> {
        return webClient.get()
            .uri("/contrats")
            .retrieve()
            .awaitBody()
    }

    suspend fun creerFacture(facture: CreerFactureRequest): Facture {
        return webClient.post()
            .uri("/factures")
            .bodyValue(facture)
            .retrieve()
            .awaitBody()
    }
}

// Utilisation
val apiKey = System.getenv("PAPAOURS_API_KEY")
val client = PapaoursApiClient(apiKey)

// Récupérer les contrats
val contrats = client.recupererContrats()
println("Contrats récupérés: $contrats")

// Créer une facture
val facture = client.creerFacture(
    CreerFactureRequest(
        contratId = "abc-123",
        montant = 1500.00,
        dateEmission = "2025-10-01"
    )
)
println("Facture créée: $facture")
```

---

### cURL (ligne de commande)

```bash
# Récupérer des contrats
curl -X GET "https://api.papaours.fr/v1/contrats" \
  -H "X-API-KEY: pk_prod_abc123def456ghi789" \
  -H "Content-Type: application/json"

# Créer une facture
curl -X POST "https://api.papaours.fr/v1/factures" \
  -H "X-API-KEY: pk_prod_abc123def456ghi789" \
  -H "Content-Type: application/json" \
  -d '{
    "contratId": "abc-123",
    "montant": 1500.00,
    "dateEmission": "2025-10-01"
  }'
```

---

## Gestion des erreurs

Voici les codes d'erreur courants que vous pourriez rencontrer lors de l'utilisation d'une clé API :

### Code 401 - Non autorisé

**Causes possibles :**
- Clé API invalide ou incorrecte
- Clé API désactivée
- Header `X-API-KEY` manquant ou mal formé
- Clé API associée à une machine inactive

**Solutions :**
- Vérifiez que la clé API est correcte (pas de caractères manquants/en trop)
- Vérifiez que la clé API est active dans l'interface Papaours
- Assurez-vous que le header `X-API-KEY` est bien présent dans la requête
- Vérifiez que la machine associée à la clé est active

---

### Code 403 - Accès refusé

**Causes possibles :**
- La machine n'a pas les droits d'accès nécessaires pour cette ressource
- L'organisation de rattachement de la machine n'est pas dans le périmètre des rôles/groupes
- L'opération demandée (lecture, écriture, suppression) n'est pas autorisée

**Solutions :**
- Vérifiez les rôles et groupes assignés à la machine
- Assurez-vous que l'organisation de rattachement de la machine est incluse dans le périmètre des rôles/groupes
- Vérifiez que les rôles associés contiennent les bonnes permissions
- Contactez un administrateur de droits d'accès pour vous assister dans la modification des droits de la machine si nécessaire

---

### Code 404 - Ressource non trouvée

**Causes possibles :**
- L'URL de l'endpoint est incorrecte
- La ressource demandée n'existe pas
- L'ID de la ressource est invalide


**Solutions :**
- Vérifiez l'URL de l'endpoint dans la documentation de l'API
- Vérifiez que l'ID de la ressource existe bien
- Assurez-vous que vous avez les droits de lecture sur cette ressource

---

### Code 500 - Erreur serveur

**Causes possibles :**
- Erreur interne du serveur Papaours
- Problème temporaire de disponibilité

**Solutions :**
- Réessayez la requête après quelques secondes
- Si le problème persiste, contactez le support Papaours

---

## Ressources complémentaires

- [Documentation de l'API Papaours](https://api.papaours.fr/swagger-ui)
- [Créer une machine →](03-gestion-des-machines.md)
- [Créer une clé API →](04-gestion-des-cles-api.md)
- [Sécurité et bonnes pratiques →](05-securite-et-bonnes-pratiques.md)

---

### Pour aller plus loin

- [Retour à la gestion des machines →](03-gestion-des-machines.md)
- [Retour à la gestion des clés API →](04-gestion-des-cles-api.md)
- [Bonnes pratiques de sécurité →](05-securite-et-bonnes-pratiques.md)
- [Comprendre les concepts →](02-definition-concepts-cles-machines-cles-api.md)

---

## Support

Si vous rencontrez des difficultés lors de l'utilisation de votre clé API :

1. Vérifiez que tous les prérequis sont remplis
2. Contactez le support technique Papaours

[Retour à l'Accueil](../accueil)
