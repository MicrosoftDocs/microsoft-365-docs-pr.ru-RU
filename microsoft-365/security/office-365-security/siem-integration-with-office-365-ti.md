---
title: Интеграция SIEM с расширенной защитой угроз
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
description: Интеграция сервера SIEM в Организации с Office 365 Advanced Threat Protection и связанными событиями угроз в API управления действиями Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 544093960570fe0e68ac47dc7bf9965fba2d30a1
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327169"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="c6244-103">Интеграция SIEM с расширенной защитой угроз</span><span class="sxs-lookup"><span data-stu-id="c6244-103">SIEM integration with Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c6244-104">Если в организации используется сервер управления инцидентами и событиями SIEM, вы можете интегрировать Office 365 Advanced Threat protection (Office 365 ATP) с сервером SIEM.</span><span class="sxs-lookup"><span data-stu-id="c6244-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="c6244-105">Эту интеграцию можно настроить с помощью [API управления действиями Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="c6244-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="c6244-106">Интеграция SIEM позволяет просматривать сведения, такие как вредоносные и фишингы, обнаруженные в Office 365 ATP, в отчетах сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="c6244-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="c6244-107">Пример интеграции SIEM с Office 365 ATP можно найти в [блоге технического сообщества: улучшите эффективность SoC с помощью office 365 ATP и API управления O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="c6244-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="c6244-108">Дополнительные сведения об API управления Office 365 можно найти в статье [Обзор API управления office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="c6244-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="c6244-109">Как работает интеграция SIEM</span><span class="sxs-lookup"><span data-stu-id="c6244-109">How SIEM integration works</span></span>

<span data-ttu-id="c6244-110">API управления действиями Office 365 извлекает сведения о действиях пользователя, администратора, системы, а также о событиях и политиках из журналов активности Microsoft 365 и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c6244-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="c6244-111">Если в вашей организации используется Office 365 ATP, план 1 или 2, или Office 365 в ~, вы можете использовать [схему office 365 ATP](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span><span class="sxs-lookup"><span data-stu-id="c6244-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="c6244-112">Недавно в API действий управления Office 365 были добавлены события автоматизированного исследования и возможности реагирования в [office 365 ATP 2 (план 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) ).</span><span class="sxs-lookup"><span data-stu-id="c6244-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="c6244-113">В дополнение к включению данных об основных сведениях расследования, таких как ID, Name и Status, API также содержит подробные сведения о действиях и сущностях расследования.</span><span class="sxs-lookup"><span data-stu-id="c6244-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="c6244-114">Сервер SIEM или другая подобная система опрашивает рабочую нагрузку **Audit. General** для доступа к событиям обнаружения.</span><span class="sxs-lookup"><span data-stu-id="c6244-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="c6244-115">Чтобы узнать больше, ознакомьтесь [со статьей начало работы с API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="c6244-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="c6244-116">Enum: AuditLogRecordType; Type: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="c6244-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="c6244-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="c6244-117">AuditLogRecordType</span></span>

<span data-ttu-id="c6244-118">В следующей таблице приведены значения **аудитлогрекордтипе** , относящиеся к событиям ATP для Office 365:</span><span class="sxs-lookup"><span data-stu-id="c6244-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="c6244-119">Значение</span><span class="sxs-lookup"><span data-stu-id="c6244-119">Value</span></span>|<span data-ttu-id="c6244-120">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="c6244-120">Member name</span></span>|<span data-ttu-id="c6244-121">Описание</span><span class="sxs-lookup"><span data-stu-id="c6244-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="c6244-122">8</span><span class="sxs-lookup"><span data-stu-id="c6244-122">28</span></span>|<span data-ttu-id="c6244-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="c6244-123">ThreatIntelligence</span></span>|<span data-ttu-id="c6244-124">События фишинга и вредоносных программ из Exchange Online Protection и Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="c6244-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="c6244-125">41</span><span class="sxs-lookup"><span data-stu-id="c6244-125">41</span></span>|<span data-ttu-id="c6244-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="c6244-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="c6244-127">События времени блокировки и переопределения блоков для безопасных ссылок из Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="c6244-127">Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="c6244-128">47</span><span class="sxs-lookup"><span data-stu-id="c6244-128">47</span></span>|<span data-ttu-id="c6244-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="c6244-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="c6244-130">События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams из Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="c6244-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="c6244-131">64</span><span class="sxs-lookup"><span data-stu-id="c6244-131">64</span></span>|<span data-ttu-id="c6244-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="c6244-132">AirInvestigation</span></span>|<span data-ttu-id="c6244-133">Автоматическое исследование и события ответа, такие как сведения об исследовании и необходимые артефакты, из Office 365 ATP (план 2).</span><span class="sxs-lookup"><span data-stu-id="c6244-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="c6244-134">Для настройки интеграции SIEM с Office 365 Advanced Threat Protection необходимо быть глобальным администратором или иметь роль администратора безопасности, назначенную для центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c6244-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="c6244-135">Для вашей среды Microsoft 365 должна быть включена функция ведения журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="c6244-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="c6244-136">Чтобы получить помощь по этому, ознакомьтесь со статьей [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="c6244-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6244-137">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c6244-137">See also</span></span>

[<span data-ttu-id="c6244-138">Анализ угроз и реагирование на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="c6244-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="c6244-139">Автоматическое исследование и реагирование (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="c6244-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)


