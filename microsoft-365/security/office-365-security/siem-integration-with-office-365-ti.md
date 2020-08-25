---
title: Интеграция SIEM с Advanced Threat Protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Интеграция сервера SIEM вашей организации с Office 365 Advanced Threat Protection и связанными событиями в API управления действиями Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e9dcf24adfb227d0c454b4f5952c879cea511f7
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860693"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="8de39-103">Интеграция SIEM с Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8de39-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="8de39-104">Если ваша организация использует сервер SIEM инцидентов безопасности и событий безопасности, вы можете интегрировать Office 365 Advanced Threat Protection (Office 365 ATP) с сервером SIEM.</span><span class="sxs-lookup"><span data-stu-id="8de39-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="8de39-105">Эту интеграцию можно настроить с помощью [API управления действиями Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="8de39-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="8de39-106">Интеграция SIEM позволяет просматривать сведения, например вредоносное ПО или фишинг, обнаруженный Office 365 ATP, в отчетах сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="8de39-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="8de39-107">Пример интеграции SIEM с Office 365 ATP см. в блоге [Tech Community: Улучшение эффективности SOC с помощью Office 365 ATP и API управления Office 365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)</span><span class="sxs-lookup"><span data-stu-id="8de39-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="8de39-108">Дополнительные сведения об API управления Office 365 см. в обзоре API управления [Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="8de39-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="8de39-109">Принцип интеграции SIEM</span><span class="sxs-lookup"><span data-stu-id="8de39-109">How SIEM integration works</span></span>

<span data-ttu-id="8de39-110">API управления действиями Office 365 получает информацию о действиях и событиях пользователя, администратора, системы и политики из журналов действий Microsoft 365 и Azure Active Directory вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8de39-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="8de39-111">Если у вашей организации есть План 1, 2 или Office 365 E5, вы можете использовать [схему Office 365 ATP.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="8de39-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="8de39-112">Недавно события возможностей автоматизированного анализа угроз и реагирования на них в [Office 365 ATP (план 2) были](office-365-atp.md#office-365-atp-plan-1-and-plan-2) добавлены в API действий управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="8de39-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="8de39-113">Помимо сведений об основных сведениях об исследовании, таких как идентификатор, имя и состояние, API также содержит высокоуровневые сведения о действиях и объектах анализа.</span><span class="sxs-lookup"><span data-stu-id="8de39-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="8de39-114">Сервер SIEM или другая подобная система опросит **участие audit.general** workload, чтобы получить доступ к событиям обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8de39-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="8de39-115">Дополнительные сведения см. в статье ["Начало работы с API управления Office 365".](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="8de39-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 


## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="8de39-116">Enum: AuditLogRecordType; Type: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="8de39-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="8de39-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="8de39-117">AuditLogRecordType</span></span>

<span data-ttu-id="8de39-118">Значения **свойства AuditLogRecordType,** относящиеся к событиям Office 365 ATP, см. в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8de39-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="8de39-119">Значение</span><span class="sxs-lookup"><span data-stu-id="8de39-119">Value</span></span>|<span data-ttu-id="8de39-120">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="8de39-120">Member name</span></span>|<span data-ttu-id="8de39-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8de39-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="8de39-122">28</span><span class="sxs-lookup"><span data-stu-id="8de39-122">28</span></span>|<span data-ttu-id="8de39-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="8de39-123">ThreatIntelligence</span></span>|<span data-ttu-id="8de39-124">События фишинга и вредоносных программ из Exchange Online Protection и Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="8de39-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="8de39-125">41</span><span class="sxs-lookup"><span data-stu-id="8de39-125">41</span></span>|<span data-ttu-id="8de39-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="8de39-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="8de39-127">События времени блокировки безопасных ссылок ATP и переопределения блокировки из Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="8de39-127">ATP Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="8de39-128">47</span><span class="sxs-lookup"><span data-stu-id="8de39-128">47</span></span>|<span data-ttu-id="8de39-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="8de39-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="8de39-130">События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams из Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="8de39-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="8de39-131">64</span><span class="sxs-lookup"><span data-stu-id="8de39-131">64</span></span>|<span data-ttu-id="8de39-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="8de39-132">AirInvestigation</span></span>|<span data-ttu-id="8de39-133">Автоматизированное исследование событий анализа угроз и реагирование на них, например сведения об исследовании и соответствующие артефакты, из Office 365 ATP (план 2).</span><span class="sxs-lookup"><span data-stu-id="8de39-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="8de39-134">Для настройки интеграции SIEM & с Office 365 Advanced Threat Protection вам необходимо быть глобальным администратором или вам должна быть назначена роль администратора безопасности, назначенная в Центре соответствия требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="8de39-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="8de39-135">Ведение журнала аудита должно быть включено для вашей среды Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8de39-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="8de39-136">Чтобы получить справку, см. раздел ["Включение и отключение поиска в журнале аудита".](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="8de39-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8de39-137">См. также</span><span class="sxs-lookup"><span data-stu-id="8de39-137">See also</span></span>

[<span data-ttu-id="8de39-138">Анализ угроз и реагирование на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="8de39-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="8de39-139">Автоматизированный анализ угроз и реагирование на них (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="8de39-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)


