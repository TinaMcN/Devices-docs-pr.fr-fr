---
title: Résoudre les problèmes liés au MicrosoftSurfaceHub
description: Résolvez les problèmes courants, notamment les problèmes d’installation et les erreurs ExchangeActiveSync.
ms.assetid: CF58F74D-8077-48C3-981E-FCFDCA34B34A
ms.reviewer: ''
manager: laurawi
keywords: Résolvez les problèmes courants, notamment les problèmes d’installation et les erreurs ExchangeActiveSync.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2018
ms.localizationpriority: medium
ms.openlocfilehash: fe87c56474a05152f991a5b63f6abf0cf05e8b03
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832687"
---
# Résoudre les problèmes liés au Microsoft Surface Hub


Résolvez les problèmes courants, notamment les problèmes d’installation et les erreurs ExchangeActiveSync.

L’[outil de diagnostic du matériel Surface Hub](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab) contient des tests interactifs qui permettent de vérifier si les fonctionnalités essentielles de votre Hub correspondent aux résultats attendus. En plus des tests du matériel, le diagnostic permet de tester le compte de ressource pour vérifier qu’il est configuré correctement pour votre environnement. Si des problèmes surviennent, les résultats peuvent être enregistrés et partagés avec l’équipe du Support Surface Hub. Pour plus d’informations sur l’utilisation, consultez [Utilisation de l’outil de diagnostic du matériel Surface Hub pour tester un compte d’appareil](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun).

Les problèmes courants sont répertoriés dans le tableau suivant, de même que leurs causes et les solutions possibles. La section [Résolution des problèmes d’installation](#setup-troubleshooting) contient une liste des problèmes qui peuvent survenir sur l’appareil, ainsi que plusieurs types de problèmes qui peuvent se produire lors de sa première utilisation. La section [Erreurs ExchangeActiveSync](#exchange-activesync-errors) répertorie les erreurs courantes que l’appareil peut rencontrer lorsque vous essayez de le synchroniser avec un serveur MicrosoftExchangeActiveSync.




## Résolution des problèmes d’installation


Cette section répertorie les causes des problèmes et les solutions possibles pour faciliter la résolution des problèmes que vous risquez de rencontrer lors de l’installation de votre Microsoft SurfaceHub.

### Sur l’appareil

Solutions possibles aux problèmes survenant sur le SurfaceHub une fois le programme de première utilisation terminé.

<table>
<tr>
<th>Problème</th>
<th>Causes</th>
<th>Solutions possibles</th>
</tr>
<tr>
<td rowspan="2">
<p>Non-réception de messages automatiques d’acceptation/de refus.</p>
</td>
<td>
<p>Le compte d’appareil n’est pas configuré pour accepter/refuser les messages automatiquement.</p>
</td>
<td>
<p>Utilisez l’applet de commande PowerShell <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>.</p>
</td>
</tr>
<tr>
<td>
<p>Le compte d’appareil n’est pas configuré pour traiter les demandes de réunions externes.</p>
</td>
<td>
<p>Utilisez l’applet de commande PowerShell <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>.</p>
</td>
</tr>
<tr>
<td>
<p>Le calendrier ne s’affiche pas sur l’écran de démarrage ou le message «Rendez-vous à cette date (aucun compte configuré)» s’affiche.</p>
</td>
<td>
<p>Aucun compte d’appareil n’est configuré sur ce SurfaceHub.</p>
</td>
<td>
<p>Approvisionnez un compte d’appareil via Paramètres.</p>
</td>
</tr>
<tr>
<td>
<p>Le calendrier ne s’affiche pas sur l’écran de démarrage ou le message «Rendez-vous à cette date (compte surutilisé)» s’affiche.</p>
</td>
<td>
<p>Le compte d’appareil est approvisionné sur un trop grand nombre d’appareils.</p>
</td>
<td>
<p>Supprimez le compte d’appareil des autres appareils sur lesquels il est approvisionné. Vous pouvez le faire à l’aide du portail d’administration Exchange.</p>
</td>
</tr>
<tr>
<td>
<p>Le calendrier ne s’affiche pas sur l’écran de démarrage ou le message «Rendez-vous à cette date (informations d’identification non valides)» s’affiche.</p>
</td>
<td>
<p>Le mot de passe du compte d’appareil a expiré et n’est plus valide.</p>
</td>
<td>
<p>Mettez à jour le mot de passe du compte dans Paramètres. Consultez également <a href="password-management-for-surface-hub-device-accounts.md">Gestion des mots de passe</a>.</p>
</td>
</tr>
<tr>
<td>
<p>Le calendrier ne s’affiche pas sur l’écran de démarrage ou le message «Rendez-vous à cette date (stratégie de compte)» s’affiche.</p>
</td>
<td>
<p>Le compte d’appareil utilise une stratégie ActiveSync non valide.</p>
</td>
<td>
<p>Assurez-vous que le compte d’appareil dispose d’une stratégie ActiveSync où <code>PasswordEnabled == False</code>.</p>
</td>
</tr>
<tr>
<td>
<p>Le calendrier ne s’affiche pas sur l’écran de démarrage ou le message «Les rendez-vous ne sont peut-être pas à jour» s’affiche.</p>
</td>
<td>
<p>Exchange n’est pas activé.</p>
</td>
<td>Activer le compte d’appareil pour les services Exchange via Paramètres. Vous devez vous assurer que vous disposez de l’ensemble approprié de stratégies ActiveSync et que vous avez installé tous les certificats nécessaires au fonctionnement des services Exchange.</td>
</tr>
<tr>
<td>
<p>Impossible de se connecter à Skype Entreprise.</p>
</td>
<td>
<p>Le compte d’appareil ne possède pas de propriété d’adresse de protocoleSIP (Session Initiation Protocol).</p>
</td>
<td>
<p>Le compte ne possède pas de propriété d’adresse de protocoleSIP et son nom d’utilisateur principal (UPN) ne correspond pas à l’adresseSIP réelle. Le compte doit avoir son adresseSIP définie, ou l’adresseSIP doit être ajoutée à l’aide de l’application Paramètres.</p>
</td>
</tr>
<tr>
<td>
<p>Impossible de se connecter à SkypeEntreprise.</p>
</td>
<td>
<p>Le compte d’appareil nécessite un certificat pour s’authentifier à SkypeEntreprise.</p>
</td>
<td>
<p>Installez le certificat approprié à l’aide des packages de mise en service.</p>
</td>
</tr>
</table>
 

### Première utilisation

Solutions possibles aux problèmes survenant avec le programme de première utilisation de SurfaceHub.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problème</th>
<th align="left">Causes</th>
<th align="left">Solutions possibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Compte introuvable avec le domaine et le nom d’utilisateur.</p></td>
<td align="left"><p>Le domaine doit être le nom de domaine complet.</p></td>
<td align="left"><p>Le nom de domaine complet doit être fourni dans le champ Domaine.</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-device-acct-page"></a>Page Compte d’appareil, problèmes liés aux paramètres d’un nouveau compte

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problème</th>
<th align="left">Causes</th>
<th align="left">Solutions possibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Impossible de trouver le compte fourni dans AzureAD.</p></td>
<td align="left"><p>Le nom d’utilisateur principal (UPN) du compte fourni possède un client qui ne peut pas être contacté dans AzureAD.</p></td>
<td align="left"><p>Vérifiez que votre connexion Internet fonctionne et que l’appareil peut contacter MicrosoftOnlineServices. Assurez-vous que les informations d’identification de compte sont saisies correctement.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Impossible de contacter le répertoire spécifié.</p></td>
<td align="left"><p>Le domaine du compte fourni spécifie un domaine qui ne peut pas être contacté.</p></td>
<td align="left"><p>Vérifiez que votre connexion réseau fonctionne et que l’appareil peut contacter le contrôleur de domaine. Assurez-vous que les informations d’identification de compte sont saisies correctement. Vous pouvez également essayer d’utiliser le nom de domaine complet à la place.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Impossible de détecter automatiquement le serveur Exchange.</p></td>
<td align="left"><p>Le serveur Exchange n’est pas configuré pour la détection automatique.</p></td>
<td align="left"><p>Activez la détection automatique du serveur Exchange pour le compte d’appareil, ou saisissez manuellement l’adresse du serveur Exchange du compte.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Impossible de détecter l’adresseSIP après la saisie des informations d’identification de compte.</p></td>
<td align="left"><p>Il n’existait aucune entrée d’adresseSIP dans ActiveDirectory ou AzureAD.</p></td>
<td align="left"><p>Assurez-vous que le compte est activé avec SkypeEntreprise et qu’il dispose d’une adresseSIP. Si ce n’est pas le cas, vous pouvez saisir manuellement l’adresseSIP dans la zone de texte.</p></td>
</tr>
</tbody>
</table>

 

### Page Compte d’appareil, problèmes liés aux paramètres d’un compte existant

<table>
<tr>
<th>Problème</th>
<th>Causes</th>
<th>Codes d’erreur</th>
<th>Solutions possibles</th>
</tr>
<tr>
<td>
<p>Le compte n’a pas pu s’authentifier avec les informations d’identification spécifiées.</p>
</td>
<td>
<p>Le compte n’est pas activé en tant qu’utilisateur dans ActiveDirectory (AD), a besoin d’un mot de passe pour s’authentifier ou le mot de passe est incorrect.</p>
</td>
<td>
<p>None</p>
</td>
<td>
<p>Assurez-vous que les informations d’identification sont saisies correctement. Activez le compte en tant qu’utilisateur dans AD et ajoutez un mot de passe, ou définissez RoomMailboxPassword</p>. </td>
</tr>
<tr>
<td>
<p>L’erreur 0x800C0019 s’affiche lors de la fourniture d’un serveur Exchange.</p>
</td>
<td>
<p>Le compte d’appareil nécessite un certificat pour s’authentifier.</p>
</td>
<td>
<p>0x800C0019</p>
</td>
<td>
<p>Installez le certificat approprié à l’aide des packages de mise en service.</p>
</td>
</tr>
<tr>
<td>
<p>Les informations d’identification de compte d’appareil ne sont pas valides pour le serveur Exchange fourni.</p>
</td>
<td>
<p>Le serveur Exchange fourni ne se trouve pas à l’emplacement où la boîte aux lettres du compte d’appareil est hébergée.</p>
</td>
<td>
<p>None</p>
</td>
<td>
<p>Vérifiez que vous fournissez le serveur de messagerie Exchange approprié pour le compte d’appareil.</p>
</td>
</tr>
<tr>
<td>
<p>Expiration HTTP lors de la tentative de contact du serveur Exchange.</p>
</td>
<td></td>
<td>
<p>0x80072EE2</p>
</td>
<td></td>
</tr>
<tr>
<td>
<p>Serveur Exchange fourni introuvable.</p>
</td>
<td>
<p>Le serveur Exchange fourni est introuvable.</p>
</td>
<td>
<p>Aucun</p>
</td>
<td>
<p>Assurez-vous que votre connexion réseau ou Internet fonctionne et que le serveur Exchange que vous avez fourni est correct.</p>
</td>
</tr>
<tr>
<td>
<p>Protocole HTTP non pris en charge.</p>
</td>
<td>
<p>Un serveur Exchange avec <i>http://</i> à la place de <i>https://</i> a été fourni.</p>
</td>
<td>
<p>None</p>
</td>
<td>
<p>Utilisez un serveur Exchange qui utilise le protocole HTTPS.</p>
</td>
</tr>
<tr>
<td rowspan="3">
<div><p>Les utilisateurs arrivent sur la page intitulée «Ce compte présente un problème» concernant ActiveSync.</p>
</div>
<div> </div>
</td>
<td>
<p>La stratégie ActiveSync PasswordEnabled est définie sur True (ou 1).</p>
</td>
<td>
<p>None</p>
</td>
<td>
<p>Créez une politique ActiveSync où PasswordEnabled est défini sur False (ou 0), puis appliquez cette stratégie au compte.</p>
</td>
</tr>
<tr>
<td>
<p>Le SurfaceHub n’est pas connecté à Exchange.</p>
</td>
<td>
<p>Aucun</p>
</td>
<td>
<p>Vérifiez que vous disposez d’une connexion réseau ou Internet qui fonctionne.</p>
</td>
</tr>
<tr>
<td>
<p>Exchange renvoie un code d’état indiquant une erreur.</p>
</td>
<td>
<p>Aucun</p>
</td>
<td>
<p>Vérifiez que vous disposez d’une connexion réseau ou Internet qui fonctionne.</p>
</td>
</tr>
</table>
 

### <a href="" id="first-run-domain-join-page"></a>Première utilisation, problèmes de jonction de domaine

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problème</th>
<th align="left">Causes</th>
<th align="left">Solutions possibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Lorsque vous essayez de joindre un domaine, une erreur indique que le compte n’a pas pu s’authentifier à l’aide des informations d’identification spécifiées.</p></td>
<td align="left"><p>Les informations d’identification fournies ne sont pas en mesure de joindre le domaine spécifié.</p></td>
<td align="left"><p>Saisissez les informations d’identification correctes pour un compte qui existe dans le domaine spécifié.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Lorsque vous spécifiez un groupe d’un domaine, une erreur indique que le groupe est introuvable dans le domaine.</p></td>
<td align="left"><p>Il est possible que le groupe ait été supprimé ou qu’il n’existe plus.</p></td>
<td align="left"><p>Vérifiez que le groupe existe au sein du domaine.</p></td>
</tr>
</tbody>
</table>

 

### Première utilisation, page Serveur Exchange

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problème</th>
<th align="left">Causes</th>
<th align="left">Solutions possibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Les utilisateurs arrivent sur cette page et l’adresse du serveur Exchange leur est demandée.</p></td>
<td align="left"><p>Le serveur Exchange n’est pas configuré pour la détection automatique.</p></td>
<td align="left"><p>Activez la détection automatique du serveur Exchange pour le compte d’appareil, ou saisissez manuellement l’adresse du serveur Exchange du compte.</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-on-device"></a>Première utilisation, problèmes sur l’appareil

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problème</th>
<th align="left">Causes</th>
<th align="left">Codes d’erreur</th>
<th align="left">Solutions possibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Impossible de synchroniser le courrier/le calendrier.</p></td>
<td align="left"><p>Le compte n’a pas approuvé le SurfaceHub en tant qu’appareil autorisé.</p></td>
<td align="left"><p>0x86000C1C</p></td>
<td align="left"><p>Ajoutez l’ID de l’appareil surface Hub à la liste autorisée en définissant la <strong> </strong> propriété ActiveSyncAllowedDeviceIds de la boîte aux lettres.</p></td>
</tr>
</tbody>
</table>

 



 

## Erreurs ExchangeActiveSync


Cette section répertorie les codes d’état, les mappages, les messages des utilisateurs et les mesures qu’un administrateur peut prendre pour résoudre les erreurs ExchangeActiveSync.

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Code hexadécimal</th>
<th align="left">Mappage</th>
<th align="left">Message convivial</th>
<th align="left">Mesure que l’administrateur doit prendre</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>0x85010002</p></td>
<td align="left"><p>E_HTTP_DENIED</p></td>
<td align="left"><p>Le mot de passe doit être mis à jour.</p></td>
<td align="left"><p>Mettez à jour le mot de passe.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072EFD</p></td>
<td align="left"><p>WININET_E_CANNOT_CONNECT</p></td>
<td align="left"><p>Impossible de se connecter au serveur pour le moment. Patientez quelques instants et réessayez, ou vérifiez les paramètres du compte.</p></td>
<td align="left"><p>Vérifiez que le nom du serveur est correct et accessible. Vérifiez que l’appareil est connecté au réseau.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C29</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (les stratégies ne correspondent pas)</p></td>
<td align="left"><p>Le compte est configuré avec des stratégies non compatibles avec SurfaceHub.</p></td>
<td align="left"><p>Désactivez la stratégie <strong>PasswordEnabled</strong> pour ce compte.</p>
<p>Nous avons rencontré un bogue qui nous est peut-être lors de la mise en surface de la stratégie si le compte ne reçoit pas de notifications de serveur dans le cadre de l’intervalle d’actualisation</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C4C</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</p></td>
<td align="left"><p>Le compte possède trop de partenariats avec des appareils.</p></td>
<td align="left"><p>Supprimez un ou plusieurs partenariats sur le serveur.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C0A</p></td>
<td align="left"><p>E_NEXUS_STATUS_SERVERERROR_RETRYLATER</p></td>
<td align="left"><p>Impossible de se connecter au serveur pour le moment.</p></td>
<td align="left"><p>Patientez jusqu’à ce que le serveur revienne en ligne. Si le problème persiste, réapprovisionnez le compte.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050003</p></td>
<td align="left"><p>E_CREDENTIALS_EXPIRED (les informations d’identification ont expiré et doivent être mises à jour)</p></td>
<td align="left"><p>Le mot de passe doit être mis à jour.</p></td>
<td align="left"><p>Mettez à jour le mot de passe.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x8505000D</p></td>
<td align="left"><p>E_AIRSYNC_RESET_RETRY</p></td>
<td align="left"><p>Impossible de se connecter au serveur pour le moment. Veuillez patienter quelques instants ou vérifier les paramètres du compte.</p></td>
<td align="left"><p>Il s’agit normalement d’une erreur temporaire, mais si le problème persiste, vérifiez le nombre d’appareils associés au compte et supprimez certains d’entre eux s’il y en a trop.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C16</p></td>
<td align="left"><p>E_NEXUS_STATUS_USER_HASNOMAILBOX</p></td>
<td align="left"><p>La boîte aux lettres a migré vers un autre serveur.</p></td>
<td align="left"><p>Vous ne devriez jamais voir cette erreur. Si le problème persiste, réapprovisionnez le compte.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010004</p></td>
<td align="left"><p>E_HTTP_FORBIDDEN</p></td>
<td align="left"><p>Impossible de se connecter au serveur pour le moment. Patientez quelques instants, puis réessayez, ou vérifiez les paramètres du compte.</p></td>
<td align="left"><p>Vérifiez le nom du serveur pour vous assurer qu’il est correct. Si le compte utilise l’authentification basée sur la certification, assurez-vous que le certificat est toujours valide, et mettez-le à jour si ce n’est pas le cas.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85030028</p></td>
<td align="left"><p>E_ACTIVESYNC_PASSWORD_OR_GETCERT</p></td>
<td align="left"><p>Le mot de passe ou le certificat client du compte est manquant ou non valide.</p></td>
<td align="left"><p>Mettez à jour le mot de passe et/ou déployez le certificat client.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C2A</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_POLICYREFRESH</p></td>
<td align="left"><p>Le compte est configuré avec des stratégies non compatibles avec SurfaceHub.</p></td>
<td align="left"><p>Désactivez la stratégie PasswordEnabled pour ce compte.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050002</p></td>
<td align="left"><p>E_CREDENTIALS_UNAVAILABLE</p></td>
<td align="left"><p>Le mot de passe doit être mis à jour.</p></td>
<td align="left"><p>Mettez à jour le mot de passe.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE2</p></td>
<td align="left"><p>WININET_E_TIMEOUT</p></td>
<td align="left"><p>Le réseau ne prend pas en charge le délai d’inactivité minimal requis pour recevoir des notifications de serveur, ou le serveur est hors connexion.</p></td>
<td align="left"><p>Vérifiez que le serveur est en cours d’exécution. Vérifiez les paramètres NAT.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85002004</p></td>
<td align="left"><p>E_FAIL_ABORT</p></td>
<td align="left"><p>Cette erreur est utilisée pour interrompre la synchronisation en suspens et ne sera pas exposée aux utilisateurs. Elle s’affiche dans les données de diagnostic si vous forcez une synchronisation interactive, supprimez le compte ou mettez à jour ses paramètres.</p></td>
<td align="left"><p>Aucune.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010017</p></td>
<td align="left"><p>E_HTTP_SERVICE_UNAVAIL</p></td>
<td align="left"><p>Impossible de se connecter au serveur pour le moment. Veuillez patienter quelques instants ou vérifier les paramètres du compte.</p></td>
<td align="left"><p>Vérifiez le nom du serveur pour vous assurer qu’il est correct. Patientez jusqu’à ce que le serveur revienne en ligne. Si le problème persiste, réapprovisionnez le compte.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C0D</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</p></td>
<td align="left"><p>Impossible de se connecter au serveur pour le moment. Veuillez patienter quelques instants ou vérifier les paramètres du compte.</p></td>
<td align="left"><p>Vérifiez le nom du serveur pour vous assurer qu’il est correct. Patientez jusqu’à ce que le serveur revienne en ligne. Si le problème persiste, réapprovisionnez le compte.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85030027</p></td>
<td align="left"><p>E_ACTIVESYNC_GETCERT</p></td>
<td align="left"><p>Le serveur Exchange exige un certificat.</p></td>
<td align="left"><p>Importez le certificat EAS approprié sur le SurfaceHub.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C2B</p></td>
<td align="left"><p>E_NEXUS_STATUS_INVALID_POLICYKEY</p></td>
<td align="left"><p>Le compte est configuré avec des stratégies non compatibles avec SurfaceHub.</p></td>
<td align="left"><p>Désactivez la stratégie PasswordEnabled pour ce compte.</p>
<p>Nous avons rencontré un bogue qui nous est peut-être lors de la mise en surface de la stratégie si le compte ne reçoit pas de notifications de serveur dans le cadre de l’intervalle d’actualisation</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010005</p></td>
<td align="left"><p>E_HTTP_NOT_FOUND</p></td>
<td align="left"><p>Le nom du serveur est non valide.</p></td>
<td align="left"><p>Vérifiez le nom du serveur pour vous assurer qu’il est correct. Si le problème persiste, réapprovisionnez le compte.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85010014</p></td>
<td align="left"><p>E_HTTP_SERVER_ERROR</p></td>
<td align="left"><p>Impossible de se connecter au serveur.</p></td>
<td align="left"><p>Vérifiez le nom du serveur pour vous assurer qu’il est correct. Déclenchez une synchronisation et, si le problème persiste, réapprovisionnez le compte.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE7</p></td>
<td align="left"><p>WININET_E_NAME_NOT_RESOLVED</p></td>
<td align="left"><p>Impossible de résoudre le nom du serveur ou l’adresse.</p></td>
<td align="left"><p>Assurez-vous que le nom du serveur est saisi correctement.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x8007052F</p></td>
<td align="left"><p>ERROR_ACCOUNT_RESTRICTION</p></td>
<td align="left"><p>Lors de la détection automatique du serveur Exchange, une stratégie est appliquée et empêche l’utilisateur connecté de se connecter au serveur.</p></td>
<td align="left"><p>Il s’agit d’un problème de minutage. Vérifiez de nouveau les informations d’identification de compte. Si elles sont correctes, essayez de les réapprovisionner.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x800C0019</p></td>
<td align="left"><p>INET_E_INVALID_CERTIFICATE</p></td>
<td align="left"><p>Le certificat de sécurité requis pour accéder à cette ressource est non valide.</p></td>
<td align="left"><p>Installez le certificat ActiveSync approprié nécessaire pour le compte d’appareil fourni.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072F0D</p></td>
<td align="left"><p>WININET_E_INVALID_CA</p></td>
<td align="left"><p>L’autorité de certification est non valide ou incorrecte. Impossible de détecter automatiquement un serveur Exchange car il manque un certificat.</p></td>
<td align="left"><p>Installez le certificat ActiveSync approprié nécessaire pour le compte d’appareil fourni.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80004005</p></td>
<td align="left"><p>E_FAIL</p></td>
<td align="left"><p>Le domaine fourni est introuvable. Le serveur Exchange n’a pas pu être détecté automatiquement et n’a pas été fourni dans les paramètres.</p></td>
<td align="left"><p>Assurez-vous que le domaine saisi est le nom de domaine complet, et qu’un serveur Exchange est saisi dans la zone de texte Serveur Exchange.</p></td>
</tr>
</tbody>
</table>

## Contacter le support

Si vous avez des questions ou si vous avez besoin d’aide, vous pouvez [créer une demande de support](https://support.microsoft.com/supportforbusiness/productselection).


 
## Contenu associé

- [Résolution des problèmes de connexion de Miracast au Surface Hub](https://docs.microsoft.com/surface-hub/miracast-troubleshooting)
 





