---
title: "Assignation machine"
description: "Vue centrée machine : Machine → Rôle et Machine → Groupe"
date: "2025-10-29"
version: "3.0"
---

# Assignation machine

Une **machine** représente un système automatisé accédant à l'API Papaours.

**Caractéristiques** :
- Possède une **organisation responsable** unique
- S'authentifie via une ou plusieurs **clés API**
- Peut avoir plusieurs **rôles** (directs ou via groupes)

---

## Types de machine

### Machine système (administrée par Papaours)

**Exemple** : `Administrateur Papaours` (machine système)

**Restrictions** :
- ❌ Non modifiable
- ❌ Rôles non modifiables
- ❌ Clés API non modifiables
- ❌ Non supprimable
- ✅ Gérée uniquement par Papaours

---

### Machine CFA (créée par le centre)

**Exemples** : `Machine API Export Centre`, `Machine API Pédagogie OI`

**Permissions** :
- ✅ Modifiable
- ✅ Rôles modifiables
- ✅ Clés API modifiables
- ✅ Supprimable

---

## Machine → Rôle

Les **mêmes règles** que pour [Utilisateur → Rôle](06-assignation-utilisateur.md#utilisateur--rôle) s'appliquent.

**+ Règle T4** : Les machines système ne peuvent pas être modifiées

### Matrice globale

| Machine (org.) | Rôle CF | Rôle OI | Rôle UF-A |
|----------------|---------|---------|-----------|
| **Machine CF** | ✅ | ❌ | ❌ |
| **Machine OI** | ✅ | ✅ | ❌ |
| **Machine UF-A** | ✅ | ✅ | ✅ |
| **Machine Système** | ❌ | ❌ | ❌ |

---

## Machine → Groupe

Les **mêmes règles** que pour [Utilisateur → Groupe](06-assignation-utilisateur.md#utilisateur--groupe) s'appliquent.

**+ Règle T4** : Les machines système ne peuvent pas être ajoutées à des groupes

---

## Exemples concrets

### Exemple 1 : Machine API Export Centre (CF)

**Organisation responsable** : Centre Formation (CF)
**Type** : Machine CFA
**Clé API** : `pk_prod_cf_export_xxxxx`

**Rôles possibles** :
- ✅ Lecteur CF sur CF, OI, UF-A, UF-B, UF-D
- ❌ Lecteur OI (Règle 1 : rôle enfant)

**Cas concret** :
```
Machine CF → Rôle "Lecteur CF" sur CF ✅
Machine CF → Rôle "Lecteur CF" sur OI ✅
Machine CF → Rôle "Lecteur OI" sur OI ❌ (Règle 1)
```

---

### Exemple 2 : Machine API Pédagogie OI (OI)

**Organisation responsable** : Org. Intermédiaire (OI)
**Type** : Machine CFA
**Clé API** : `pk_prod_oi_pedagogie_xxxxx`

**Rôles possibles** :
- ✅ Lecteur CF sur OI, UF-A, UF-B
- ✅ Gestionnaire Pédago OI sur OI, UF-A, UF-B
- ❌ Sur CF (Règle 2 : hors périmètre)

**Groupe possible** :
- ✅ Groupe "API Pédagogie OI" avec rôles sur OI et enfants

---

### Exemple 3 : Machine système (Règle T4)

**Machine** : Administrateur Papaours (machine système)
**Type** : Machine Système

| Action | Résultat | Raison |
|--------|----------|--------|
| Ajouter un rôle | ❌ | Règle T4 : Machine système |
| Modifier un rôle | ❌ | Règle T4 : Machine système |
| Ajouter à un groupe | ❌ | Règle T4 : Machine système |
| Modifier clé API | ❌ | Règle T4 : Machine système |

---

## Gestion des clés API

### Format des clés

```
pk_{environnement}_{usage}_{random}
```

**Exemples** :
- `pk_prod_export_a1b2c3d4e5f6` (Production)
- `pk_test_consultation_x9y8z7w6v5u4` (Test)

---

### Sécurité

✅ **À FAIRE** :
- Stocker les clés de manière sécurisée (variables d'environnement)
- Utiliser des clés de test pour le développement
- Révoquer immédiatement une clé compromise

❌ **À NE PAS FAIRE** :
- Commiter les clés dans Git
- Partager les clés par email
- Utiliser la même clé pour différents environnements

---

### Permissions héritées

Les clés API d'une machine héritent de **toutes les permissions** de la machine.

**Exemple** :
```
Machine API Export Centre
├── Clé API: pk_prod_export_xxxxx
│   └── Hérite de:
│       ├── Lecteur CF sur CF
│       ├── Lecteur CF sur OI
│       └── Export CF sur CF
│
└── Clé API: pk_test_export_yyyyy
    └── Hérite des mêmes permissions (environnement test)
```

---

## Comparaison Utilisateur vs Machine

| Aspect | Utilisateur | Machine |
|--------|-------------|---------|
| **Authentification** | Mot de passe | Clé API |
| **Rôles directs** | ✅ | ✅ |
| **Groupes** | ✅ | ✅ |
| **3 règles fondamentales** | ✅ | ✅ |
| **Auto-assignation** | ❌ (Règle T3) | N/A |
| **Entités système** | ❌ | ✅ (Règle T4) |
| **Usage** | Manuel (humain) | Automatisé |

---

## Documentation API

Pour plus de détails :
- [Gestion des machines →](../acces-api/03-gestion-des-machines.md)
- [Gestion des clés API →](../acces-api/04-gestion-des-cles-api.md)
- [Sécurité et bonnes pratiques →](../acces-api/05-securite-et-bonnes-pratiques.md)

---

## Navigation

- [← Assignation utilisateur](06-assignation-utilisateur.md)
- [← Retour à l'index](index.md)

[Retour à la gestion des droits](../index.md)
