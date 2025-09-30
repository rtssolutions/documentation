---
title: "02 - Consultation et modification"
description: "Gestion complète des besoins spécifiques d’un apprenant : consultation, modification et dépôt de justificatifs."
date: "2025-09-28"
version: "1"
---

## 📝 Table des matières

- [Accès à la consultation](#accès-à-la-consultation)
- [Permissions requises](#permissions-requises)
- [Consultation des besoins spécifiques](#consultation-des-besoins-spécifiques)
- [Modification des besoins spécifiques](#modification-des-besoins-spécifiques)
- [Gestion des documents justificatifs](#gestion-des-documents-justificatifs)
- [Bonnes pratiques et confidentialité](#bonnes-pratiques-et-confidentialité)

---

## Accès à la consultation

🔍 Pour consulter les besoins spécifiques d’un apprenant, rendez-vous sur la fiche de l’apprenant concerné. Une carte dédiée aux besoins spécifiques est affichée sur la fiche. Cette carte indique si l’apprenant présente ou non des besoins spécifiques. Pour accéder au détail complet, cliquez sur le bouton **"Voir le détail"** présent sur la carte. Cette action nécessite de disposer de la permission **"Lecture des besoins spécifiques"** sur l’apprenant.

![Carte besoins spécifiques - fiche apprenant](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/8/carte-besoins-specifiques.png)

---

## Permissions requises

🔒 L’accès et la gestion des besoins spécifiques sont strictement encadrés par des permissions distinctes:

- **Lecture des besoins spécifiques** : permet de consulter les informations relatives aux besoins spécifiques d’un apprenant (statut, titres, partage, etc.).
- **Écriture des besoins spécifiques** : permet de modifier les informations relatives aux besoins spécifiques.
- **Lecture des documents des besoins spécifiques** : permet de consulter les documents justificatifs associés aux besoins spécifiques d’un apprenant.
- **Écriture des documents des besoins spécifiques** : permet de téléverser de nouveaux documents justificatifs liés aux besoins spécifiques.

Seuls les utilisateurs disposant des permissions adéquates peuvent accéder à chaque fonctionnalité: la consultation et la modification des besoins spécifiques, ainsi que la gestion des documents justificatifs, sont indépendantes et nécessitent des droits spécifiques.

---

## Consultation des besoins spécifiques

ℹ️ Lors de la consultation, les informations suivantes sont affichées:

- **Sportif de haut niveau** : indique si l’apprenant bénéficie de ce statut (Oui/Non).
- **Apprenant en situation de handicap** : indique si l’apprenant est reconnu comme tel (Oui/Non).
    - Si l’apprenant est en situation de handicap, le titre de la situation est précisé:
        - **RQTH** (Reconnaissance de la Qualité de Travailleur Handicapé)
        - **BOE** (Bénéficiaire de l’Obligation d’Emploi)
        - **Équivalence jeune RQTH** (possible uniquement pour les apprenants âgés de 15 à 20 ans)
            - Si le titre est "Équivalence jeune RQTH", le type d’équivalence est affiché:
                - **PPS** (Projet Personnalisé de Scolarisation)
                - **AEEH** (Allocation d’Éducation de l’Enfant Handicapé)
                - **PCH** (Prestation de Compensation du Handicap)
    - Si l’apprenant est en situation de handicap, il est également précisé s’il souhaite partager les informations liées à son handicap avec les équipes pédagogiques ou administratives (Oui/Non).

Pour chaque situation de handicap renseignée (RQTH, BOE, Équivalence jeune RQTH), il est obligatoire de déposer un document justificatif. Un bouton **"Ajouter un justificatif"** apparaît à côté du champ concerné pour téléverser le document directement.
En haut à droite de la carte besoins spécifiques, un bouton **"Ressources utiles"** permet d’accéder à des liens d’information publique sur les travailleurs en situation de handicap et les sportifs de haut niveau:

![Page consultation besoins spécifiques](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/8/consultation-besoins-specifiques.png)

---

## Modification des besoins spécifiques

✏️ La modification des besoins spécifiques s’effectue uniquement depuis la page de consultation détaillée. Si vous disposez de la permission **"Écriture des besoins spécifiques"**, un bouton **"Modifier"** apparaît en haut à droite de la page. En cliquant dessus, vous accédez au formulaire de modification.

![Bouton modifier besoins spécifiques](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/8/bouton-modifier-besoins-specifiques.png)

Le formulaire permet de:
- Cocher ou décocher le statut de **sportif de haut niveau**.
- Indiquer si l’apprenant est en **situation de handicap**.
    - Si oui, sélectionner le titre de la situation parmi: RQTH, BOE, Équivalence jeune RQTH.
        - Si "Équivalence jeune RQTH" est choisi, le champ n’est accessible que si l’apprenant a entre 15 et 20 ans, puis sélectionner le type d’équivalence: PPS, AEEH, PCH.
    - Indiquer si l’apprenant souhaite partager les informations liées à son handicap.

Pour chaque situation de handicap sélectionnée, il est obligatoire de déposer un document justificatif via le bouton **"Ajouter un justificatif"** qui apparaît à côté du champ concerné.

![Formulaire modification besoins spécifiques](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/8/formulaire-modification-besoins-specifiques.png)

⚠️ Des contrôles de validité sont appliqués à chaque champ. En cas d’erreur ou d’incohérence, un message explicite s’affiche pour guider la correction. Une fois la saisie terminée, cliquez sur **"Enregistrer les modifications"** pour valider les modifications.

---

## Gestion des documents justificatifs

📎 La section **Documents justificatifs** est affichée uniquement si vous disposez de la permission spécifique de lecture sur les documents des besoins spécifiques d’un apprenant. Elle présente la liste des documents déjà déposés, qui peuvent être consultés selon les droits de l’utilisateur.

![Section documents justificatifs](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/8/section-documents-justificatifs.png)

📁 Si vous avez la permission spécifique d’écriture sur les documents des besoins spécifiques, un bouton **"Ajouter un document"** apparaît, permettant de téléverser de nouveaux justificatifs (par exemple : attestation RQTH, certificat sportif, justificatif d’équivalence, etc.). Ces documents sont essentiels pour la contractualisation et le suivi administratif de l’apprenant.

![Bouton ajouter un document justificatif](https://papaours.s3.fr-par.scw.cloud/documentations/tutoriel/apprenant/8/bouton-ajouter-document.png)

---

## Bonnes pratiques et confidentialité

🛡️ Les besoins spécifiques et les documents associés sont des données particulièrement sensibles. Il est impératif de respecter la confidentialité et de limiter l’accès aux seules personnes disposant des permissions adéquates. Chaque modification ou dépôt de document est historisé (date, utilisateur, détail de l’action) afin d’assurer la traçabilité et la sécurité des informations.
