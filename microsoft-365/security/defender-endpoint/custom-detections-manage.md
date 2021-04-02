---
title: Просмотр и управление пользовательскими правилами обнаружения в ATP Защитника Майкрософт
ms.reviewer: ''
description: Узнайте, как просматривать и управлять пользовательскими правилами обнаружения
keywords: настраиваемые обнаружения, просмотр, управление, оповещения, редактирование, запуск по требованию, правила обнаружения, расширенные правила охоты, охота, запрос, действия отклика, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498755"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="75115-104">Просмотр и управление пользовательскими правилами обнаружения</span><span class="sxs-lookup"><span data-stu-id="75115-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="75115-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="75115-105">**Applies to:**</span></span>
- [<span data-ttu-id="75115-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="75115-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="75115-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75115-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="75115-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="75115-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="75115-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="75115-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="75115-110">Управление [существующими пользовательскими правилами обнаружения,](custom-detection-rules.md) чтобы убедиться, что они эффективно находят угрозы и принимают меры.</span><span class="sxs-lookup"><span data-stu-id="75115-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="75115-111">Узнайте, как просмотреть список правил, проверить предыдущие запуски и просмотреть срабатываемую ими оповещений.</span><span class="sxs-lookup"><span data-stu-id="75115-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="75115-112">Вы также можете запустить правило по запросу и изменить его.</span><span class="sxs-lookup"><span data-stu-id="75115-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="75115-113">Обязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="75115-113">Required permissions</span></span>

<span data-ttu-id="75115-114">Чтобы создать или управлять пользовательскими обнаружениями, [ваша роль](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) должна иметь разрешение на управление **настройками безопасности.**</span><span class="sxs-lookup"><span data-stu-id="75115-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="75115-115">Просмотр существующих правил</span><span class="sxs-lookup"><span data-stu-id="75115-115">View existing rules</span></span>

<span data-ttu-id="75115-116">Чтобы просмотреть все существующие пользовательские правила обнаружения, перейдите к **настройкам**  >  **настраиваемой обнаружения.**</span><span class="sxs-lookup"><span data-stu-id="75115-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="75115-117">На странице перечислены все правила со следующими сведениями о запуске:</span><span class="sxs-lookup"><span data-stu-id="75115-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="75115-118">**Последний запуск**— при последнем запуске правила для проверки совпадений запросов и создания оповещений</span><span class="sxs-lookup"><span data-stu-id="75115-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="75115-119">**Состояние последнего запуска**— успешно ли выполнило правило</span><span class="sxs-lookup"><span data-stu-id="75115-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="75115-120">**Следующий запуск**— следующий запланированный запуск</span><span class="sxs-lookup"><span data-stu-id="75115-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="75115-121">**Состояние**— независимо от того, включено или отключено правило</span><span class="sxs-lookup"><span data-stu-id="75115-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="75115-122">Просмотр сведений о правилах, изменение правила и правила запуска</span><span class="sxs-lookup"><span data-stu-id="75115-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="75115-123">Чтобы просмотреть всестороннюю информацию о пользовательском правиле обнаружения, выберите имя правила из списка правил в **настройках**  >  **настраиваемого обнаружения.**</span><span class="sxs-lookup"><span data-stu-id="75115-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="75115-124">На странице выбранного правила отображаются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="75115-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="75115-125">Общие сведения о правиле, включая сведения о оповещении, состоянии запуска и области</span><span class="sxs-lookup"><span data-stu-id="75115-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="75115-126">Список срабатывных оповещений</span><span class="sxs-lookup"><span data-stu-id="75115-126">List of triggered alerts</span></span>
- <span data-ttu-id="75115-127">Список срабатывуем действий</span><span class="sxs-lookup"><span data-stu-id="75115-127">List of triggered actions</span></span>

<span data-ttu-id="75115-128">![Страница правила обнаружения настраиваемой](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="75115-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="75115-129">*Страница правила обнаружения настраиваемой*</span><span class="sxs-lookup"><span data-stu-id="75115-129">*Custom detection rule page*</span></span>

<span data-ttu-id="75115-130">На этой странице также можно принять следующие действия по правилу:</span><span class="sxs-lookup"><span data-stu-id="75115-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="75115-131">**Запустите**— запустите правило немедленно.</span><span class="sxs-lookup"><span data-stu-id="75115-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="75115-132">Это действие также сбрасывает интервал для следующего запуска.</span><span class="sxs-lookup"><span data-stu-id="75115-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="75115-133">**Изменение**— изменение правила без изменения запроса</span><span class="sxs-lookup"><span data-stu-id="75115-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="75115-134">**Изменение запроса**— изменение запроса в продвинутой охоте</span><span class="sxs-lookup"><span data-stu-id="75115-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="75115-135">**Включаем**  /  **Отключите** правило или остановите его работу</span><span class="sxs-lookup"><span data-stu-id="75115-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="75115-136">**Удаление**— отключите правило и удалите его</span><span class="sxs-lookup"><span data-stu-id="75115-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="75115-137">Чтобы быстро просмотреть сведения и принять меры по элементу в таблице, используйте столбец выбора [&#10003;] слева от таблицы.</span><span class="sxs-lookup"><span data-stu-id="75115-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="75115-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="75115-138">Related topics</span></span>
- [<span data-ttu-id="75115-139">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="75115-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="75115-140">Создание правил обнаружения</span><span class="sxs-lookup"><span data-stu-id="75115-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="75115-141">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="75115-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="75115-142">Просмотр и организация оповещений</span><span class="sxs-lookup"><span data-stu-id="75115-142">View and organize alerts</span></span>](alerts-queue.md)
