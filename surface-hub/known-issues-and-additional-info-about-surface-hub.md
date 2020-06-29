---
title: Problèmes connus et informations supplémentaires sur le Microsoft SurfaceHub
description: Décrit les problèmes connus liés à Microsoft surface Hub.
ms.assetid: aee90a0c-fb05-466e-a2b1-92de89d0f2b7
keywords: surface, concentrateur, problèmes
ms.prod: surface-hub
ms.sitesec: library
author: todmccoy
ms.author: v-todmc
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: ec6746098203b5e91e2aaf3b044d21b81c31c897
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833090"
---
# Problèmes connus et informations supplémentaires sur le Microsoft SurfaceHub

Nous sommes à votre écoute. La qualité est une priorité élevée et nous voulons vous informer des problèmes affectant les clients. Voici quelques-uns des problèmes connus de Microsoft surface Hub:

- **Skype entreprise n’utilise pas de proxy pour le trafic multimédia avec RS2**
<br/>Pour certains utilisateurs de surface Hub qui se trouvent derrière un proxy, Skype entreprise n’utilise pas le serveur proxy pour les médias. Toutefois, le Hub surface est en mesure de se connecter au compte. Nous avons reçu vos commentaires et sommes informés du problème du trafic multimédia lors de l’utilisation de proxy. Nous étudions activement ce problème et mettrons à jour les correctifs dès qu’une solution sera identifiée et testée. 

- **S’il s’agit d’un appareil das joint, lorsqu’un utilisateur tente de se connecter à «mes réunions & fichiers», surface Hub signale qu’il n’y a pas de connexion Internet**
<br/>Nous avons pris en charge un ensemble de problèmes affectant la connexion et l’accès aux documents sur surface Hub. Nous cherchons activement ces problèmes. Pour contourner ce problème, les clients peuvent réinitialiser leurs périphériques et configurer leur concentrateur pour qu’ils utilisent un compte d’administrateur local. Après avoir reconfiguré pour utiliser le compte d’administrateur local, «mes réunions et fichiers» fonctionneront comme prévu.
- **Connexion unique lors de la participation d’Azure AD**
<br/>Surface Hub a été conçu pour les espaces de la surface communale, ce qui a un impact sur le mode de stockage des informations d’identification de l’utilisateur. C’est la raison pour laquelle il existe actuellement des limitations sur le fonctionnement de l’authentification unique lorsque des appareils sont liés à Azure AD. Microsoft est consciente de cette limitation et examine activement les options de résolution.
- **La projection d’infrastructure Miracast sur surface Hub ne fonctionne pas si le centre de surface a un caractère point (.) dans le nom convivial**
<br/>Les utilisateurs de surface Hub peuvent éprouver des difficultés à se projeter sur leur appareil si le nom convivial inclut un point ou point (.)--par exemple, «CONF. Room42». Pour contourner ce problème, remplacez le nom convivial du Hub dans les **paramètres**  >  **surface Hub**  >  **About**, puis redémarrez l’appareil. Microsoft travaille actuellement à la résolution de ce problème.