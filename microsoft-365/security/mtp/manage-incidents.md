---
title: Управление инцидентами в службе Защиты от угроз (Майкрософт)
description: Узнайте, как назначать, обновлять статус,
keywords: инцидент, инциденты, оповещения, коррелированные оповещения, назначить, обновить, состояние, управление, классификация, Microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 46904323a1ec8f969355931f8b69a3ed0ebf4519
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600216"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="8063b-104">Управление инцидентами в службе Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8063b-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="8063b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8063b-105">**Applies to:**</span></span>
- <span data-ttu-id="8063b-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8063b-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8063b-107">Управление инцидентами крайне важно, чтобы обеспечить локализацию и устранение угроз.</span><span class="sxs-lookup"><span data-stu-id="8063b-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="8063b-108">Служба Защиты от угроз (Майкрософт) позволяет управлять инцидентами устройств, пользователей и почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="8063b-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="8063b-109">Для управления инцидентами выберите инцидент в **очереди инцидентов**.</span><span class="sxs-lookup"><span data-stu-id="8063b-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="8063b-110">Здесь можно изменить имя инцидента, устранить его, задать его классификацию и определение.</span><span class="sxs-lookup"><span data-stu-id="8063b-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="8063b-111">Вы также можете назначить инцидент себе, добавить теги и примечания.</span><span class="sxs-lookup"><span data-stu-id="8063b-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="8063b-112">Если при расследовании инцидента необходимо перенести оповещения из одного сегмента в другой, это также можно сделать на вкладке "Оповещения", создавая крупные или меньшие инциденты, в которых есть все необходимые оповещения.</span><span class="sxs-lookup"><span data-stu-id="8063b-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="8063b-113">Изменение имени инцидента</span><span class="sxs-lookup"><span data-stu-id="8063b-113">Edit incident name</span></span>
<span data-ttu-id="8063b-114">По умолчанию инциденту присвоен номер.</span><span class="sxs-lookup"><span data-stu-id="8063b-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="8063b-115">Имя инцидента можно изменить для лучшего соответствия используемому вами соглашению об именовании.</span><span class="sxs-lookup"><span data-stu-id="8063b-115">You can modify the incident name to better align with your preferred naming convention.</span></span>
 
## <a name="assign-incidents"></a><span data-ttu-id="8063b-116">Назначение инцидентов</span><span class="sxs-lookup"><span data-stu-id="8063b-116">Assign incidents</span></span>
<span data-ttu-id="8063b-117">Если инцидент еще не назначен, вы можете выбрать **Назначить мне**, чтобы назначить инцидент себе.</span><span class="sxs-lookup"><span data-stu-id="8063b-117">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="8063b-118">При этом передается не только владение инцидентом, но и все связанные с ним оповещения.</span><span class="sxs-lookup"><span data-stu-id="8063b-118">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="8063b-119">Установка статуса и классификации</span><span class="sxs-lookup"><span data-stu-id="8063b-119">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="8063b-120">Статус инцидента</span><span class="sxs-lookup"><span data-stu-id="8063b-120">Incident status</span></span>
<span data-ttu-id="8063b-121">Инциденты можно распределять по категориям (например, **Активно** или **Устранено**), изменяя его статус в ходе расследования.</span><span class="sxs-lookup"><span data-stu-id="8063b-121">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="8063b-122">Это помогает организовать обработку инцидентов вашей группой и управлять ею.</span><span class="sxs-lookup"><span data-stu-id="8063b-122">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="8063b-123">Например, ваш аналитик SOC может просмотреть срочные инциденты со статусом **Активно**, появившиеся за день, и назначить их себе для расследования.</span><span class="sxs-lookup"><span data-stu-id="8063b-123">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="8063b-124">Или же аналитик SOC может дать инциденту статус **Устранено**, если он был ликвидирован.</span><span class="sxs-lookup"><span data-stu-id="8063b-124">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="8063b-125">При устранении инцидента все оповещения, которые относятся к этому инциденту и еще открыты, автоматически закрываются.</span><span class="sxs-lookup"><span data-stu-id="8063b-125">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="8063b-126">Классификация и определение</span><span class="sxs-lookup"><span data-stu-id="8063b-126">Classification and determination</span></span>
<span data-ttu-id="8063b-127">Можно не задавать классификацию, а также указать, будет ли инцидент истинным или ложным.</span><span class="sxs-lookup"><span data-stu-id="8063b-127">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="8063b-128">Это поможет заметить закономерности в инцидентах и изучить их.</span><span class="sxs-lookup"><span data-stu-id="8063b-128">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="8063b-129">Добавление примечаний</span><span class="sxs-lookup"><span data-stu-id="8063b-129">Add comments</span></span>
<span data-ttu-id="8063b-130">К инциденту можно добавить комментарии, а также просмотреть историю связанных с ним событий, чтобы узнать об изменениях, ранее внесенных в него.</span><span class="sxs-lookup"><span data-stu-id="8063b-130">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="8063b-131">Каждое изменение или комментарий к оповещению записывается в раздел комментариев и журнал.</span><span class="sxs-lookup"><span data-stu-id="8063b-131">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="8063b-132">Добавленные комментарии сразу же появляются в соответствующей области.</span><span class="sxs-lookup"><span data-stu-id="8063b-132">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="8063b-133">Добавление тегов инцидента</span><span class="sxs-lookup"><span data-stu-id="8063b-133">Add incident tags</span></span>
<span data-ttu-id="8063b-134">К инциденту можно добавить пользовательские теги, например, чтобы пометить группу инцидентов с общими характеристиками.</span><span class="sxs-lookup"><span data-stu-id="8063b-134">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="8063b-135">Впоследствии из очереди тегов можно будет выделить все инциденты, которые содержат определенный тег.</span><span class="sxs-lookup"><span data-stu-id="8063b-135">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>

