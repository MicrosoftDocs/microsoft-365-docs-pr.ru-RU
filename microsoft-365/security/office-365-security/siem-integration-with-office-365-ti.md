---
title: Интеграция SIEM с Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Интеграция siEM-сервера организации с Microsoft Defender для Office 365 и связанных с ними событий в API управления Office 365 действий.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e11d1e64b7c8c3b9d5b93516fe05aed3d5937290
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105636"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="72acb-103">Интеграция SIEM с Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="72acb-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="72acb-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="72acb-104">**Applies to**</span></span>
- [<span data-ttu-id="72acb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="72acb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="72acb-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="72acb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="72acb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72acb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="72acb-108">Если ваша организация использует сервер управления сведениями о безопасности и событиями (SIEM), вы можете интегрировать Microsoft Defender для Office 365 с сервером SIEM.</span><span class="sxs-lookup"><span data-stu-id="72acb-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="72acb-109">Эту интеграцию можно настроить с помощью [API Office 365 управления деятельностью.](/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="72acb-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="72acb-110">Интеграция SIEM позволяет просматривать сведения, например вредоносные программы или фишинг, обнаруженные Microsoft Defender для Office 365, в отчетах на сервере SIEM.</span><span class="sxs-lookup"><span data-stu-id="72acb-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="72acb-111">Пример интеграции SIEM с Microsoft Defender для Office 365 см. в блоге Tech Community: Повышение эффективности вашего SOC с помощью Defender для Office 365 и API управления [O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="72acb-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>
- <span data-ttu-id="72acb-112">Дополнительные сведения об API Office 365 управления см. в Office 365 [API управления.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="72acb-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="72acb-113">Работа интеграции SIEM</span><span class="sxs-lookup"><span data-stu-id="72acb-113">How SIEM integration works</span></span>

<span data-ttu-id="72acb-114">API Office 365 управления деятельностью извлекает сведения о действиях пользователя, администратора, системы и политик и событиях из журналов Microsoft 365 и Azure Active Directory действий организации.</span><span class="sxs-lookup"><span data-stu-id="72acb-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="72acb-115">Если в вашей организации есть Microsoft Defender для Office 365 плана 1 или 2 или Office 365 E5, можно использовать схему Microsoft Defender для [Office 365.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="72acb-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="72acb-116">Недавно в API Office 365 управления событиями из возможностей автоматического расследования и ответа в Microsoft Defender для Office 365 Plan [2.](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)</span><span class="sxs-lookup"><span data-stu-id="72acb-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="72acb-117">Помимо добавления данных о основных данных расследования, таких как ID, имя и состояние, API также содержит сведения высокого уровня о следственных действиях и сущностях.</span><span class="sxs-lookup"><span data-stu-id="72acb-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="72acb-118">SiEM-сервер или другая аналогичная система опове-вает данные о рабочей нагрузке **audit.general** для доступа к событиям обнаружения.</span><span class="sxs-lookup"><span data-stu-id="72acb-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="72acb-119">Дополнительные дополнительные ссылки см. в Office 365 [API управления.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="72acb-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="72acb-120">Enum: AuditLogRecordType; Type: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="72acb-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="72acb-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="72acb-121">AuditLogRecordType</span></span>

<span data-ttu-id="72acb-122">В следующей таблице суммируют значения **AuditLogRecordType,** которые важны для Microsoft Defender для Office 365 событий:</span><span class="sxs-lookup"><span data-stu-id="72acb-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

<br>

****

|<span data-ttu-id="72acb-123">Значение</span><span class="sxs-lookup"><span data-stu-id="72acb-123">Value</span></span>|<span data-ttu-id="72acb-124">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="72acb-124">Member name</span></span>|<span data-ttu-id="72acb-125">Описание</span><span class="sxs-lookup"><span data-stu-id="72acb-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="72acb-126">28</span><span class="sxs-lookup"><span data-stu-id="72acb-126">28</span></span>|<span data-ttu-id="72acb-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="72acb-127">ThreatIntelligence</span></span>|<span data-ttu-id="72acb-128">События фишинга и вредоносных программ из Exchange Online Protection и Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="72acb-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="72acb-129">41</span><span class="sxs-lookup"><span data-stu-id="72acb-129">41</span></span>|<span data-ttu-id="72acb-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="72acb-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="72acb-131">Сейф Ссылки на время блокировки и переопределение событий из Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="72acb-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="72acb-132">47</span><span class="sxs-lookup"><span data-stu-id="72acb-132">47</span></span>|<span data-ttu-id="72acb-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="72acb-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="72acb-134">Фишинг и события вредоносных программ для файлов SharePoint Online, OneDrive для бизнеса и Microsoft Teams из Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="72acb-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="72acb-135">64</span><span class="sxs-lookup"><span data-stu-id="72acb-135">64</span></span>|<span data-ttu-id="72acb-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="72acb-136">AirInvestigation</span></span>|<span data-ttu-id="72acb-137">Автоматические события расследования и реагирования, такие как сведения о расследовании и соответствующие артефакты, из Microsoft Defender для Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="72acb-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="72acb-138">Вы должны быть глобальным администратором или иметь роль администратора безопасности, назначенную на портале Microsoft 365 Defender, чтобы настроить интеграцию SIEM с Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="72acb-138">You must be a global administrator or have the Security Administrator role assigned in the Microsoft 365 Defender portal to set up SIEM integration with Microsoft Defender for Office 365.</span></span> <span data-ttu-id="72acb-139">Дополнительные сведения см. в статье [Разрешения на портале Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="72acb-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
>
> <span data-ttu-id="72acb-140">Ведение журнала аудита должно быть включено для Microsoft 365 среды.</span><span class="sxs-lookup"><span data-stu-id="72acb-140">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="72acb-141">Чтобы получить помощь в этом, см. в справке о включите поиск [журнала аудита включите или отключите.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="72acb-141">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="72acb-142">См. также</span><span class="sxs-lookup"><span data-stu-id="72acb-142">See also</span></span>

[<span data-ttu-id="72acb-143">Анализ угроз и реагирование на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="72acb-143">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="72acb-144">Автоматическое расследование и ответ (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="72acb-144">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)