---
title: Désinscrire des appareils surface de SEMM (surface)
description: Apprenez à annuler l’inscription d’un appareil à partir d’SEMM à l’aide d’un package de réinitialisation UEFI de surface ou de l’option de demande de récupération.
keywords: gestion des entreprises de surface
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: aa24ff1ac8a93ebc8078490c5e0c8fa34c940a25
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832472"
---
# Désinscrire les appareils Surface de SEMM

Lorsqu’un appareil surface est inscrit en mode de gestion de surface Enterprise (SEMM), un certificat est stocké dans le microprogramme de cet appareil. La présence de ce certificat et l’inscription dans SEMM empêchent toute modification non autorisée des paramètres ou des options de surface UEFI lors de l’inscription de l’appareil dans SEMM. Pour restaurer le contrôle des paramètres de surface UEFI pour l’utilisateur, le périphérique surface doit être désinscrit de SEMM, un processus parfois décrit en tant que réinitialisation ou récupération. Il existe deux méthodes qui vous permettent d’annuler l’inscription d’un appareil à partir de SEMM: package de réinitialisation UEFI de surface et demande de récupération.

>[!WARNING]
>Pour désinscrire un appareil de SEMM et restaurer le contrôle utilisateur des paramètres de surface UEFI, vous devez disposer du certificat SEMM utilisé pour inscrire l’appareil dans SEMM. Si ce certificat est perdu ou endommagé, il n’est pas possible de procéder à l’annulation de l’inscription à partir de SEMM. Sauvegardez et protégez votre certificat SEMM en conséquence.

Pour plus d’informations sur SEMM, voir [Microsoft surface Enterprise Management mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

## Annuler l’inscription d’un appareil surface à partir de SEMM avec un package de réinitialisation UEFI de surface

Le package de réinitialisation de surface UEFI est la méthode principale utilisée pour annuler l’inscription d’un appareil surface à partir de SEMM. À l’instar d’un package de configuration UEFI de surface, le package de réinitialisation est un fichier Windows Installer (. msi) qui configure SEMM sur l’appareil. Contrairement au package de configuration, le package de réinitialisation restaure la configuration de surface UEFI sur un appareil surface avec ses paramètres par défaut, supprime le certificat SEMM et annuler l’inscription de l’appareil à partir de SEMM.

Les packages de réinitialisation sont créés spécifiquement pour un appareil surface individuel. Pour commencer le processus de création d’un package de réinitialisation, vous aurez besoin du numéro de série de l’appareil que vous voulez annuler, ainsi que du certificat SEMM utilisé pour inscrire l’appareil. Vous pouvez trouver le numéro de série de votre périphérique surface dans la page informations sur le **PC** de surface UEFI, comme illustré dans la figure 1. Cette page s’affiche, même si la surface UEFI est protégée par mot de passe et que le mot de passe incorrect est entré.

![Le numéro de série de l’appareil surface est affiché.](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*Figure1. Le numéro de série de l’appareil surface est affiché dans la page informations sur le PC surface UEFI.*

>[!NOTE]
>Pour démarrer sur surface UEFI, appuyez simultanément sur **volume** et **alimentation** . Mettre le **volume** en attente jusqu’à ce que le logo de la surface s’affiche et que l’appareil commence à démarrer.

Pour créer un package de réinitialisation UEFI de surface, procédez comme suit:

1. Ouvrez le configurateur Microsoft surface UEFI à partir du menu Démarrer.
2. Cliquez sur **Démarrer**.
3. Cliquez sur **Réinitialiser le package**, comme illustré dans la figure 2.

   ![Sélectionnez Réinitialiser le package pour créer un package pour l’inscription de l’appareil surface de SEMM](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *Figure2. Cliquez sur Réinitialiser le package pour créer un package permettant d’annuler l’inscription d’un appareil surface à partir de SEMM*

4. Cliquez sur **protection des certificats** pour ajouter votre fichier de certificat SEMM avec la clé privée (. pfx), comme illustré dans la figure 3. Naviguez jusqu’à l’emplacement de votre fichier de certificat, sélectionnez le fichier, puis cliquez sur **OK**.

   ![Ajouter le certificat SEMM au package de réinitialisation UEFI de surface](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *Figure3. Ajouter le certificat SEMM à un package de réinitialisation de surface UEFI*

5. Cliquez sur **Suivant**.
6. Tapez le numéro de série de l’appareil que vous voulez annuler de SEMM (comme illustré dans la figure 4), puis cliquez sur **générer** pour générer le package de réinitialisation UEFI de surface.

   ![Créer un package de réinitialisation de surface UEFI avec le numéro de série de l’appareil surface](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *Figure4. Utiliser le numéro de série de votre périphérique surface pour créer un package de réinitialisation UEFI surface*

7. Dans la boîte de dialogue **Enregistrer sous** , spécifiez un nom pour le package de réinitialisation UEFI de surface, naviguez jusqu’à l’emplacement où vous souhaitez enregistrer le fichier, puis cliquez sur **Enregistrer**.
8. Lorsque la génération du package est terminée, **la page qui** s’affiche est affichée. Cliquez sur **Terminer** pour terminer la création du package et fermer le configurateur Microsoft surface UEFI.

Exécutez le fichier Windows Installer (. msi) package de réinitialisation de surface UEFI sur le périphérique surface pour annuler l’inscription de l’appareil à partir de SEMM. Le package de réinitialisation nécessite un redémarrage pour procéder à l’annulation de l’inscription. Après l’annulation de l’inscription de l’appareil, vous pouvez vérifier la suppression réussie en vous assurant que l’élément **package de configuration de surface Microsoft** dans les **programmes et fonctionnalités** (illustré dans la figure 5) n’est plus présent.

![Écran montrant que l’appareil est inscrit à SEMM](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*Figure5. La présence de l’élément package de configuration de surface Microsoft dans les programmes et fonctionnalités indique que l’appareil est inscrit à SEMM*

## Désinscrire un appareil surface d’SEMM avec une demande de récupération

Dans certains cas, un package de réinitialisation UEFI de surface peut ne pas être une option viable pour annuler l’inscription d’un appareil surface à partir de SEMM (par exemple, lorsque Windows est devenu inutilisable). Dans ces scénarios, vous pouvez désinscrire l’appareil à l’aide d’une requête de récupération générée à partir de surface UEFI. Le processus de requête de récupération peut être démarré même sur les appareils sur lesquels vous n’avez pas le mot de passe surface UEFI.

Le processus de requête de récupération est lancé à partir de surface UEFI sur le périphérique surface, approuvé avec le configurateur Microsoft surface UEFI sur un autre ordinateur, puis exécuté dans surface UEFI. Comme le package de réinitialisation, l’approbation d’une demande de récupération auprès du configurateur Microsoft surface UEFI nécessite l’accès au certificat SEMM utilisé pour inscrire le périphérique surface.

Pour initier une demande de récupération, procédez comme suit:

1. Amorcez le périphérique surface qui doit être désinscrit de SEMM à surface UEFI.
2. Tapez le mot de passe UEFI surface si vous êtes invité à le faire.
3. Cliquez sur la page gestion de l' **entreprise** , comme illustré dans la figure 6.

   ![Page gestion d’entreprise](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *Figure6. La page gestion d’entreprise s’affiche dans surface UEFI sur les appareils inscrits dans SEMM*

4. Cliquez ou appuyez sur **commencer**.
5. Cliquez ou appuyez sur **suivant** pour démarrer le processus de demande de récupération.
   >[!NOTE]
   >Une demande de récupération expire deux heures après sa création. Si une demande de récupération n’est pas exécutée pour le moment, vous devez redémarrer le processus de demande de récupération.
6. Sélectionnez **SEMM certificat** dans la liste des certificats affichée dans la page **choisir une clé de réinitialisation SEMM** (illustrée dans la figure 7), puis cliquez ou appuyez sur **suivant**.

   ![Sélectionner le certificat SEMM pour votre demande de récupération](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *Figure7. Choisissez le certificat SEMM de votre demande de récupération (demande de réinitialisation)*

7. Dans la page **Entrez le code de vérification de réinitialisation SEMM** , vous pouvez cliquer sur le **code QR** ou sur les boutons de **texte** pour afficher votre demande de récupération (requête de réinitialisation), comme illustré dans la figure 8 ou le bouton **USB** pour enregistrer votre demande de récupération (demande de réinitialisation) en tant que fichier sur un lecteur USB, comme illustré dans la figure 9

   ![Demande de récupération affichée sous forme de code QR](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *Figure8. Une demande de récupération (demande de réinitialisation) affichée en tant que code QR*

   ![Enregistrer une demande de récupération sur un lecteur USB](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *Figure9. Enregistrer une demande de récupération (demande de réinitialisation) sur un lecteur USB*

   * Pour utiliser une demande de récupération de code QR (demande de réinitialisation), utilisez une application de lecture QR sur un appareil mobile pour lire le code. L’application de lecture QR traduit le code QR en une chaîne alphanumérique. Vous pouvez ensuite envoyer par courrier électronique ou envoyer par message une chaîne à l’administrateur qui génère le code de vérification de réinitialisation à l’aide du configurateur Microsoft surface UEFI.
   * Pour utiliser une requête de récupération (demande de réinitialisation) enregistrée sur un lecteur USB comme fichier, utilisez le lecteur USB pour transférer le fichier sur l’ordinateur sur lequel le configurateur Microsoft surface UEFI sera utilisé pour générer le code de vérification de réinitialisation. Le fichier peut également être copié à partir du lecteur USB sur un autre appareil pour être envoyé par courrier électronique ou transféré via le réseau.
   * Pour utiliser la demande de récupération en tant que texte, il vous suffit de taper le texte directement dans le configurateur Microsoft surface UEFI.

8. Ouvrez le configurateur Microsoft surface UEFI à partir du menu Démarrer sur un autre ordinateur.
    >[!NOTE]
    >Le configurateur Microsoft surface UEFI doit s’exécuter dans un environnement capable d’authentifier la chaîne de certificats pour le certificat SEMM.
9. Cliquez sur **Démarrer**.
10. Cliquez sur **demande de récupération**, comme illustré dans la figure 10.

    ![Démarrer le processus d’approbation d’une demande de récupération](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *Figure10. Cliquez sur demande de récupération pour commencer le processus d’approbation d’une demande de récupération*

11. Cliquez sur **protection des certificats** pour authentifier la demande de récupération avec le certificat SEMM.
12. Accédez à votre fichier de certificat SEMM et sélectionnez-le, puis cliquez sur **OK**.
13. Lorsque vous êtes invité à entrer le mot de passe de certificat comme illustré dans la figure 11, tapez et confirmez le mot de passe du fichier de certificat, puis cliquez sur **OK**.

    ![Tapez un mot de passe pour le certificat SEMM](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *Figure11. Tapez le mot de passe pour le certificat SEMM*

14. Cliquez sur **Suivant**.
15. Entrez la demande de récupération (requête de réinitialisation), puis cliquez sur **générer** pour créer un code de vérification de réinitialisation (comme illustré dans la figure 12).

    ![Entrer la demande de récupération](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *Figure12. Entrer la demande de récupération (demande de réinitialisation)*

    * Si vous avez affiché la demande de récupération (demande de réinitialisation) en tant que texte de réinitialisation de l’appareil surface, utilisez le clavier pour entrer la demande de récupération (requête de réinitialisation) dans le champ fourni.
    * Si vous avez affiché la demande de récupération (demande de réinitialisation) en tant que code QR, puis utilisé une application de messagerie ou de messagerie pour envoyer le code à l’ordinateur à l’aide du configurateur Microsoft surface UEFI, copiez et collez le code dans le champ fourni.
    * Si vous avez enregistré la demande de récupération (requête de réinitialisation) comme fichier pour un lecteur USB, cliquez sur le bouton **Importer** , recherchez et sélectionnez le fichier de demande de récupération (demande de réinitialisation), puis cliquez sur **OK**.

16. Le code de vérification de réinitialisation est affiché dans le configurateur Microsoft surface UEFI, comme illustré dans la figure 13.

    ![Affichage du code de vérification de réinitialisation](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *Figure13. Le code de vérification de réinitialisation affiché dans le configurateur Microsoft surface UEFI*

    * Cliquez sur le bouton **partager** pour envoyer le code de vérification de réinitialisation par courrier électronique.

17. Entrez le code de vérification de réinitialisation dans le champ fourni sur le périphérique surface (illustré dans la figure 8), puis cliquez ou appuyez sur **vérifier** pour réinitialiser l’appareil et annuler l’inscription de l’appareil à partir de SEMM.
18. Cliquez ou appuyez sur **redémarrer maintenant** dans la page **réinitialisation réussie de SEMM** pour terminer l’inscription de SEMM, comme illustré dans la figure 14.

    ![Exemple d’affichage de l’annulation de l’inscription réussie de SEMM](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *Figure14. Désinscription réussie de SEMM*

19. Cliquez sur **fin** dans Microsoft surface UEFI Configurator pour terminer le processus de demande de récupération (demande de réinitialisation) et de fermeture du configurateur Microsoft surface UEFI.


