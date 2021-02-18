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
description: Интеграция сервера SIEM организации с Microsoft Defender для Office 365 и связанными с ними событиями угроз в API управления действиями Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f637750a31b5034d2ee1110ab0070fa6abcda49b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290397"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="a4bcd-103">Интеграция SIEM с Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="a4bcd-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="a4bcd-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="a4bcd-104">**Applies to**</span></span>
- [<span data-ttu-id="a4bcd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a4bcd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a4bcd-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="a4bcd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a4bcd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4bcd-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a4bcd-108">Если в вашей организации используется сервер SIEM, вы можете интегрировать Microsoft Defender для Office 365 с сервером SIEM.</span><span class="sxs-lookup"><span data-stu-id="a4bcd-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="a4bcd-109">Вы можете настроить эту интеграцию с помощью API управления действиями [Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="a4bcd-109">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="a4bcd-110">Интеграция SIEM позволяет просматривать сведения, такие как вредоносные программы или фишинг, обнаруженные Microsoft Defender для Office 365, в отчетах сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="a4bcd-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="a4bcd-111">Пример интеграции SIEM с Microsoft Defender для Office 365 см. в блоге Tech Community: улучшение эффективности SOC с Помощью [Защитника для Office 365 и API управления O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)</span><span class="sxs-lookup"><span data-stu-id="a4bcd-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="a4bcd-112">Дополнительные сведения об API управления Office 365 см. в обзоре [API управления Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="a4bcd-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="a4bcd-113">Как работает интеграция SIEM</span><span class="sxs-lookup"><span data-stu-id="a4bcd-113">How SIEM integration works</span></span>

<span data-ttu-id="a4bcd-114">API управления действиями Office 365 извлекает сведения о действиях и событиях пользователей, администраторов, систем и политик из журналов действий Microsoft 365 и Azure Active Directory вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a4bcd-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="a4bcd-115">Если в вашей организации есть Microsoft Defender для Office 365 (план 1 или 2) или Office 365 E5, вы можете использовать схему [Microsoft Defender для Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="a4bcd-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="a4bcd-116">Недавно в API действий управления Office 365 были добавлены события из автоматизированного исследования и реагирования в Microsoft Defender для [Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) (план 2).</span><span class="sxs-lookup"><span data-stu-id="a4bcd-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="a4bcd-117">Помимо данных об основных сведениях исследования, таких как ИД, имя и состояние, API также содержит высокоуровневую информацию о действиях и сущностях расследования.</span><span class="sxs-lookup"><span data-stu-id="a4bcd-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="a4bcd-118">Сервер SIEM или другая аналогичная система оповещую нагрузку **audit.general** для доступа к событиям обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a4bcd-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="a4bcd-119">Дополнительные информации см. в руководстве ["Начало работы с API управления Office 365".](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="a4bcd-119">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="a4bcd-120">Enum: AuditLogRecordType; Type: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="a4bcd-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="a4bcd-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="a4bcd-121">AuditLogRecordType</span></span>

<span data-ttu-id="a4bcd-122">В следующей таблице сводятся значения **AuditLogRecordType,** релевантные для событий Microsoft Defender в Office 365:</span><span class="sxs-lookup"><span data-stu-id="a4bcd-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="a4bcd-123">Значение</span><span class="sxs-lookup"><span data-stu-id="a4bcd-123">Value</span></span>|<span data-ttu-id="a4bcd-124">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="a4bcd-124">Member name</span></span>|<span data-ttu-id="a4bcd-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a4bcd-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="a4bcd-126">28</span><span class="sxs-lookup"><span data-stu-id="a4bcd-126">28</span></span>|<span data-ttu-id="a4bcd-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="a4bcd-127">ThreatIntelligence</span></span>|<span data-ttu-id="a4bcd-128">События фишинга и вредоносных программ из Exchange Online Protection и Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4bcd-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="a4bcd-129">41</span><span class="sxs-lookup"><span data-stu-id="a4bcd-129">41</span></span>|<span data-ttu-id="a4bcd-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="a4bcd-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="a4bcd-131">События переопределения времени блокировки и блокировки безопасных ссылок из Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4bcd-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="a4bcd-132">47</span><span class="sxs-lookup"><span data-stu-id="a4bcd-132">47</span></span>|<span data-ttu-id="a4bcd-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="a4bcd-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="a4bcd-134">События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams из Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4bcd-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="a4bcd-135">64</span><span class="sxs-lookup"><span data-stu-id="a4bcd-135">64</span></span>|<span data-ttu-id="a4bcd-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="a4bcd-136">AirInvestigation</span></span>|<span data-ttu-id="a4bcd-137">События автоматического исследования и реагирования, такие как сведения об исследованиях и соответствующие артефакты, из Microsoft Defender для Office 365 (план 2).</span><span class="sxs-lookup"><span data-stu-id="a4bcd-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="a4bcd-138">Чтобы настроить интеграцию SIEM с Microsoft Defender для Office 365, необходимо быть глобальным администратором или иметь роль администратора безопасности, назначенную Центру безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a4bcd-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="a4bcd-139">Ведение журнала аудита должно быть включено для вашей среды Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a4bcd-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="a4bcd-140">Чтобы получить помощь по этой теме, см. "Включите или отключите поиск [в журнале аудита".](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="a4bcd-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a4bcd-141">См. также</span><span class="sxs-lookup"><span data-stu-id="a4bcd-141">See also</span></span>

[<span data-ttu-id="a4bcd-142">Анализ угроз и реагирование на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="a4bcd-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="a4bcd-143">Автоматическое исследование и реагирование на них (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="a4bcd-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

