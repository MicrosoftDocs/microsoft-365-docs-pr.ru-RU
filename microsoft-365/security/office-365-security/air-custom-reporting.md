---
title: Пользовательские решения для отчетов с автоматизированным исследованием и реагированием
keywords: SIEM, API, AIR, autoIR, ATP, автоматизированное исследование, интеграция, настраиваемый отчет
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
description: Узнайте, как интегрировать автоматизированное исследование и реагирование на них с пользовательским или сторонним решением для отчетности.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13782a8e0a8c691a66f214d3f9f03ef9cad4da1f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287141"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="74264-104">Пользовательские или сторонние решения для отчетов в Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="74264-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="74264-105">С [помощью Microsoft Defender для Office 365](office-365-atp.md)вы получаете подробные сведения об [автоматизированных расследованиях.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="74264-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="74264-106">Однако в некоторых организациях также используется пользовательское или стороне решение для отчетов.</span><span class="sxs-lookup"><span data-stu-id="74264-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="74264-107">Если ваша организация хочет [](office-365-air.md) интегрировать сведения об автоматизированных расследованиях с таким решением, вы можете использовать API действий управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="74264-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="74264-108">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="74264-108">**Applies to**</span></span>
- [<span data-ttu-id="74264-109">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="74264-109">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="74264-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74264-110">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="74264-111">С [помощью Microsoft Defender для Office 365](office-365-atp.md)вы получаете подробные сведения об [автоматизированных расследованиях.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="74264-111">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="74264-112">Однако в некоторых организациях также используется пользовательское или стороне решение для отчетов.</span><span class="sxs-lookup"><span data-stu-id="74264-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="74264-113">Если ваша организация хочет интегрировать сведения об автоматизированных расследованиях с таким решением, вы можете использовать API действий управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="74264-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="74264-114">Ресурс</span><span class="sxs-lookup"><span data-stu-id="74264-114">Resource</span></span>|<span data-ttu-id="74264-115">Описание</span><span class="sxs-lookup"><span data-stu-id="74264-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="74264-116">Обзор API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="74264-116">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="74264-117">API действий управления Office 365 предоставляет сведения о различных действиях и событиях пользователей, администраторов, систем и политик из журналов действий Microsoft 365 и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74264-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="74264-118">Начало работы с API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="74264-118">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="74264-119">API управления Office 365 использует Azure AD для предоставления служб проверки подлинности вашему приложению для доступа к данным Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74264-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="74264-120">Чтобы настроить эту возможность, выполните действия, которые необходимо предпринять в этой статье.</span><span class="sxs-lookup"><span data-stu-id="74264-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="74264-121">Справочник по API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="74264-121">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="74264-122">Вы можете использовать API действий управления Office 365 для получения сведений о действиях и событиях пользователей, администраторов, систем и политик из журналов действий Microsoft 365 и Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74264-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="74264-123">Прочитайте эту статью, чтобы узнать больше о том, как это работает.</span><span class="sxs-lookup"><span data-stu-id="74264-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="74264-124">Схема API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="74264-124">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="74264-125">Обзор общей схемы и Защитника [Office 365,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) а также схемы анализа угроз и реагирования на них, чтобы узнать о конкретных типах данных, доступных через API действий управления Office 365. [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)</span><span class="sxs-lookup"><span data-stu-id="74264-125">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="74264-126">См. также</span><span class="sxs-lookup"><span data-stu-id="74264-126">See also</span></span>

- [<span data-ttu-id="74264-127">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="74264-127">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="74264-128">Автоматическое исследование и реагирование в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74264-128">Automated investigation and response in Microsoft 365 Defender</span></span>](../mtp/mtp-autoir.md)
