---
title: Создание правила уведомления об отборе или отключении
description: Получите уведомление, когда используется локальный сценарий бортового или оффбординга.
keywords: onboarding, offboarding, local, script, notification, rule
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5dfdfc6d14add33154ed4c2370bca458e752125d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187336"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a><span data-ttu-id="0e110-104">Создание правила уведомлений при локальном сценарии бортового или offboarding</span><span class="sxs-lookup"><span data-stu-id="0e110-104">Create a notification rule when a local onboarding or offboarding script is used</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0e110-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0e110-105">**Applies to:**</span></span>
- [<span data-ttu-id="0e110-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0e110-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0e110-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e110-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="0e110-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0e110-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0e110-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="0e110-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="0e110-110">Создайте правило уведомлений, чтобы при создании локального сценария включив или отключаясь, вы будете уведомлены.</span><span class="sxs-lookup"><span data-stu-id="0e110-110">Create a notification rule so that when a local onboarding or offboarding script is used, you'll be notified.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="0e110-111">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="0e110-111">Before you begin</span></span>
<span data-ttu-id="0e110-112">Необходимо иметь доступ к:</span><span class="sxs-lookup"><span data-stu-id="0e110-112">You'll need to have access to:</span></span>
 - <span data-ttu-id="0e110-113">Microsoft Flow (план потока 1 как минимум).</span><span class="sxs-lookup"><span data-stu-id="0e110-113">Microsoft Flow (Flow Plan 1 at a minimum).</span></span> <span data-ttu-id="0e110-114">Дополнительные сведения см. на странице [Цена потока](https://flow.microsoft.com/pricing/).</span><span class="sxs-lookup"><span data-stu-id="0e110-114">For more information, see [Flow pricing page](https://flow.microsoft.com/pricing/).</span></span>
 - <span data-ttu-id="0e110-115">Azure Table или SharePoint List или Library / SQL DB</span><span class="sxs-lookup"><span data-stu-id="0e110-115">Azure Table or SharePoint List or Library / SQL DB</span></span>

## <a name="create-the-notification-flow"></a><span data-ttu-id="0e110-116">Создание потока уведомлений</span><span class="sxs-lookup"><span data-stu-id="0e110-116">Create the notification flow</span></span>

1. <span data-ttu-id="0e110-117">В [flow.microsoft.com](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="0e110-117">In [flow.microsoft.com](https://flow.microsoft.com/).</span></span>

2. <span data-ttu-id="0e110-118">Перейдите **к потоку > New > Scheduled - из пустого**.</span><span class="sxs-lookup"><span data-stu-id="0e110-118">Navigate to **My flows > New > Scheduled - from blank**.</span></span> 

    ![Изображение потока](images/new-flow.png)


3. <span data-ttu-id="0e110-120">Создайте запланированный поток.</span><span class="sxs-lookup"><span data-stu-id="0e110-120">Build a scheduled flow.</span></span>
   1. <span data-ttu-id="0e110-121">Введите имя потока.</span><span class="sxs-lookup"><span data-stu-id="0e110-121">Enter a flow name.</span></span>
   2. <span data-ttu-id="0e110-122">Укажите начало и время.</span><span class="sxs-lookup"><span data-stu-id="0e110-122">Specify the start and time.</span></span>
   3. <span data-ttu-id="0e110-123">Укажите частоту.</span><span class="sxs-lookup"><span data-stu-id="0e110-123">Specify the frequency.</span></span> <span data-ttu-id="0e110-124">Например, каждые 5 минут.</span><span class="sxs-lookup"><span data-stu-id="0e110-124">For example, every 5 minutes.</span></span>

    ![Изображение потока уведомлений](images/build-flow.png)

4. <span data-ttu-id="0e110-126">Выберите кнопку +, чтобы добавить новое действие.</span><span class="sxs-lookup"><span data-stu-id="0e110-126">Select the + button to add a new action.</span></span> <span data-ttu-id="0e110-127">Новое действие будет http-запросом для API центра безопасности Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="0e110-127">The new action will be an HTTP request to the Defender for Endpoint security center device(s) API.</span></span> <span data-ttu-id="0e110-128">Кроме того, его можно заменить на внедорожный соединителка WDATP (действие: "Machines - Get list of machines").</span><span class="sxs-lookup"><span data-stu-id="0e110-128">You can also replace it with the out-of-the-box "WDATP Connector" (action: "Machines - Get list of machines").</span></span> 

    ![Изображение повторения и добавления действия](images/recurrence-add.png)


5. <span data-ttu-id="0e110-130">Введите следующие поля HTTP:</span><span class="sxs-lookup"><span data-stu-id="0e110-130">Enter the following HTTP fields:</span></span>

   - <span data-ttu-id="0e110-131">Метод: "GET" в качестве значения для получения списка устройств.</span><span class="sxs-lookup"><span data-stu-id="0e110-131">Method: "GET" as a value to get the list of devices.</span></span>
   - <span data-ttu-id="0e110-132">URI. Введите `https://api.securitycenter.microsoft.com/api/machines` .</span><span class="sxs-lookup"><span data-stu-id="0e110-132">URI: Enter `https://api.securitycenter.microsoft.com/api/machines`.</span></span>
   - <span data-ttu-id="0e110-133">Проверка подлинности. Выберите "Active Directory OAuth".</span><span class="sxs-lookup"><span data-stu-id="0e110-133">Authentication: Select "Active Directory OAuth".</span></span>
   - <span data-ttu-id="0e110-134">Клиент. Войдите и перейдите в https://portal.azure.com Azure Active **Directory > регистрации** приложений и получите значение Tenant ID.</span><span class="sxs-lookup"><span data-stu-id="0e110-134">Tenant: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and get the Tenant ID value.</span></span>
   - <span data-ttu-id="0e110-135">Аудитория: `https://securitycenter.onmicrosoft.com/windowsatpservice\`</span><span class="sxs-lookup"><span data-stu-id="0e110-135">Audience: `https://securitycenter.onmicrosoft.com/windowsatpservice\`</span></span>
   - <span data-ttu-id="0e110-136">Client ID. Войдите и перейдите в Azure Active Directory > регистрации приложений и получите значение https://portal.azure.com Client ID. </span><span class="sxs-lookup"><span data-stu-id="0e110-136">Client ID: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and  get the Client ID value.</span></span>
   - <span data-ttu-id="0e110-137">Тип учетных данных. Выберите "Секрет".</span><span class="sxs-lookup"><span data-stu-id="0e110-137">Credential Type: Select "Secret".</span></span>
   - <span data-ttu-id="0e110-138">Секрет. Войдите и перейдите в https://portal.azure.com **Azure Active Directory > регистрации** приложений и получите значение Tenant ID.</span><span class="sxs-lookup"><span data-stu-id="0e110-138">Secret: Sign-in to https://portal.azure.com and navigate to **Azure Active Directory > App Registrations** and get the Tenant ID value.</span></span>

    ![Изображение условий HTTP](images/http-conditions.png)


6. <span data-ttu-id="0e110-140">Добавьте новый шаг, выбрав **Добавить новое действие,** а затем **ищите** операции данных и выберите **Parse JSON**.</span><span class="sxs-lookup"><span data-stu-id="0e110-140">Add a new step by selecting **Add new action** then search for **Data Operations** and select **Parse JSON**.</span></span>

    ![Изображение операций с данными](images/data-operations.png)

7. <span data-ttu-id="0e110-142">Добавление body в **поле контента.**</span><span class="sxs-lookup"><span data-stu-id="0e110-142">Add Body in the **Content** field.</span></span>

    ![Изображение размыка JSON](images/parse-json.png)

8. <span data-ttu-id="0e110-144">Выберите пример **полезной нагрузки Use для создания ссылки схемы.**</span><span class="sxs-lookup"><span data-stu-id="0e110-144">Select the **Use sample payload to generate schema** link.</span></span>

    ![Изображение json parse с полезной нагрузкой](images/parse-json-schema.png)

9. <span data-ttu-id="0e110-146">Скопируйте и вклеите следующий фрагмент JSON:</span><span class="sxs-lookup"><span data-stu-id="0e110-146">Copy and paste the following JSON snippet:</span></span>

    ```
    {
        "type": "object",
        "properties": {
            "@@odata.context": {
                "type": "string"
            },
            "value": {
                "type": "array",
                "items": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "computerDnsName": {
                            "type": "string"
                        },
                        "firstSeen": {
                            "type": "string"
                        },
                        "lastSeen": {
                            "type": "string"
                        },
                        "osPlatform": {
                            "type": "string"
                        },
                        "osVersion": {},
                        "lastIpAddress": {
                            "type": "string"
                        },
                        "lastExternalIpAddress": {
                            "type": "string"
                        },
                        "agentVersion": {
                            "type": "string"
                        },
                        "osBuild": {
                            "type": "integer"
                        },
                        "healthStatus": {
                            "type": "string"
                        },
                        "riskScore": {
                            "type": "string"
                        },
                        "exposureScore": {
                            "type": "string"
                        },
                        "aadDeviceId": {},
                        "machineTags": {
                            "type": "array"
                        }
                    },
                    "required": [
                        "id",
                        "computerDnsName",
                        "firstSeen",
                        "lastSeen",
                        "osPlatform",
                        "osVersion",
                        "lastIpAddress",
                        "lastExternalIpAddress",
                        "agentVersion",
                        "osBuild",
                        "healthStatus",
                        "rbacGroupId",
                        "rbacGroupName",
                        "riskScore",
                        "exposureScore",
                        "aadDeviceId",
                        "machineTags"
                    ]
                }
            }
        }
    }

    ```

10.  <span data-ttu-id="0e110-147">Извлечение значений из вызова JSON и проверка того, есть ли в списке SharePoint уже зарегистрированное устройство(ы) в качестве примера:</span><span class="sxs-lookup"><span data-stu-id="0e110-147">Extract the values from the JSON call and check if the onboarded device(s) is / are already registered at the SharePoint list as an example:</span></span>
- <span data-ttu-id="0e110-148">Если да, уведомление не запускается</span><span class="sxs-lookup"><span data-stu-id="0e110-148">If yes, no notification will be triggered</span></span>
- <span data-ttu-id="0e110-149">Если нет, зарегистрирует новое бортовом устройстве (ы) в списке SharePoint и уведомление будет отправлено администратору Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0e110-149">If no, will register the new onboarded device(s) in the SharePoint list and a notification will be sent to the Defender for Endpoint admin</span></span>

    ![Изображение, применяемого к каждому](images/flow-apply.png)

    ![Изображение, применяемого к каждому элементу с получением элементов](images/apply-to-each.png)

11. <span data-ttu-id="0e110-152">В **condition** добавьте следующее выражение: "length(body('Get_items'???'' значение'])" и установите условие равно 0.</span><span class="sxs-lookup"><span data-stu-id="0e110-152">Under **Condition**, add the following expression: "length(body('Get_items')?['value'])" and set the condition to equal to 0.</span></span>

    <span data-ttu-id="0e110-153">![Изображение применения к каждому условию](images/apply-to-each-value.png)</span><span class="sxs-lookup"><span data-stu-id="0e110-153">![Image of apply to each condition](images/apply-to-each-value.png)</span></span>  
    <span data-ttu-id="0e110-154">![Изображение condition1 ](images/conditions-2.png) 
     ![ Image of condition2](images/condition3.png)</span><span class="sxs-lookup"><span data-stu-id="0e110-154">![Image of condition1](images/conditions-2.png) 
    ![Image of condition2](images/condition3.png)</span></span>  
<span data-ttu-id="0e110-155">![Изображение отправки электронной почты](images/send-email.png)</span><span class="sxs-lookup"><span data-stu-id="0e110-155">![Image of send email](images/send-email.png)</span></span>

## <a name="alert-notification"></a><span data-ttu-id="0e110-156">Оповещение</span><span class="sxs-lookup"><span data-stu-id="0e110-156">Alert notification</span></span>
<span data-ttu-id="0e110-157">Следующее изображение является примером уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="0e110-157">The following image is an example of an email notification.</span></span>

![Изображение уведомления электронной почты](images/alert-notification.png)


## <a name="tips"></a><span data-ttu-id="0e110-159">Советы </span><span class="sxs-lookup"><span data-stu-id="0e110-159">Tips</span></span>

- <span data-ttu-id="0e110-160">Здесь можно фильтровать только lastSeen:</span><span class="sxs-lookup"><span data-stu-id="0e110-160">You can filter here using lastSeen only:</span></span>
    - <span data-ttu-id="0e110-161">Каждые 60 минут:</span><span class="sxs-lookup"><span data-stu-id="0e110-161">Every 60 min:</span></span>
      - <span data-ttu-id="0e110-162">Возьмите все устройства, которые последний раз видели в течение последних 7 дней.</span><span class="sxs-lookup"><span data-stu-id="0e110-162">Take all devices last seen in the past 7 days.</span></span> 

- <span data-ttu-id="0e110-163">Для каждого устройства:</span><span class="sxs-lookup"><span data-stu-id="0e110-163">For each device:</span></span> 
    - <span data-ttu-id="0e110-164">Если последнее увиденное свойство находится с интервалом в один час [-7 дней, -7days + 60 минут] -> оповещение о возможности отключения.</span><span class="sxs-lookup"><span data-stu-id="0e110-164">If last seen property is on the one hour interval of [-7 days, -7days + 60 minutes ] -> Alert for offboarding possibility.</span></span>
    - <span data-ttu-id="0e110-165">Если вы впервые увидели в последний час - > оповещение для бортового.</span><span class="sxs-lookup"><span data-stu-id="0e110-165">If first seen is on the past hour -> Alert for onboarding.</span></span>

<span data-ttu-id="0e110-166">В этом решении не будет дублироваться оповещений: есть клиенты с многочисленными устройствами.</span><span class="sxs-lookup"><span data-stu-id="0e110-166">In this solution you will not have duplicate alerts: There are tenants that have numerous devices.</span></span> <span data-ttu-id="0e110-167">Получение всех этих устройств может быть очень дорогим и может потребовать paging.</span><span class="sxs-lookup"><span data-stu-id="0e110-167">Getting all those devices might be very expensive and might require paging.</span></span>

<span data-ttu-id="0e110-168">Вы можете разделить его на два запроса:</span><span class="sxs-lookup"><span data-stu-id="0e110-168">You can split it to two queries:</span></span> 
1.  <span data-ttu-id="0e110-169">Для offboarding возьмите только этот интервал с помощью OData $filter только уведомить, если условия выполнены.</span><span class="sxs-lookup"><span data-stu-id="0e110-169">For offboarding take only this interval using the OData $filter and only notify if the conditions are met.</span></span>
2.  <span data-ttu-id="0e110-170">Возьмите все устройства, которые последний раз видели в течение последнего часа, и проверьте впервые увиденное свойство для них (если первое увиденное свойство находится в последний час, последний вид должен быть там).</span><span class="sxs-lookup"><span data-stu-id="0e110-170">Take all devices last seen in the past hour and check first seen property for them (if the first seen property is on the past hour, the last seen must be there too).</span></span> 

