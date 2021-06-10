---
title: Начало работы с обозревателем действий
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Обозреватель действий обобщает функции компонента классификации данных, позволяя просматривать и фильтровать действия, выполняемые пользователями над содержимым с метками.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114011"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="16443-103">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="16443-103">Get started with activity explorer</span></span>

<span data-ttu-id="16443-104">Обзор [классификации данных](data-classification-overview.md) и вкладки [обозревателя](data-classification-content-explorer.md) контента дают представление о том, какое содержимое было обнаружено и помечено, и где это содержимое.</span><span class="sxs-lookup"><span data-stu-id="16443-104">The [data classification overview](data-classification-overview.md) and [content explorer](data-classification-content-explorer.md) tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="16443-105">Обозреватель действий обобщает набор функций, позволяя отслеживать действия над содержимым с метками.</span><span class="sxs-lookup"><span data-stu-id="16443-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="16443-106">Обозреватель действий предоставляет историческое представление действий в вашем содержимом с меткой.</span><span class="sxs-lookup"><span data-stu-id="16443-106">Activity explorer provides a historical view of activities on your labeled content.</span></span> <span data-ttu-id="16443-107">Сведения о действиях собираются из унифицированных журналов аудита Microsoft 365, преобразованы и доступны в пользовательском интерфейсе обозревателя действий.</span><span class="sxs-lookup"><span data-stu-id="16443-107">The activity information is collected from the Microsoft 365 unified audit logs, transformed and made available in the Activity explorer UI.</span></span> 

![снимок экрана: обзор обозревателя действий](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="16443-109">Поддерживается свыше 30 фильтров, доступных для использования, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="16443-109">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="16443-110">диапазон дат;</span><span class="sxs-lookup"><span data-stu-id="16443-110">date range</span></span>
- <span data-ttu-id="16443-111">тип действия;</span><span class="sxs-lookup"><span data-stu-id="16443-111">activity type</span></span>
- <span data-ttu-id="16443-112">расположение;</span><span class="sxs-lookup"><span data-stu-id="16443-112">location</span></span>
- <span data-ttu-id="16443-113">пользователь;</span><span class="sxs-lookup"><span data-stu-id="16443-113">user</span></span>
- <span data-ttu-id="16443-114">метка конфиденциальности;</span><span class="sxs-lookup"><span data-stu-id="16443-114">sensitivity label</span></span>
- <span data-ttu-id="16443-115">метка хранения;</span><span class="sxs-lookup"><span data-stu-id="16443-115">retention label</span></span>
- <span data-ttu-id="16443-116">путь к файлу</span><span class="sxs-lookup"><span data-stu-id="16443-116">file path</span></span>
- <span data-ttu-id="16443-117">Политика защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="16443-117">DLP policy</span></span>



## <a name="prerequisites"></a><span data-ttu-id="16443-118">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="16443-118">Prerequisites</span></span>

<span data-ttu-id="16443-119">Каждой учетной записи, которая осуществляет доступ и использует классификацию данных, необходимо назначить лицензию из одной из следующих подписок:</span><span class="sxs-lookup"><span data-stu-id="16443-119">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="16443-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="16443-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="16443-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="16443-121">Office 365 (E5)</span></span>
- <span data-ttu-id="16443-122">Дополнение Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="16443-122">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="16443-123">Дополнение Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="16443-123">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="16443-124">Защита информации и управление данными в Microsoft 365 E5 или A5</span><span class="sxs-lookup"><span data-stu-id="16443-124">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="16443-125">Соответствие требованиям Microsoft 365 E5 или A5</span><span class="sxs-lookup"><span data-stu-id="16443-125">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="16443-126">Разрешения</span><span class="sxs-lookup"><span data-stu-id="16443-126">Permissions</span></span>

 <span data-ttu-id="16443-127">Чтобы получить доступ к вкладке Обозреватель действий, учетной записи должно быть явно назначено членство в любой из этих групп ролей или явно предоставлена роль.</span><span class="sxs-lookup"><span data-stu-id="16443-127">In order to get access to the activity explorer tab, an account must be explicitly assigned membership in any one of these role groups or explicitly granted the role.</span></span>

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

<span data-ttu-id="16443-128">**Группы ролей Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="16443-128">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="16443-129">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="16443-129">Global administrator</span></span>
- <span data-ttu-id="16443-130">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="16443-130">Compliance administrator</span></span>
- <span data-ttu-id="16443-131">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="16443-131">Security administrator</span></span>
- <span data-ttu-id="16443-132">Администратор данных о соответствии требованиям</span><span class="sxs-lookup"><span data-stu-id="16443-132">Compliance data administrator</span></span>

<span data-ttu-id="16443-133">**Microsoft 365 ролей**</span><span class="sxs-lookup"><span data-stu-id="16443-133">**Microsoft 365 roles**</span></span>

- <span data-ttu-id="16443-134">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="16443-134">Compliance administrator</span></span>
- <span data-ttu-id="16443-135">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="16443-135">Security administrator</span></span>

## <a name="activity-types"></a><span data-ttu-id="16443-136">Типы действий</span><span class="sxs-lookup"><span data-stu-id="16443-136">Activity types</span></span>

<span data-ttu-id="16443-137">Обозреватель действий собирает сведения о действиях из журналов аудита на нескольких источниках действий.</span><span class="sxs-lookup"><span data-stu-id="16443-137">Activity explorer gathers activity information from the audit logs on multiple sources of activities.</span></span> <span data-ttu-id="16443-138">Дополнительные сведения о том, какие действия метки делают ее проводнику действий, см. в описании событий маркировки, доступных [в обозревателе действий.](data-classification-activity-explorer-available-events.md)</span><span class="sxs-lookup"><span data-stu-id="16443-138">For more detailed information on what labeling activity makes it to Activity explorer, see [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span></span>

<span data-ttu-id="16443-139">**Действия метки**  конфиденциальности и действия по маркировке хранения из Office приложений, надстройки Azure Information Protection, SharePoint Online, Exchange Online (только метки конфиденциальности) и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="16443-139">**Sensitivity label activities** and **Retention labeling activities** from Office native applications, Azure Information Protection add-in, SharePoint Online, Exchange Online (sensitivity labels only) and OneDrive.</span></span> <span data-ttu-id="16443-140">Ниже приведен ряд примеров.</span><span class="sxs-lookup"><span data-stu-id="16443-140">Some examples are:</span></span>

- <span data-ttu-id="16443-141">применение метки</span><span class="sxs-lookup"><span data-stu-id="16443-141">label applied</span></span>
- <span data-ttu-id="16443-142">изменение метки (обновление, возврат к прежней, удаление)</span><span class="sxs-lookup"><span data-stu-id="16443-142">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="16443-143">моделирование автоматического применения метки</span><span class="sxs-lookup"><span data-stu-id="16443-143">auto-labeling simulation</span></span>
- <span data-ttu-id="16443-144">чтение файла</span><span class="sxs-lookup"><span data-stu-id="16443-144">file read</span></span> 

<span data-ttu-id="16443-145">**Сканер Azure Information Protection (AIP) и клиенты AIP**</span><span class="sxs-lookup"><span data-stu-id="16443-145">**Azure Information Protection (AIP) scanner and AIP clients**</span></span>

- <span data-ttu-id="16443-146">применяемая защита</span><span class="sxs-lookup"><span data-stu-id="16443-146">protection applied</span></span>
- <span data-ttu-id="16443-147">изменена защита</span><span class="sxs-lookup"><span data-stu-id="16443-147">protection changed</span></span>
- <span data-ttu-id="16443-148">защита удалена</span><span class="sxs-lookup"><span data-stu-id="16443-148">protection removed</span></span>
- <span data-ttu-id="16443-149">обнаруженные файлы</span><span class="sxs-lookup"><span data-stu-id="16443-149">files discovered</span></span> 

<span data-ttu-id="16443-150">Обозреватель действий также собирает события политики **DLP,** совпадающих с событиями из Exchange Online, SharePoint Online, OneDrive, Teams Chat и Channel (предварительный просмотр), локальной SharePoint папок и библиотек, а также из локального файла и Windows 10 устройств с помощью предотвращения потери данных **endpoint (DLP).**</span><span class="sxs-lookup"><span data-stu-id="16443-150">Activity explorer also gathers **DLP policy matches** events from Exchange Online, SharePoint Online, OneDrive, Teams Chat and Channel (preview), on-premises SharePoint folders and libraries, and on-premises file shares, and Windows 10 devices via **Endpoint data loss prevention (DLP)**.</span></span> <span data-ttu-id="16443-151">Некоторые примеры событий из Windows 10 являются файлами:</span><span class="sxs-lookup"><span data-stu-id="16443-151">Some examples events from Windows 10 devices are file:</span></span>

- <span data-ttu-id="16443-152">удаления</span><span class="sxs-lookup"><span data-stu-id="16443-152">deletions</span></span>
- <span data-ttu-id="16443-153">создания</span><span class="sxs-lookup"><span data-stu-id="16443-153">creations</span></span>
- <span data-ttu-id="16443-154">скопирован в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="16443-154">copied to clipboard</span></span>
- <span data-ttu-id="16443-155">изменено</span><span class="sxs-lookup"><span data-stu-id="16443-155">modified</span></span>
- <span data-ttu-id="16443-156">read</span><span class="sxs-lookup"><span data-stu-id="16443-156">read</span></span>
- <span data-ttu-id="16443-157">напечатано</span><span class="sxs-lookup"><span data-stu-id="16443-157">printed</span></span>
- <span data-ttu-id="16443-158">переименовано</span><span class="sxs-lookup"><span data-stu-id="16443-158">renamed</span></span>
- <span data-ttu-id="16443-159">скопирован в сеть</span><span class="sxs-lookup"><span data-stu-id="16443-159">copied to network share</span></span>
- <span data-ttu-id="16443-160">доступ к незаверяемой приложению</span><span class="sxs-lookup"><span data-stu-id="16443-160">accessed by unallowed app</span></span> 

<span data-ttu-id="16443-161">Значение понимания того, какие действия принимаются с конфиденциальным контентом с меткой, состоит в том, что вы можете увидеть, эффективны ли элементы управления, которые вы уже ввели, например предотвращение потери данных. [](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="16443-161">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention](dlp-learn-about-dlp.md) are effective or not.</span></span> <span data-ttu-id="16443-162">В противном случае или при выявлении чего-то неожиданного, например большого числа элементов, метка которых изменена с `highly confidential` на `general`, вы можете управлять различными политиками и выполнять новые действия, чтобы ограничить нежелательное поведение.</span><span class="sxs-lookup"><span data-stu-id="16443-162">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="16443-163">Обозреватель действий в настоящее время не отслеживает действия по удержанию данных в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="16443-163">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="16443-164">См. также</span><span class="sxs-lookup"><span data-stu-id="16443-164">See also</span></span>

- [<span data-ttu-id="16443-165">Сведения о метках конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="16443-165">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="16443-166">Сведения о политиках и метках хранения</span><span class="sxs-lookup"><span data-stu-id="16443-166">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="16443-167">Сведения о типах конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="16443-167">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="16443-168">Сведения о классификации данных</span><span class="sxs-lookup"><span data-stu-id="16443-168">Learn about data classification</span></span>](data-classification-overview.md)
