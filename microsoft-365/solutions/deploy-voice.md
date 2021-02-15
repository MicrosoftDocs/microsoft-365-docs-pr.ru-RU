---
title: Развертывание голосовой почты в Microsoft 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-voice
- M365-voice
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Узнайте, как выбрать и развернуть правильное голосовое решение Teams для вашей организации.
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580915"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="72909-103">Планирование и развертывание голосового решения Teams</span><span class="sxs-lookup"><span data-stu-id="72909-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="72909-104">Голосовое решение Teams позволяет пользователям в вашей организации звонить как внутри, так и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="72909-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="72909-105">Полное голосовое решение состоит из Teams, телефонной системы Майкрософт и выбора вариантов подключения к телефонной сети общего параметров (STN).</span><span class="sxs-lookup"><span data-stu-id="72909-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Обзор голосовых решений Teams](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="72909-107">Телефонная система предоставляет для вашей организации полные возможности PBX.</span><span class="sxs-lookup"><span data-stu-id="72909-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="72909-108">Звонки между пользователями в организации (независимо от их географического расположения) обрабатываются внутри телефонной системы, тем самым убирая междугородние расходы на эти внутренние вызовы.</span><span class="sxs-lookup"><span data-stu-id="72909-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="72909-109">Подключив телефонную систему к телефонной сети общего звонков (PSTN), пользователи Teams также могут звонить за пределы вашей организации.</span><span class="sxs-lookup"><span data-stu-id="72909-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="72909-110">Это руководство по решению поможет вам:</span><span class="sxs-lookup"><span data-stu-id="72909-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="72909-111">Выбор решения голосовой почты для вашей организации</span><span class="sxs-lookup"><span data-stu-id="72909-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="72909-112">Развертывание выбранного решения голосовой почты</span><span class="sxs-lookup"><span data-stu-id="72909-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="72909-113">Выполните следующие действия, чтобы выбрать, спланировать и настроить голосовое решение:</span><span class="sxs-lookup"><span data-stu-id="72909-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Выбор голосового решения](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="72909-115">Выбор голосового решения</span><span class="sxs-lookup"><span data-stu-id="72909-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="72909-116">Настройка телефонной системы</span><span class="sxs-lookup"><span data-stu-id="72909-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="72909-117">Настройка подключения к STN путем выбора одного из следующих сочетаний:</span><span class="sxs-lookup"><span data-stu-id="72909-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="72909-118">[План звонков](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) — облачное решение Корпорации Майкрософт с Майкрософт в качестве оператора ЗВОНКОВ</span><span class="sxs-lookup"><span data-stu-id="72909-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="72909-119">[Прямая маршрутка](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) : использование прямой маршрутки для подключения собственного оператора STN к Teams</span><span class="sxs-lookup"><span data-stu-id="72909-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="72909-120">Кроме того, вам может потребоваться ознакомиться с тем, как крупная транснациональная корпорация перейти на голосовое решение Teams в примере [Contoso.](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="72909-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="72909-121">Сведения о необходимых лицензиях см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="72909-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="72909-122">Лицензии на надстройки Teams</span><span class="sxs-lookup"><span data-stu-id="72909-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="72909-123">Требования к лицензированию прямой маршрутки</span><span class="sxs-lookup"><span data-stu-id="72909-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
