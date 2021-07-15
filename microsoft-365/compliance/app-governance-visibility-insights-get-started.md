---
title: Начало работы с видимостью и аналитикой
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Начало работы с видимостью и аналитикой.
ms.openlocfilehash: 12c1a01667b1bda545b619e931d99132e6611e35
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420268"
---
# <a name="get-started-with-visibility-and-insights"></a><span data-ttu-id="63bcf-103">Начало работы с видимостью и аналитикой</span><span class="sxs-lookup"><span data-stu-id="63bcf-103">Get started with visibility and insights</span></span>

><span data-ttu-id="63bcf-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="63bcf-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="63bcf-105">Начните работу с панели мониторинга управления приложениями по адресу [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="63bcf-105">The first place to get started is the app governance dashboard at [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance).</span></span> <span data-ttu-id="63bcf-106">Обратите внимание на то, что для просмотра любых данных управления приложениями вашей учетной записи, в которой вы выполняете вход, должна быть назначена одна из [ролей администратора управления приложениями](app-governance-get-started.md#administrator-roles).</span><span class="sxs-lookup"><span data-stu-id="63bcf-106">Note that your sign-in account must have one of [these app governance administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

![Страница обзора управления приложениями в Центре соответствия требованиям Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

<span data-ttu-id="63bcf-108">Вы также можете получить доступ к панели мониторинга управления приложениями на странице **Центр администрирования Microsoft 365 > Центр соответствия требованиям Microsoft 365 > Управление приложениями > Обзор**.</span><span class="sxs-lookup"><span data-stu-id="63bcf-108">You can also access the app governance dashboard from **Microsoft 365 admin center > Microsoft 365 Compliance Center > App governance > Overview page**.</span></span>

## <a name="whats-available-on-the-dashboard"></a><span data-ttu-id="63bcf-109">Что доступно на панели мониторинга:</span><span class="sxs-lookup"><span data-stu-id="63bcf-109">What’s available on the dashboard</span></span>

<span data-ttu-id="63bcf-110">Панель мониторинга содержит сводку компонентов экосистемы приложений Microsoft 365 в клиенте:</span><span class="sxs-lookup"><span data-stu-id="63bcf-110">The dashboard contains a summary of the components of the Microsoft 365 app ecosystem in the tenant:</span></span>

- <span data-ttu-id="63bcf-111">**Сводка по клиенту**: количество ключевых категорий приложений и оповещений.</span><span class="sxs-lookup"><span data-stu-id="63bcf-111">**Tenant summary**: The count of key app and alert categories.</span></span>
- <span data-ttu-id="63bcf-112">**Оповещения об обнаружении и оповещения политик**: последние активные оповещения в клиенте</span><span class="sxs-lookup"><span data-stu-id="63bcf-112">**Detection and policy alerts**: The most recent active alerts in the tenant</span></span>
- <span data-ttu-id="63bcf-113">**Доступ к данным и ресурсам**: сводный доступ к API приложения и общее использование основных ресурсов в клиенте.</span><span class="sxs-lookup"><span data-stu-id="63bcf-113">**Data and resources access**: Aggregate application API access and overall usage of top resources in the tenant.</span></span> <span data-ttu-id="63bcf-114">Чтобы увидеть соответствующее значение, наведите указатель мыши на столбец каждого месяца в графике.</span><span class="sxs-lookup"><span data-stu-id="63bcf-114">Mouse over each month column in the graph to see the corresponding value.</span></span>
- <span data-ttu-id="63bcf-115">**Улучшение защиты и управления приложениями**: рекомендуемые действия, такие как создание политики использования приложений или политики разрешений.</span><span class="sxs-lookup"><span data-stu-id="63bcf-115">**Improve your app protection and governance**: Recommended actions such as creating an app usage or permissions policy.</span></span>
- <span data-ttu-id="63bcf-116">**Основные приложения по категориям**: основные приложения, отсортированные по следующим категориям:</span><span class="sxs-lookup"><span data-stu-id="63bcf-116">**Top apps by categories**: The top apps sorted by these categories:</span></span>
  
  - <span data-ttu-id="63bcf-117">**Все категории**: сортировка по всем доступным категориям.</span><span class="sxs-lookup"><span data-stu-id="63bcf-117">**All categories**: Sorts across all available categories.</span></span>
  - <span data-ttu-id="63bcf-118">**С высокими привилегиями**: высокие привилегии — это определяемая внутри организации категория, основанная на машинном обучении платформы и сигналах.</span><span class="sxs-lookup"><span data-stu-id="63bcf-118">**High privilege**: High privilege is an internally determined category based on platform machine learning and signals.</span></span>
  - <span data-ttu-id="63bcf-119">**С избыточными правами**: когда управление приложениями получает телеметрию, указывающую, что разрешение, предоставленное приложению, не использовалось в течение последних 90 дней, то данное приложение обладает избыточными правами.</span><span class="sxs-lookup"><span data-stu-id="63bcf-119">**Overprivileged**: When app governance receives telemetry that indicates that a permission granted to an application has not been used in the last 90 days, that application is overprivileged.</span></span> <span data-ttu-id="63bcf-120">Управление приложениями должно работать не менее 90 дней, чтобы определить, не обладает ли приложение избыточными правами.</span><span class="sxs-lookup"><span data-stu-id="63bcf-120">App governance must be operating for at least 90 days to determine if any app is overprivileged.</span></span>  
  - <span data-ttu-id="63bcf-121">**Непроверенные**: приложения, не получившие [сертификацию издателя](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview), считаются непроверенными.</span><span class="sxs-lookup"><span data-stu-id="63bcf-121">**Unverified**: Applications that have not received [publisher certification](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) are considered unverified.</span></span>
  - <span data-ttu-id="63bcf-122">**Только приложение**: [разрешения приложения](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) используются приложениями, которые могут работать без присутствия пользователя, выполнившего вход.</span><span class="sxs-lookup"><span data-stu-id="63bcf-122">**App only**: [Application permissions](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) are used by apps that can run without a signed-in user present.</span></span> <span data-ttu-id="63bcf-123">Приложения с разрешениями на доступ к данным в клиенте потенциально представляют повышенный риск.</span><span class="sxs-lookup"><span data-stu-id="63bcf-123">Apps with permissions to access data across the tenant are potentially a higher risk.</span></span>
  - <span data-ttu-id="63bcf-124">**Новые приложения**: новые приложения Microsoft 365, зарегистрированные в течение последних 7 дней.</span><span class="sxs-lookup"><span data-stu-id="63bcf-124">**New apps**: New Microsoft 365 apps that have been registered in the last seven days.</span></span>  

## <a name="next-step"></a><span data-ttu-id="63bcf-125">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="63bcf-125">Next step</span></span>

<span data-ttu-id="63bcf-126">[Получите подробную аналитику об определенном приложении](app-governance-visibility-insights-view-apps.md).</span><span class="sxs-lookup"><span data-stu-id="63bcf-126">[Get detailed insights on a specific app](app-governance-visibility-insights-view-apps.md).</span></span>
