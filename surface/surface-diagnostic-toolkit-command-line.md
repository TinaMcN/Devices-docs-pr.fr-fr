---
title: Exécuter le Kit de ressources de diagnostic pour Surface Entreprise à l’aide de commandes
description: Comment exécuter surface Diagnostic Shared Computer Toolkit dans une console de commande
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
ms.openlocfilehash: f3856499bd769b96e22c0a47323c984eb38d8a18
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327328"
---
# Exécuter le Kit de ressources de diagnostic pour Surface Entreprise à l’aide de commandes

L’exécution du Shared Computer Toolkit de diagnostic Surface (SDT) à l’invite de commandes nécessite le téléchargement de la console d’application SDT. Une fois l’installation installée, vous pouvez exécuter SDT à une invite de commandes via la console de commandes Windows (cmd.exe) ou à l’aide de Windows PowerShell, y compris l’environnement de script intégré à PowerShell (ISE), qui permet la prise en charge de lacomplément automatique des commandes, du copier-coller et d’autres fonctionnalités.  Pour obtenir la liste des appareils Surface pris en charge dans SDT, reportez-vous à [Deploy Surface Diagnostic Shared Computer Toolkit for Business](surface-diagnostic-toolkit-business.md).

>[!NOTE]
>Pour exécuter SDT à l’aide de commandes, vous devez être connecté au compte Administrateur ou connecté à un compte membre du groupe Administrateur sur votre appareil Surface.

## Exécution de la console d’application SDT

Téléchargez et installez la console d’application SDT à partir de la page de [téléchargement des outils Surface pour l’informatique.](https://www.microsoft.com/download/details.aspx?id=46703) Vous pouvez utiliser l’invite de commandes Windows (cmd.exe) ou Windows PowerShell pour : 

- Collectez tous les fichiers journaux.
- Exécutez des diagnostics d’état à l’aide de Best Practice Analyzer.
- Recherchez les mises à jour du microprogramme ou des pilotes manquantes dans la mise à jour.

>[!NOTE]
>Dans cette version, la console d’application SDT prend en charge les commandes simples uniquement. L’exécution de plusieurs options de ligne de commande nécessite l’exécution de la console séparément pour chaque commande. 

Par défaut, les fichiers de sortie sont enregistrés au même emplacement que l’application console. Reportez-vous au tableau suivant pour obtenir la liste complète des commandes.

Commande | Remarques
--- | ---
-DataCollector «fichier de sortie» | Collecte les détails système dans un fichier zip. « fichier de sortie » est le chemin d’accès au fichier pour créer le fichier zip des détails système.<br><br>**Exemple**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa «fichier de sortie» | Vérifie plusieurs paramètres et indicateurs d’intégrité dans l’appareil. « fichier de sortie » est le chemin d’accès au fichier pour créer le rapport HTML.<br><br>**Exemple**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Vérifie si les mises à jour du microprogramme et/ou des pilotes sont manquantes sur les serveurs En ligne de Windows Update.<br><br>**Exemple**:<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-warranty «output file» | Vérifie les informations de garantie sur l’appareil (valides ou non valides). Le « fichier de sortie » facultatif est le chemin d’accès au fichier pour créer le fichier xml. <br><br>**Exemple**: <br>Microsoft.Surface.Diagnostics.App.Console.exe –warranty «warranty.xml»


>[!NOTE]
>Pour exécuter la console d’application SDT à distance sur les appareils cibles, vous pouvez utiliser un outil de gestion de la configuration tel que Microsoft Endpoint Configuration Manager. Vous pouvez également créer un fichier .zip contenant l’application console et les commandes de console appropriées, puis déployer selon les processus de distribution de logiciels de votre organisation. 

## Exécution de Best Practice Analyzer 

Vous pouvez exécuter des tests BPA sur des composants clés tels que BitLocker, démarrage sécurisé et module de plateforme sécurisée (TPM), puis produire les résultats dans un fichier partageable. L’outil génère une série de tableaux avec des titres et des descripteurs de condition codés en couleur, ainsi que des instructions sur la façon d’aborder la résolution du problème. 

- Le vert indique que le composant est en cours d’exécution dans une condition optimale (optimale).
- Orange indique que le composant n’est pas en cours d’exécution dans une condition optimale (pas optimale).
- Le rouge indique que le composant est dans un état anormal. 

### Exemple de résultat BPA

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si BitLocker est activé sur le lecteur système.</td></tr>
<tr><td><strong>Valeur :</strong></td><td>Protection sur</td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="00ff00">Optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td>Il est vivement recommandé d’activer BitLocker pour protéger vos données.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Démarrage sécurisé</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si le démarrage sécurisé est activé.</td></tr>
<tr><td><strong>Valeur :</strong></td><td>Vrai</td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="00ff00">Optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td>Il est vivement recommandé d’activer le démarrage sécurisé pour protéger votre PC.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Module de plateforme sécurisée</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Garantit que le TPM est fonctionnel.</td></tr>
<tr><td><strong>Valeur :</strong></td><td>Vrai</td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="00ff00">Optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td>Sans TPM fonctionnel, les fonctions de sécurité telles que BitLocker risquent de ne pas fonctionner correctement.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Veille connectée</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si la veille connectée est activée.</td></tr>
<tr><td><strong>Valeur :</strong></td><td>Vrai</td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="00ff00">Optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td>La veille connectée permet à un appareil Surface de recevoir des mises à jour et des notifications sans être utilisé. Pour une expérience de meilleure expérience, la veille connectée doit être activée.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Bluetooth</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si Bluetooth est activé.</td></tr>
<tr><td><strong>Valeur :</strong></td><td>Activé</td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="00ff00">Optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Mode débogage</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si le système d’exploitation est en mode débogage.</td></tr>
<tr><td><strong>Valeur :</strong></td><td>Normal</td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="00ff00">Optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td>L’option de démarrage de débogage active ou désactive le débogage du noyau du système d’exploitation Windows. L’activation de cette option peut provoquer l’instabilité du système et empêcher la lecture des supports protégés par des droits numériques (DRM).</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Signature de test</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si la signature de test est activée.</td></tr>
<tr><td><strong>Valeur :</strong></td><td>Normal</td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="00ff00">Optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td>La signature de test est un paramètre de démarrage Windows qui doit uniquement être utilisé pour tester les pilotes de version pré-version.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Plan d’alimentation actif</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie que le plan d’alimentation correct est actif.</td></tr>
<tr><td><strong>Valeur :</strong></td><td>Équilibrée</td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="00ff00">Optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td>Il est vivement recommandé d’utiliser le plan d’alimentation « équilibré » pour optimiser la productivité et l’autonomie de la batterie.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows Update</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Vérifie si l’appareil est à jour avec les mises à jour Windows.</td></tr>
<tr><td><strong>Valeur :</strong></td><td>Microsoft Silverlight (KB4023307), Mise à jour des définitions pour l’antivirus Windows Defender - KB2267602 (définition 1.279.1433.0)</td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="ff9500">Non optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td>La mise à jour vers les dernières fenêtres vous permet de vous assurer que vous êtes sur les derniers microprogrammes et pilotes. Il est recommandé de toujours maintenir votre appareil à jour</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Espace disque libre</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Recherche l’espace disque libre faible.</td></tr>
<tr><td><strong>Valeur :</strong></td><td>66%</td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="00ff00">Optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td>Pour de meilleures performances, votre disque dur doit avoir au moins 10 % de sa capacité en tant qu’espace libre.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Appareils non fonctionnels</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Liste des appareils qui ne fonctionnent pas dans le Gestionnaire de périphériques.</td></tr>
<tr><td><strong>Valeur :</strong></td><td></td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="00ff00">Optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td>Les appareils qui ne fonctionnent pas dans le Gestionnaire de périphériques peuvent entraîner des problèmes imprévisibles avec les appareils Surface, tels que, sans s’y limiter, aucune économie d’énergie pour le composant matériel respectif.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Moniteur externe</font></th></tr>
<tr><td><strong>Description:</strong></td><td>Recherche un moniteur externe qui peut avoir des problèmes de compatibilité.</td></tr>
<tr><td><strong>Valeur :</strong></td><td></td></tr>
<tr><td><strong>Condition :</strong></td><td><font color="00ff00">Optimal</font></td></tr>
<tr><td><strong>Conseils :</strong></td><td>Vérifiez la compatibilité avec votre appareil Surface auprès du fabricant de l’équipement d’origine.</td></tr>
</table>
