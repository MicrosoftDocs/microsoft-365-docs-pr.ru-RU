---
title: Примеры конфигураций каналов развертывания и обновления
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: Как организации используют каналы в развертывании и обновлении.
ms.openlocfilehash: 88567fedd92f01885c4971acc273a676c3e82de8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686158"
---
# <a name="deployment-and-update-channel-example-configurations"></a><span data-ttu-id="b26d7-103">Примеры конфигураций каналов развертывания и обновления</span><span class="sxs-lookup"><span data-stu-id="b26d7-103">Deployment and update channel example configurations</span></span>

<span data-ttu-id="b26d7-104">Выбор каналов обновления для приложений Windows 10 и Microsoft 365 может зависеть от типа вашей организации, а также от того, на каком этапе цикла разработки вы хотите развернуть и использовать новые функции и возможности.</span><span class="sxs-lookup"><span data-stu-id="b26d7-104">Choosing which update channels to use for Windows 10 and Microsoft 365 Apps can depend on your type of organization and where on the development cycle you want to be deploying and using new features and capabilities.</span></span> <span data-ttu-id="b26d7-105">Найдите канал предварительных релизов и канал производства, которые в наибольшей степени отвечают вашим потребностям.</span><span class="sxs-lookup"><span data-stu-id="b26d7-105">Find the pre-release and production channels that best fit your needs.</span></span>

## <a name="pre-release-channels"></a><span data-ttu-id="b26d7-106">Каналы предварительных релизов</span><span class="sxs-lookup"><span data-stu-id="b26d7-106">Pre-release channels</span></span>

| <span data-ttu-id="b26d7-107">Предложения клиента/канала</span><span class="sxs-lookup"><span data-stu-id="b26d7-107">Customer/Channel Offering</span></span> | <span data-ttu-id="b26d7-108">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b26d7-108">Windows 10</span></span> | <span data-ttu-id="b26d7-109">Приложения Microsoft 365 для предприятий (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="b26d7-109">Microsoft 365 Apps for Enterprise (Windows 10)</span></span> |
|:-------|:-------|:-----|
| <span data-ttu-id="b26d7-110">Подходит для пользователей с высоким уровнем технической квалификации и разработчиков.</span><span class="sxs-lookup"><span data-stu-id="b26d7-110">Right for highly technical users and developers.</span></span> <br><br> <span data-ttu-id="b26d7-111">Вы будете первым, кто получит доступ к последним сборкам на ранних стадиях циклах разработки, да еще и с новейшим кодом.</span><span class="sxs-lookup"><span data-stu-id="b26d7-111">Be the first to access the latest builds earliest in the development cycle with the newest code.</span></span> <br><br> <span data-ttu-id="b26d7-112">В этом случае возможны некоторые шероховатости и нестабильность.</span><span class="sxs-lookup"><span data-stu-id="b26d7-112">There will be rough edges and some instability.</span></span> | <span data-ttu-id="b26d7-113">Разработка</span><span class="sxs-lookup"><span data-stu-id="b26d7-113">Dev</span></span> | <span data-ttu-id="b26d7-114">Недоступно</span><span class="sxs-lookup"><span data-stu-id="b26d7-114">N/A</span></span> |
| <span data-ttu-id="b26d7-115">Подходит для ранних пользователей и ИТ-специалистов, которые хотят получить доступ к более надежным сборкам, которые еще находятся в разработке.</span><span class="sxs-lookup"><span data-stu-id="b26d7-115">Right for early adopters and IT Pros who want more reliable builds that are still in development.</span></span> <br><br> <span data-ttu-id="b26d7-116">Посмотрите, что будет дальше, и помогите проверить новые функции.</span><span class="sxs-lookup"><span data-stu-id="b26d7-116">See what’s coming up next and help validate new features.</span></span> | <span data-ttu-id="b26d7-117">Бета-канал</span><span class="sxs-lookup"><span data-stu-id="b26d7-117">Beta Channel</span></span> | <span data-ttu-id="b26d7-118">Бета-канал</span><span class="sxs-lookup"><span data-stu-id="b26d7-118">Beta Channel</span></span> |
| <span data-ttu-id="b26d7-119">Подходит для тех, кто хочет получить ранний доступ к предстоящим выпускам.</span><span class="sxs-lookup"><span data-stu-id="b26d7-119">Right for those who want early access to upcoming releases.</span></span> <br><br> <span data-ttu-id="b26d7-120">Где компании предварительно просматривают и утверждают предстоящие выпуски перед широким развертыванием.</span><span class="sxs-lookup"><span data-stu-id="b26d7-120">Where companies preview and validate upcoming releases before broad deployment.</span></span> <br><br> <span data-ttu-id="b26d7-121">Поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b26d7-121">These are supported.</span></span> <br>  | <span data-ttu-id="b26d7-122">Предварительный просмотр выпуска</span><span class="sxs-lookup"><span data-stu-id="b26d7-122">Release Preview</span></span> | <span data-ttu-id="b26d7-123">Актуальный канал (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="b26d7-123">Current Channel (Preview)</span></span> <br><br> <span data-ttu-id="b26d7-124">Полугодовой канал (предварительная корпоративная версия)</span><span class="sxs-lookup"><span data-stu-id="b26d7-124">Semi-Annual Enterprise Channel (Preview)</span></span>|
||||

## <a name="production-channels-for-broad-deployment"></a><span data-ttu-id="b26d7-125">Каналы производства для широкого развертывания</span><span class="sxs-lookup"><span data-stu-id="b26d7-125">Production channels for broad deployment</span></span>

<span data-ttu-id="b26d7-126">Нажмите на ссылку в **Пример** столбце, чтобы просмотреть этапы развертывания и сгруппировать для выбранной организации.</span><span class="sxs-lookup"><span data-stu-id="b26d7-126">Click the link in the **Example** column to step through deployment stages and groups for an example organization.</span></span>

| <span data-ttu-id="b26d7-127">Предложения клиента/канала</span><span class="sxs-lookup"><span data-stu-id="b26d7-127">Customer/Channel Offering</span></span> | <span data-ttu-id="b26d7-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b26d7-128">Windows 10</span></span> | <span data-ttu-id="b26d7-129">Приложения Microsoft 365 для предприятий (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="b26d7-129">Microsoft 365 Apps for Enterprise (Windows 10)</span></span> | <span data-ttu-id="b26d7-130">Пример</span><span class="sxs-lookup"><span data-stu-id="b26d7-130">Example</span></span> |
|:-------|:-------|:-----|:-------|
| <span data-ttu-id="b26d7-131">Подходит для клиентов, которые хотят получить последние выпуски, как только они будут готовы.</span><span class="sxs-lookup"><span data-stu-id="b26d7-131">Right for customers who want the latest releases as soon as they are ready.</span></span> | <span data-ttu-id="b26d7-132">Полугодовой канал</span><span class="sxs-lookup"><span data-stu-id="b26d7-132">Semi-Annual Channel</span></span> | [<span data-ttu-id="b26d7-133">Актуальный канал</span><span class="sxs-lookup"><span data-stu-id="b26d7-133">Current Channel</span></span>](https://docs.microsoft.com/deployoffice/overview-update-channels#current-channel-overview) | [<span data-ttu-id="b26d7-134">Последние выпуски</span><span class="sxs-lookup"><span data-stu-id="b26d7-134">Latest releases</span></span>](deploy-update-channels-examples-rapid-deploy.md) |
| <span data-ttu-id="b26d7-135">Подходит для предприятий, которые хотят получить последние выпуски с дополнительной предсказуемостью.</span><span class="sxs-lookup"><span data-stu-id="b26d7-135">Right for enterprises who want the latest release with additional predictability.</span></span> | <span data-ttu-id="b26d7-136">Полугодовой канал</span><span class="sxs-lookup"><span data-stu-id="b26d7-136">Semi-Annual Channel</span></span> | [<span data-ttu-id="b26d7-137">Ежемесячный канал (корпоративный)</span><span class="sxs-lookup"><span data-stu-id="b26d7-137">Monthly Enterprise Channel</span></span>](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview) |  |
| <span data-ttu-id="b26d7-138">Подходит для предприятий, которым необходимо комплексное ИТ-тестирование перед каждым обновлением.</span><span class="sxs-lookup"><span data-stu-id="b26d7-138">Right for enterprises with need for extensive IT testing before each update.</span></span> | <span data-ttu-id="b26d7-139">Полугодовой канал</span><span class="sxs-lookup"><span data-stu-id="b26d7-139">Semi-Annual Channel</span></span> | [<span data-ttu-id="b26d7-140">Полугодовой канал (корпоративный)</span><span class="sxs-lookup"><span data-stu-id="b26d7-140">Semi-Annual Enterprise Channel</span></span>](https://docs.microsoft.com/deployoffice/overview-update-channels#semi-annual-enterprise-channel-overview) |  |
|||||


## <a name="see-also"></a><span data-ttu-id="b26d7-141">См. также</span><span class="sxs-lookup"><span data-stu-id="b26d7-141">See also</span></span>

[<span data-ttu-id="b26d7-142">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="b26d7-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b26d7-143">Руководства по лаборатории тестирования</span><span class="sxs-lookup"><span data-stu-id="b26d7-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
