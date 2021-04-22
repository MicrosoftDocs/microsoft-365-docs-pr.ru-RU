---
title: Настраиваемые решения для отчетов с автоматическим расследованием и ответом
keywords: SIEM, API, AIR, autoIR, Microsoft Defender for Endpoint, automated investigation, integration, custom report
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: 4a7ccc0f07691c5183b9cb7a6e5b3f512f35f76b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935405"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="63f54-104">Пользовательские или сторонние решения отчетности для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="63f54-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="63f54-105">В [Microsoft Defender для Office 365](defender-for-office-365.md)вы получите подробные сведения об [автоматизированных расследованиях.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="63f54-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="63f54-106">Однако в некоторых организациях также используется настраиваемая или сторонная отчетность.</span><span class="sxs-lookup"><span data-stu-id="63f54-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="63f54-107">Если ваша организация хочет [](office-365-air.md) интегрировать сведения об автоматизированных расследованиях с таким решением, вы можете использовать API управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="63f54-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="63f54-108">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="63f54-108">**Applies to**</span></span>
- [<span data-ttu-id="63f54-109">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="63f54-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="63f54-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63f54-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="63f54-111">В [Microsoft Defender для Office 365](defender-for-office-365.md)вы получите подробные сведения об [автоматизированных расследованиях.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="63f54-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="63f54-112">Однако в некоторых организациях также используется настраиваемая или сторонная отчетность.</span><span class="sxs-lookup"><span data-stu-id="63f54-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="63f54-113">Если ваша организация хочет интегрировать сведения об автоматизированных расследованиях с таким решением, вы можете использовать API управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="63f54-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="63f54-114">Resource</span><span class="sxs-lookup"><span data-stu-id="63f54-114">Resource</span></span>|<span data-ttu-id="63f54-115">Описание</span><span class="sxs-lookup"><span data-stu-id="63f54-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="63f54-116">Обзор API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="63f54-116">Office 365 Management APIs overview</span></span>](/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="63f54-117">API управления Office 365 предоставляет сведения о различных действиях пользователя, администратора, системы и политик и событиях из журналов действий Microsoft 365 и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="63f54-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="63f54-118">Начало работы с API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="63f54-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="63f54-119">API управления Office 365 использует Azure AD для предоставления служб проверки подлинности для приложения для доступа к данным Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="63f54-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="63f54-120">Выполните действия в этой статье, чтобы настроить это.</span><span class="sxs-lookup"><span data-stu-id="63f54-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="63f54-121">Справочник по API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="63f54-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="63f54-122">API управления Office 365 можно использовать для получения сведений о действиях пользователя, администратора, системы и политик и событиях из журналов действий Microsoft 365 и Azure AD.</span><span class="sxs-lookup"><span data-stu-id="63f54-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="63f54-123">Подробнее о том, как это работает, читайте в этой статье.</span><span class="sxs-lookup"><span data-stu-id="63f54-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="63f54-124">Схема API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="63f54-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="63f54-125">Обзор общей схемы и защитника [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) и схемы расследования угроз и ответов, чтобы узнать о конкретных видах данных, доступных в API управления Office 365. [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)</span><span class="sxs-lookup"><span data-stu-id="63f54-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="63f54-126">См. также</span><span class="sxs-lookup"><span data-stu-id="63f54-126">See also</span></span>

- [<span data-ttu-id="63f54-127">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="63f54-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="63f54-128">Автоматическое исследование и ответ в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63f54-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
