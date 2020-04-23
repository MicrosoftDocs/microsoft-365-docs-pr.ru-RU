---
title: Развертывание Microsoft Teams для Microsoft 365 корпоративный
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Пошаговое изучение с последующим развертыванием Microsoft Teams в организации.
ms.openlocfilehash: d34673a412539dfc73296f0139fa2eb555c17099
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636703"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a><span data-ttu-id="d83e1-103">Развертывание Microsoft Teams для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="d83e1-103">Deploy Microsoft Teams for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d83e1-104">*Эта рабочая нагрузка включена в планы E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="d83e1-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="d83e1-p101">В Microsoft Teams объединены функции чата, конференций, общего доступа к документам и бесед с несколькими ветками. Это сделано так, чтобы упростить создание контента и предоставление общего доступа к нему в группах. Teams — это способ выполнения групповой и совместной работы в Microsoft 365 корпоративный и ключевой элемент преимущества, созданного для командной работы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d83e1-p101">Microsoft Teams brings together chat, conferencing, document sharing, and threaded conversations in a way that makes it easy to create and share content across groups. Teams is the way you do teamwork and collaboration for Microsoft 365 Enterprise and is a key element of the Built for Teamwork value of Microsoft 365.</span></span> 

<span data-ttu-id="d83e1-107">Если вы не знакомы с Teams, прочитайте статью [Знакомство с Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span><span class="sxs-lookup"><span data-stu-id="d83e1-107">If you're brand new to Teams, see [Welcome to Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span> 


## <a name="roll-out-teams-to-your-organization"></a><span data-ttu-id="d83e1-108">Развертывание Teams в организации</span><span class="sxs-lookup"><span data-stu-id="d83e1-108">Roll out Teams to your organization</span></span>

<span data-ttu-id="d83e1-109">Подготовка:</span><span class="sxs-lookup"><span data-stu-id="d83e1-109">Before you begin:</span></span>

- <span data-ttu-id="d83e1-110">Настройте правильные этапы [базовой инфраструктуры](deploy-foundation-infrastructure.md), чтобы в ваших командах имелись учетные записи пользователей и нужные функции безопасности.</span><span class="sxs-lookup"><span data-stu-id="d83e1-110">Make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your teams have the user accounts and security capabilities you need.</span></span> <span data-ttu-id="d83e1-111">Этапы идентификации и защиты данных являются наиболее важными для входа и использования защиты почты и файлов с помощью меток хранения и конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="d83e1-111">The Identity and Information Protection phases are the most important for signing on and using securing email and files with retention and sensitivity labels.</span></span>
- <span data-ttu-id="d83e1-112">Сведения о безопасности и соответствии требованиям в Teams см. в [этой статье](https://docs.microsoft.com/microsoftteams/security-compliance-overview).</span><span class="sxs-lookup"><span data-stu-id="d83e1-112">Learn about security and compliance in Teams with [this article](https://docs.microsoft.com/microsoftteams/security-compliance-overview).</span></span>
- <span data-ttu-id="d83e1-113">Сведения о лицензировании для Teams см. в [этой статье](https://docs.microsoft.com/microsoftteams/office-365-licensing).</span><span class="sxs-lookup"><span data-stu-id="d83e1-113">Learn about licensing for Teams with [this article](https://docs.microsoft.com/microsoftteams/office-365-licensing).</span></span>

<span data-ttu-id="d83e1-114">Чтобы развернуть Teams в организации, ознакомьтесь со статьей [Способ развертывания Teams](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams).</span><span class="sxs-lookup"><span data-stu-id="d83e1-114">To roll out Teams in your organization, read [How to roll out Teams](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams).</span></span>

<span data-ttu-id="d83e1-115">Для знакомства с первоначальным набором функций Teams см. статью [Чат, команды, каналы и приложения в Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page).</span><span class="sxs-lookup"><span data-stu-id="d83e1-115">For your first set of Teams capabilities, see [Chat, teams, channels, and apps in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page).</span></span>

<span data-ttu-id="d83e1-116">Сведения о дополнительных функциях Teams см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="d83e1-116">For more advanced Teams capabilities, see:</span></span>

- [<span data-ttu-id="d83e1-117">Собрания и конференции</span><span class="sxs-lookup"><span data-stu-id="d83e1-117">Meetings and Conferencing</span></span>](https://docs.microsoft.com/microsoftteams/deploy-meetings-microsoft-teams-landing-page)
- <span data-ttu-id="d83e1-118">[Облачные решения для голосовой связи](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (требуется Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="d83e1-118">[Cloud voice](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (requires Microsoft 365 E5)</span></span>

<span data-ttu-id="d83e1-119">Чтобы отслеживать использование Teams в организации, ознакомьтесь со следующими статьями:</span><span class="sxs-lookup"><span data-stu-id="d83e1-119">To monitor your organization's usage of Teams, see:</span></span>

- [<span data-ttu-id="d83e1-120">Аналитика командной и межкомандной работы в Teams</span><span class="sxs-lookup"><span data-stu-id="d83e1-120">Cross-team and per-team analytics in Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/cross-team-per-team-analytics)
- [<span data-ttu-id="d83e1-121">Аналитика и отчеты</span><span class="sxs-lookup"><span data-stu-id="d83e1-121">Analytics and reporting</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/teams-reporting-reference)


## <a name="upgrade-to-teams"></a><span data-ttu-id="d83e1-122">Переход на Teams</span><span class="sxs-lookup"><span data-stu-id="d83e1-122">Upgrade to Teams</span></span>

<span data-ttu-id="d83e1-123">Если это еще не произошло, вы скоро перейдете со Skype для бизнеса на Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d83e1-123">If it hasn’t happened already, you will soon upgrade from Skype for Business to Microsoft Teams.</span></span> <span data-ttu-id="d83e1-124">Независимо от того, начинаете ли вы работу с Teams, уже используете Teams наряду со Skype для бизнеса или полностью готовы к переходу, мы стремимся, чтобы у вас было все необходимое для успешного перехода на Teams.</span><span class="sxs-lookup"><span data-stu-id="d83e1-124">Whether you’re just getting started with Teams, already using Teams alongside Skype for Business, or ready to upgrade, we want to ensure you have everything you need to navigate a successful journey to Teams.</span></span>

<span data-ttu-id="d83e1-125">При переходе со Skype для бизнеса Online или из локальной среды Skype для бизнеса на Teams структура обновления поможет вам выполнить все необходимые действия в соответствии с вашим бизнес-сценарием.</span><span class="sxs-lookup"><span data-stu-id="d83e1-125">Whether you are upgrading from Skype for Business Online to Teams or from a Skype for Business on-premises environment to Teams, the upgrade framework will guide you through the process based on your business scenario.</span></span>
 
<span data-ttu-id="d83e1-126">Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="d83e1-126">See the [Getting started with your Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here) for more information.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="d83e1-127">Как корпорация Майкрософт реализует Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="d83e1-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d83e1-128">Загляните в корпорацию Майкрософт и узнайте, как мы развернули и используем Teams для совместной работы, прочтя следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="d83e1-128">To peek inside Microsoft and learn how we deployed and are using Teams for collaboration, see:</span></span>

- [<span data-ttu-id="d83e1-129">Стратегия внедрения Microsoft Teams готовит сотрудников к новой культуре работы</span><span class="sxs-lookup"><span data-stu-id="d83e1-129">Microsoft Teams adoption strategy prepares employees for a new culture of work</span></span>](https://www.microsoft.com/itshowcase/microsoft-teams-adoption-strategy-prepares-employees-for-a-new-culture-of-work)
- [<span data-ttu-id="d83e1-130">Благодаря комнатам Microsoft Teams предоставляется глобально масштабируемый современный интерфейс для собраний</span><span class="sxs-lookup"><span data-stu-id="d83e1-130">With Microsoft Teams Rooms, comes a globally scalable modern meeting experience</span></span>](https://www.microsoft.com/itshowcase/with-microsoft-teams-rooms-comes-a-globally-scalable-modern-meeting-experience)

## <a name="next-steps"></a><span data-ttu-id="d83e1-131">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="d83e1-131">Next steps</span></span>

- [<span data-ttu-id="d83e1-132">Управление функциями Microsoft Teams в организации</span><span class="sxs-lookup"><span data-stu-id="d83e1-132">Manage Microsoft Teams features for your organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [<span data-ttu-id="d83e1-133">Обучение администратора для работы с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d83e1-133">Admin training for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/itadmin-readiness)

