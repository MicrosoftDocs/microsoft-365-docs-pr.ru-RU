---
title: Развертывание голосовой системы в Microsoft 365
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
description: Узнайте, как выбрать и развернуть правильное голосовое решение Teams для организации.
ms.openlocfilehash: ede8075767e9d0a80123ac742403f8a4d171392e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918386"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="9c02e-103">Планирование и развертывание голосового решения Teams</span><span class="sxs-lookup"><span data-stu-id="9c02e-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="9c02e-104">Голосовое решение Teams позволяет пользователям в организации звонить как внутри организации, так и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="9c02e-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="9c02e-105">Полное голосовое решение состоит из Teams, Microsoft Phone System и выбора вариантов подключения к сети общедоступных звонков с переключениями (PSTN).</span><span class="sxs-lookup"><span data-stu-id="9c02e-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Обзор голосовых решений teams](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="9c02e-107">Телефонная система предоставляет полные возможности private Branch Exchange (PBX) для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9c02e-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="9c02e-108">Звонки между пользователями в организации независимо от их географического расположения обрабатываются внутри системы телефонов, тем самым снимая междугородние затраты на эти внутренние вызовы.</span><span class="sxs-lookup"><span data-stu-id="9c02e-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="9c02e-109">Подключив телефонную систему к открытой телефонной сети (PSTN), пользователи Teams также могут звонить за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="9c02e-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="9c02e-110">Это руководство по решению поможет вам:</span><span class="sxs-lookup"><span data-stu-id="9c02e-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="9c02e-111">Выбор правильного решения голосовой почты для организации</span><span class="sxs-lookup"><span data-stu-id="9c02e-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="9c02e-112">Развертывание выбранного голосового решения</span><span class="sxs-lookup"><span data-stu-id="9c02e-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="9c02e-113">Выполните следующие действия, чтобы выбрать, спланировать и настроить голосовое решение:</span><span class="sxs-lookup"><span data-stu-id="9c02e-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Выбор голосового решения](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="9c02e-115">Выбор голосового решения</span><span class="sxs-lookup"><span data-stu-id="9c02e-115">Choose your voice solution</span></span>](/MicrosoftTeams/cloud-voice-landing-page?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

2. [<span data-ttu-id="9c02e-116">Настройка телефонной системы</span><span class="sxs-lookup"><span data-stu-id="9c02e-116">Set up Phone System</span></span>](/microsoftteams/setting-up-your-phone-system?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

3. <span data-ttu-id="9c02e-117">Настройка подключения к PSTN путем выбора одного или комбинации из следующих ниже.</span><span class="sxs-lookup"><span data-stu-id="9c02e-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="9c02e-118">[Вызываемая](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) программа — это облачное решение Корпорации Майкрософт с Microsoft в качестве носителя PSTN</span><span class="sxs-lookup"><span data-stu-id="9c02e-118">[Calling Plan](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="9c02e-119">[Прямая маршрутная маршрутная](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) маршрутия . Использование прямой маршрутной маршрутики для подключения собственного оператора PSTN к Teams</span><span class="sxs-lookup"><span data-stu-id="9c02e-119">[Direct Routing](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="9c02e-120">Кроме того, вы можете прочитать о том, как крупная многонациональная корпорация мигрировала в голосовое решение Teams в [примере Contoso.](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="9c02e-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json).</span></span>

<span data-ttu-id="9c02e-121">Сведения о необходимых лицензиях см. в следующих сведениях:</span><span class="sxs-lookup"><span data-stu-id="9c02e-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="9c02e-122">Лицензии надстройки teams</span><span class="sxs-lookup"><span data-stu-id="9c02e-122">Teams add-on licenses</span></span>](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json)

- [<span data-ttu-id="9c02e-123">Требования к лицензированию прямой маршрутной маршрутики</span><span class="sxs-lookup"><span data-stu-id="9c02e-123">Direct Routing licensing requirements</span></span>](/microsoftteams/direct-routing-plan?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json#licensing-and-other-requirements/toc.json)