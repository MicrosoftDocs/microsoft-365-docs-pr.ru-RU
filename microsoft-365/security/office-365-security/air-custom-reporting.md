---
title: Использование настраиваемых решений для создания отчетов с автоматизированным исследованием и ответом
keywords: ВОЗДУШный, Аутоир, ATP, автоматизированный, исследование, ответ, исправление, угрозы, усовершенствованный, угроза, защита
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
ms.collection: M365-security-compliance
description: Сведения о том, как интегрировать автоматическое исследование и отвечать с помощью настраиваемого или стороннего решения для создания отчетов.
ms.openlocfilehash: 2ff0ef995fc8418c3d57895f00ea96f05b0aaa97
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195609"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="34c59-104">Использование API действий управления для настраиваемых и сторонних решений для создания отчетов</span><span class="sxs-lookup"><span data-stu-id="34c59-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="34c59-105">С помощью [Office 365 Advanced Threat protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)вы получаете [подробные сведения об автоматическом расследовании](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="34c59-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="34c59-106">Однако в некоторых организациях также используется собственное или стороннее решение для создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="34c59-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="34c59-107">Если в Организации требуется интегрировать сведения об автоматическом расследовании с таким решением, вы можете использовать API действий управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="34c59-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="34c59-108">Используйте следующие ресурсы для настройки:</span><span class="sxs-lookup"><span data-stu-id="34c59-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="34c59-109">Ресурс</span><span class="sxs-lookup"><span data-stu-id="34c59-109">Resource</span></span>|<span data-ttu-id="34c59-110">Описание</span><span class="sxs-lookup"><span data-stu-id="34c59-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="34c59-111">Обзор API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="34c59-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="34c59-112">API действий управления Office 365 предоставляет сведения о различных действиях и событиях пользователя, администратора, системы и политики из Microsoft 365 и журналов активности Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34c59-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="34c59-113">Начало работы с API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="34c59-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="34c59-114">API управления Office 365 использует Azure AD для предоставления службам проверки подлинности приложениям доступа к данным Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34c59-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="34c59-115">Выполните действия, описанные в этой статье, чтобы настроить ее.</span><span class="sxs-lookup"><span data-stu-id="34c59-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="34c59-116">Справочник по API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="34c59-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="34c59-117">Вы можете использовать API действий управления Office 365 для получения сведений о действиях пользователя, администратора, системы, а также событиях и событиях из Microsoft 365 и журналов активности Azure AD.</span><span class="sxs-lookup"><span data-stu-id="34c59-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="34c59-118">Прочтите эту статью, чтобы узнать больше о том, как это работает.</span><span class="sxs-lookup"><span data-stu-id="34c59-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="34c59-119">Схема API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="34c59-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="34c59-120">В этой статье представлены общие сведения о конкретных типах данных, доступных через API действий управления Office 365, а также сведения о том, как ознакомиться с [общими схемами](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) и сведениями об [анализе и ответе на Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) .</span><span class="sxs-lookup"><span data-stu-id="34c59-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="related-articles"></a><span data-ttu-id="34c59-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="34c59-121">Related articles</span></span>

- [<span data-ttu-id="34c59-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="34c59-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="34c59-123">Сведения об автоматическом расследовании и ответе в защите от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="34c59-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
