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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c599343233e7e29589bc4e3d1cda01da505b16f1
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430565"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="750fb-104">Управление инцидентами в службе Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="750fb-104">Manage incidents in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="750fb-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="750fb-105">**Applies to:**</span></span>
- <span data-ttu-id="750fb-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="750fb-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="750fb-107">Управление инцидентами крайне важно, чтобы обеспечить локализацию и устранение угроз.</span><span class="sxs-lookup"><span data-stu-id="750fb-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="750fb-108">Служба Защиты от угроз (Майкрософт) позволяет управлять инцидентами устройств, пользователей и почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="750fb-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="750fb-109">Для управления инцидентами выберите инцидент в **очереди инцидентов**.</span><span class="sxs-lookup"><span data-stu-id="750fb-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="750fb-110">Здесь можно изменить имя инцидента, устранить его, задать его классификацию и определение.</span><span class="sxs-lookup"><span data-stu-id="750fb-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="750fb-111">Вы также можете назначить инцидент себе, добавить теги и примечания.</span><span class="sxs-lookup"><span data-stu-id="750fb-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="750fb-112">Если при расследовании инцидента необходимо перенести оповещения из одного сегмента в другой, это также можно сделать на вкладке "Оповещения", создавая крупные или меньшие инциденты, в которых есть все необходимые оповещения.</span><span class="sxs-lookup"><span data-stu-id="750fb-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="750fb-113">Изменение имени инцидента</span><span class="sxs-lookup"><span data-stu-id="750fb-113">Edit incident name</span></span>
<span data-ttu-id="750fb-114">Инцидентам автоматически назначается имя на основе атрибутов оповещений, таких как количество затронутых конечных точек, затронутых пользователей, источников обнаружения или категорий.</span><span class="sxs-lookup"><span data-stu-id="750fb-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="750fb-115">Это позволяет быстро оценить область инцидента.</span><span class="sxs-lookup"><span data-stu-id="750fb-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="750fb-116">Пример: *многоэтапное инциденто на нескольких конечных точках, обнаруженных несколькими источниками.*</span><span class="sxs-lookup"><span data-stu-id="750fb-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="750fb-117">Имя инцидента можно изменить для лучшего соответствия используемому вами соглашению об именовании.</span><span class="sxs-lookup"><span data-stu-id="750fb-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="750fb-118">Инциденты, существовавшие до развертывания функции автоматического именования инцидентов, сохранят свои имена.</span><span class="sxs-lookup"><span data-stu-id="750fb-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="750fb-119">Назначение инцидентов</span><span class="sxs-lookup"><span data-stu-id="750fb-119">Assign incidents</span></span>
<span data-ttu-id="750fb-120">Если инцидент еще не назначен, вы можете выбрать **Назначить мне**, чтобы назначить инцидент себе.</span><span class="sxs-lookup"><span data-stu-id="750fb-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="750fb-121">При этом передается не только владение инцидентом, но и все связанные с ним оповещения.</span><span class="sxs-lookup"><span data-stu-id="750fb-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="750fb-122">Установка статуса и классификации</span><span class="sxs-lookup"><span data-stu-id="750fb-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="750fb-123">Статус инцидента</span><span class="sxs-lookup"><span data-stu-id="750fb-123">Incident status</span></span>
<span data-ttu-id="750fb-124">Инциденты можно распределять по категориям (например, **Активно** или **Устранено**), изменяя его статус в ходе расследования.</span><span class="sxs-lookup"><span data-stu-id="750fb-124">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="750fb-125">Это помогает организовать обработку инцидентов вашей группой и управлять ею.</span><span class="sxs-lookup"><span data-stu-id="750fb-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="750fb-126">Например, ваш аналитик SOC может просмотреть срочные инциденты со статусом **Активно**, появившиеся за день, и назначить их себе для расследования.</span><span class="sxs-lookup"><span data-stu-id="750fb-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="750fb-127">Или же аналитик SOC может дать инциденту статус **Устранено**, если он был ликвидирован.</span><span class="sxs-lookup"><span data-stu-id="750fb-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="750fb-128">При устранении инцидента все оповещения, которые относятся к этому инциденту и еще открыты, автоматически закрываются.</span><span class="sxs-lookup"><span data-stu-id="750fb-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="750fb-129">Классификация и определение</span><span class="sxs-lookup"><span data-stu-id="750fb-129">Classification and determination</span></span>
<span data-ttu-id="750fb-130">Можно не задавать классификацию, а также указать, будет ли инцидент истинным или ложным.</span><span class="sxs-lookup"><span data-stu-id="750fb-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="750fb-131">Это поможет заметить закономерности в инцидентах и изучить их.</span><span class="sxs-lookup"><span data-stu-id="750fb-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="750fb-132">Добавление примечаний</span><span class="sxs-lookup"><span data-stu-id="750fb-132">Add comments</span></span>
<span data-ttu-id="750fb-133">К инциденту можно добавить комментарии, а также просмотреть историю связанных с ним событий, чтобы узнать об изменениях, ранее внесенных в него.</span><span class="sxs-lookup"><span data-stu-id="750fb-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="750fb-134">Каждое изменение или комментарий к оповещению записывается в раздел комментариев и журнал.</span><span class="sxs-lookup"><span data-stu-id="750fb-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="750fb-135">Добавленные комментарии сразу же появляются в соответствующей области.</span><span class="sxs-lookup"><span data-stu-id="750fb-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="750fb-136">Добавление тегов инцидента</span><span class="sxs-lookup"><span data-stu-id="750fb-136">Add incident tags</span></span>
<span data-ttu-id="750fb-137">К инциденту можно добавить пользовательские теги, например, чтобы пометить группу инцидентов с общими характеристиками.</span><span class="sxs-lookup"><span data-stu-id="750fb-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="750fb-138">Впоследствии из очереди тегов можно будет выделить все инциденты, которые содержат определенный тег.</span><span class="sxs-lookup"><span data-stu-id="750fb-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>
