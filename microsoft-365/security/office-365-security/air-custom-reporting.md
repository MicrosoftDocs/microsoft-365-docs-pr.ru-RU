---
title: Использование настраиваемых решений для создания отчетов с автоматизированным исследованием и ответом
keywords: SIEM, API, AIR, Аутоир, ATP, автоматическое исследование, интеграция, настраиваемый отчет
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Сведения о том, как интегрировать автоматическое исследование и отвечать с помощью настраиваемого или стороннего решения для создания отчетов.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 9bc5de44700b7f1b7207f8fae002adcb55d32841
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446687"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="6e86b-104">Использование API действий управления для настраиваемых и сторонних решений для создания отчетов</span><span class="sxs-lookup"><span data-stu-id="6e86b-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6e86b-105">С помощью [защитника Microsoft для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)вы получаете [подробные сведения об автоматическом расследовании](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="6e86b-105">With [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="6e86b-106">Однако в некоторых организациях также используется собственное или стороннее решение для создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="6e86b-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="6e86b-107">Если в Организации требуется интегрировать сведения об автоматическом расследовании с таким решением, вы можете использовать API действий управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e86b-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="6e86b-108">Используйте следующие ресурсы для настройки:</span><span class="sxs-lookup"><span data-stu-id="6e86b-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="6e86b-109">Ресурс</span><span class="sxs-lookup"><span data-stu-id="6e86b-109">Resource</span></span>|<span data-ttu-id="6e86b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="6e86b-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="6e86b-111">Обзор API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="6e86b-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="6e86b-112">API действий управления Office 365 предоставляет сведения о различных действиях и событиях пользователя, администратора, системы и политики из Microsoft 365 и журналов активности Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6e86b-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="6e86b-113">Начало работы с API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="6e86b-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="6e86b-114">API управления Office 365 использует Azure AD для предоставления службам проверки подлинности приложениям доступа к данным Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6e86b-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="6e86b-115">Выполните действия, описанные в этой статье, чтобы настроить ее.</span><span class="sxs-lookup"><span data-stu-id="6e86b-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="6e86b-116">Справочник по API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="6e86b-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="6e86b-117">Вы можете использовать API действий управления Office 365 для получения сведений о действиях пользователя, администратора, системы, а также событиях и событиях из Microsoft 365 и журналов активности Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6e86b-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="6e86b-118">Прочтите эту статью, чтобы узнать больше о том, как это работает.</span><span class="sxs-lookup"><span data-stu-id="6e86b-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="6e86b-119">Схема API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="6e86b-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="6e86b-120">В этой статье представлены общие сведения о конкретных типах данных, доступных через API действий управления Office 365, а также сведения о том, как ознакомиться с [общими схемами](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) и сведениями об [анализе и ответе на Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) .</span><span class="sxs-lookup"><span data-stu-id="6e86b-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="6e86b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="6e86b-121">See also</span></span>

- [<span data-ttu-id="6e86b-122">Защитник Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="6e86b-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

- [<span data-ttu-id="6e86b-123">Автоматическое исследование и ответ в защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6e86b-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
