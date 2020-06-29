---
title: Mise à jour du microprogramme Microsoft surface Dock-informations techniques destinées aux administrateurs informatiques
description: Cet article décrit l’utilisation de la mise à jour du microprogramme Microsoft surface Dock pour mettre à jour le microprogramme du Dock surface. Lorsqu’il est installé sur votre appareil surface, il met à jour tout Dock de surface relié à votre surface.
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
ms.openlocfilehash: aab4c67a6a262b11cd5982ebe145afbddfeaa1c9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832490"
---
# Mise à jour du microprogramme Microsoft surface Dock: informations techniques destinées aux administrateurs informatiques

> [!IMPORTANT]
> Cet article contient des instructions techniques destinées aux administrateurs informatiques. Si vous êtes un particulier, voir [Comment mettre à jour le microprogramme de votre Dock surface](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   sur le site du support Microsoft. Les instructions sur le site d’assistance sont les mêmes que les étapes générales d’installation ci-dessous, mais cet article contient des informations supplémentaires pour surveiller, vérifier et déployer la mise à jour sur plusieurs appareils sur un réseau.

Cet article décrit l’utilisation de la mise à jour du microprogramme Microsoft surface Dock pour mettre à jour le microprogramme du Dock surface. Lorsqu’il est installé sur votre appareil surface, il met à jour tout Dock de surface relié à votre surface. 

Cet outil remplace l’outil de mise à jour de l’outil de mise à jour de Microsoft surface Dock antérieur, auparavant disponible en téléchargement dans le cadre des outils surface. L’outil précédent a été nommé Surface_Dock_Updater_vx.xx.xxx.x.msi (où x indique le numéro de version) et n’est plus disponible en téléchargement et ne doit pas être utilisé.

## Installez la mise à jour du microprogramme de surface Dock

Cette section décrit comment installer manuellement la mise à jour du microprogramme.

> [!NOTE]
> Microsoft publie régulièrement de nouvelles versions de la mise à jour du microprogramme de surface Dock. Le fichier MSI n’est pas mis à jour automatiquement. Si vous avez déployé le MSI sur les appareils surface et qu’une nouvelle version du microprogramme est publiée, vous devrez déployer la nouvelle version.

1. Téléchargez et installez la [mise à jour du microprogramme Microsoft surface Dock](https://www.microsoft.com/download/details.aspx?id=46703).
    - La mise à jour nécessite un appareil surface exécutant Windows 10, version 1803 ou ultérieure.
    - L’installation du fichier MSI peut vous inviter à redémarrer surface. Toutefois, le redémarrage n’est pas nécessaire pour effectuer la mise à jour.

2. Déconnectez votre périphérique surface du Dock de surface (à l’aide de la carte Power), attendez ~ 5 secondes, puis reconnectez-vous. La mise à jour du microprogramme de surface Dock met à jour le Dock en silence en arrière-plan. Le processus peut prendre quelques minutes et continuer même en cas d’interruption. 

## Surveiller la mise à jour du microprogramme de surface Dock

Cette section est facultative et offre une vue d’ensemble de la façon de surveiller l’installation de la mise à jour du microprogramme. 

Pour surveiller la mise à jour:

1. Ouvrez l’observateur d’événements, accédez à l' **application journaux de >** à l’application, puis, sous **actions** dans le volet droit, cliquez sur **filtrer le journal actuel**, entrez **SurfaceDockFwUpdate** en regard de **sources d’événements**, puis cliquez sur **OK**.

2. Tapez la commande suivante à l’invite de commandes avec élévation de privilèges:

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. Installez la mise à jour comme décrit dans la [section suivante](#install-the-surface-dock-firmware-update) de cet article.
4. L’événement 2007 avec le texte suivant indique une mise à jour réussie: **mise à jour du microprogramme terminée. hr = 0 DriverTelementry eventCode = 2007**. 
    - Si la mise à jour échoue, l’événement ID 2007 est affiché en tant qu’événement d' **erreur** plutôt que par **informations**. Par ailleurs, la version indiquée dans le Registre Windows ne sera pas la version actuelle.
5. À l’issue de la mise à jour, les valeurs DWORD mises à jour s’affichent dans le Registre Windows, correspondant à la version actuelle de l’outil. Pour plus d’informations, consultez la section de [référence des versions](#versions-reference) de cet article. Exemple:
    - Component10CurrentFwVersion 0x04ac3970 (78395760)
    - Component20CurrentFwVersion 0x04915a70 (76634736)

>[!TIP]
>Si vous voyez «la description de l’ID d’événement XXXX à partir de la source SurfaceDockFwUpdate est introuvable» dans le texte de l’événement, il est attendu et peut être ignoré.

Reportez-vous également aux sections suivantes de cet article: 
  - [Vérifier la fin de la mise à jour du microprogramme](#how-to-verify-completion-of-the-firmware-update)
  - [Journalisation des événements](#event-logging)
  - [Conseils pour la résolution des problèmes](#troubleshooting-tips)
  - [Réf version](#versions-reference)

## Déploiement réseau

Vous pouvez utiliser les commandes du programme d’installation Windows (Msiexec.exe) pour déployer la mise à jour de microprogramme de surface Dock sur plusieurs appareils sur votre réseau. Lors de l’utilisation du gestionnaire de configuration de point de terminaison Microsoft ou d’un autre outil de déploiement, entrez la syntaxe suivante pour vous assurer que l’installation est silencieuse:

- **Msiexec.exe/i \<path to msi file\> /Quiet/norestart** 

  Exemple:
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > Par défaut, un fichier journal n’est pas créé. Pour créer un fichier journal, vous devrez ajouter «/l*v [chemin]». Par exemple: Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI. log "

  Pour plus d’informations, voir la documentation des [options de ligne de commande](https://docs.microsoft.com/windows/win32/msi/command-line-options) .

> [!IMPORTANT]
> Si vous souhaitez conserver votre ancrage de surface à jour à l’aide d’une autre méthode, voir [mettre à jour votre station](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) de dessin de surface pour plus d’informations.

## Déploiement de Intune

Vous pouvez utiliser Intune pour distribuer les mises à jour de microprogramme de surface Dock sur vos appareils. Tout d’abord, vous devez convertir le fichier MSI au format. intunewin, comme décrit dans la documentation suivante: [Intune standalone-gestion des applications Win32](https://docs.microsoft.com/intune/apps/apps-win32-app-management).

Utilisez la commande suivante:
  - **msiexec/i \<path to msi file\> /Quiet/q**

## Vérifier la fin de la mise à jour du microprogramme

Le microcode de surface Dock comporte deux composants:

- **Component10:** Microcontroller Unit (MCU)
- **Component20:** Microprogramme de port d’affichage (DP).

Réussite de la mise à jour du microprogramme du Dock de surface entraîne de nouvelles valeurs de clé de Registre pour ces composants microprogrammes.

**Pour vérifier les mises à jour:**

1. Ouvrez Regedit et naviguez jusqu’au chemin de Registre suivant:

    - **HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. Recherchez les clés de Registre suivantes: **Component10CurrentFwVersion et Component20CurrentFwVersion**, qui font référence au microprogramme actuellement sur l’appareil.

   ![Processus d’installation de la mise à jour du microprogramme du Dock surface](images/regeditDock.png)

3. Vérifiez que les nouvelles valeurs de clé de Registre correspondent aux valeurs de clé de Registre mises à jour répertoriées dans la référence de versions à la fin de ce document. Si les valeurs correspondent, le microprogramme a été correctement mis à jour.

4. Si vous ne parvenez pas à vérifier, consultez la journalisation des événements et conseils de dépannage dans la section suivante.

## Journalisation des événements

**Tableau1. Fichiers journaux pour la mise à jour du microprogramme de surface Dock**

| Journal                              | Location                               | Remarques                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Journal des mises à jour du microprogramme du Dock surface | Le chemin d’accès doit être spécifié (voir remarque) | Les versions précédentes de cet outil écrivaient des événements pour les applications et les services Logs\Microsoft de mise à jour de surface Dock.                                                                                                  |
| Journal d’installation des appareils Windows       | %windir%\inf\setupapi.dev.log           | Pour plus d’informations sur l’utilisation du journal d’installation de périphériques, voir la documentation sur l' [enregistrement Setupapi](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) . |


**Tableau2. ID du journal des événements pour la mise à jour du microprogramme de surface Dock**<br>
Les événements sont enregistrés dans le journal des événements de l’application.  Remarque: les versions antérieures de cet outil écrivaient des événements pour les applications et les services Logs\Microsoft de mise à jour de surface Dock.

| ID d’événement | Type d’événement                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | La mise à jour du microprogramme est lancée.                                    |
| 2002     | Le retrait du microprogramme a été ignoré, car le Dock est connu comme étant à jour. |
| 2003     | La mise à jour du microprogramme a échoué pour obtenir la version du microprogramme.                 |
| 2004     | Interrogation de la version du microprogramme.                                       |
| 2005     | Échec du démarrage de la mise à jour du microprogramme.                                |
| 2006     | Échec de l’envoi des paires d’avantages et de charges utiles.                                  |
| 2007     | Mise à jour du microprogramme terminée.                                            |
| 2008     | COMMENCER la télémétrie de la station d’accueil.                                                |
| 2011     | Télémétrie du Dock.                                                  |

## Conseils pour la résolution des problèmes

- Déconnectez complètement l’alimentation du Dock de surface de l’alimentation CA pour réinitialiser le quai de surface.
- Déconnectez tous les périphériques à l’exception du Dock surface.
- Désinstallez toutes les mises à jour de microprogramme de surface Dock actuelles, puis installez la version la plus récente.
- Assurez-vous que le Dock de surface est déconnecté, puis Prévoyez suffisamment de temps pour que la mise à jour s’exécute comme surveillé par le biais d’un témoin sur le port Ethernet du Dock. Patientez jusqu’à ce que le témoin lumineux cesse de clignoter avant de débrancher le quai de surface.
- Connectez le Dock de surface à un autre appareil pour voir s’il est en mesure de mettre à jour le Dock.

## Réf version

>[!NOTE]
>Le fichier d’installation est mis en forme avec le format d’attribution de noms suivant: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (par exemple: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) et installé par défaut dans C:\Program Files\SurfaceUpdate.

### Version 1.42.139 
*Date de publication: 18 2019 septembre*

Cette version, incluse dans Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, met à jour le microprogramme en arrière-plan. 
**Valeurs de clé de Registre mises à jour:**<br>

- Component10CurrentFwVersion mis à jour sur **4ac3970**.
- Component20CurrentFwVersion mis à jour sur **4a1d570**.

La prise en charge de surface Pro 7 et de surface Laptop 3 est ajoutée.

## Versions héritées

### Version 2.23.139.0
*Date de publication: 10 octobre 2018*

Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:

- Ajouter la prise en charge de surface Pro 6
- Ajouter la prise en charge de surface Laptop 2


### Version 2.22.139.0
*Date de publication: 26 juillet 2018*

Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:

- Augmenter la fiabilité des mises à jour
- Ajouter la prise en charge de surface Go

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

