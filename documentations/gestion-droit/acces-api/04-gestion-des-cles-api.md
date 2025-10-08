---
title: "04 - Gestion des clés API"
description: "Créer, consulter et modifier des clés API dans Papaours"
date: "2025-10-07"
version: "1"
---

## 📚 Table des matières

1. [Créer une clé API](#créer-une-clé-api)
2. [Consulter les clés API d'une machine](#consulter-les-clés-api-dune-machine)
3. [Modifier une clé API](#modifier-une-clé-api)

---

## Créer une clé API

Cette section détaille la procédure à suivre pour créer une nouvelle clé API pour une machine existante au sein du
système. Les clés API permettent aux machines d'accéder de manière sécurisée aux services de la plateforme Papaours.

### Prérequis

- Une machine doit déjà exister (voir [Créer une machine](03-gestion-des-machines.md#créer-une-machine))
- Vous devez disposer de la permission **Gestion des droits / Machines / Écriture**

### Étapes de création

1. **Accéder à la gestion des machines** : Naviguez vers la section *Machines* du menu *Gestion des droits*.

   ![Menu machine](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/04/menu%20machine.png "319×211")

2. **Sélectionner la machine** : Cliquez sur la machine pour laquelle vous souhaitez créer une clé API afin d'accéder à
   sa page de détail.

3. **Ouvrir le formulaire de création** : Dans la carte **Clés API**, cliquez sur le bouton **Créer une clé API** (icône
   plus).

   ![Liste cle api bouton creation](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/04/bouton%20creation%20api%20key.png)

4. **Renseigner les informations** :
    - **Libellé** : Saisissez un nom descriptif pour identifier facilement l'usage de cette clé API (exemple : "Clé
      production", "Clé environnement de test", etc.).

   ![creation api key](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/04/Cre%CC%81er%20cle%CC%81%20api.png "422×273")

5. **Créer la clé** : Cliquez sur le bouton **Créer** pour générer la clé API.

6. **Récupérer la valeur de la clé** : Une fenêtre s'affiche immédiatement avec la valeur générée de la clé API.

   ![confirmation api key](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/04/Cle%20api%20valeur%20non%20copie.png "996×371")

### ⚠️ Important : Sauvegarder la clé API

> **La valeur de la clé API ne sera affichée qu'une seule fois.** Il est impératif de la copier et de la sauvegarder
> dans un endroit sécurisé avant de fermer la fenêtre.
>
> Une fois la fenêtre fermée, **il sera impossible de récupérer cette valeur**. Si vous perdez la clé, vous devrez en
> créer une nouvelle et mettre à jour tous les systèmes qui l'utilisaient.

### Utilisation du bouton Copier

Pour faciliter la sauvegarde de la clé, utilisez le bouton **Copier** présent dans la fenêtre d'affichage. Ce bouton
copie automatiquement la valeur de la clé dans votre presse-papiers.

### Conseils additionnels

- **Nommer clairement vos clés** : Utilisez des libellés explicites indiquant l'environnement ou le service concerné.
- **Documenter l'usage de chaque clé** : Conservez une trace de l'utilisation de chaque clé API pour faciliter la
  maintenance.
- **Stocker les clés de manière sécurisée** : Utilisez un gestionnaire de secrets ou un coffre-fort numérique pour
  conserver les clés API.

---

## Consulter les clés API d'une machine

Cette section explique comment visualiser l'ensemble des clés API associées à une machine spécifique.

### Accès à la liste des clés API

1. **Accéder à la gestion des machines** : Naviguez vers la section *Machines* du menu *Gestion des droits*.
2. **Sélectionner la machine** : Cliquez sur la machine dont vous souhaitez consulter les clés API.
3. **Visualiser la carte Clés API** : La page de détail de la machine affiche une carte **Clés API** contenant la liste
   de toutes les clés associées.

![Liste des cles api](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/04/Liste%20cle%CC%81%20api.png)

### Informations affichées

Pour chaque clé API, vous pouvez consulter :

- **Libellé** : Le nom descriptif de la clé API.
- **Statut** : L'état actuel de la clé (Active ou Inactive).
    - Une clé **Active** peut être utilisée pour authentifier la machine auprès des services.
    - Une clé **Inactive** ne peut plus être utilisée, mais reste visible dans la liste.

### Clés API masquées

Pour des raisons de sécurité, **les valeurs des clés API ne sont jamais affichées** dans cette liste. Seules les
informations de libellé et de statut sont visibles. La valeur d'une clé n'est montrée qu'une seule fois, lors de sa
création.

### Absence de clés API

Si aucune clé API n'est associée à la machine, le message suivant s'affiche :

> "Aucune clé API associée à cette machine"

---

## Modifier une clé API

Cette section détaille la procédure à suivre pour modifier une clé API existante. La modification permet de changer le
libellé d'une clé ou de désactiver/réactiver son utilisation.

### Prérequis

Vous devez disposer de la permission **Gestion des droits / Machines / Écriture**.

### Étapes de modification

1. **Accéder à la liste des clés API** : Depuis la page de détail d'une machine, consultez la carte **Clés API**.

2. **Sélectionner la clé à modifier** : Dans la ligne correspondant à la clé API que vous souhaitez modifier, cliquez
   sur le bouton **Modifier** dans la colonne des actions (icône crayon).

3. **Éditer les informations de la clé** : Une fenêtre modale s'ouvre vous permettant de modifier :
    - **Libellé** : Changez le nom descriptif de la clé API.
    - **Active** : Utilisez l'interrupteur pour activer ou désactiver la clé.

   ![Modification api key](https://papaours-documentation.s3.fr-par.scw.cloud/tutoriels/gestion-des-droits/acces-api/04/Modifier%20cle%20api.png "383×293")

4. **Enregistrer les modifications** : Cliquez sur le bouton **Enregistrer** pour appliquer les changements.

### Désactivation d'une clé API

Désactiver une clé API permet de la rendre inutilisable sans la supprimer définitivement. Cette approche est recommandée
dans les cas suivants :

- **Rotation des clés** : Lors de la mise en place d'une nouvelle clé, vous pouvez désactiver l'ancienne après avoir
  vérifié que tous les systèmes utilisent la nouvelle.
- **Suspension temporaire** : En cas de suspicion de compromission ou pour des raisons de maintenance.
- **Conservation de l'historique** : Pour garder une trace des clés utilisées sans permettre leur utilisation.

### Réactivation d'une clé API

Une clé désactivée peut être réactivée à tout moment en utilisant l'interrupteur **Active** dans le formulaire de
modification. La clé retrouvera alors sa pleine fonctionnalité.

### Conséquences de la modification

- **Modification du libellé** : N'a aucun impact sur le fonctionnement de la clé. Il s'agit uniquement d'un changement
  cosmétique pour faciliter l'identification.
- **Désactivation de la clé** : Tous les appels API utilisant cette clé seront immédiatement rejetés. Assurez-vous
  qu'aucun système critique ne dépend de cette clé avant de la désactiver.
- **Réactivation de la clé** : La clé redevient immédiatement utilisable avec sa valeur d'origine.

> ℹ️ **Note** : La modification d'une clé API ne change pas sa valeur. Si vous suspectez qu'une clé a été compromise, il
> est préférable de la désactiver et d'en créer une nouvelle.

### Conseils additionnels

- **Tester avant de désactiver** : Vérifiez qu'une nouvelle clé fonctionne correctement avant de désactiver l'ancienne.
- **Informer les équipes concernées** : Communiquez les changements de statut des clés aux équipes techniques
  concernées.
- **Documenter les modifications** : Conservez un journal des modifications de clés pour faciliter le dépannage et
  l'audit.

---

### Pour aller plus loin

- [Sécurité et bonnes pratiques →](05-securite-et-bonnes-pratiques.md)
- [Utiliser une clé API dans votre code →](06-utilisation-cle-api.md)
- [Retour à la gestion des machines](03-gestion-des-machines.md)

[Retour à l'Accueil](../../accueil)
