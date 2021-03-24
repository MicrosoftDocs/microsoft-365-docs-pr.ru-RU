---
title: Интеграция SIEM с Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Интеграция siEM-сервера организации с Microsoft Defender для Office 365 и связанными с ними событиями угрозы в API управления деятельностью Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a456ee970015aea5936ae86ec009cb2ff46e99c2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072502"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="67658-103">Интеграция SIEM с Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="67658-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="67658-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="67658-104">**Applies to**</span></span>
- [<span data-ttu-id="67658-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="67658-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="67658-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="67658-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="67658-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67658-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="67658-108">Если ваша организация использует сервер управления данными безопасности и событиями (SIEM), вы можете интегрировать Microsoft Defender для Office 365 с сервером SIEM.</span><span class="sxs-lookup"><span data-stu-id="67658-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="67658-109">Эту интеграцию можно настроить с помощью API управления деятельностью [Office 365.](/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="67658-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="67658-110">Интеграция SIEM позволяет просматривать сведения, например вредоносные программы или фишинг, обнаруженные Microsoft Defender для Office 365, в отчетах на сервере SIEM.</span><span class="sxs-lookup"><span data-stu-id="67658-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="67658-111">Пример интеграции SIEM с Microsoft Defender для Office 365 см. в блоге Tech Community: Повышение эффективности soc с [помощью Defender для Office 365 и API управления O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)</span><span class="sxs-lookup"><span data-stu-id="67658-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="67658-112">Дополнительные сведения об API управления Office 365 см. в обзоре API управления [Office 365.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="67658-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="67658-113">Работа интеграции SIEM</span><span class="sxs-lookup"><span data-stu-id="67658-113">How SIEM integration works</span></span>

<span data-ttu-id="67658-114">API управления действиями Office 365 извлекает сведения о действиях пользователя, администратора, системы и политик и событиях из журналов действий Microsoft 365 и Azure Active Directory вашей организации.</span><span class="sxs-lookup"><span data-stu-id="67658-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="67658-115">Если в вашей организации есть Microsoft Defender для Office 365 Plan 1 или 2 или Office 365 E5, можно использовать схему [Microsoft Defender для Office 365.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="67658-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="67658-116">Недавно в API управления Office 365 были добавлены события из возможностей автоматического расследования и реагирования в [Microsoft Defender для Office 365 Plan 2.](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)</span><span class="sxs-lookup"><span data-stu-id="67658-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="67658-117">Помимо добавления данных о основных данных расследования, таких как ID, имя и состояние, API также содержит сведения высокого уровня о следственных действиях и сущностях.</span><span class="sxs-lookup"><span data-stu-id="67658-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="67658-118">SiEM-сервер или другая аналогичная система опове-вает данные о рабочей нагрузке **audit.general** для доступа к событиям обнаружения.</span><span class="sxs-lookup"><span data-stu-id="67658-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="67658-119">Дополнительные дополнительные ссылки см. в [руб. Начало работы с API управления Office 365.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="67658-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="67658-120">Enum: AuditLogRecordType; Type: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="67658-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="67658-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="67658-121">AuditLogRecordType</span></span>

<span data-ttu-id="67658-122">В следующей таблице суммируют значения **AuditLogRecordType,** которые актуальны для событий Microsoft Defender для Office 365:</span><span class="sxs-lookup"><span data-stu-id="67658-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="67658-123">Значение</span><span class="sxs-lookup"><span data-stu-id="67658-123">Value</span></span>|<span data-ttu-id="67658-124">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="67658-124">Member name</span></span>|<span data-ttu-id="67658-125">Описание</span><span class="sxs-lookup"><span data-stu-id="67658-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="67658-126">28</span><span class="sxs-lookup"><span data-stu-id="67658-126">28</span></span>|<span data-ttu-id="67658-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="67658-127">ThreatIntelligence</span></span>|<span data-ttu-id="67658-128">События фишинга и вредоносных программ из Exchange Online Protection и Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="67658-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="67658-129">41</span><span class="sxs-lookup"><span data-stu-id="67658-129">41</span></span>|<span data-ttu-id="67658-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="67658-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="67658-131">Время блокировки безопасных ссылок и блокировка переопределения событий из Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="67658-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="67658-132">47</span><span class="sxs-lookup"><span data-stu-id="67658-132">47</span></span>|<span data-ttu-id="67658-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="67658-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="67658-134">События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams из Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="67658-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="67658-135">64</span><span class="sxs-lookup"><span data-stu-id="67658-135">64</span></span>|<span data-ttu-id="67658-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="67658-136">AirInvestigation</span></span>|<span data-ttu-id="67658-137">Автоматические события расследования и реагирования, такие как сведения о расследовании и соответствующие артефакты, из Microsoft Defender для Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="67658-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="67658-138">Вы должны быть глобальным администратором или иметь роль администратора безопасности, назначенную Центру & безопасности, чтобы настроить интеграцию SIEM с Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="67658-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="67658-139">Ведение журнала аудита должно быть включено для среды Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67658-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="67658-140">Чтобы получить помощь в этом, см. в справке о включите поиск [журнала аудита включите или отключите.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="67658-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="67658-141">См. также</span><span class="sxs-lookup"><span data-stu-id="67658-141">See also</span></span>

[<span data-ttu-id="67658-142">Анализ угроз и реагирование на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="67658-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="67658-143">Автоматическое расследование и ответ (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="67658-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)