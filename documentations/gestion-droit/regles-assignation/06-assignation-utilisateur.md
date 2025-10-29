---
title: "06 - Assignation utilisateur"
description: "Vue centrée utilisateur : Utilisateur → Rôle et Utilisateur → Groupe"
date: "2025-10-29"
version: "3.0"
---

# 06 - Assignation utilisateur

Un utilisateur peut obtenir des permissions de **deux manières** :

```
Utilisateur
├── Assignation directe : Utilisateur → Rôle
└── Assignation via groupe : Utilisateur → Groupe → Rôles
```

---

## Utilisateur → Rôle

Les **3 règles fondamentales** s'appliquent (voir [Règles générales](03-regles-generales.md)).

### Matrice globale

| Utilisateur (org.) | Rôle CF | Rôle OI | Rôle UF-A |
|--------------------|---------|---------|-----------|
| **Marie (CF)** | ✅ | ❌ | ❌ |
| **Pierre (OI)** | ✅ | ✅ | ❌ |
| **Sophie (UF-A)** | ✅ | ✅ | ✅ |
| **Lucas (UF-B)** | ✅ | ✅ | ❌ |
| **Emma (UF-D)** | ✅ | ❌ | ❌ |

---

### Organisations assignées possibles

| Utilisateur (org.) | Rôle CF | Rôle OI | Rôle UF-A |
|--------------------|---------|---------|-----------|
| **Marie (CF)** | CF, OI, UF-A, UF-B, UF-D | - | - |
| **Pierre (OI)** | OI, UF-A, UF-B | OI, UF-A, UF-B | - |
| **Sophie (UF-A)** | UF-A | UF-A | UF-A |
| **Lucas (UF-B)** | UF-B | UF-B | UF-B |
| **Emma (UF-D)** | UF-D | - | UF-D |

---

## Utilisateur → Groupe

### Règles spécifiques

1. **Héritage automatique** : L'utilisateur hérite de **tous les rôles** du groupe
2. **Validation globale** : Chaque rôle du groupe doit respecter les 3 règles
3. **Interdiction d'auto-assignation** : Un utilisateur ne peut pas s'ajouter lui-même

---

### Matrice Utilisateur → Groupe

| Utilisateur (org.) | Groupe CF | Groupe OI | Groupe UF-A |
|--------------------|-----------|-----------|-------------|
| **Marie (CF)** | ✅ | ❌ | ❌ |
| **Pierre (OI)** | ❌ | ✅ | ❌ |
| **Sophie (UF-A)** | ❌ | ✅* | ✅ |
| **Lucas (UF-B)** | ❌ | ✅* | ❌ |
| **Emma (UF-D)** | ❌ | ❌ | ❌ |

**✅*** : Possible SI les rôles du groupe respectent le périmètre de l'utilisateur

---

## Exemples concrets

### Exemple 1 : Marie (CF) avec rôles directs

**Rôles possibles** :
- ✅ Directeur CF sur CF, OI, UF-A, UF-B, UF-D
- ❌ Responsable Pédago OI (Règle 1 : rôle enfant)
- ❌ Formateur UF-A (Règle 1 : rôle enfant éloigné)

---

### Exemple 2 : Pierre (OI) avec groupe

**Groupe** : Équipe Pédagogique OI
**Rôles du groupe** :
- Responsable Pédago OI sur OI
- Formateur OI sur UF-A
- Formateur OI sur UF-B

**Validation** : ✅ Toutes les règles respectées

**Permissions héritées** :
```
Pierre
└── Via Groupe "Équipe Pédagogique OI"
    ├── Responsable Pédago OI sur OI
    ├── Formateur OI sur UF-A
    └── Formateur OI sur UF-B
```

---

### Exemple 3 : Auto-assignation interdite (Règle T3)

**Situation** : Pierre tente de s'ajouter au groupe "Direction Centre"

| Règle | Vérification | Résultat |
|-------|--------------|----------|
| Règle T3 | Pierre ne s'auto-assigne pas ? | ❌ |
| **RÉSULTAT** | Auto-assignation interdite | **❌ INVALIDE** |

---

### Exemple 4 : Utilisateur dans plusieurs groupes

**Sophie** appartient à :
- Groupe "Formateurs UF-A" → Formateur UF-A sur UF-A
- Groupe "Validation UF-A" → Validateur CF sur UF-A

**Permissions effectives** :
```
Sophie
├── Rôles directs:
│   └── Gestionnaire apprenants sur UF-A
│
└── Via Groupes:
    ├── Formateur UF-A sur UF-A (Groupe "Formateurs UF-A")
    └── Validateur CF sur UF-A (Groupe "Validation UF-A")
```

---

## Tableau récapitulatif complet

### Par utilisateur - Rôles directs possibles

| Utilisateur | Peut recevoir | Organisations assignées |
|-------------|---------------|------------------------|
| Marie (CF) | Rôles CF uniquement | CF, OI, UF-A, UF-B, UF-D |
| Pierre (OI) | Rôles CF, OI | OI, UF-A, UF-B |
| Sophie (UF-A) | Rôles CF, OI, UF-A | UF-A uniquement |
| Lucas (UF-B) | Rôles CF, OI, UF-B | UF-B uniquement |
| Emma (UF-D) | Rôles CF, UF-D | UF-D uniquement |

---

### Par utilisateur - Groupes possibles

| Utilisateur | Groupes possibles | Condition |
|-------------|------------------|-----------|
| Marie (CF) | Groupes CF | Si rôles sur CF ou enfants |
| Pierre (OI) | Groupes OI | Si rôles sur OI ou enfants |
| Sophie (UF-A) | Groupes OI, UF-A | Si rôles sur UF-A uniquement |
| Lucas (UF-B) | Groupes OI, UF-B | Si rôles sur UF-B uniquement |
| Emma (UF-D) | Groupes UF-D | Si rôles sur UF-D uniquement |

---

## Navigation

- [← Assignation de groupe](05-assignation-groupe.md)
- [← Retour à l'index](index.md)
- [Assignation machine →](07-assignation-machine.md)

[Retour à la gestion des droits](../index.md)
