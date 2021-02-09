---
title: Mise à jour du microprogramme de Microsoft Surface Dock 1
description: Cet article explique comment utiliser la mise à jour du microprogramme de station d’accueil Microsoft Surface pour installer et gérer le microprogramme sur la station d’accueil Surface 1 d’origine. Lorsqu’il est installé sur votre appareil Surface, il met à jour les appareils de la station d’accueil Surface 1 attachés à votre appareil Surface.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 2/08/2021
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319208"
---
# Mise à jour du microprogramme de station d’accueil Microsoft Surface

> [!IMPORTANT]
> Cet article contient des instructions techniques pour les administrateurs informatiques. Si vous êtes un utilisateur d’accueil, voir comment mettre à jour votre [microprogramme](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)de station d’accueil Surface sur le site de   support Microsoft. Les instructions du site de support sont les mêmes que les étapes d’installation générale ci-dessous, mais cet article contient des informations supplémentaires sur la surveillance, la vérification et le déploiement de la mise à jour sur plusieurs appareils sur un réseau.

Cet article explique comment utiliser la mise à jour du microprogramme de station d’accueil Microsoft Surface pour installer et gérer le microprogramme sur la station d’accueil Surface 1 d’origine. Lorsqu’il est installé sur votre appareil Surface, il met à jour les appareils de la station d’accueil Surface 1 attachés à votre appareil Surface.

> [!NOTE]
> Cet article ne s’applique pas à la station d’accueil Surface 2, qui reçoit automatiquement les mises à jour via Windows Update ou à l’aide de Microsoft Endpoint Configuration Manager ou d’autres outils de déploiement MSI. Pour plus d’informations, [voir Nouveautés de la station d’accueil Surface.](surface-dock-whats-new.md)

Cet outil a la place de l’outil Microsoft Surface Dock Updater précédent, précédemment disponible en téléchargement dans le cadre des outils Surface pour l’informatique. L’outil précédent, nommé Surface_Dock_Updater_vx.xx.xxx.x.msi (où x indique le numéro de version), n’est plus disponible en téléchargement et ne doit pas être utilisé.

## Installer la mise à jour du microprogramme de station d’accueil Surface

Cette section décrit comment installer manuellement la mise à jour du microprogramme.

> [!NOTE]
> Microsoft publie régulièrement de nouvelles versions de la mise à jour du microprogramme de station d’accueil Surface. Le fichier MSI n’est pas auto-mis à jour. Si vous avez déployé le MSI sur les appareils Surface et qu’une nouvelle version du microprogramme est publiée, vous devez déployer la nouvelle version.

1. Téléchargez et installez [la mise à jour du microprogramme de la station d’accueil Microsoft Surface.](https://www.microsoft.com/download/details.aspx?id=46703)
    - La mise à jour nécessite un appareil Surface exécutant Windows 10, version 1803 ou ultérieure.
    - L’installation du fichier MSI peut vous demander de redémarrer Surface. Toutefois, le redémarrage n’est pas nécessaire pour effectuer la mise à jour.

2. Déconnectez votre appareil Surface de la station d’accueil Surface, patientez environ 5 secondes, puis reconnectez-vous. La mise à jour du microprogramme de station d’accueil Surface met à jour la station d’accueil en mode silencieux en arrière-plan. Le processus peut prendre quelques minutes et se poursuivre même s’il est interrompu. 

## Surveiller la mise à jour du microprogramme de station d’accueil Surface

Cette section est facultative et fournit une vue d’ensemble de la surveillance de l’installation de la mise à jour du microprogramme. 

Pour surveiller la mise à jour :

1. Ouvrez l’Observateur d’événements, accédez à **Windows Logs > Application,** puis sous **Actions** dans le volet droit, cliquez sur Filtrer le journal **actuel,** entrez **SurfaceDockFwUpdate** en regard des **sources**d’événements, puis cliquez sur **OK.**

2. Tapez la commande suivante à une invite de commandes avec élévation de élévation de niveaux :

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. Installez la mise à jour comme décrit dans [la section suivante](#install-the-surface-dock-firmware-update) de cet article.

4. L’événement 2007 avec le texte suivant indique une mise à jour réussie : Mise à jour du microprogramme **terminée. hr=0 DriverTelementry EventCode = 2007**. 

   Si la mise à jour n’est pas réussie, l’ID d’événement 2007 s’affichera en tant qu’événement **d’erreur** au lieu **d’informations.** En outre, la version signalée dans le Registre Windows n’est pas à jour.
   
5. Une fois la mise à jour terminée, les valeurs DWORD mises à jour s’affichent dans le Registre Windows, correspondant à la version actuelle de l’outil. Pour plus [d’informations, voir](#versions-reference) la section de référence versions de cet article. Par exemple:

    - Component10CurrentFwVersion 0x04ac3970 (78395760)
    - Component20CurrentFwVersion 0x04915a70 (76634736)

>[!TIP]
>Si vous voyez « Impossible de trouver la description de l’ID d’événement xxxx de la source SurfaceDockFwUpdate » dans le texte de l’événement, cette description est attendue et peut être ignorée.

Consultez également les sections suivantes de cet article : 
  - [Comment vérifier la fin de la mise à jour du microprogramme](#how-to-verify-completion-of-the-firmware-update)
  - [Journalisation des événements](#event-logging)
  - [Conseils pour la résolution des problèmes](#troubleshooting-tips)
  - [Référence des versions](#versions-reference)

## Déploiement réseau

Vous pouvez utiliser les commandes Windows Installer (Msiexec.exe) pour déployer la mise à jour du microprogramme de station d’accueil Surface sur plusieurs appareils sur votre réseau. Lorsque vous utilisez Microsoft Endpoint Configuration Manager ou un autre outil de déploiement, entrez la syntaxe suivante pour vous assurer que l’installation est silencieuse :

- **Msiexec.exe /i \<path to msi file\> /quiet /norestart** 

Par exemple:

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> Un fichier journal n’est pas créé par défaut. Pour créer un fichier journal, vous devez l’ajoutez « /l*v [chemin d’accès] ». Par exemple : Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log »

Pour plus d’informations, reportez-vous à la documentation [des options de ligne de](https://docs.microsoft.com/windows/win32/msi/command-line-options) commande.

> [!IMPORTANT]
> Si vous souhaitez maintenir la mise à jour de votre station d’accueil Surface à l’aide d’une autre méthode, reportez-vous à Mettre à jour votre station d’accueil [Surface](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) pour plus d’informations.

## Déploiement d’Intune

Vous pouvez utiliser Intune pour distribuer la mise à jour du microprogramme de station d’accueil Surface à vos appareils. Vous devez d’abord convertir le fichier MSI au format .intunewin, comme décrit dans la documentation suivante : Intune Autonome - Gestion des applications [Win32.](https://docs.microsoft.com/intune/apps/apps-win32-app-management)

Utilisez la commande suivante :
  - **msiexec /i \<path to msi file\> /quiet /q**

## Comment vérifier la fin de la mise à jour du microprogramme

Le microprogramme de station d’accueil Surface se compose de deux composants :

- **Component10 :** Microprogramme de l’unité de micro-contrôleur (MCU)
- **Component20 :** Microprogramme de port d’affichage (DP).

L’exécution réussie de la mise à jour du microprogramme de station d’accueil Surface a abouti à de nouvelles valeurs de clé de Registre pour ces composants de microprogramme.

**Pour vérifier les mises à jour :**

1. Ouvrez Regedit et accédez au chemin de Registre suivant :

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. Recherchez les clés de Registre **: Component10CurrentFwVersion et Component20CurrentFwVersion**, qui font référence au microprogramme actuellement présent sur l’appareil.

   ![Processus d’installation de la mise à jour du microprogramme de station d’accueil Surface](images/regeditDock.png)

3. Vérifiez que les nouvelles valeurs de clé de Registre correspondent aux valeurs de clé de Registre mises à jour répertoriées dans la référence versions à la fin de ce document. Si les valeurs correspondent, le microprogramme a été mis à jour avec succès.

4. Si vous ne parvenez pas à le vérifier, examinez les conseils de journalisation et de dépannage des événements dans la section suivante.

## Journalisation des événements

**Tableau1. Fichiers journaux pour la mise à jour du microprogramme de station d’accueil Surface**

| Journal                              | Emplacement                               | Remarques                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Journal de mise à jour du microprogramme de station d’accueil Surface | Le chemin d’accès doit être spécifié (voir la remarque) | Les versions antérieures de cet outil ont écrit des événements dans Journaux des applications et des services\Microsoft Surface Dock Updater.                                                                                                  |
| Journal d’installation de l’appareil Windows       | %windir%\inf\setupapi.dev.log           | Pour plus d’informations sur l’utilisation du journal d’installation des appareils, consultez la documentation [de journalisation SetupAPI.](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) |


**Tableau2. ID du journal des événements pour la mise à jour du microprogramme de station d’accueil Surface**<br>
Les événements sont consignés dans le journal des événements de l’application.  Remarque : les versions antérieures de cet outil ont écrit des événements dans Journaux des applications et des services\Microsoft Surface Dock Updater.

| ID d’événement | Type d’événement                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | La mise à jour du microprogramme de la station d’accueil a démarré.                                    |
| 2002     | La mise à jour du microprogramme de la station d’accueil a été ignorée, car la station d’accueil est connue pour être à jour. |
| 2003     | Échec de la mise à jour du microprogramme de la station d’accueil pour obtenir la version du microprogramme.                 |
| 2004     | Interrogation de la version du microprogramme.                                       |
| 2005     | Le microprogramme de station d’accueil n’a pas réussi à démarrer la mise à jour.                                |
| 2006     | Échec de l’envoi des paires offre/charge utile.                                  |
| 2007     | Mise à jour du microprogramme terminée.                                            |
| 2008     | BEGIN dock telemetry.                                                |
| 2011     | Télémétrie end dock.                                                  |

## Conseils pour la résolution des problèmes

- Déconnectez complètement la station d’accueil Surface de l’alimentation ac pour réinitialiser la station d’accueil Surface.
- Déconnectez tous les périphériques à l’exception de la station d’accueil Surface.
- Désinstallez toute mise à jour du microprogramme de station d’accueil Surface actuelle, puis installez la dernière version.
- Assurez-vous que la station d’accueil Surface est déconnectée, puis laissez suffisamment de temps pour que la mise à jour se termine comme surveillé via un LED dans le port Ethernet de la station d’accueil. Patientez jusqu’à ce que le voyant cesse de clignoter avant de débrancher la station d’accueil Surface de l’alimentation.
- Connectez la station d’accueil Surface à un autre appareil pour voir s’il est en mesure de mettre à jour la station d’accueil.

## Référence des versions

>[!NOTE]
>Le fichier d’installation est publié avec le format d’attribution de noms suivant : **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) et s’installe par défaut sur C:\Program Files\SurfaceUpdate.

### Version 1.53.139.0
*Date de publication : 4 août 2020*

Cette version de la mise à jour du microprogramme de station d’accueil Surface inclut des correctifs de bogue et la prise en charge des :
- Mise à jour de la station d’accueil Surface 1 à l’aide de Surface Pro X. 
   > [!NOTE]
   > Si vous exécutez Surface Pro X, téléchargez le . Build ARM64. Pour tous les autres appareils, utilisez la build AMD64. 

#### Valeurs des clés de Registre

Les valeurs de Registre qui indiquent l’état des mises à jour du microprogramme restent inchangées par rapport à la version précédente de cet outil : 

- Component10CurrentFwVersion mis à jour vers **4ac3970**.
- Component20CurrentFwVersion mis à jour vers **4a1d570**.
 
### Version 1.42.139 
*Date de publication : 18 septembre 2019*

Cette version, contenue dans Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, met à jour le microprogramme en arrière-plan. 

#### Valeurs de clé de Registre mises à jour

- Component10CurrentFwVersion mis à jour vers **4ac3970**.
- Component20CurrentFwVersion mis à jour vers **4a1d570**.

Il ajoute la prise en charge de Surface Pro 7 et surface laptop 3.

## Versions héritées

### Version 2.23.139.0
*Date de publication : 10 octobre 2018*

Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:

- Ajouter la prise en charge de Surface Pro 6
- Ajouter la prise en charge de Surface Laptop 2


### Version 2.22.139.0
*Date de publication : 26 juillet 2018*

Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:

- Augmenter la fiabilité des mises à jour
- Ajouter la prise en charge de Surface Go

### Version2.12.136.0
*Date de publication: 29 janvier2018*

Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:
* Mise à jour du microprogramme du principal circuit microprogrammé de Surface Dock
* Mise à jour du microprogramme DisplayPort de Surface Dock
* Stabilité d’affichage améliorée pour les écrans externes lorsqu'ils sont utilisés avec Surface Book ou Surface Book2

En outre, l’installation de cette version de Surface Dock Updater sur les appareils Surface Book comprend les éléments suivants:
* Mise à jour du microprogramme de base Surface Book
* Prise en charge des mises à jour du microprogramme de la station d’accueil Surface avec des améliorations destinées aux appareils Surface Book


### Version2.9.136.0
*Date de publication: 3novembre2017*

Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:

* Mise à jour du microprogramme DisplayPort de Surface Dock
* Résout un problème audio sur les cartes DisplayPort passives

### Version 2.1.15.0
*Date de publication: 19 juin2017*

Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:

* Surface Laptop
* SurfacePro

### Version 2.1.6.0
*Date de publication: 7 avril2017*

Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:

* Mise à jour du microprogramme DisplayPort de Surface Dock
* Requiert Windows10

### Version 2.0.22.0
*Date de publication: 21 octobre2016*

Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:

* Mise à jour du microprogramme Surface Dock USB
* Plus grande fiabilité d’Ethernet, du son et des ports USB

### Version 1.0.8.0
*Date de publication: 26 avril2016*

Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:

* Mise à jour du microprogramme du principal circuit microprogrammé de Surface Dock
* Mise à jour du microprogramme DisplayPort de Surface Dock

