---
title: Exécuter le Kit de ressources de diagnostic pour Surface Entreprise à l’aide de commandes
description: Exécuter le kit de diagnostic de surface dans une console de commande
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 6a56e1231ff5d2f672305d7166bbfa46d1bc0354
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832238"
---
# Exécuter le Kit de ressources de diagnostic pour Surface Entreprise à l’aide de commandes

L’exécution du service de diagnostic de surface (SDT) à une invite de commandes nécessite le téléchargement de la console de l’application STD. Une fois l’installation effectuée, vous pouvez exécuter SDT à une invite de commandes via la console de commandes Windows (cmd.exe) ou à l’aide de Windows PowerShell, y compris l’environnement d’écriture de script intégré PowerShell (ISE), qui prend en charge la saisie semi-automatique des commandes, le copier/coller et d’autres fonctionnalités.  Pour obtenir la liste des appareils surface pris en charge dans le SDT, voir [déploiement de surface diagnostic Toolkit pour les entreprises](surface-diagnostic-toolkit-business.md).

>[!NOTE]
>Pour exécuter SDT à l’aide de commandes, vous devez être connecté au compte d’administrateur ou connecté à un compte membre du groupe Administrateurs sur votre appareil surface.

## Exécution de la console de l’application SDT

Téléchargez et installez la console de l’application SDT à partir de la [page de téléchargement des outils surface](https://www.microsoft.com/download/details.aspx?id=46703). L’invite de commandes Windows (cmd.exe) ou Windows PowerShell vous permet d’effectuer les opérations suivantes: 

- Collectez tous les fichiers journaux.
- Exécutez des diagnostics d’intégrité à l’aide de la méthode recommandée Analyzer.
- Recherchez les mises à jour de microprogramme ou de pilote manquantes.

>[!NOTE]
>Dans cette version, la console de l’application SDT ne prend en charge que les commandes uniques. L’exécution de plusieurs options de ligne de commande implique l’exécution séparée de la console exe pour chaque commande. 

Par défaut, les fichiers de sortie sont enregistrés au même emplacement que l’application console. Pour obtenir la liste complète des commandes, consultez le tableau suivant.

Commande | Remarques
--- | ---
-DataCollector "fichier de sortie" | Collecte les informations système dans un fichier zip. «fichier de sortie» est le chemin d’accès du fichier pour créer le fichier zip des détails système.<br><br>**Exemple**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-fichier de sortie BPA | Vérifie plusieurs paramètres et indicateurs d’intégrité dans l’appareil. «fichier de sortie» est le chemin d’accès au fichier pour créer le rapport HTML.<br><br>**Exemple**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Vérifie quels sont les mises à jour de microprogramme et/ou de pilote manquantes sur les serveurs Windows Update online.<br><br>**Exemple**:<br>Microsoft.Surface.Diagnostics.App.Console.exe-windowsupdate
"fichier de sortie" | Vérifie les informations de garantie sur le périphérique (valides ou non valides). Le «fichier de sortie» facultatif correspond au chemin d’accès de fichier pour créer le fichier XML. <br><br>**Exemple**: <br>Microsoft.Surface.Diagnostics.App.Console.exe: garantie "warranty.xml"


>[!NOTE]
>Pour exécuter la console de l’application SDT à distance sur les appareils cibles, vous pouvez utiliser un outil de gestion de la configuration tel que Microsoft Endpoint Configuration Manager. Vous pouvez également créer un fichier. zip contenant l’application console et des commandes de console appropriées, puis déployer conformément aux processus de distribution de logiciels de votre organisation. 

## Exécution de l’analyseur de meilleures pratiques 

Vous pouvez exécuter des tests BPA sur les principaux composants tels que BitLocker, démarrage sécurisé et module de plateforme sécurisée (TPM), puis générer les résultats dans un fichier partageable. L’outil génère une série de tableaux avec des en-têtes et des descripteurs de condition avec des codes couleur, ainsi que des recommandations sur la résolution du problème. 

- La couleur verte indique que le composant s’exécute dans une condition optimale (optimale).
- Orange indique que le composant n’est pas en cours d’exécution dans une condition optimale (non optimale).
- Rouge indique que le composant se trouve dans un état anormal. 

### Exemples de résultat BPA

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si BitLocker est activé sur le lecteur système.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td>Protection activée</td></tr>
<tr><td><strong>Autant</strong></td><td><font color="00ff00">Solution</font></td></tr>
<tr><td><strong>Relatives</strong></td><td>Il est vivement recommandé d’activer BitLocker pour protéger vos données.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Démarrage sécurisé</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si le démarrage sécurisé est activé.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td>Vrai</td></tr>
<tr><td><strong>Autant</strong></td><td><font color="00ff00">Solution</font></td></tr>
<tr><td><strong>Relatives</strong></td><td>Il est vivement recommandé d’activer le démarrage sécurisé pour protéger votre PC.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Module de plateforme sécurisée</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie que le TPM fonctionne.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td>Vrai</td></tr>
<tr><td><strong>Autant</strong></td><td><font color="00ff00">Solution</font></td></tr>
<tr><td><strong>Relatives</strong></td><td>Sans module de plateforme sécurisée fonctionnelle, il est possible que les fonctions de sécurité telles que BitLocker ne fonctionnent pas correctement.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Veille connectée</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si la mise en veille connectée est activée.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td>Vrai</td></tr>
<tr><td><strong>Autant</strong></td><td><font color="00ff00">Solution</font></td></tr>
<tr><td><strong>Relatives</strong></td><td>La veille connectée permet à un appareil surface de recevoir des mises à jour et des notifications en cas d’absence d’utilisation. Pour une utilisation optimale, la veille connectée doit être activée.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Bluetooth</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si la technologie Bluetooth est activée.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td>Activé</td></tr>
<tr><td><strong>Autant</strong></td><td><font color="00ff00">Solution</font></td></tr>
<tr><td><strong>Relatives</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Mode débogage</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si le système d’exploitation est en mode débogage.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td>Normal</td></tr>
<tr><td><strong>Autant</strong></td><td><font color="00ff00">Solution</font></td></tr>
<tr><td><strong>Relatives</strong></td><td>L’option de démarrage de débogage active ou désactive le débogage du noyau du système d’exploitation Windows. L’activation de cette option peut entraîner une instabilité du système et peut empêcher la lecture de contenus DRM (Digital Rights managemend).</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Test de la signature</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si la signature de test est activée.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td>Normal</td></tr>
<tr><td><strong>Autant</strong></td><td><font color="00ff00">Solution</font></td></tr>
<tr><td><strong>Relatives</strong></td><td>Le test de signature est un paramètre de démarrage de Windows qui doit uniquement être utilisé pour tester les pilotes précommercials.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Plan d’alimentation actif</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie que le mode de gestion de l’alimentation approprié est actif.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td>Manquant</td></tr>
<tr><td><strong>Autant</strong></td><td><font color="00ff00">Solution</font></td></tr>
<tr><td><strong>Relatives</strong></td><td>Il est vivement recommandé d’utiliser le plan d’alimentation «équilibré» pour optimiser la productivité et l’autonomie de la batterie.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">WindowsUpdate</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si le périphérique est à jour avec les mises à jour Windows.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td>Microsoft Silverlight (KB4023307), mise à jour de définition pour l’antivirus Windows Defender-KB2267602 (définition 1.279.1433.0)</td></tr>
<tr><td><strong>Autant</strong></td><td><font color="ff9500">Non optimal</font></td></tr>
<tr><td><strong>Relatives</strong></td><td>La mise à jour vers la dernière version de Windows assure que vous utilisez les derniers microprogrammes et pilotes. Il est recommandé de toujours tenir à jour votre appareil</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Espace disque disponible</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie l’espace disque disponible.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td>66%</td></tr>
<tr><td><strong>Autant</strong></td><td><font color="00ff00">Solution</font></td></tr>
<tr><td><strong>Relatives</strong></td><td>Pour des performances optimales, votre disque dur doit avoir au moins 10% de sa capacité d’espace libre.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Appareils non fonctionnels</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Liste des appareils qui ne fonctionnent pas dans le gestionnaire de périphériques.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td></td></tr>
<tr><td><strong>Autant</strong></td><td><font color="00ff00">Solution</font></td></tr>
<tr><td><strong>Relatives</strong></td><td>Les appareils non fonctionnels dans le gestionnaire de périphériques peuvent entraîner des problèmes inattendus liés à des appareils surface tels que, mais sans s’y limiter, à des problèmes d’économie d’énergie liés aux composants matériels correspondants.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Moniteur externe</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Recherche un moniteur externe susceptible de rencontrer des problèmes de compatibilité.</td></tr>
<tr><td><strong>Ajoutée</strong></td><td></td></tr>
<tr><td><strong>Autant</strong></td><td><font color="00ff00">Solution</font></td></tr>
<tr><td><strong>Relatives</strong></td><td>Vérifiez auprès du fabricant d’équipements d’origine la compatibilité avec votre périphérique surface.</td></tr>
</table>
