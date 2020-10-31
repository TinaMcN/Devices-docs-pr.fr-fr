---
title: Utiliser le Kit de ressources de diagnostic pour Surface Entreprise en mode bureau
description: Comment utiliser le SDT pour aider les utilisateurs de votre organisation à exécuter l’outil d’identification et de diagnostic des problèmes liés à l’appareil surface, ainsi que l’envoi des demandes de support directement à partir de l’outil.
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
ms.date: 7/31/2020
ms.openlocfilehash: 8b113d16f2053fe0904518b2643f1bafeaebdf64
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145939"
---
# Utiliser le Kit de ressources de diagnostic pour Surface Entreprise en mode bureau

Cette rubrique explique comment utiliser le kit de ressources de diagnostic de surface (SDT) pour aider les utilisateurs au sein de votre organisation à exécuter l’outil d’identification et de diagnostic des problèmes liés à leur appareil surface, ainsi que l’envoi de demandes de support technique directement à partir de l’outil. 

L’exécution réussie de SDT peut déterminer rapidement si un problème signalé est lié à un problème de matériel ou d’erreur d’utilisateur. Pour obtenir la liste des appareils surface pris en charge dans le SDT, voir [déploiement de surface diagnostic Toolkit pour les entreprises](surface-diagnostic-toolkit-business.md).


1. Demandez à l’utilisateur d’installer [le package SDT](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution)) à partir d’un point de distribution de logiciels ou d’un partage réseau. Une fois l’installation terminée, vous pouvez guider l’utilisateur dans le cadre d’une série de tests. 

2. Commencez sur la page d’accueil, qui permet aux utilisateurs d’entrer une description du problème, puis cliquez sur **Continuer**, comme illustré dans la figure 1.

    ![Démarrer le SDT en mode Bureau ](images/sdt-desk-1.png)
 *figure 1. SDT en mode Bureau*

3. Lorsque le SDT indique que l’appareil comporte les mises à jour les plus récentes, cliquez sur **Continuer** pour accéder au catalogue de tests disponibles, comme illustré dans la figure 2.

    ![Sélectionnez à partir des options SDT ](images/sdt1.png)
 *figure 2. Sélectionner à partir des options SDT*

4. Vous pouvez choisir d’exécuter tous les tests de diagnostic. Ou, si vous soupçonnez un problème particulier tel qu’un affichage défectueux ou un problème d’alimentation électrique, cliquez sur **Sélectionner** pour effectuer votre choix parmi les tests disponibles, puis cliquez sur **exécuter la sélection**, comme illustré dans la figure 3. Pour plus d’informations sur chaque test, consultez le tableau suivant. 

    ![Sélectionnez tests matériels ](images/sdt2.png)
 *figure 3. Sélectionner tests matériels*

    Test du matériel | Description
    --- | ---
    Alimentation électrique et batterie |  Vérifie que l’alimentation secteur fonctionne de façon optimale.
    Affichage et son   | Contrôle le fonctionnement de la luminosité, du son coincé ou du micro
    Ports et accessoires   | Vérifie les accessoires, l’ajout d’écran et le fonctionnement USB
    Connectivité |  Vérifie la connectivité Bluetooth, sans fil et LTE
    Sécurité    | Vérifie les problèmes liés à la sécurité
    Commandes tactiles   | Vérifie les problèmes liés à l’interaction
    Clavier et fonctions vocales |    Vérifie la connexion au clavier intégrée et la couverture de type
    Capteurs | Vérifie le fonctionnement de différents capteurs dans l’appareil.
    Matériel |  Vérifie les problèmes liés à différents composants matériels tels que la carte graphique et l’appareil photo

5. Lorsque tous les tests sont terminés, l’outil vous demande de confirmer que le problème est résolu. 

 ![Votre problème est-il résolu? ](images/sdt3.png)
 *Figure 3A. avez-vous résolu le problème?*

6. Si le problème n’est pas résolu ou que vous ne le connaissez pas, vous pouvez lui envoyer un ticket de support en sélectionnant **Contactez-nous** pour **obtenir de l’aide.**
 
 ![Envoyez un ticket d’assistance ](images/sdt4.png)
 *figure 3b. soumission d’un ticket de support*

<span id="multiple" />

## Exécution de plusieurs tests matériels pour résoudre les problèmes

Le SDT est conçu comme un outil interactif qui exécute une série de tests. Pour chaque test, le SDT fournit des instructions résumant la nature du test, ainsi que les utilisateurs qui doivent s’attendre à la réussite pour le test. Par exemple, pour diagnostiquer le bon fonctionnement de la luminosité de l’écran, le SDT démarre à zéro et augmente la luminosité à 100 pour cent, demandant aux utilisateurs de confirmer, en répondant à **Yes** ou **no** --la luminosité fonctionne comme prévu, comme illustré dans la figure 4. 

Pour chaque test, si la fonctionnalité ne fonctionne pas comme prévu et que l’utilisateur clique sur **non**, Sdt génère un rapport des causes possibles et des moyens de résoudre les problèmes. 

![Exécution des tests de diagnostic de matériel ](images/sdt-desk-4.png)
 *figure 4. Exécution de diagnostics de matériel*

1. Si la luminosité est ajustée à partir de 0-100% comme prévu, demandez à l’utilisateur de cliquer sur **Oui** , puis cliquez sur **Continuer**. 
2. Si la luminosité ne s’ajuste pas à partir de 0-100% comme prévu, demandez à l’utilisateur de cliquer sur **non** , puis sur **Continuer**. 
3. Guidez les utilisateurs dans les tests restants, le cas échéant. Lorsque vous avez terminé, SDT fournit automatiquement une synthèse générale du rapport, y compris les causes possibles des problèmes matériels et des recommandations en matière de résolution.


### Réparation d’applications

Le SDT vous permet de diagnostiquer et réparer des applications susceptibles de causer des problèmes, comme illustré dans la figure 5.

![Exécution des réparations ](images/sdt-desk-5.png)
 *figure 5. Exécution des réparations*
<span id="logs" />

### Génération de journaux pour l’analyse des problèmes 

SDT fournit une prise en charge complète du diagnostic compatible avec les applications, les pilotes, le matériel et les problèmes de système d’exploitation, comme illustré dans la figure 6.

![Génération de journaux ](images/sdt-desk-6.png)
 *figure 6. Génération de journaux*

<span id="detailed-report" />

### Génération d’un rapport détaillé comparant l’appareil et la configuration optimale

D’après les journaux, SDT génère un rapport pour les problèmes de logiciels et de microprogrammes que vous pouvez enregistrer dans un emplacement préféré.

## Rubriques associées

- [Exécuter le Kit de ressources de diagnostic pour Surface Entreprise à l’aide de commandes](surface-diagnostic-toolkit-command-line.md)

