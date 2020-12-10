---
title: Интеграция SIEM с защитником Майкрософт для Office 365
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
description: Интеграция сервера SIEM в Организации с защитником Майкрософт для Office 365 и связанными событиями угроз в API управления действиями Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 93ff1606130c60ceb46087d28bb26f9a6d27d330
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615664"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="3471d-103">Интеграция SIEM с защитником Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="3471d-103">SIEM integration with Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3471d-104">Если в Организации используются сведения о безопасности и управление событиями (SIEM), можно интегрировать защитник Майкрософт для Office 365 с сервером SIEM.</span><span class="sxs-lookup"><span data-stu-id="3471d-104">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="3471d-105">Эту интеграцию можно настроить с помощью [API управления действиями Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="3471d-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="3471d-106">Интеграция SIEM позволяет просматривать сведения, такие как вредоносные программы и фишинг, обнаруженные защитником Майкрософт для Office 365, в отчетах сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="3471d-106">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="3471d-107">Чтобы просмотреть пример интеграции SIEM с защитником Майкрософт для Office 365, посетите [блог технического сообщества: улучшите эффективность SoC с помощью защитника для Office 365 и API управления O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="3471d-107">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="3471d-108">Дополнительные сведения об API управления Office 365 можно найти в статье [Обзор API управления office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="3471d-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="3471d-109">Как работает интеграция SIEM</span><span class="sxs-lookup"><span data-stu-id="3471d-109">How SIEM integration works</span></span>

<span data-ttu-id="3471d-110">API управления действиями Office 365 извлекает сведения о действиях пользователя, администратора, системы, а также о событиях и политиках из журналов активности Microsoft 365 и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3471d-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="3471d-111">Если в вашей организации используется защитник Майкрософт для Office 365 (план 1 или 2) или Office 365 в ~, вы можете использовать [схему Microsoft Defender для office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span><span class="sxs-lookup"><span data-stu-id="3471d-111">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="3471d-112">Недавно в API действий по управлению Office 365 были добавлены события автоматизированного исследования и возможности реагирования в [защитнике Майкрософт для office 365 (план 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) ).</span><span class="sxs-lookup"><span data-stu-id="3471d-112">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="3471d-113">В дополнение к включению данных об основных сведениях расследования, таких как ID, Name и Status, API также содержит подробные сведения о действиях и сущностях расследования.</span><span class="sxs-lookup"><span data-stu-id="3471d-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="3471d-114">Сервер SIEM или другая подобная система опрашивает рабочую нагрузку **Audit. General** для доступа к событиям обнаружения.</span><span class="sxs-lookup"><span data-stu-id="3471d-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="3471d-115">Чтобы узнать больше, ознакомьтесь [со статьей начало работы с API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="3471d-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="3471d-116">Enum: AuditLogRecordType; Type: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="3471d-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="3471d-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="3471d-117">AuditLogRecordType</span></span>

<span data-ttu-id="3471d-118">В следующей таблице приведены значения **аудитлогрекордтипе** , относящиеся к защитнику Майкрософт для событий Office 365:</span><span class="sxs-lookup"><span data-stu-id="3471d-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="3471d-119">Значение</span><span class="sxs-lookup"><span data-stu-id="3471d-119">Value</span></span>|<span data-ttu-id="3471d-120">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="3471d-120">Member name</span></span>|<span data-ttu-id="3471d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="3471d-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="3471d-122">8</span><span class="sxs-lookup"><span data-stu-id="3471d-122">28</span></span>|<span data-ttu-id="3471d-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="3471d-123">ThreatIntelligence</span></span>|<span data-ttu-id="3471d-124">События фишинга и вредоносных программ из Exchange Online Protection и защитник Майкрософт для Office 365.</span><span class="sxs-lookup"><span data-stu-id="3471d-124">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="3471d-125">41</span><span class="sxs-lookup"><span data-stu-id="3471d-125">41</span></span>|<span data-ttu-id="3471d-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="3471d-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="3471d-127">События времени блокировки и переопределения блокировки для безопасных ссылок в защитнике Майкрософт для Office 365.</span><span class="sxs-lookup"><span data-stu-id="3471d-127">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="3471d-128">47</span><span class="sxs-lookup"><span data-stu-id="3471d-128">47</span></span>|<span data-ttu-id="3471d-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="3471d-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="3471d-130">События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams от защитника Майкрософт для Office 365.</span><span class="sxs-lookup"><span data-stu-id="3471d-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="3471d-131">64</span><span class="sxs-lookup"><span data-stu-id="3471d-131">64</span></span>|<span data-ttu-id="3471d-132">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="3471d-132">AirInvestigation</span></span>|<span data-ttu-id="3471d-133">Автоматическое исследование и события ответа, такие как сведения об исследовании и необходимые артефакты, от защитника Майкрософт для Office 365 (план 2).</span><span class="sxs-lookup"><span data-stu-id="3471d-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="3471d-134">Для настройки интеграции SIEM с защитником Майкрософт для Office 365 необходимо быть глобальным администратором или иметь роль администратора безопасности, назначенную для центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3471d-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="3471d-135">Для вашей среды Microsoft 365 должна быть включена функция ведения журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="3471d-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="3471d-136">Чтобы получить помощь по этому, ознакомьтесь со статьей [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="3471d-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3471d-137">См. также</span><span class="sxs-lookup"><span data-stu-id="3471d-137">See also</span></span>

[<span data-ttu-id="3471d-138">Анализ угроз и реагирование на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="3471d-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="3471d-139">Автоматическое исследование и реагирование (AIR) в Office 365</span><span class="sxs-lookup"><span data-stu-id="3471d-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

