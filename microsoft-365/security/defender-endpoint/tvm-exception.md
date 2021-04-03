---
title: Создание и просмотр исключений для рекомендаций по безопасности — управление угрозами и уязвимостью
description: Создание и мониторинг исключений для рекомендаций по безопасности в управлении угрозами и уязвимостью.
keywords: Microsoft defender atp tvm remediation, mdatp tvm, threat and vulnerability management, threat & vulnerability management, threat & vulnerability management remediation, tvm remediation intune, tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13ac09b1ad918ed945edec6167fd57ea02b616ea
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500185"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="433e8-104">Создание и просмотр исключений для рекомендаций по безопасности — управление угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="433e8-104">Create and view exceptions for security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="433e8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="433e8-105">**Applies to:**</span></span>

- [<span data-ttu-id="433e8-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="433e8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="433e8-107">Управление угрозами и уязвимостями</span><span class="sxs-lookup"><span data-stu-id="433e8-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="433e8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="433e8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="433e8-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="433e8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="433e8-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="433e8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="433e8-111">В качестве альтернативы запросу на исправление, если рекомендация на данный момент не актуальна, можно создать исключения для рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="433e8-111">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> <span data-ttu-id="433e8-112">Если в организации есть группы устройств, вы сможете использовать исключение для определенных групп устройств.</span><span class="sxs-lookup"><span data-stu-id="433e8-112">If your organization has device groups, you will be able to scope the exception to specific device groups.</span></span> <span data-ttu-id="433e8-113">Исключения можно создавать либо для выбранных групп устройств, либо для всех групп устройств в прошлом и настоящем.</span><span class="sxs-lookup"><span data-stu-id="433e8-113">Exceptions can either be created for selected device groups, or for all device groups past and present.</span></span>  

<span data-ttu-id="433e8-114">Если для рекомендации создается исключение, рекомендация не будет активна до окончания срока действия исключения.</span><span class="sxs-lookup"><span data-stu-id="433e8-114">When an exception is created for a recommendation, the recommendation will not be active until the end of the exception duration.</span></span> <span data-ttu-id="433e8-115">Состояние рекомендации будет изменяться на **полное исключение или** **частичное** исключение (по группе устройств).</span><span class="sxs-lookup"><span data-stu-id="433e8-115">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

## <a name="permissions"></a><span data-ttu-id="433e8-116">Разрешения</span><span class="sxs-lookup"><span data-stu-id="433e8-116">Permissions</span></span>

<span data-ttu-id="433e8-117">Управлять исключениями (включая создание или отмену) могут только пользователи с разрешениями "обработка исключений".</span><span class="sxs-lookup"><span data-stu-id="433e8-117">Only users with “exceptions handling” permissions can manage exceptions (including creating or canceling).</span></span> <span data-ttu-id="433e8-118">[Узнайте больше о ролях RBAC.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="433e8-118">[Learn more about RBAC roles](user-roles.md).</span></span>

![Просмотр разрешения на обработку исключений.](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a><span data-ttu-id="433e8-120">Создание исключения</span><span class="sxs-lookup"><span data-stu-id="433e8-120">Create an exception</span></span>

<span data-ttu-id="433e8-121">Выберите рекомендацию по безопасности, для чего необходимо создать исключение, а затем выберите **параметры Исключения** и заполните форму.</span><span class="sxs-lookup"><span data-stu-id="433e8-121">Select a security recommendation you would like create an exception for, and then select **Exception options** and fill out the form.</span></span>  

![Отображение расположения кнопки "Параметры исключений" в вылете рекомендации по безопасности.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a><span data-ttu-id="433e8-123">Исключение по группе устройств</span><span class="sxs-lookup"><span data-stu-id="433e8-123">Exception by device group</span></span>

<span data-ttu-id="433e8-124">Примени исключение для всех текущих групп устройств или выберите определенные группы устройств.</span><span class="sxs-lookup"><span data-stu-id="433e8-124">Apply the exception to all current device groups or choose specific device groups.</span></span> <span data-ttu-id="433e8-125">Будущие группы устройств не будут включены в исключение.</span><span class="sxs-lookup"><span data-stu-id="433e8-125">Future device groups won't be included in the exception.</span></span> <span data-ttu-id="433e8-126">Группы устройств, которые уже имеют исключение, не будут отображаться в списке.</span><span class="sxs-lookup"><span data-stu-id="433e8-126">Device groups that already have an exception will not be displayed in the list.</span></span> <span data-ttu-id="433e8-127">Если выбрать только определенные группы устройств, состояние рекомендации изменится с "active" на "частичное исключение".</span><span class="sxs-lookup"><span data-stu-id="433e8-127">If you only select certain device groups, the recommendation state will change from “active” to “partial exception.”</span></span> <span data-ttu-id="433e8-128">При выборе всех групп устройств состояние изменится на "полное исключение".</span><span class="sxs-lookup"><span data-stu-id="433e8-128">The state will change to “full exception” if you select all the device groups.</span></span>

![Отображение отсев группы устройств.](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a><span data-ttu-id="433e8-130">Отфильтрованные представления</span><span class="sxs-lookup"><span data-stu-id="433e8-130">Filtered views</span></span>

<span data-ttu-id="433e8-131">Если вы отфильтрованы группой устройств на любой из страниц управления угрозами и уязвимостями, в качестве параметров будут отображаться только группы отфильтрованных устройств.</span><span class="sxs-lookup"><span data-stu-id="433e8-131">If you have filtered by device group on any of the threat and vulnerability management pages, only your filtered device groups will appear as options.</span></span>

<span data-ttu-id="433e8-132">Это кнопка фильтрации группой устройств на любой из страниц управления угрозами и уязвимостями:</span><span class="sxs-lookup"><span data-stu-id="433e8-132">This is the button to filter by device group on any of the threat and vulnerability management pages:</span></span> 

![Отображение фильтра выбранных групп устройств.](images/tvm-selected-device-groups.png)

<span data-ttu-id="433e8-134">Представление исключения с отфильтрованными группами устройств:</span><span class="sxs-lookup"><span data-stu-id="433e8-134">Exception view with filtered device groups:</span></span>

![Отображение отфильтрованного отфильтрованного падения группы устройств.](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a><span data-ttu-id="433e8-136">Большое количество групп устройств</span><span class="sxs-lookup"><span data-stu-id="433e8-136">Large number of device groups</span></span>

<span data-ttu-id="433e8-137">Если в организации более 20 групп устройств, выберите **Изменить** рядом с фильтрованным вариантом группы устройств.</span><span class="sxs-lookup"><span data-stu-id="433e8-137">If your organization has more than 20 device groups, select **Edit** next to the filtered device group option.</span></span>

![Отображение редактирования большого числа групп.](images/tvm-exception-edit-groups.png)

<span data-ttu-id="433e8-139">Появится вылет, в котором можно будет искать и выбирать группы устройств, которые необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="433e8-139">A flyout will appear where you can search and choose device groups you want included.</span></span> <span data-ttu-id="433e8-140">Выберите значок контрольного знака ниже Поиск, чтобы проверить или оточеовать все.</span><span class="sxs-lookup"><span data-stu-id="433e8-140">Select the check mark icon below Search to check/uncheck all.</span></span>

![Отображение групповой вылет большой группы устройств.](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a><span data-ttu-id="433e8-142">Глобальные исключения</span><span class="sxs-lookup"><span data-stu-id="433e8-142">Global exceptions</span></span>

<span data-ttu-id="433e8-143">Если у вас есть глобальные разрешения администратора (так называемый администратор ATP Microsoft Defender), вы сможете создать и отменить глобальное исключение.</span><span class="sxs-lookup"><span data-stu-id="433e8-143">If you have global administrator permissions (called Microsoft Defender ATP administrator), you will be able to create and cancel a global exception.</span></span> <span data-ttu-id="433e8-144">Она затрагивает **все текущие** и будущие группы устройств в вашей организации, и изменить ее сможет только пользователь с аналогичным разрешением.</span><span class="sxs-lookup"><span data-stu-id="433e8-144">It affects **all** current and future device groups in your organization, and only a user with similar permission would be able to change it.</span></span> <span data-ttu-id="433e8-145">Состояние рекомендации изменится с "active" на "полное исключение".</span><span class="sxs-lookup"><span data-stu-id="433e8-145">The recommendation state will change from “active” to “full exception.”</span></span>

![Отображение глобального варианта исключения.](images/tvm-exception-global.png)

<span data-ttu-id="433e8-147">Некоторые вещи, которые необходимо иметь в виду:</span><span class="sxs-lookup"><span data-stu-id="433e8-147">Some things to keep in mind:</span></span>

- <span data-ttu-id="433e8-148">Если рекомендация находится под глобальным исключением, то вновь созданные исключения для групп устройств будут приостановлены до истечения или отмены глобального исключения.</span><span class="sxs-lookup"><span data-stu-id="433e8-148">If a recommendation is under global exception, then newly created exceptions for device groups will be suspended until the global exception has expired or been cancelled.</span></span> <span data-ttu-id="433e8-149">После этого новые исключения группы устройств вступает в силу до истечения срока их действия.</span><span class="sxs-lookup"><span data-stu-id="433e8-149">After that point, the new device group exceptions will go into effect until they expire.</span></span>
- <span data-ttu-id="433e8-150">Если в рекомендации уже есть исключения для определенных групп устройств и создается глобальное исключение, исключение группы устройств будет приостановлено до истечения срока действия или глобального исключения до истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="433e8-150">If a recommendation already has exceptions for specific device groups and a global exception is created, then the device group exception will be suspended until it expires or the global exception is cancelled before it expires.</span></span>

### <a name="justification"></a><span data-ttu-id="433e8-151">Justification</span><span class="sxs-lookup"><span data-stu-id="433e8-151">Justification</span></span>

<span data-ttu-id="433e8-152">Выберите обоснование исключения, необходимого для файла, а не исправление рекомендации по безопасности, о чем идет речь.</span><span class="sxs-lookup"><span data-stu-id="433e8-152">Select your justification for the exception you need to file instead of remediating the security recommendation in question.</span></span> <span data-ttu-id="433e8-153">Заполните контекст обоснования, а затем установите длительность исключения.</span><span class="sxs-lookup"><span data-stu-id="433e8-153">Fill out the justification context, then set the exception duration.</span></span>

<span data-ttu-id="433e8-154">В следующем списке подробно извесятся об обоснованиях для параметров исключений:</span><span class="sxs-lookup"><span data-stu-id="433e8-154">The following list details the justifications behind the exception options:</span></span>

- <span data-ttu-id="433e8-155">**Управление сторонними** средствами . Сторонний продукт или программное обеспечение уже адресована эта рекомендация . Выбор этого типа обоснования позволит снизить оценку экспозиции и повысить безопасную оценку, так как риск снижается.</span><span class="sxs-lookup"><span data-stu-id="433e8-155">**Third party control** - A third party product or software already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="433e8-156">**Альтернативное** смягчение последствий . Внутренний инструмент уже решает эту рекомендацию. Выбор этого типа обоснования позволит снизить оценку экспозиции и повысить безопасную оценку, так как риск снижается.</span><span class="sxs-lookup"><span data-stu-id="433e8-156">**Alternate mitigation** - An internal tool already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="433e8-157">**Риск, принятый** . Создает низкий риск и/или реализация рекомендации является слишком дорогой</span><span class="sxs-lookup"><span data-stu-id="433e8-157">**Risk accepted** - Poses low risk and/or implementing the recommendation is too expensive</span></span>
- <span data-ttu-id="433e8-158">**Запланированное исправление (благодать)** — уже запланировано, но ожидает выполнения или авторизации</span><span class="sxs-lookup"><span data-stu-id="433e8-158">**Planned remediation (grace)** - Already planned but is awaiting execution or authorization</span></span>

## <a name="view-all-exceptions"></a><span data-ttu-id="433e8-159">Просмотр всех исключений</span><span class="sxs-lookup"><span data-stu-id="433e8-159">View all exceptions</span></span>

<span data-ttu-id="433e8-160">Перейдите на **вкладку Исключения** на странице **Исправление.**</span><span class="sxs-lookup"><span data-stu-id="433e8-160">Navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="433e8-161">Можно фильтровать по оправданию, типу и статусу.</span><span class="sxs-lookup"><span data-stu-id="433e8-161">You can filter by justification, type, and status.</span></span>

 <span data-ttu-id="433e8-162">Выберите исключение, чтобы открыть вылет с дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="433e8-162">Select an exception to open a flyout with more details.</span></span> <span data-ttu-id="433e8-163">Исключения для каждой группы устройств будут иметь список каждой группы устройств, на которые распространяется исключение, которое можно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="433e8-163">Exceptions per devices group will have a list of every device group the exception covers, which you can export.</span></span> <span data-ttu-id="433e8-164">Вы также можете просмотреть связанную рекомендацию или отменить исключение.</span><span class="sxs-lookup"><span data-stu-id="433e8-164">You can also view the related recommendation or cancel the exception.</span></span>

![Отображение вкладки "Исключения" на странице Исправление.](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a><span data-ttu-id="433e8-166">Отмена исключения</span><span class="sxs-lookup"><span data-stu-id="433e8-166">How to cancel an exception</span></span>

<span data-ttu-id="433e8-167">Чтобы отменить исключение, перейдите на вкладку **Исключения** на странице **Исправление.**</span><span class="sxs-lookup"><span data-stu-id="433e8-167">To cancel an exception, navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="433e8-168">Выберите исключение.</span><span class="sxs-lookup"><span data-stu-id="433e8-168">Select the exception.</span></span>

<span data-ttu-id="433e8-169">Чтобы отменить исключение для всех групп устройств или глобальное исключение, выберите кнопку **Отмена для всех групп** устройств.</span><span class="sxs-lookup"><span data-stu-id="433e8-169">To cancel the exception for all device groups or for a global exception, select the **Cancel exception for all device groups** button.</span></span> <span data-ttu-id="433e8-170">Вы сможете отменить исключения только для групп устройств, на которые у вас есть разрешения.</span><span class="sxs-lookup"><span data-stu-id="433e8-170">You will only be able to cancel exceptions for device groups you have permissions for.</span></span>

![Кнопка отмены.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a><span data-ttu-id="433e8-172">Отмена исключения для определенной группы устройств</span><span class="sxs-lookup"><span data-stu-id="433e8-172">Cancel the exception for a specific device group</span></span>

<span data-ttu-id="433e8-173">Выберите конкретную группу устройств, чтобы отменить исключение для нее.</span><span class="sxs-lookup"><span data-stu-id="433e8-173">Select the specific device group to cancel the exception for it.</span></span> <span data-ttu-id="433e8-174">Для группы устройств появится вылет, и вы можете выбрать исключение **Отмена.**</span><span class="sxs-lookup"><span data-stu-id="433e8-174">A flyout will appear for the device group, and you can select **Cancel exception**.</span></span>

![Отображение выбора определенной группы устройств.](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a><span data-ttu-id="433e8-176">Просмотр влияния после примененных исключений</span><span class="sxs-lookup"><span data-stu-id="433e8-176">View impact after exceptions are applied</span></span>

<span data-ttu-id="433e8-177">На странице Рекомендации по безопасности выберите **Параметры** столбцов и проверьте поля для устройств **Exposed (после** исключений) и **Impact (после исключений).**</span><span class="sxs-lookup"><span data-stu-id="433e8-177">In the Security Recommendations page, select **Customize columns** and check the boxes for **Exposed devices (after exceptions)** and **Impact (after exceptions)**.</span></span>

![Отображение параметров настройки столбцов.](images/tvm-after-exceptions.png)

<span data-ttu-id="433e8-179">Столбец выставленных устройств (после исключений) отображает оставшиеся устройства, которые по-прежнему подвержены уязвимостям после примененных исключений.</span><span class="sxs-lookup"><span data-stu-id="433e8-179">The exposed devices (after exceptions) column shows the remaining devices that are still exposed to vulnerabilities after exceptions are applied.</span></span> <span data-ttu-id="433e8-180">Исключения, влияющие на экспозицию, включают "сторонний контроль" и "альтернативное смягчение".</span><span class="sxs-lookup"><span data-stu-id="433e8-180">Exception justifications that affect the exposure include ‘third party control’ and ‘alternate mitigation’.</span></span> <span data-ttu-id="433e8-181">Другие обоснования не уменьшают экспозицию устройства, и они по-прежнему считаются выставленными.</span><span class="sxs-lookup"><span data-stu-id="433e8-181">Other justifications do not reduce the exposure of a device, and they are still considered exposed.</span></span>

<span data-ttu-id="433e8-182">Влияние (после исключений) показывает оставшееся влияние на оценку экспозиции или безопасную оценку после примененных исключений.</span><span class="sxs-lookup"><span data-stu-id="433e8-182">The impact (after exceptions) shows remaining impact to exposure score or secure score after exceptions are applied.</span></span> <span data-ttu-id="433e8-183">Исключения, влияющие на оценки, включают "сторонний контроль" и "альтернативное смягчение".</span><span class="sxs-lookup"><span data-stu-id="433e8-183">Exception justifications that affect the scores include ‘third party control’ and ‘alternate mitigation.’</span></span> <span data-ttu-id="433e8-184">Другие обоснования не уменьшают экспозицию устройства, поэтому оценка экспозиции и безопасная оценка не изменяются.</span><span class="sxs-lookup"><span data-stu-id="433e8-184">Other justifications do not reduce the exposure of a device, and so the exposure score and secure score do not change.</span></span>

![Отображение столбцов в таблице.](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a><span data-ttu-id="433e8-186">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="433e8-186">Related topics</span></span>

- [<span data-ttu-id="433e8-187">Обзор управления угрозами и уязвимостью</span><span class="sxs-lookup"><span data-stu-id="433e8-187">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="433e8-188">Устранение уязвимостей</span><span class="sxs-lookup"><span data-stu-id="433e8-188">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="433e8-189">Рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="433e8-189">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="433e8-190">Показатель уязвимости</span><span class="sxs-lookup"><span data-stu-id="433e8-190">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="433e8-191">Оценка безопасности (Майкрософт) для устройств</span><span class="sxs-lookup"><span data-stu-id="433e8-191">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
