---
title: "07 - Suppression d'une unité de formation"
description: ""
date: "2025-09-01"
version: "1"
---

### Table des matières
1. [Prérequis et permissions](#prérequis-et-permissions)
2. [Vérifications préalables](#vérifications-préalables)
3. [Processus de suppression](#processus-de-suppression)
4. [Impact sur les éléments liés](#impact-sur-les-éléments-liés)
5. [Suppression définitive vs archivage](#suppression-définitive-vs-archivage)
6. [Restauration d'une unité supprimée](#restauration-dune-unité-supprimée)

---

## Prérequis et permissions

### Permissions requises
La suppression d'une unité de formation est une action critique qui nécessite le role **d'administrateur de centre de formation**

### Restrictions d'accès
La suppression est **bloquée** et non affiché dans les écrans dans certains cas :
- **Utilisateur standard** : Pas d'accès à cette fonction
- **Actions de formation associées** : Il faut d'abord les supprimer manuellement

---

## Processus de suppression

### Accès à la suppression
Pour supprimer une unité de formation :

**Depuis la fiche détaillée**
- Cliquez sur le bouton rouge **"Supprimer"** en haut de page

![Accès suppression fiche](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/07/detail-uf-btn-supp.png)

### Confirmation progressive

La suppression d'une unité de formation est critique dans le système, et nous ne préconisons d'éviter les suppressions.
La suppression est donc précédé d'une fenêtre de confirmation et indique :
- **Nature irréversible** de l'action
- **Impact** sur les données liées

![confirmation suppression fiche](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/unite-formation/07/supp-confirmation-uf.png "506x298")

---

## Impact sur les éléments liés

- **Révocation automatique** des accès utilisateurs ayant ce périmètre
- **Suppression de l'organisation** associée dans la gestion des droits d'accès

---

### Traçabilité des suppressions

La suppression est une action qui est historisée dans l'application.

### Pour aller plus loin
-> [08 - Processus d'approbation des unités de formation](08-processus-approbation)