---
title: "15 - Formatage des devises"
description: "Formater et convertir des montants monétaires dans les templates"
date: "2025-11-20"
version: "1"
---

# Formatage des devises

Formater et convertir des montants monétaires

**FONCTIONNALITÉ COMMUNAUTAIRE** — Disponible pour :
- Plateforme Cloud
- Plateforme On-premise
- Plateforme embarquée (JS) — v2.0+

---

## :formatC(precisionOrFormat, targetCurrency)

Formate une valeur monétaire selon la locale et la devise.

### Paramètres

- `precisionOrFormat` :
  - nombre → nombre de décimales
  - `"L"` → montant avec symbole (par défaut)
  - `"LL"` → nom complet de la devise majeure
  - `"M"` → nom de la devise majeure seule
- `targetCurrency` (optionnel) :
  - code ISO de la devise cible (ex. `EUR`, `USD`)

### Exemples

```text
1000.456:formatC()
1000.456:formatC(2)
1000:formatC('L')
1000:formatC('LL')
1:formatC('M')
1000:formatC('L', 'USD')
```

---

## :convCurr(target, source)

Convertit un montant d’une devise vers une autre.

### Paramètres

- `target` (optionnel) : devise cible
- `source` (optionnel) : devise source

Si aucun paramètre n’est fourni, la conversion utilise :
- `options.currencySource`
- `options.currencyTarget`

Les taux de change sont intégrés par défaut mais peuvent être surchargés via `currencyRates`.

### Exemples

```text
10:convCurr()
1000:convCurr('EUR')
1000:convCurr('USD')
1000:convCurr('USD', 'EUR')
```

---

## Combiner conversion et formatage

Il est courant de combiner les deux formatters :

```text
1000:convCurr('USD'):formatC('L')
```

---

## Bonnes pratiques

- Toujours utiliser des codes ISO 4217 valides
- Définir les devises source et cible dans les options si possible
- Tester le rendu avec plusieurs locales
- Combiner avec `formatN` pour des cas spécifiques

---

---
## Pour aller plus loin

-> [16 - Formatage des dates](16-formatage-des-dates)
