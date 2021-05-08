---
title: Настраиваемые решения для отчетов с автоматическим расследованием и ответом
keywords: SIEM, API, AIR, autoIR, Microsoft Defender for Endpoint, automated investigation, integration, custom report
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Узнайте, как интегрировать автоматизированное расследование и ответы с пользовательским или сторонним решением для отчетности.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275016"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="f59a2-104">Пользовательские или сторонние решения отчетности для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="f59a2-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="f59a2-105">С [помощью Microsoft Defender для Office 365](defender-for-office-365.md)вы получите подробные сведения об [автоматизированных расследованиях.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="f59a2-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="f59a2-106">Однако в некоторых организациях также используется настраиваемая или сторонная отчетность.</span><span class="sxs-lookup"><span data-stu-id="f59a2-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="f59a2-107">Если ваша организация хочет [](office-365-air.md) интегрировать сведения об автоматизированных расследованиях с таким решением, вы можете использовать API Office 365 управления.</span><span class="sxs-lookup"><span data-stu-id="f59a2-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="f59a2-108">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f59a2-108">**Applies to**</span></span>
- [<span data-ttu-id="f59a2-109">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="f59a2-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f59a2-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f59a2-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f59a2-111">С [помощью Microsoft Defender для Office 365](defender-for-office-365.md)вы получите подробные сведения об [автоматизированных расследованиях.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="f59a2-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="f59a2-112">Однако в некоторых организациях также используется настраиваемая или сторонная отчетность.</span><span class="sxs-lookup"><span data-stu-id="f59a2-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="f59a2-113">Если ваша организация хочет интегрировать сведения об автоматизированных расследованиях с таким решением, можно использовать API Office 365 управления.</span><span class="sxs-lookup"><span data-stu-id="f59a2-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="f59a2-114">Resource</span><span class="sxs-lookup"><span data-stu-id="f59a2-114">Resource</span></span>|<span data-ttu-id="f59a2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f59a2-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="f59a2-116">Обзор API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="f59a2-116">Office 365 Management APIs overview</span></span>](/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="f59a2-117">API Office 365 управления предоставляет сведения о различных действиях и событиях и действиях пользователей, администраторов, систем и политик из журналов Microsoft 365 и Azure Active Directory действий.</span><span class="sxs-lookup"><span data-stu-id="f59a2-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="f59a2-118">Начало работы с API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="f59a2-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="f59a2-119">API Office 365 управления использует Azure AD для предоставления служб проверки подлинности для приложения для доступа к Microsoft 365 данным.</span><span class="sxs-lookup"><span data-stu-id="f59a2-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="f59a2-120">Выполните действия в этой статье, чтобы настроить это.</span><span class="sxs-lookup"><span data-stu-id="f59a2-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="f59a2-121">Справочник по API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="f59a2-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="f59a2-122">API Office 365 управления можно использовать для получения сведений о действиях и событиях пользователей, администраторов, систем и политик из журналов Microsoft 365 и Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f59a2-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="f59a2-123">Подробнее о том, как это работает, читайте в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f59a2-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="f59a2-124">Схема API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="f59a2-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="f59a2-125">Узнайте [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) об [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) определенных видах данных, доступных в API Office 365 управления.</span><span class="sxs-lookup"><span data-stu-id="f59a2-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="f59a2-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f59a2-126">See also</span></span>

- [<span data-ttu-id="f59a2-127">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="f59a2-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f59a2-128">Автоматическое расследование и ответ в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f59a2-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
