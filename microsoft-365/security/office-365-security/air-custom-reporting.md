---
title: Настраиваемые решения для отчетов с автоматическим расследованием и ответом
keywords: SIEM, API, AIR, autoIR, ATP, automated investigation, integration, custom report
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
ms.openlocfilehash: 9f62d73417cc4d7ecaa113ae1c304630ef1852eb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921436"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="0b2c1-104">Пользовательские или сторонние решения отчетности для Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="0b2c1-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0b2c1-105">В [Microsoft Defender для Office 365](office-365-atp.md)вы получите подробные сведения об [автоматизированных расследованиях.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="0b2c1-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="0b2c1-106">Однако в некоторых организациях также используется настраиваемая или сторонная отчетность.</span><span class="sxs-lookup"><span data-stu-id="0b2c1-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="0b2c1-107">Если ваша организация хочет [](office-365-air.md) интегрировать сведения об автоматизированных расследованиях с таким решением, вы можете использовать API управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="0b2c1-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="0b2c1-108">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="0b2c1-108">**Applies to**</span></span>
- [<span data-ttu-id="0b2c1-109">Microsoft Defender для Office 365 (план 2)</span><span class="sxs-lookup"><span data-stu-id="0b2c1-109">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="0b2c1-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b2c1-110">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="0b2c1-111">В [Microsoft Defender для Office 365](office-365-atp.md)вы получите подробные сведения об [автоматизированных расследованиях.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="0b2c1-111">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="0b2c1-112">Однако в некоторых организациях также используется настраиваемая или сторонная отчетность.</span><span class="sxs-lookup"><span data-stu-id="0b2c1-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="0b2c1-113">Если ваша организация хочет интегрировать сведения об автоматизированных расследованиях с таким решением, вы можете использовать API управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="0b2c1-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="0b2c1-114">Resource</span><span class="sxs-lookup"><span data-stu-id="0b2c1-114">Resource</span></span>|<span data-ttu-id="0b2c1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0b2c1-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="0b2c1-116">Обзор API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="0b2c1-116">Office 365 Management APIs overview</span></span>](/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="0b2c1-117">API управления Office 365 предоставляет сведения о различных действиях пользователя, администратора, системы и политик и событиях из журналов действий Microsoft 365 и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0b2c1-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="0b2c1-118">Начало работы с API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="0b2c1-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="0b2c1-119">API управления Office 365 использует Azure AD для предоставления служб проверки подлинности для приложения для доступа к данным Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0b2c1-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="0b2c1-120">Выполните действия в этой статье, чтобы настроить это.</span><span class="sxs-lookup"><span data-stu-id="0b2c1-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="0b2c1-121">Справочник по API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="0b2c1-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="0b2c1-122">API управления Office 365 можно использовать для получения сведений о действиях пользователя, администратора, системы и политик и событиях из журналов действий Microsoft 365 и Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0b2c1-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="0b2c1-123">Подробнее о том, как это работает, читайте в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0b2c1-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="0b2c1-124">Схема API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="0b2c1-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="0b2c1-125">Обзор общей схемы и защитника [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) и схемы расследования угроз и ответов, чтобы узнать о конкретных видах данных, доступных в API управления Office 365. [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)</span><span class="sxs-lookup"><span data-stu-id="0b2c1-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="0b2c1-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0b2c1-126">See also</span></span>

- [<span data-ttu-id="0b2c1-127">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="0b2c1-127">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="0b2c1-128">Автоматическое исследование и ответ в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b2c1-128">Automated investigation and response in Microsoft 365 Defender</span></span>](../mtp/mtp-autoir.md)