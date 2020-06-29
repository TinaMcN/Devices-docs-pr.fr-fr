---
title: Surveiller votre Microsoft Surface Hub
description: La surveillance des appareils Microsoft SurfaceHub s’effectue par le biais de Microsoft Operations Management Suite (OMS).
ms.assetid: 1D2ED317-DFD9-423D-B525-B16C2B9D6942
ms.reviewer: ''
manager: laurawi
keywords: surveiller SurfaceHub, Microsoft Operations Management Suite, OMS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 108f24036a0e02295cf2a5588bb6b51e517eba8d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833653"
---
# Surveiller votre Microsoft SurfaceHub

La surveillance des appareils Microsoft SurfaceHub s’effectue par le biais de Microsoft Operations Management Suite (OMS). [Operations Management Suite](https://go.microsoft.com/fwlink/?LinkId=718138) est une solution de gestion informatique de Microsoft qui vous permet de gérer et de protéger l’ensemble de votre infrastructure informatique, y compris vos SurfaceHub.


Le SurfaceHub est proposé en tant que solution LogAnalytics dans OMS, ce qui vous permet de collecter et d’afficher les données d’utilisation et de fiabilité sur l’ensemble de vos SurfaceHub. Utilisez la solution SurfaceHub pour:
- Inventorier vos SurfaceHub.
- Afficher un instantané des données d’utilisation et de fiabilité pour les réunions Skype, les projections câblées et sans fil, et les applications sur vos SurfaceHub.
- Créer des alertes personnalisées pour réagir rapidement si vos SurfaceHub signalent des problèmes logiciels ou matériels.

## Ajouter un SurfaceHub à Operations Management Suite

1. **Connectez-vous à Operations Management Suite (OMS)**. Vous pouvez utiliser un compte Microsoft ou un compte professionnel ou scolaire pour créer un espace de travail. Si votre entreprise utilise déjà Azure Active Directory (AzureAD), utilisez un compte professionnel ou scolaire lorsque vous vous connectez à OMS. Un compte de ce type vous permet d’utiliser les identités de votre AzureAD pour gérer les autorisations dans OMS.
2. **Créez un espace de travail OMS**. Entrez un nom pour l’espace de travail, sélectionnez la région de l’espace de travail et indiquez l’adresse de messagerie que vous souhaitez associer à cet espace de travail. Sélectionnez **Créer**.
3. **Liez un abonnement Azure à votre espace de travail**. Si votre organisation possède déjà un abonnement Azure, vous pouvez le lier à votre espace de travail. Notez que vous devrez peut-être demander un accès auprès de l’administrateur Azure de votre organisation.

    > [!NOTE] 
    > Si votre organisation ne possède pas d’abonnement Azure, créez-en un ou sélectionnez l’abonnement Azure OMS par défaut dans la liste. Votre espace de travail s’ouvre.

4. **Ajoutez la solution SurfaceHub**. Dans la galerie de solutions, sélectionnez la vignette **SurfaceHub** dans la galerie, puis sélectionnez **Ajouter** dans la page de détails de la solution. La solution est désormais visible dans votre espace de travail.

## Utiliser le tableau de bord SurfaceHub
Dans la page **Vue d’ensemble** de votre espace de travail OMS, cliquez sur la vignette SurfaceHub pour afficher le tableau de bord SurfaceHub. Utilisez le tableau de bord pour obtenir un instantané des données d’utilisation et de fiabilité de vos SurfaceHub. Cliquez sur chaque vue du tableau de bord pour afficher des données détaillées, modifier la requête comme il vous convient, et créer des alertes.

> [!NOTE]
> La plupart de ces vues affichent les données des 30derniers jours, mais cela dépend de la stratégie de conservation des données de votre abonnement.

**SurfaceHub actifs**

Utilisez cette vue pour obtenir un inventaire de tous vos SurfaceHub. Une fois connecté à OMS, chaque SurfaceHub envoie régulièrement un événement de «pulsation» au serveur. Cette vue indique les SurfaceHub qui ont signalé une pulsation au cours des dernières 24heures.

<!--
**Skype meetings**

Use this view to get usage data for Skype over the past 30 days. The graph shows the total number of Skype Meetings started across your Surface Hubs, and a breakdown between scheduled meetings, ad hoc meetings, and PSTN calls.
-->
 
**Projection sans fil**

Utilisez cette vue pour obtenir les données d’utilisation et de fiabilité des projections sans fil des 30derniers jours. Le graphique affiche le nombre total de connexions sans fil de tous vos SurfaceHub, ce qui indique si les membres de votre organisation utilisent cette fonctionnalité. Si ce nombre est petit, vous devez peut-être envisager de proposer une formation pour aider les utilisateurs de votre organisation à apprendre à se connecter sans fil à un SurfaceHub.
 
De plus, le graphique affiche une répartition des connexions réussies et infructueuses. Si vous observez un nombre élevé de connexions infructueuses, les appareils ne peuvent peut-être pas prendre en charge correctement les projections sans fil à l’aide de Miracast. Pour des performances optimales, Microsoft suggère d’utiliser un pilote Wi-Fi WDI et un pilote de graphiques WDDM2.0 pour les appareils. Utilisez la vue Détails pour savoir si les problèmes de projection sans fil sont courants avec des appareils spécifiques.
 
En cas d’échec d’une connexion, les utilisateurs peuvent également procéder comme suit s’ils utilisent un ordinateur portable ou un téléphone Windows:
- Supprimez l’appareil couplé dans **Paramètres** > **Appareils** > **Appareils connectés**, puis réessayez de vous connecter.
- Redémarrez l’appareil.
 
**Projection câblée**

Utilisez cette vue pour obtenir les données d’utilisation et de fiabilité des projections câblées des 30derniers jours. Si le graphique indique un nombre élevé de connexions infructueuses, il peut s’agir d’un problème de connectivité dans votre pipeline audiovisuel. Par exemple, si vous utilisez un répéteur HDMI ou un panneau de configuration central, ils doivent peut-être être redémarrés.
 
**Utilisation des applications**

Utilisez cette vue pour obtenir les données d’utilisation des applications de vos SurfaceHub des 30derniers jours. Les données proviennent des lancements d’applications sur vos SurfaceHub, à l’exclusion de SkypeEntreprise. Cette vue vous permet de connaître les applications des SurfaceHub qui sont les plus intéressantes pour votre organisation. Si vous déployez de nouvelles applications métier dans votre environnement, cela peut également vous aider à connaître leur fréquence d’utilisation.
 
**Blocages d’applications**

Utilisez cette vue pour obtenir les données de fiabilité des applications de vos SurfaceHub des 30derniers jours. Les données proviennent des blocages d’applications qui se sont produits sur vos SurfaceHub. Cette vue vous permet de détecter les applications métier et fournies qui ne fonctionnent pas de manière satisfaisante et de le notifier aux développeurs.
 
**Exemples de requêtes**

Utilisez cette vue pour créer des alertes personnalisées basées sur un ensemble de requêtes recommandé. Les alertes vous permettent de réagir rapidement si vos SurfaceHub signalent des problèmes logiciels ou matériels. Pour plus d’informations, voir [Configurer des alertes à l’aide d’exemples de requêtes](#set-up-alerts-with-sample-queries).

## Configurer des alertes à l’aide d’exemples de requêtes

Utilisez des alertes pour réagir rapidement si vos SurfaceHub signalent des problèmes logiciels ou matériels. Les règles d’alerte exécutent automatiquement des recherches de journaux selon un planning, et exécutent une ou plusieurs actions si les résultats correspondent à des critères spécifiques. Pour plus d’informations, voir [Alertes dans Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/).
 
La solution Surface Hub Log Analytics inclut un ensemble d’exemples de requêtes qui vous aident à configurer les alertes appropriées et à résoudre les problèmes que vous êtes susceptible de rencontrer. Utilisez-les comme point de départ pour planifier votre surveillance et votre stratégie de support.

Le tableau suivant décrit les exemples de requêtes de la solution SurfaceHub:

| Type d’alerte | Impact | Solutions recommandées | Détails |
| ---------- | ------ | ----------------------- | ------- |
| Logiciels   | Erreur  | **Redémarrez l’appareil**. <br> Redémarrez manuellement ou à l’aide du [fournisseur de services de configuration de redémarrage](https://msdn.microsoft.com/library/windows/hardware/mt720802(v=vs.85).aspx). <br> Suggérez d’effectuer cette opération entre les réunions afin de limiter l’impact sur les membres de votre organisation. | Conditions de déclenchement: <br> -Un processus essentiel dans le système d’exploitation du SurfaceHub, par exemple l’interpréteur de commandes, la projection ou Skype, se bloque ou ne réagit plus. <br> -L’appareil n’a pas signalé de pulsations au cours des dernières 24heures. Ce peut être dû à un problème de connectivité réseau ou à une défaillance matérielle liée au réseau, ou bien encore à une erreur du système de création de rapports de données de diagnostics. |
| Logiciels   | Erreur  | **Vérifiez votre service Exchange**. <br> Vérifiez les points suivants: <br> -Le service est disponible. <br> -Le mot de passe du compte d’appareil est à jour (pour en savoir plus, voir [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md)).| Se déclenche en cas d’erreur de synchronisation du calendrier de l’appareil avec Exchange. |
| Logiciels   | Erreur  | **Vérifiez votre service SkypeEntreprise**. <br> Vérifiez les points suivants: <br> -Le service est disponible. <br> -Le mot de passe du compte d’appareil est à jour (pour en savoir plus, voir [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md)). <br> -Le nom de domaine de SkypeEntreprise est configuré correctement (voir [Configurer un nom de domaine](use-fully-qualified-domain-name-surface-hub.md)). | Se déclenche en cas d’échec de la connexion de Skype. |
| Logiciels   | Erreur  | **Réinitialisez l’appareil**. <br> Comme cette opération prend un certain temps, vous devez mettre l’appareil en mode hors connexion. <br> Pour plus d’informations, voir [Réinitialiser l’appareil (SurfaceHub)](device-reset-surface-hub.md).| Se déclenche en cas d’erreur de nettoyage des données utilisateur et d’application à la fin d’une session. Si cette opération échoue à plusieurs reprises, l’appareil est verrouillé afin de protéger les données utilisateur. Pour poursuivre, vous devez réinitialiser l’appareil. |
| Matériel   | Avertissement | **Aucune**. Indique un impact négligeable sur les fonctionnalités.| Se déclenche en cas d’erreur avec l’un des composants matériels suivants: <br> -Connecteurs de stylet virtuel <br> -PiloteNFC <br> -Pilote de concentrateur USB <br> -Pilote Bluetooth <br> -Capteur de proximité <br> -Performances graphiques (pilote de carte vidéo) <br> -Disque dur incompatible <br> -Pas de souris/clavier détectés |
| Matériel   | Erreur | **Contactez le support technique Microsoft**. <br> Indique l’impact sur les fonctionnalités principales (par exemple, Skype, la projection, l’interaction tactile et la connectivité Internet). <br> **Remarque** Certains événements, notamment les pulsations, incluent le numéro de série de l’appareil que vous pouvez utiliser lorsque vous contactez le support.| Se déclenche en cas d’erreur avec l’un des composants matériels suivants: <br> **Composants qui affectent Skype**: <br> -Pilote de haut-parleur <br> -Pilote de microphone <br> -Pilote d’appareil photo <br> **Composants qui affectent la projection câblée et sans fil**: <br> -Pilote touchback câblé <br> -Pilote ingest câblé <br> - Pilote de carte sans fil <br> -Erreur Wi-Fi Direct <br> **Autres composants**: <br> -Pilote de numériseur tactile <br> -Erreur de carte réseau (non signalée à OMS)|

**Pour configurer une alerte**
1. À partir de la solution SurfaceHub, sélectionnez l’un des exemples de requêtes.
2. Modifiez la requête comme il vous convient. Pour en savoir plus, voir Référence de recherche Log Analytics.
3. Cliquez sur **Alerte** en haut de la page pour ouvrir l’écran **Ajouter une règle d’alerte**. Pour en savoir plus sur les options de configuration de l’alerte, voir [Alertes dans Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/).
4. Cliquez sur **Enregistrer** pour terminer la règle d’alerte. Son exécution commence immédiatement.

## Inscrire votre SurfaceHub

Pour que le SurfaceHub se connecte et s’inscrive auprès du service OMS, il doit avoir accès au numéro de port de vos domaines et des URL. Le tableau ci-dessous répertorie les ports utiles au service OMS. Pour plus d’informations, voir [Configurer les paramètres de pare-feu et de proxy dans Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-proxy-firewall/).

>[!NOTE]
>Le SurfaceHub ne prend pas actuellement en charge l’utilisation d’un serveur proxy pour communiquer avec le service OMS.

| Ressource de l’agent              | Ports | Contourner l’inspection HTTPS? |
| --------------------------- | ----- | ------------------------ |
| *.ods.opinsights.azure.com  | 443   | Oui |
| *.oms.opinsights.azure.com  | 443   | Oui |
| *.blob.core.windows.net     | 443   | Oui |
| ods.systemcenteradvisor.com | 443   | Non  |

Comme Microsoft Monitoring Agent, utilisé pour connecter des appareils au service OMS, est intégré au système d’exploitation du Surface Hub, il n’est pas nécessaire d’installer des clients supplémentaires pour connecter le SurfaceHub au service OMS.
 
Une fois votre espace de travail OMS configuré, vous pouvez inscrire vos appareils SurfaceHub de plusieurs façons:
- [Application Paramètres](#enroll-using-the-settings-app)
- [Package d’approvisionnement](#enroll-using-a-provisioning-package)
- [Fournisseur GPM](#enroll-using-a-mdm-provider), par exemple MicrosoftIntune et Configuration Manager
 
Vous devez disposer de l’ID de l’espace de travail et de la clé principale de votre espace de travail OMS. Vous pouvez vous les procurer depuis le portail OMS.
 
### Inscrire un appareil à l’aide de l’application Paramètres

**Pour inscrire un appareil à l’aide de l’application Paramètres**

1. À partir de votre SurfaceHub, démarrez **Paramètres**.
2. Entrez les informations d’identification d’administrateur de l’appareil lorsque vous y êtes invité.
3. Sélectionnez **Cet appareil**, puis accédez à **Gestion des appareils**.
4. Sous **Analyse**, sélectionnez **Configurer les paramètres OMS**.
5. Dans la boîte de dialogue Paramètres OMS, sélectionnez **Activer l’analyse**.
6. Entrez l’ID de l’espace de travail et la clé principale de votre espace de travail OMS. Vous pouvez vous les procurer depuis le portail OMS.
7. Cliquez sur **OK** pour terminer la configuration.
 
Une boîte de dialogue de confirmation s’affiche indiquant si la configuration OMS a été appliquée à l’appareil avec succès. Si tel est le cas, l’appareil commence l’envoi des données vers OMS.

### Inscrire un appareil à l’aide d’un package d’approvisionnement
Vous pouvez utiliser un package d’approvisionnement pour inscrire votre SurfaceHub. Pour plus d’informations, voir [Créer des packages de mise en service (SurfaceHub)](provisioning-packages-for-certificates-surface-hub.md).
 
### Inscrire un appareil à l’aide d’un fournisseur GPM
Vous pouvez inscrire un SurfaceHub auprès du service OMS à l’aide du fournisseur CSP SurfaceHub. MicrosoftIntune et Configuration Manager fournissent des expériences intégrées pour vous aider à créer des modèles de stratégie pour le SurfaceHub. Pour plus d’informations, voir [Gérer les paramètres avec un fournisseur GPM (SurfaceHub)](manage-settings-with-mdm-for-surface-hub.md).

## Rubriques connexes

[Gérer le Microsoft SurfaceHub](manage-surface-hub.md)

[Guide de l’administrateur Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





