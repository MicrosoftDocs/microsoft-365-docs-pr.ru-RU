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
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: Интеграция сервера SIEM в Организации с Office 365 Advanced Threat Protection и связанными событиями угроз в API управления действиями Office 365.
ms.openlocfilehash: 770e2348c4e5729531118fb4a014a72c352a0dd1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638300"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="f3d7b-103">Интеграция SIEM с расширенной защитой угроз</span><span class="sxs-lookup"><span data-stu-id="f3d7b-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="f3d7b-104">Если в организации используется сервер управления инцидентами и событиями SIEM, вы можете интегрировать Office 365 Advanced Threat protection с сервером SIEM.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="f3d7b-105">Интеграция SIEM позволяет просматривать сведения, такие как вредоносные программы и фишинг, обнаруженные в Office 365 Advanced Protection, в отчетах сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="f3d7b-106">Для настройки интеграции с SIEM используется [API управления действиями Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="f3d7b-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="f3d7b-107">API управления действиями Office 365 получает сведения о действиях пользователя, администратора, системы, а также о событиях и политиках в журналах активности организации Microsoft 365 для бизнеса и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 for business and Azure Active Directory activity logs.</span></span> <span data-ttu-id="f3d7b-108">[Схема Advanced Threat Protection в office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) работает с Advanced Threat Protection, поэтому если в 365 организации используется Advanced Threat protection (план 1) или план 2 или Office 365, вы по-прежнему можете использовать тот же API для интеграции сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="f3d7b-109">В ходе последних обновлений мы также добавили события из автоматизированного исследования и возможности реагирования в Office 365 ATP (план 2) в API действий управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="f3d7b-110">Помимо включения данных об основных сведениях расследования, таких как ID, Name и Status, он также содержит сведения высокого уровня о действиях и сущностях расследования.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>   

<span data-ttu-id="f3d7b-111">Сервер SIEM или другая подобная система должны опрашивать события **аудита. Общая** Рабочая нагрузка для доступа к событиям обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="f3d7b-112">Чтобы узнать больше, ознакомьтесь [со статьей начало работы с API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="f3d7b-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="f3d7b-113">Кроме того, для событий Office 365 ATP важны следующие значения **аудитлогрекордтипе** :</span><span class="sxs-lookup"><span data-stu-id="f3d7b-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="f3d7b-114">Enum: AuditLogRecordType; Type: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="f3d7b-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="f3d7b-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="f3d7b-115">AuditLogRecordType</span></span>

|<span data-ttu-id="f3d7b-116">Значение</span><span class="sxs-lookup"><span data-stu-id="f3d7b-116">Value</span></span>|<span data-ttu-id="f3d7b-117">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="f3d7b-117">Member name</span></span>|<span data-ttu-id="f3d7b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f3d7b-118">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f3d7b-119">8</span><span class="sxs-lookup"><span data-stu-id="f3d7b-119">28</span></span>|<span data-ttu-id="f3d7b-120">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="f3d7b-120">ThreatIntelligence</span></span>|<span data-ttu-id="f3d7b-121">События фишинга и вредоносных программ из Exchange Online Protection и Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="f3d7b-122">41</span><span class="sxs-lookup"><span data-stu-id="f3d7b-122">41</span></span>|<span data-ttu-id="f3d7b-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="f3d7b-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="f3d7b-124">События "безопасные ссылки" ATP "время блокировки" и "переопределение блока" из Office 365 Advanced Threat protection.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="f3d7b-125">47</span><span class="sxs-lookup"><span data-stu-id="f3d7b-125">47</span></span>|<span data-ttu-id="f3d7b-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="f3d7b-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="f3d7b-127">События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams из Office 365 Advanced Threat protection.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="f3d7b-128">64</span><span class="sxs-lookup"><span data-stu-id="f3d7b-128">64</span></span>|<span data-ttu-id="f3d7b-129">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="f3d7b-129">AirInvestigation</span></span>|<span data-ttu-id="f3d7b-130">Автоматизированные события расследования и реагирования, такие как сведения об исследовании и необходимые компоненты из Office 365 Advanced Threat Protection Plan 2.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|


> [!IMPORTANT]
> <span data-ttu-id="f3d7b-131">Для настройки интеграции SIEM с Office 365 Advanced Threat Protection необходимо быть глобальным администратором или иметь роль администратора безопасности, назначенную для центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-131">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="f3d7b-132">Для вашей среды Microsoft 365 должна быть включена функция ведения журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="f3d7b-132">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="f3d7b-133">Чтобы получить помощь по этому, ознакомьтесь со статьей [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="f3d7b-133">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3d7b-134">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f3d7b-134">Related topics</span></span>

[<span data-ttu-id="f3d7b-135">Анализ угроз и реагирование на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="f3d7b-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="f3d7b-136">Автоматическое исследование и реагирование (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="f3d7b-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="f3d7b-137">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f3d7b-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="f3d7b-138">Интеллектуальные отчеты и аналитика в центре безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="f3d7b-138">Smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="f3d7b-139">Разрешения в центре безопасности &amp; и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="f3d7b-139">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
