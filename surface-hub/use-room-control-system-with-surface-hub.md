---
title: Utilisation d’un système de contrôle d’espace (Surface Hub)
description: Les systèmes de contrôle d’espace peuvent être utilisés avec votre Microsoft Surface Hub.
ms.assetid: DC365002-6B35-45C5-A2B8-3E1EB0CB8B50
ms.reviewer: ''
manager: laurawi
keywords: système de contrôle d’espace, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0e3b1706e58edb6e37156eda8d06fb0faefa4c91
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832652"
---
# <span data-ttu-id="6d20a-104">Utilisation d’un système de contrôle d’espace (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="6d20a-104">Using a room control system (Surface Hub)</span></span>


<span data-ttu-id="6d20a-105">Les systèmes de contrôle d’espace peuvent être utilisés avec votre Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="6d20a-105">Room control systems can be used with your Microsoft Surface Hub.</span></span>

<span data-ttu-id="6d20a-106">L’utilisation d’un système de contrôle d’espace avec Surface Hub implique la connexion du matériel de contrôle d’espace au Surface Hub, généralement via le port série RJ11 situé au bas du Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="6d20a-106">Using a room control system with your Surface Hub involves connecting room control hardware to the Surface Hub, usually through the RJ11 serial port on the bottom of the Surface Hub.</span></span>

## <span data-ttu-id="6d20a-107">Paramètres du terminal</span><span class="sxs-lookup"><span data-stu-id="6d20a-107">Terminal settings</span></span>

<span data-ttu-id="6d20a-108">La connexion à un système de contrôle d’espace ne nécessite pas la configuration de paramètres du terminal sur le Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="6d20a-108">To connect to a room control system control panel, you don't need to configure any terminal settings on the Surface Hub.</span></span> <span data-ttu-id="6d20a-109">Si vous voulez connecter un PC ou un ordinateur portable à votre Surface Hub et envoyer des commandes de série à partir de ce dernier, vous pouvez utiliser un programme d’émulation de terminal tel que Tera Term ou PuTTY.</span><span class="sxs-lookup"><span data-stu-id="6d20a-109">If you want to connect a PC or laptop to your Surface Hub and send serial commands from the Surface Hub, you can use a terminal emulator program like Tera Term or PuTTY.</span></span> 

| <span data-ttu-id="6d20a-110">Paramètre</span><span class="sxs-lookup"><span data-stu-id="6d20a-110">Setting</span></span> | <span data-ttu-id="6d20a-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="6d20a-111">Value</span></span> |
| --- | --- |
| <span data-ttu-id="6d20a-112">Vitesse (en bauds)</span><span class="sxs-lookup"><span data-stu-id="6d20a-112">Baud rate</span></span> | <span data-ttu-id="6d20a-113">115200</span><span class="sxs-lookup"><span data-stu-id="6d20a-113">115200</span></span> |
| <span data-ttu-id="6d20a-114">Bits de données</span><span class="sxs-lookup"><span data-stu-id="6d20a-114">Data bits</span></span> | <span data-ttu-id="6d20a-115">version8</span><span class="sxs-lookup"><span data-stu-id="6d20a-115">8</span></span> | 
| <span data-ttu-id="6d20a-116">Bits d’arrêt</span><span class="sxs-lookup"><span data-stu-id="6d20a-116">Stop bits</span></span> | <span data-ttu-id="6d20a-117">1</span><span class="sxs-lookup"><span data-stu-id="6d20a-117">1</span></span> |
| <span data-ttu-id="6d20a-118">Parité</span><span class="sxs-lookup"><span data-stu-id="6d20a-118">Parity</span></span> | <span data-ttu-id="6d20a-119">aucun</span><span class="sxs-lookup"><span data-stu-id="6d20a-119">none</span></span> |
| <span data-ttu-id="6d20a-120">Contrôle de flux</span><span class="sxs-lookup"><span data-stu-id="6d20a-120">Flow control</span></span> | <span data-ttu-id="6d20a-121">aucun</span><span class="sxs-lookup"><span data-stu-id="6d20a-121">none</span></span> |
| <span data-ttu-id="6d20a-122">Saut de ligne</span><span class="sxs-lookup"><span data-stu-id="6d20a-122">Line feed</span></span> | <span data-ttu-id="6d20a-123">chaque retour chariot</span><span class="sxs-lookup"><span data-stu-id="6d20a-123">every carriage return</span></span> |
 

## <span data-ttu-id="6d20a-124">Diagramme de connexion</span><span class="sxs-lookup"><span data-stu-id="6d20a-124">Wiring diagram</span></span>

<span data-ttu-id="6d20a-125">Vous pouvez utiliser un connecteur RJ-11 (6P6C) standard pour la connexion au port série Surface Hub à un système de contrôle d’espace.</span><span class="sxs-lookup"><span data-stu-id="6d20a-125">You can use a standard RJ-11 (6P6C) connector to connect the Surface Hub serial port to a room control system.</span></span> <span data-ttu-id="6d20a-126">Il s’agit de la méthode recommandée.</span><span class="sxs-lookup"><span data-stu-id="6d20a-126">This is the recommended method.</span></span> <span data-ttu-id="6d20a-127">Vous pouvez également utiliser un câble conducteur à 4fils RJ-11, toutefois cette méthode n’est pas recommandée.</span><span class="sxs-lookup"><span data-stu-id="6d20a-127">You can also use an RJ-11 4-conductor cable, but we do not recommend this method.</span></span>

<span data-ttu-id="6d20a-128">Ce diagramme montre le brochage correct utilisé pour un connecteur RJ-11 (6P6C) vers un câble DB9.</span><span class="sxs-lookup"><span data-stu-id="6d20a-128">This diagram shows the correct pinout used for an RJ-11 (6P6C) to DB9 cable.</span></span>

![Image illustrant le schéma de connexion.](images/room-control-wiring-diagram.png)

## <span data-ttu-id="6d20a-130">Jeux de commandes</span><span class="sxs-lookup"><span data-stu-id="6d20a-130">Command sets</span></span>

<span data-ttu-id="6d20a-131">Les systèmes de contrôle d’espace utilisent des scénarios de salle courants pour les commandes.</span><span class="sxs-lookup"><span data-stu-id="6d20a-131">Room control systems use common meeting-room scenarios for commands.</span></span> <span data-ttu-id="6d20a-132">Les commandes sont issues du système de contrôle d’espace et communiquées via une connexion en série au Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="6d20a-132">Commands originate from the room control system, and are communicated over a serial connection to a Surface Hub.</span></span> <span data-ttu-id="6d20a-133">Il s’agit de commandes ASCII. Le Surface Hub reconnaît la survenue d’un changement d’état.</span><span class="sxs-lookup"><span data-stu-id="6d20a-133">Commands are ASCII based, and the Surface Hub will acknowledge when state changes occur.</span></span>

<span data-ttu-id="6d20a-134">Les modificateurs de commande suivants sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="6d20a-134">The following command modifiers are available.</span></span> <span data-ttu-id="6d20a-135">Les commandes se terminent par un saut de ligne (\n).</span><span class="sxs-lookup"><span data-stu-id="6d20a-135">Commands terminate with a new line character (\n).</span></span> <span data-ttu-id="6d20a-136">Les réponses peuvent survenir à tout moment en réaction aux changements d’état qui ne sont pas déclenchés directement par une commande du port de gestion.</span><span class="sxs-lookup"><span data-stu-id="6d20a-136">Responses can come at any time in response to state changes not triggered directly by a management port command.</span></span>

| <span data-ttu-id="6d20a-137">Modificateur</span><span class="sxs-lookup"><span data-stu-id="6d20a-137">Modifier</span></span> | <span data-ttu-id="6d20a-138">Résultat</span><span class="sxs-lookup"><span data-stu-id="6d20a-138">Result</span></span> |
| --- | --- |
| + | <span data-ttu-id="6d20a-139">Incrémente une valeur</span><span class="sxs-lookup"><span data-stu-id="6d20a-139">Increment a value</span></span> |
| - | <span data-ttu-id="6d20a-140">Réduit une valeur</span><span class="sxs-lookup"><span data-stu-id="6d20a-140">Decrease a value</span></span> |
| = | <span data-ttu-id="6d20a-141">Définir une valeur discrète</span><span class="sxs-lookup"><span data-stu-id="6d20a-141">Set a discrete value</span></span> |
| <span data-ttu-id="6d20a-142">?</span><span class="sxs-lookup"><span data-stu-id="6d20a-142">?</span></span> | <span data-ttu-id="6d20a-143">Requêtes pour une valeur actuelle</span><span class="sxs-lookup"><span data-stu-id="6d20a-143">Queries for a current value</span></span> |
 

## <span data-ttu-id="6d20a-144">Alimentation</span><span class="sxs-lookup"><span data-stu-id="6d20a-144">Power</span></span>

<span data-ttu-id="6d20a-145">Le Surface Hub peut se trouver dans l’un des états suivants:</span><span class="sxs-lookup"><span data-stu-id="6d20a-145">Surface Hub can be in one of these power states.</span></span>

| <span data-ttu-id="6d20a-146">État</span><span class="sxs-lookup"><span data-stu-id="6d20a-146">State</span></span> | <span data-ttu-id="6d20a-147">État Energy Star</span><span class="sxs-lookup"><span data-stu-id="6d20a-147">Energy Star state</span></span>| <span data-ttu-id="6d20a-148">Description</span><span class="sxs-lookup"><span data-stu-id="6d20a-148">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="6d20a-149">0,4</span><span class="sxs-lookup"><span data-stu-id="6d20a-149">0</span></span> | <span data-ttu-id="6d20a-150">S5</span><span class="sxs-lookup"><span data-stu-id="6d20a-150">S5</span></span> | <span data-ttu-id="6d20a-151">Désactivé</span><span class="sxs-lookup"><span data-stu-id="6d20a-151">Off</span></span> |
| <span data-ttu-id="6d20a-152">1</span><span class="sxs-lookup"><span data-stu-id="6d20a-152">1</span></span> | - | <span data-ttu-id="6d20a-153">Mise sous tension (indéterminé)</span><span class="sxs-lookup"><span data-stu-id="6d20a-153">Power up (indeterminate)</span></span> |
| <span data-ttu-id="6d20a-154">deuxième</span><span class="sxs-lookup"><span data-stu-id="6d20a-154">2</span></span> | <span data-ttu-id="6d20a-155">S3</span><span class="sxs-lookup"><span data-stu-id="6d20a-155">S3</span></span> | <span data-ttu-id="6d20a-156">Veille</span><span class="sxs-lookup"><span data-stu-id="6d20a-156">Sleep</span></span> |
| <span data-ttu-id="6d20a-157">n°5</span><span class="sxs-lookup"><span data-stu-id="6d20a-157">5</span></span> | <span data-ttu-id="6d20a-158">S0</span><span class="sxs-lookup"><span data-stu-id="6d20a-158">S0</span></span> | <span data-ttu-id="6d20a-159">Prêt</span><span class="sxs-lookup"><span data-stu-id="6d20a-159">Ready</span></span> |


<span data-ttu-id="6d20a-160">En mode PC de remplacement, les états d’alimentation sont uniquement Prêt et Désactivé et modifient seulement l’affichage.</span><span class="sxs-lookup"><span data-stu-id="6d20a-160">In Replacement PC mode, the power states are only Ready and Off and only change the display.</span></span> <span data-ttu-id="6d20a-161">Le port de gestion ne permet pas de mettre le PC de remplacement sous tension.</span><span class="sxs-lookup"><span data-stu-id="6d20a-161">The management port can't be used to power on the replacement PC.</span></span> 

| <span data-ttu-id="6d20a-162">État</span><span class="sxs-lookup"><span data-stu-id="6d20a-162">State</span></span> | <span data-ttu-id="6d20a-163">État Energy Star</span><span class="sxs-lookup"><span data-stu-id="6d20a-163">Energy Star state</span></span>| <span data-ttu-id="6d20a-164">Description</span><span class="sxs-lookup"><span data-stu-id="6d20a-164">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="6d20a-165">0,4</span><span class="sxs-lookup"><span data-stu-id="6d20a-165">0</span></span> | <span data-ttu-id="6d20a-166">S5</span><span class="sxs-lookup"><span data-stu-id="6d20a-166">S5</span></span> | <span data-ttu-id="6d20a-167">Désactivé</span><span class="sxs-lookup"><span data-stu-id="6d20a-167">Off</span></span> |
| <span data-ttu-id="6d20a-168">n°5</span><span class="sxs-lookup"><span data-stu-id="6d20a-168">5</span></span> | <span data-ttu-id="6d20a-169">S0</span><span class="sxs-lookup"><span data-stu-id="6d20a-169">S0</span></span> | <span data-ttu-id="6d20a-170">Prêt</span><span class="sxs-lookup"><span data-stu-id="6d20a-170">Ready</span></span> |

<span data-ttu-id="6d20a-171">Pour un appareil de contrôle, tout autre état que 5/Prêt doit être considéré comme désactivé.</span><span class="sxs-lookup"><span data-stu-id="6d20a-171">For a control device, anything other than 5 / Ready should be considered off.</span></span> <span data-ttu-id="6d20a-172">Chaque commande PowerOn génère deux modifications et réponses d’État.</span><span class="sxs-lookup"><span data-stu-id="6d20a-172">Each PowerOn command results in two state changes and responses.</span></span> 

| <span data-ttu-id="6d20a-173">Commande</span><span class="sxs-lookup"><span data-stu-id="6d20a-173">Command</span></span> | <span data-ttu-id="6d20a-174">Changement d’état</span><span class="sxs-lookup"><span data-stu-id="6d20a-174">State change</span></span>| <span data-ttu-id="6d20a-175">Réponse</span><span class="sxs-lookup"><span data-stu-id="6d20a-175">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="6d20a-176">PowerOn</span><span class="sxs-lookup"><span data-stu-id="6d20a-176">PowerOn</span></span> | <span data-ttu-id="6d20a-177">L’appareil se met sous tension (écran + PC).</span><span class="sxs-lookup"><span data-stu-id="6d20a-177">Device turns on (display + PC).</span></span></br></br><span data-ttu-id="6d20a-178">Le service du PC informe le SMC que le PC est prêt.</span><span class="sxs-lookup"><span data-stu-id="6d20a-178">PC service notifies SMC that the PC is ready.</span></span> |  <span data-ttu-id="6d20a-179">Power=0</span><span class="sxs-lookup"><span data-stu-id="6d20a-179">Power=0</span></span></br></br><span data-ttu-id="6d20a-180">Power=5</span><span class="sxs-lookup"><span data-stu-id="6d20a-180">Power=5</span></span> |
| <span data-ttu-id="6d20a-181">PowerOff</span><span class="sxs-lookup"><span data-stu-id="6d20a-181">PowerOff</span></span> | <span data-ttu-id="6d20a-182">L’appareil passe à l’état ambiant (PC allumé, assombrissement de l’affichage).</span><span class="sxs-lookup"><span data-stu-id="6d20a-182">Device transitions to ambient state (PC on, display dim).</span></span> |  <span data-ttu-id="6d20a-183">Power=0</span><span class="sxs-lookup"><span data-stu-id="6d20a-183">Power=0</span></span> |
| <span data-ttu-id="6d20a-184">Power?</span><span class="sxs-lookup"><span data-stu-id="6d20a-184">Power?</span></span> |  <span data-ttu-id="6d20a-185">Le SMC indique le dernier état d’alimentation connu.</span><span class="sxs-lookup"><span data-stu-id="6d20a-185">SMC reports the last-known power state.</span></span> |  <span data-ttu-id="6d20a-186">Marche/Arrêt=<#></span><span class="sxs-lookup"><span data-stu-id="6d20a-186">Power=<#></span></span> |



## <span data-ttu-id="6d20a-187">Luminosité</span><span class="sxs-lookup"><span data-stu-id="6d20a-187">Brightness</span></span>

<span data-ttu-id="6d20a-188">Le niveau de luminosité actuel est une plage comprise entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="6d20a-188">The current brightness level is a range from 0 to 100.</span></span>

<span data-ttu-id="6d20a-189">Les modifications apportées aux niveaux de luminosité peuvent être envoyées par un système de contrôle d’espace ou d’autres systèmes.</span><span class="sxs-lookup"><span data-stu-id="6d20a-189">Changes to brightness levels can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="6d20a-190">Commande</span><span class="sxs-lookup"><span data-stu-id="6d20a-190">Command</span></span> | <span data-ttu-id="6d20a-191">Changement d’état</span><span class="sxs-lookup"><span data-stu-id="6d20a-191">State change</span></span> |<span data-ttu-id="6d20a-192">Réponse</span><span class="sxs-lookup"><span data-stu-id="6d20a-192">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="6d20a-193">Brightness+</span><span class="sxs-lookup"><span data-stu-id="6d20a-193">Brightness+</span></span> | <span data-ttu-id="6d20a-194">Le contrôleur de gestion de système (SMC) envoie la commande d’augmentation de la luminosité.</span><span class="sxs-lookup"><span data-stu-id="6d20a-194">System management controller (SMC) sends the brightness up command.</span></span></br></br><span data-ttu-id="6d20a-195">Le service du PC du système de contrôle d’espace informe le SMC du nouveau niveau de luminosité.</span><span class="sxs-lookup"><span data-stu-id="6d20a-195">PC service on the room control system notifies SMC of new brightness level.</span></span> |  <span data-ttu-id="6d20a-196">Brightness = 51</span><span class="sxs-lookup"><span data-stu-id="6d20a-196">Brightness = 51</span></span> |
| <span data-ttu-id="6d20a-197">Brightness-</span><span class="sxs-lookup"><span data-stu-id="6d20a-197">Brightness-</span></span> |  <span data-ttu-id="6d20a-198">Le SMC envoie la commande de réduction de la luminosité.</span><span class="sxs-lookup"><span data-stu-id="6d20a-198">SMC sends the brightness down command.</span></span></br></br><span data-ttu-id="6d20a-199">Le service du PC informe le SMC du nouveau niveau de luminosité.</span><span class="sxs-lookup"><span data-stu-id="6d20a-199">PC service notifies SMC of new brightness level.</span></span> | <span data-ttu-id="6d20a-200">Brightness = 50</span><span class="sxs-lookup"><span data-stu-id="6d20a-200">Brightness = 50</span></span> |

## <span data-ttu-id="6d20a-201">Volume</span><span class="sxs-lookup"><span data-stu-id="6d20a-201">Volume</span></span>

<span data-ttu-id="6d20a-202">Le niveau de volume actuel est une plage comprise entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="6d20a-202">The current volume level is a range from 0 to 100.</span></span>

<span data-ttu-id="6d20a-203">Les modifications apportées aux niveaux de volume peuvent être envoyées par un système de contrôle d’espace ou d’autres systèmes.</span><span class="sxs-lookup"><span data-stu-id="6d20a-203">Changes to volume levels can be sent by a room control system, or other system.</span></span>

>[!NOTE]
><span data-ttu-id="6d20a-204">La commande Volume contrôle uniquement le volume pour le mode incorporé ou le mode PC de remplacement, pas à partir de [sources invitées](connect-and-display-with-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="6d20a-204">The Volume command will only control the volume for embedded or Replacement PC mode, not from [Guest sources](connect-and-display-with-surface-hub.md).</span></span>

| <span data-ttu-id="6d20a-205">Commande</span><span class="sxs-lookup"><span data-stu-id="6d20a-205">Command</span></span> | <span data-ttu-id="6d20a-206">Changement d’état</span><span class="sxs-lookup"><span data-stu-id="6d20a-206">State change</span></span> | <span data-ttu-id="6d20a-207">Réponse</span><span class="sxs-lookup"><span data-stu-id="6d20a-207">Response</span></span></br><span data-ttu-id="6d20a-208">(Activée en [ModePC de remplacement](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span><span class="sxs-lookup"><span data-stu-id="6d20a-208">(On in [Replacement PC mode](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span></span> |
| --- | --- | --- |
| <span data-ttu-id="6d20a-209">Volume+</span><span class="sxs-lookup"><span data-stu-id="6d20a-209">Volume+</span></span> |  <span data-ttu-id="6d20a-210">Le SMC envoie la commande d’augmentation du volume.</span><span class="sxs-lookup"><span data-stu-id="6d20a-210">SMC sends the volume up command.</span></span></br></br><span data-ttu-id="6d20a-211">Le service du PC informe le SMC du nouveau niveau de volume.</span><span class="sxs-lookup"><span data-stu-id="6d20a-211">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="6d20a-212">Volume = 51</span><span class="sxs-lookup"><span data-stu-id="6d20a-212">Volume = 51</span></span> |
| <span data-ttu-id="6d20a-213">Volume-</span><span class="sxs-lookup"><span data-stu-id="6d20a-213">Volume-</span></span> |  <span data-ttu-id="6d20a-214">Le SMC envoie la commande de baisse du volume.</span><span class="sxs-lookup"><span data-stu-id="6d20a-214">SMC sends the volume down command.</span></span></br></br><span data-ttu-id="6d20a-215">Le service du PC informe le SMC du nouveau niveau de volume.</span><span class="sxs-lookup"><span data-stu-id="6d20a-215">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="6d20a-216">Volume = 50</span><span class="sxs-lookup"><span data-stu-id="6d20a-216">Volume = 50</span></span> |


 

## <span data-ttu-id="6d20a-217">Désactivation du son</span><span class="sxs-lookup"><span data-stu-id="6d20a-217">Mute for audio</span></span>

<span data-ttu-id="6d20a-218">Le son peut être désactivé.</span><span class="sxs-lookup"><span data-stu-id="6d20a-218">Audio can be muted.</span></span>

| <span data-ttu-id="6d20a-219">Commande</span><span class="sxs-lookup"><span data-stu-id="6d20a-219">Command</span></span> | <span data-ttu-id="6d20a-220">Changement d’état</span><span class="sxs-lookup"><span data-stu-id="6d20a-220">State change</span></span> | <span data-ttu-id="6d20a-221">Réponse</span><span class="sxs-lookup"><span data-stu-id="6d20a-221">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="6d20a-222">AudioMute+</span><span class="sxs-lookup"><span data-stu-id="6d20a-222">AudioMute+</span></span> |  <span data-ttu-id="6d20a-223">Le SMC envoie la commande de désactivation du son.</span><span class="sxs-lookup"><span data-stu-id="6d20a-223">SMC sends the audio mute command.</span></span></br></br><span data-ttu-id="6d20a-224">Le service du PC informe le SMC que le son est désactivé.</span><span class="sxs-lookup"><span data-stu-id="6d20a-224">PC service notifies SMC that audio is muted.</span></span> |  <span data-ttu-id="6d20a-225">aucune</span><span class="sxs-lookup"><span data-stu-id="6d20a-225">none</span></span> |


 

## <span data-ttu-id="6d20a-226">Source vidéo</span><span class="sxs-lookup"><span data-stu-id="6d20a-226">Video source</span></span>

<span data-ttu-id="6d20a-227">Plusieurs sources vidéo peuvent être utilisées.</span><span class="sxs-lookup"><span data-stu-id="6d20a-227">Several display sources can be used.</span></span>

| <span data-ttu-id="6d20a-228">État</span><span class="sxs-lookup"><span data-stu-id="6d20a-228">State</span></span> | <span data-ttu-id="6d20a-229">Description</span><span class="sxs-lookup"><span data-stu-id="6d20a-229">Description</span></span> | 
| --- | --- |
| <span data-ttu-id="6d20a-230">0,4</span><span class="sxs-lookup"><span data-stu-id="6d20a-230">0</span></span> |  <span data-ttu-id="6d20a-231">PC intégré</span><span class="sxs-lookup"><span data-stu-id="6d20a-231">Onboard PC</span></span> |
| <span data-ttu-id="6d20a-232">1</span><span class="sxs-lookup"><span data-stu-id="6d20a-232">1</span></span> |  <span data-ttu-id="6d20a-233">DisplayPort</span><span class="sxs-lookup"><span data-stu-id="6d20a-233">DisplayPort</span></span> |
| <span data-ttu-id="6d20a-234">deuxième</span><span class="sxs-lookup"><span data-stu-id="6d20a-234">2</span></span> |  <span data-ttu-id="6d20a-235">HDMI</span><span class="sxs-lookup"><span data-stu-id="6d20a-235">HDMI</span></span> |
| <span data-ttu-id="6d20a-236">3D</span><span class="sxs-lookup"><span data-stu-id="6d20a-236">3</span></span> |  <span data-ttu-id="6d20a-237">VGA</span><span class="sxs-lookup"><span data-stu-id="6d20a-237">VGA</span></span> |


 

<span data-ttu-id="6d20a-238">Les modifications apportées à la source vidéo peuvent être envoyées par un système de contrôle d’espace ou d’autres systèmes.</span><span class="sxs-lookup"><span data-stu-id="6d20a-238">Changes to display source can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="6d20a-239">Commande</span><span class="sxs-lookup"><span data-stu-id="6d20a-239">Command</span></span> | <span data-ttu-id="6d20a-240">Changement d’état</span><span class="sxs-lookup"><span data-stu-id="6d20a-240">State change</span></span> | <span data-ttu-id="6d20a-241">Réponse</span><span class="sxs-lookup"><span data-stu-id="6d20a-241">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="6d20a-242">Source=#</span><span class="sxs-lookup"><span data-stu-id="6d20a-242">Source=#</span></span> |  <span data-ttu-id="6d20a-243">Modifications SMC à la source souhaitée.</span><span class="sxs-lookup"><span data-stu-id="6d20a-243">SMC changes to the desired source.</span></span></br></br><span data-ttu-id="6d20a-244">Le service du PC informe le SMC que la source d’affichage a changé.</span><span class="sxs-lookup"><span data-stu-id="6d20a-244">PC service notifies SMC that the display source has switched.</span></span> |  <span data-ttu-id="6d20a-245">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="6d20a-245">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="6d20a-246">Source+</span><span class="sxs-lookup"><span data-stu-id="6d20a-246">Source+</span></span> |  <span data-ttu-id="6d20a-247">Le SMC recherche la source d’entrée active suivante.</span><span class="sxs-lookup"><span data-stu-id="6d20a-247">SMC cycles to the next active input source.</span></span></br></br><span data-ttu-id="6d20a-248">Le service du PC informe le SMC de la source d’entrée actuelle.</span><span class="sxs-lookup"><span data-stu-id="6d20a-248">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="6d20a-249">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="6d20a-249">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="6d20a-250">Source-</span><span class="sxs-lookup"><span data-stu-id="6d20a-250">Source-</span></span> | <span data-ttu-id="6d20a-251">Le SMC recherche la source d’entrée active précédente.</span><span class="sxs-lookup"><span data-stu-id="6d20a-251">SMC cycles to the previous active input source.</span></span></br></br><span data-ttu-id="6d20a-252">Le service du PC informe le SMC de la source d’entrée actuelle.</span><span class="sxs-lookup"><span data-stu-id="6d20a-252">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="6d20a-253">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="6d20a-253">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="6d20a-254">Source?</span><span class="sxs-lookup"><span data-stu-id="6d20a-254">Source?</span></span> |  <span data-ttu-id="6d20a-255">Le SMC interroge le service du PC concernant la source d’entrée active.</span><span class="sxs-lookup"><span data-stu-id="6d20a-255">SMC queries PC service for the active input source.</span></span></br></br><span data-ttu-id="6d20a-256">Le service du PC indique au SMC la source d’entrée actuelle.</span><span class="sxs-lookup"><span data-stu-id="6d20a-256">PC service notifies SMC of the current in;put source.</span></span> | <span data-ttu-id="6d20a-257">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="6d20a-257">Source=&lt;#&gt;</span></span> |

## <span data-ttu-id="6d20a-258">Erreurs</span><span class="sxs-lookup"><span data-stu-id="6d20a-258">Errors</span></span>

<span data-ttu-id="6d20a-259">Les erreurs sont renvoyées au format indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="6d20a-259">Errors are returned following the format in this table.</span></span>

| <span data-ttu-id="6d20a-260">Erreur</span><span class="sxs-lookup"><span data-stu-id="6d20a-260">Error</span></span> | <span data-ttu-id="6d20a-261">Remarques</span><span class="sxs-lookup"><span data-stu-id="6d20a-261">Notes</span></span> |
| --- | --- |
| <span data-ttu-id="6d20a-262">Error: Unknown command ’&lt;input&gt;’.</span><span class="sxs-lookup"><span data-stu-id="6d20a-262">Error: Unknown command '&lt;input&gt;'.</span></span> |  <span data-ttu-id="6d20a-263">L’instruction contient une commande initiale inconnue.</span><span class="sxs-lookup"><span data-stu-id="6d20a-263">The instruction contains an unknown initial command.</span></span> <span data-ttu-id="6d20a-264">Par exemple, &quot;VOL+&quot; ne serait pas valide et renverrait &quot; Error: Unknown command ’VOL’&quot;.</span><span class="sxs-lookup"><span data-stu-id="6d20a-264">For example, &quot;VOL+&quot; would be invalid and return &quot; Error: Unknown command 'VOL'&quot;.</span></span> |
| <span data-ttu-id="6d20a-265">Error: Unknown operator ’&lt;input&gt;’.</span><span class="sxs-lookup"><span data-stu-id="6d20a-265">Error: Unknown operator '&lt;input&gt;'.</span></span> |  <span data-ttu-id="6d20a-266">L’instruction contient un opérateur inconnu.</span><span class="sxs-lookup"><span data-stu-id="6d20a-266">The instruction contains an unknown operator.</span></span> <span data-ttu-id="6d20a-267">Par exemple, &quot;Volume!&quot; ne serait pas valide et renverrait &quot; Error: Unknown operator ’!’&quot;</span><span class="sxs-lookup"><span data-stu-id="6d20a-267">For example, &quot;Volume!&quot; would be invalid and return &quot; Error: Unknown operator '!'&quot;.</span></span> |
| <span data-ttu-id="6d20a-268">Error: Unknown parameter ’&lt;input&gt;’.</span><span class="sxs-lookup"><span data-stu-id="6d20a-268">Error: Unknown parameter '&lt;input&gt;'.</span></span> |  <span data-ttu-id="6d20a-269">L’instruction contient un paramètre inconnu.</span><span class="sxs-lookup"><span data-stu-id="6d20a-269">The instruction contains an unknown parameter.</span></span> <span data-ttu-id="6d20a-270">Par exemple, &quot;Volume=abc&quot; ne serait pas valide et renverrait &quot; Error: Unknown parameter ’abc’&quot;.</span><span class="sxs-lookup"><span data-stu-id="6d20a-270">For example, &quot;Volume=abc&quot; would be invalid and return &quot; Error: Unknown parameter 'abc'&quot;.</span></span> |
| <span data-ttu-id="6d20a-271">Error: Command not available when off ’&lt;input&gt;’.</span><span class="sxs-lookup"><span data-stu-id="6d20a-271">Error: Command not available when off '&lt;input&gt;'.</span></span> |  <span data-ttu-id="6d20a-272">Quand le Surface Hub est désactivé, les commandes autres que celle relative à la gestion de l’alimentation renvoient cette erreur.</span><span class="sxs-lookup"><span data-stu-id="6d20a-272">When the Surface Hub is off, commands other than Power return this error.</span></span> <span data-ttu-id="6d20a-273">Par exemple, &quot;Volume+&quot; ne serait pas valide et renverrait &quot; Error: Command not available when off ’Volume’&quot;.</span><span class="sxs-lookup"><span data-stu-id="6d20a-273">For example, &quot;Volume+&quot; would be invalid and return &quot; Error: Command not available when off 'Volume'&quot;.</span></span> |


 

## <span data-ttu-id="6d20a-274">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6d20a-274">Related topics</span></span>


[<span data-ttu-id="6d20a-275">Gérer le Microsoft SurfaceHub</span><span class="sxs-lookup"><span data-stu-id="6d20a-275">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="6d20a-276">Guide de l’administrateur Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="6d20a-276">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





