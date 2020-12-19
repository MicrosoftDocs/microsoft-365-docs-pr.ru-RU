---
title: API списка инцидентов в Microsoft 365 Defender
description: Список API инцидентов в Microsoft 365 Defender
keywords: список, инцидент, инциденты, api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 13508d3ad9d61797517ccb55a27152883947843a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719432"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="b8d84-104">API списка инцидентов в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8d84-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b8d84-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b8d84-105">**Applies to:**</span></span>

- <span data-ttu-id="b8d84-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8d84-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8d84-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="b8d84-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b8d84-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b8d84-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="b8d84-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="b8d84-109">API description</span></span>

<span data-ttu-id="b8d84-110">API инцидентов списков позволяет сортировать инциденты, чтобы создать информированный ответ на кибербезопасность.</span><span class="sxs-lookup"><span data-stu-id="b8d84-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="b8d84-111">Он предоставляет коллекцию инцидентов, которые были помечены в сети в течение указанного вами диапазона времени в политике хранения среды.</span><span class="sxs-lookup"><span data-stu-id="b8d84-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="b8d84-112">Последние инциденты отображаются в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="b8d84-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="b8d84-113">Каждый инцидент содержит массив связанных оповещений и связанных с ними сущностями.</span><span class="sxs-lookup"><span data-stu-id="b8d84-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="b8d84-114">API поддерживает следующие **операторы OData:**</span><span class="sxs-lookup"><span data-stu-id="b8d84-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="b8d84-115">`$filter`в `lastUpdateTime` `createdTime` свойствах , `status` , и `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="b8d84-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="b8d84-116">`$top`, с максимальным значением **100**</span><span class="sxs-lookup"><span data-stu-id="b8d84-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="b8d84-117">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b8d84-117">Limitations</span></span>

1. <span data-ttu-id="b8d84-118">Максимальный размер страницы составляет **100 инцидентов.**</span><span class="sxs-lookup"><span data-stu-id="b8d84-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="b8d84-119">Максимальная скорость запросов составляет **50 вызовов в минуту** и **1500 вызовов в час.**</span><span class="sxs-lookup"><span data-stu-id="b8d84-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="b8d84-120">Разрешения</span><span class="sxs-lookup"><span data-stu-id="b8d84-120">Permissions</span></span>

<span data-ttu-id="b8d84-121">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="b8d84-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b8d84-122">Дополнительные возможности, включая выбор разрешений, см. в [API Access в Microsoft 365 Defender](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="b8d84-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="b8d84-123">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="b8d84-123">Permission type</span></span> | <span data-ttu-id="b8d84-124">Разрешение</span><span class="sxs-lookup"><span data-stu-id="b8d84-124">Permission</span></span> | <span data-ttu-id="b8d84-125">Отображаемая имя разрешения</span><span class="sxs-lookup"><span data-stu-id="b8d84-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="b8d84-126">Приложение</span><span class="sxs-lookup"><span data-stu-id="b8d84-126">Application</span></span> | <span data-ttu-id="b8d84-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="b8d84-127">Incident.Read.All</span></span> | <span data-ttu-id="b8d84-128">Чтение всех инцидентов</span><span class="sxs-lookup"><span data-stu-id="b8d84-128">Read all incidents</span></span>
<span data-ttu-id="b8d84-129">Приложение</span><span class="sxs-lookup"><span data-stu-id="b8d84-129">Application</span></span> | <span data-ttu-id="b8d84-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b8d84-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="b8d84-131">Чтение и написание всех инцидентов</span><span class="sxs-lookup"><span data-stu-id="b8d84-131">Read and write all incidents</span></span>
<span data-ttu-id="b8d84-132">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="b8d84-132">Delegated (work or school account)</span></span> | <span data-ttu-id="b8d84-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="b8d84-133">Incident.Read</span></span> | <span data-ttu-id="b8d84-134">Чтение инцидентов</span><span class="sxs-lookup"><span data-stu-id="b8d84-134">Read incidents</span></span>
<span data-ttu-id="b8d84-135">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="b8d84-135">Delegated (work or school account)</span></span> | <span data-ttu-id="b8d84-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b8d84-136">Incident.ReadWrite</span></span> | <span data-ttu-id="b8d84-137">Чтение и написание инцидентов</span><span class="sxs-lookup"><span data-stu-id="b8d84-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="b8d84-138">При получении маркера с использованием учетных данных пользователя:</span><span class="sxs-lookup"><span data-stu-id="b8d84-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="b8d84-139">Пользователь должен иметь разрешение на просмотр инцидентов на портале.</span><span class="sxs-lookup"><span data-stu-id="b8d84-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="b8d84-140">Ответ будет включать только инциденты, с которые пользователь может получить данные.</span><span class="sxs-lookup"><span data-stu-id="b8d84-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="b8d84-141">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="b8d84-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="b8d84-142">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="b8d84-142">Request headers</span></span>

<span data-ttu-id="b8d84-143">Имя</span><span class="sxs-lookup"><span data-stu-id="b8d84-143">Name</span></span> | <span data-ttu-id="b8d84-144">Тип</span><span class="sxs-lookup"><span data-stu-id="b8d84-144">Type</span></span> | <span data-ttu-id="b8d84-145">Описание</span><span class="sxs-lookup"><span data-stu-id="b8d84-145">Description</span></span>
-|-|-
<span data-ttu-id="b8d84-146">Авторизация</span><span class="sxs-lookup"><span data-stu-id="b8d84-146">Authorization</span></span> | <span data-ttu-id="b8d84-147">String</span><span class="sxs-lookup"><span data-stu-id="b8d84-147">String</span></span> | <span data-ttu-id="b8d84-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b8d84-148">Bearer {token}.</span></span> <span data-ttu-id="b8d84-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="b8d84-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="b8d84-150">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="b8d84-150">Request body</span></span>

<span data-ttu-id="b8d84-151">Нет.</span><span class="sxs-lookup"><span data-stu-id="b8d84-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="b8d84-152">Отклик</span><span class="sxs-lookup"><span data-stu-id="b8d84-152">Response</span></span>

<span data-ttu-id="b8d84-153">В случае успеха этот метод возвращает список инцидентов в `200 OK` теле ответа. [](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="b8d84-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="b8d84-154">Сопоставление схемы</span><span class="sxs-lookup"><span data-stu-id="b8d84-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="b8d84-155">Метаданные инцидента</span><span class="sxs-lookup"><span data-stu-id="b8d84-155">Incident metadata</span></span>

<span data-ttu-id="b8d84-156">Имя поля</span><span class="sxs-lookup"><span data-stu-id="b8d84-156">Field name</span></span> | <span data-ttu-id="b8d84-157">Описание</span><span class="sxs-lookup"><span data-stu-id="b8d84-157">Description</span></span> | <span data-ttu-id="b8d84-158">Пример значения</span><span class="sxs-lookup"><span data-stu-id="b8d84-158">Example value</span></span>
-|-|-
<span data-ttu-id="b8d84-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="b8d84-159">incidentId</span></span> | <span data-ttu-id="b8d84-160">Уникальный идентификатор для представления инцидента</span><span class="sxs-lookup"><span data-stu-id="b8d84-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="b8d84-161">924565</span><span class="sxs-lookup"><span data-stu-id="b8d84-161">924565</span></span>
<span data-ttu-id="b8d84-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="b8d84-162">redirectIncidentId</span></span> | <span data-ttu-id="b8d84-163">Заполняется только в том случае, если инцидент сгруппировали вместе с другим инцидентом в рамках логики обработки инцидента.</span><span class="sxs-lookup"><span data-stu-id="b8d84-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="b8d84-164">924569</span><span class="sxs-lookup"><span data-stu-id="b8d84-164">924569</span></span>
<span data-ttu-id="b8d84-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="b8d84-165">incidentName</span></span> | <span data-ttu-id="b8d84-166">Строка, доступная для каждого инцидента.</span><span class="sxs-lookup"><span data-stu-id="b8d84-166">String value available for every incident.</span></span> | <span data-ttu-id="b8d84-167">Действия программы-вымогателя</span><span class="sxs-lookup"><span data-stu-id="b8d84-167">Ransomware activity</span></span>
<span data-ttu-id="b8d84-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="b8d84-168">createdTime</span></span> | <span data-ttu-id="b8d84-169">Время создания инцидента.</span><span class="sxs-lookup"><span data-stu-id="b8d84-169">Time when incident was first created.</span></span> | <span data-ttu-id="b8d84-170">2020-09-06T14:46:57.073333Z</span><span class="sxs-lookup"><span data-stu-id="b8d84-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="b8d84-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="b8d84-171">lastUpdateTime</span></span> | <span data-ttu-id="b8d84-172">Время последнего обновления инцидента на тыловом сайте.</span><span class="sxs-lookup"><span data-stu-id="b8d84-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="b8d84-173">Это поле можно использовать при настройке параметра запроса в течение диапазона времени, в течение времени, в течение который извлекаются инциденты.</span><span class="sxs-lookup"><span data-stu-id="b8d84-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="b8d84-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="b8d84-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="b8d84-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="b8d84-175">assignedTo</span></span> | <span data-ttu-id="b8d84-176">Владелец инцидента или *null,* если владелец не назначен.</span><span class="sxs-lookup"><span data-stu-id="b8d84-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="b8d84-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8d84-177">secop2@contoso.com</span></span>
<span data-ttu-id="b8d84-178">classification</span><span class="sxs-lookup"><span data-stu-id="b8d84-178">classification</span></span> | <span data-ttu-id="b8d84-179">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="b8d84-179">The specification for the incident.</span></span> <span data-ttu-id="b8d84-180">Значения свойств: *Unknown,* *FalsePositive,* *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="b8d84-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="b8d84-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="b8d84-181">Unknown</span></span>
<span data-ttu-id="b8d84-182">определение</span><span class="sxs-lookup"><span data-stu-id="b8d84-182">determination</span></span> | <span data-ttu-id="b8d84-183">Определяет определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="b8d84-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="b8d84-184">Значения свойств: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="b8d84-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="b8d84-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="b8d84-185">NotAvailable</span></span>
<span data-ttu-id="b8d84-186">status</span><span class="sxs-lookup"><span data-stu-id="b8d84-186">status</span></span> | <span data-ttu-id="b8d84-187">Классифицировать инциденты (как *активные* или *разрешенные).*</span><span class="sxs-lookup"><span data-stu-id="b8d84-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="b8d84-188">Это поможет вам организовать реагирование на инциденты и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="b8d84-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="b8d84-189">Активное</span><span class="sxs-lookup"><span data-stu-id="b8d84-189">Active</span></span>
<span data-ttu-id="b8d84-190">severity</span><span class="sxs-lookup"><span data-stu-id="b8d84-190">severity</span></span> | <span data-ttu-id="b8d84-191">Указывает возможное влияние на ресурсы.</span><span class="sxs-lookup"><span data-stu-id="b8d84-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="b8d84-192">Чем выше степень серьезности, тем больше это влияние.</span><span class="sxs-lookup"><span data-stu-id="b8d84-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="b8d84-193">Как правило, элементы с более высокой степенью серьезности требуют непосредственного внимания.</span><span class="sxs-lookup"><span data-stu-id="b8d84-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="b8d84-194">Одно из следующих значений: *Informational,* \*Low,\*\*Medium и *High.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="b8d84-195">Средняя</span><span class="sxs-lookup"><span data-stu-id="b8d84-195">Medium</span></span>
<span data-ttu-id="b8d84-196">tags</span><span class="sxs-lookup"><span data-stu-id="b8d84-196">tags</span></span> | <span data-ttu-id="b8d84-197">Массив пользовательских тегов, связанных с инцидентом, например для пометки группы инцидентов с общей характеристикой.</span><span class="sxs-lookup"><span data-stu-id="b8d84-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="b8d84-198">alerts</span><span class="sxs-lookup"><span data-stu-id="b8d84-198">alerts</span></span> | <span data-ttu-id="b8d84-199">Массив, содержащий все оповещения, связанные с инцидентом, а также другие сведения, такие как серьезность, объекты, задействованные в оповещении, и источник оповещений.</span><span class="sxs-lookup"><span data-stu-id="b8d84-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="b8d84-200">\[\] (См. сведения о полях оповещений ниже)</span><span class="sxs-lookup"><span data-stu-id="b8d84-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="b8d84-201">Метаданные оповещений</span><span class="sxs-lookup"><span data-stu-id="b8d84-201">Alerts metadata</span></span>

<span data-ttu-id="b8d84-202">Имя поля</span><span class="sxs-lookup"><span data-stu-id="b8d84-202">Field name</span></span> | <span data-ttu-id="b8d84-203">Описание</span><span class="sxs-lookup"><span data-stu-id="b8d84-203">Description</span></span> | <span data-ttu-id="b8d84-204">Пример значения</span><span class="sxs-lookup"><span data-stu-id="b8d84-204">Example value</span></span>
-|-|-
<span data-ttu-id="b8d84-205">alertId</span><span class="sxs-lookup"><span data-stu-id="b8d84-205">alertId</span></span> | <span data-ttu-id="b8d84-206">Уникальный идентификатор для представления оповещения</span><span class="sxs-lookup"><span data-stu-id="b8d84-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="b8d84-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="b8d84-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="b8d84-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="b8d84-208">incidentId</span></span> | <span data-ttu-id="b8d84-209">Уникальный идентификатор для представления инцидента, с котором связано данное оповещение</span><span class="sxs-lookup"><span data-stu-id="b8d84-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="b8d84-210">924565</span><span class="sxs-lookup"><span data-stu-id="b8d84-210">924565</span></span>
<span data-ttu-id="b8d84-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="b8d84-211">serviceSource</span></span> | <span data-ttu-id="b8d84-212">Служба, от которую исходит оповещение, например Microsoft Defender для конечной точки, Microsoft Cloud App Security, Microsoft Defender для удостоверений или Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8d84-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="b8d84-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="b8d84-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="b8d84-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="b8d84-214">creationTime</span></span> | <span data-ttu-id="b8d84-215">Время создания оповещения.</span><span class="sxs-lookup"><span data-stu-id="b8d84-215">Time when alert was first created.</span></span> | <span data-ttu-id="b8d84-216">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="b8d84-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="b8d84-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="b8d84-217">lastUpdatedTime</span></span> | <span data-ttu-id="b8d84-218">Время последнего обновления оповещения на тыловом уровне.</span><span class="sxs-lookup"><span data-stu-id="b8d84-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="b8d84-219">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="b8d84-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="b8d84-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="b8d84-220">resolvedTime</span></span> | <span data-ttu-id="b8d84-221">Время разрешения оповещения.</span><span class="sxs-lookup"><span data-stu-id="b8d84-221">Time when alert was resolved.</span></span> | <span data-ttu-id="b8d84-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="b8d84-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="b8d84-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="b8d84-223">firstActivity</span></span> | <span data-ttu-id="b8d84-224">Время, когда оповещение впервые сообщило об обновлении активности на тыловой части.</span><span class="sxs-lookup"><span data-stu-id="b8d84-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="b8d84-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="b8d84-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="b8d84-226">title</span><span class="sxs-lookup"><span data-stu-id="b8d84-226">title</span></span> | <span data-ttu-id="b8d84-227">Краткое определение строки, доступной для каждого оповещения.</span><span class="sxs-lookup"><span data-stu-id="b8d84-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="b8d84-228">Действия программы-вымогателя</span><span class="sxs-lookup"><span data-stu-id="b8d84-228">Ransomware activity</span></span>
<span data-ttu-id="b8d84-229">description</span><span class="sxs-lookup"><span data-stu-id="b8d84-229">description</span></span> | <span data-ttu-id="b8d84-230">Строка, описывающие каждое оповещение.</span><span class="sxs-lookup"><span data-stu-id="b8d84-230">String value describing each alert.</span></span> | <span data-ttu-id="b8d84-231">Пользователь Test User2 (testUser2@contoso.com) с помощью 99 файлов с несколькими расширениями, заканчивающийся на редкое расширение *herunterladen.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="b8d84-232">Это необычное количество манипуляций с файлами, что свидетельствует о возможной атаке программы-вымогателя.</span><span class="sxs-lookup"><span data-stu-id="b8d84-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="b8d84-233">category</span><span class="sxs-lookup"><span data-stu-id="b8d84-233">category</span></span> | <span data-ttu-id="b8d84-234">Визуальное и числовое представление о том, как далеко идет атака по цепочке атак.</span><span class="sxs-lookup"><span data-stu-id="b8d84-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="b8d84-235">Соответствует структуре [MITRE ATT&CK™](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="b8d84-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="b8d84-236">Влияние</span><span class="sxs-lookup"><span data-stu-id="b8d84-236">Impact</span></span>
<span data-ttu-id="b8d84-237">status</span><span class="sxs-lookup"><span data-stu-id="b8d84-237">status</span></span> | <span data-ttu-id="b8d84-238">Классифицировать оповещения *(например, "Новый",* *"Активный"* или *"Разрешено").*</span><span class="sxs-lookup"><span data-stu-id="b8d84-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="b8d84-239">Это поможет вам упорядоизировать и управлять ответами на оповещения.</span><span class="sxs-lookup"><span data-stu-id="b8d84-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="b8d84-240">Новое</span><span class="sxs-lookup"><span data-stu-id="b8d84-240">New</span></span>
<span data-ttu-id="b8d84-241">severity</span><span class="sxs-lookup"><span data-stu-id="b8d84-241">severity</span></span> | <span data-ttu-id="b8d84-242">Указывает возможное влияние на ресурсы.</span><span class="sxs-lookup"><span data-stu-id="b8d84-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="b8d84-243">Чем выше степень серьезности, тем больше это влияние.</span><span class="sxs-lookup"><span data-stu-id="b8d84-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="b8d84-244">Как правило, элементы с более высокой степенью серьезности требуют непосредственного внимания.</span><span class="sxs-lookup"><span data-stu-id="b8d84-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="b8d84-245">Одно из следующих значений: *Informational,* \*Low,\*\*Medium и *High.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="b8d84-246">Средняя</span><span class="sxs-lookup"><span data-stu-id="b8d84-246">Medium</span></span>
<span data-ttu-id="b8d84-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="b8d84-247">investigationId</span></span> | <span data-ttu-id="b8d84-248">ИД автоматического исследования, инициированный этим оповещением.</span><span class="sxs-lookup"><span data-stu-id="b8d84-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="b8d84-249">1234</span><span class="sxs-lookup"><span data-stu-id="b8d84-249">1234</span></span>
<span data-ttu-id="b8d84-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="b8d84-250">investigationState</span></span> | <span data-ttu-id="b8d84-251">Сведения о текущем состоянии исследования.</span><span class="sxs-lookup"><span data-stu-id="b8d84-251">Information on the investigation's current status.</span></span> <span data-ttu-id="b8d84-252">Одно из следующих значений: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedAlertType*, *SuppressedAlert*. </span><span class="sxs-lookup"><span data-stu-id="b8d84-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="b8d84-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="b8d84-253">UnsupportedAlertType</span></span>
<span data-ttu-id="b8d84-254">classification</span><span class="sxs-lookup"><span data-stu-id="b8d84-254">classification</span></span> | <span data-ttu-id="b8d84-255">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="b8d84-255">The specification for the incident.</span></span> <span data-ttu-id="b8d84-256">Значения свойств: *Unknown,* *FalsePositive,* *TruePositive* или *null*</span><span class="sxs-lookup"><span data-stu-id="b8d84-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="b8d84-257">Unknown</span><span class="sxs-lookup"><span data-stu-id="b8d84-257">Unknown</span></span>
<span data-ttu-id="b8d84-258">определение</span><span class="sxs-lookup"><span data-stu-id="b8d84-258">determination</span></span> | <span data-ttu-id="b8d84-259">Определяет определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="b8d84-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="b8d84-260">Значения свойств: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* или  *null*</span><span class="sxs-lookup"><span data-stu-id="b8d84-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="b8d84-261">Apt</span><span class="sxs-lookup"><span data-stu-id="b8d84-261">Apt</span></span>
<span data-ttu-id="b8d84-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="b8d84-262">assignedTo</span></span> | <span data-ttu-id="b8d84-263">Владелец инцидента или *null,* если владелец не назначен.</span><span class="sxs-lookup"><span data-stu-id="b8d84-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="b8d84-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8d84-264">secop2@contoso.com</span></span>
<span data-ttu-id="b8d84-265">actorName</span><span class="sxs-lookup"><span data-stu-id="b8d84-265">actorName</span></span> | <span data-ttu-id="b8d84-266">Группа действий, если она есть, связанная с этим оповещением.</span><span class="sxs-lookup"><span data-stu-id="b8d84-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="b8d84-267">ВАЗОН</span><span class="sxs-lookup"><span data-stu-id="b8d84-267">BORON</span></span>
<span data-ttu-id="b8d84-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="b8d84-268">threatFamilyName</span></span> | <span data-ttu-id="b8d84-269">Семейство угроз, связанное с этим оповещением.</span><span class="sxs-lookup"><span data-stu-id="b8d84-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="b8d84-270">null</span><span class="sxs-lookup"><span data-stu-id="b8d84-270">null</span></span>
<span data-ttu-id="b8d84-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="b8d84-271">mitreTechniques</span></span> | <span data-ttu-id="b8d84-272">Методы атаки в соответствие с решением [MITRE ATT](https://attack.mitre.org/)&CK ™ CK.</span><span class="sxs-lookup"><span data-stu-id="b8d84-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="b8d84-273">устройства</span><span class="sxs-lookup"><span data-stu-id="b8d84-273">devices</span></span> | <span data-ttu-id="b8d84-274">Все устройства, на которые были отправлены оповещения, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="b8d84-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="b8d84-275">\[\] (см. сведения о полях суностей ниже)</span><span class="sxs-lookup"><span data-stu-id="b8d84-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="b8d84-276">Формат устройства</span><span class="sxs-lookup"><span data-stu-id="b8d84-276">Device format</span></span>

<span data-ttu-id="b8d84-277">Имя поля</span><span class="sxs-lookup"><span data-stu-id="b8d84-277">Field name</span></span> | <span data-ttu-id="b8d84-278">Описание</span><span class="sxs-lookup"><span data-stu-id="b8d84-278">Description</span></span> | <span data-ttu-id="b8d84-279">Пример значения</span><span class="sxs-lookup"><span data-stu-id="b8d84-279">Example value</span></span>
-|-|-
<span data-ttu-id="b8d84-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="b8d84-280">DeviceId</span></span> | <span data-ttu-id="b8d84-281">ИД устройства, указанный в ATP в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b8d84-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="b8d84-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="b8d84-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="b8d84-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="b8d84-283">aadDeviceId</span></span> |  <span data-ttu-id="b8d84-284">ИД устройства, назначенный в [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="b8d84-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="b8d84-285">Доступно только для устройств, которые присоединились к домену.</span><span class="sxs-lookup"><span data-stu-id="b8d84-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="b8d84-286">null</span><span class="sxs-lookup"><span data-stu-id="b8d84-286">null</span></span>
<span data-ttu-id="b8d84-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="b8d84-287">deviceDnsName</span></span> | <span data-ttu-id="b8d84-288">Полное доменное имя устройства.</span><span class="sxs-lookup"><span data-stu-id="b8d84-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="b8d84-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8d84-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="b8d84-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="b8d84-290">osPlatform</span></span> | <span data-ttu-id="b8d84-291">Платформа ОС, запущенная на устройстве.</span><span class="sxs-lookup"><span data-stu-id="b8d84-291">The OS platform the device is running.</span></span>| <span data-ttu-id="b8d84-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="b8d84-292">WindowsServer2016</span></span>
<span data-ttu-id="b8d84-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="b8d84-293">osBuild</span></span> | <span data-ttu-id="b8d84-294">Версия сборки для ОС, запущенной на устройстве.</span><span class="sxs-lookup"><span data-stu-id="b8d84-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="b8d84-295">14393</span><span class="sxs-lookup"><span data-stu-id="b8d84-295">14393</span></span>
<span data-ttu-id="b8d84-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="b8d84-296">rbacGroupName</span></span> | <span data-ttu-id="b8d84-297">Группа [управления доступом](https://docs.microsoft.com/azure/role-based-access-control/overview) на основе ролей (RBAC), связанная с устройством.</span><span class="sxs-lookup"><span data-stu-id="b8d84-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="b8d84-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="b8d84-298">WDATP-Ring0</span></span>
<span data-ttu-id="b8d84-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="b8d84-299">firstSeen</span></span> | <span data-ttu-id="b8d84-300">Время первого увидеть устройство.</span><span class="sxs-lookup"><span data-stu-id="b8d84-300">Time when device was first seen.</span></span> | <span data-ttu-id="b8d84-301">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="b8d84-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="b8d84-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="b8d84-302">healthStatus</span></span> | <span data-ttu-id="b8d84-303">Состояние состояния состояния устройства.</span><span class="sxs-lookup"><span data-stu-id="b8d84-303">The health state of the device.</span></span> | <span data-ttu-id="b8d84-304">Активное</span><span class="sxs-lookup"><span data-stu-id="b8d84-304">Active</span></span>
<span data-ttu-id="b8d84-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="b8d84-305">riskScore</span></span> | <span data-ttu-id="b8d84-306">Оценка риска для устройства.</span><span class="sxs-lookup"><span data-stu-id="b8d84-306">The risk score for the  device.</span></span> | <span data-ttu-id="b8d84-307">Высокий</span><span class="sxs-lookup"><span data-stu-id="b8d84-307">High</span></span>
<span data-ttu-id="b8d84-308">entities</span><span class="sxs-lookup"><span data-stu-id="b8d84-308">entities</span></span> | <span data-ttu-id="b8d84-309">Все сущности, которые были определены как часть или связанные с заданным оповещением.</span><span class="sxs-lookup"><span data-stu-id="b8d84-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="b8d84-310">\[\] (см. сведения о полях суностей ниже)</span><span class="sxs-lookup"><span data-stu-id="b8d84-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="b8d84-311">Формат сущности</span><span class="sxs-lookup"><span data-stu-id="b8d84-311">Entity Format</span></span>

<span data-ttu-id="b8d84-312">Имя поля</span><span class="sxs-lookup"><span data-stu-id="b8d84-312">Field name</span></span> | <span data-ttu-id="b8d84-313">Описание</span><span class="sxs-lookup"><span data-stu-id="b8d84-313">Description</span></span> | <span data-ttu-id="b8d84-314">Пример значения</span><span class="sxs-lookup"><span data-stu-id="b8d84-314">Example value</span></span>
-|-|-
<span data-ttu-id="b8d84-315">entityType</span><span class="sxs-lookup"><span data-stu-id="b8d84-315">entityType</span></span> | <span data-ttu-id="b8d84-316">Сущности, которые определены как часть заданного оповещения или связаны с ним.</span><span class="sxs-lookup"><span data-stu-id="b8d84-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="b8d84-317">Значения свойств: *User*, *Ip*, *URL*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="b8d84-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="b8d84-318">Пользователь</span><span class="sxs-lookup"><span data-stu-id="b8d84-318">User</span></span>
<span data-ttu-id="b8d84-319">sha1</span><span class="sxs-lookup"><span data-stu-id="b8d84-319">sha1</span></span> | <span data-ttu-id="b8d84-320">Доступно, если entityType имеет *тип File.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="b8d84-321">Hash файла для оповещений, связанных с файлом или процессом.</span><span class="sxs-lookup"><span data-stu-id="b8d84-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="b8d84-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="b8d84-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="b8d84-323">sha256</span><span class="sxs-lookup"><span data-stu-id="b8d84-323">sha256</span></span> | <span data-ttu-id="b8d84-324">Доступно, если entityType имеет *тип File.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="b8d84-325">Hash файла для оповещений, связанных с файлом или процессом.</span><span class="sxs-lookup"><span data-stu-id="b8d84-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="b8d84-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="b8d84-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="b8d84-327">fileName</span><span class="sxs-lookup"><span data-stu-id="b8d84-327">fileName</span></span> | <span data-ttu-id="b8d84-328">Доступно, если entityType имеет *тип File.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="b8d84-329">Имя файла оповещений, связанных с файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="b8d84-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="b8d84-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="b8d84-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="b8d84-331">filePath</span><span class="sxs-lookup"><span data-stu-id="b8d84-331">filePath</span></span> | <span data-ttu-id="b8d84-332">Доступно, если entityType имеет *тип File.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="b8d84-333">Путь к файлу для оповещений, связанных с файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="b8d84-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="b8d84-334">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="b8d84-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="b8d84-335">processId</span><span class="sxs-lookup"><span data-stu-id="b8d84-335">processId</span></span> | <span data-ttu-id="b8d84-336">Доступно, если entityType является *Process*.</span><span class="sxs-lookup"><span data-stu-id="b8d84-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="b8d84-337">24348</span><span class="sxs-lookup"><span data-stu-id="b8d84-337">24348</span></span>
<span data-ttu-id="b8d84-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="b8d84-338">processCommandLine</span></span> | <span data-ttu-id="b8d84-339">Доступно, если entityType — *"Процесс".*</span><span class="sxs-lookup"><span data-stu-id="b8d84-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="b8d84-340">"Ваш файл готов к загрузке \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="b8d84-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="b8d84-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="b8d84-341">processCreationTime</span></span> | <span data-ttu-id="b8d84-342">Доступно, если entityType — *"Процесс".*</span><span class="sxs-lookup"><span data-stu-id="b8d84-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="b8d84-343">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="b8d84-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="b8d84-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="b8d84-344">parentProcessId</span></span> | <span data-ttu-id="b8d84-345">Доступно, если entityType — *"Процесс".*</span><span class="sxs-lookup"><span data-stu-id="b8d84-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="b8d84-346">16840</span><span class="sxs-lookup"><span data-stu-id="b8d84-346">16840</span></span>
<span data-ttu-id="b8d84-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="b8d84-347">parentProcessCreationTime</span></span> | <span data-ttu-id="b8d84-348">Доступно, если entityType — *"Процесс".*</span><span class="sxs-lookup"><span data-stu-id="b8d84-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="b8d84-349">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="b8d84-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="b8d84-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="b8d84-350">ipAddress</span></span> | <span data-ttu-id="b8d84-351">Доступно, если entityType *имеет ip.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="b8d84-352">IP-адрес для оповещений, связанных с сетевыми событиями, такими как *связь с вредоносным сетевым адресом.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="b8d84-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="b8d84-353">62.216.203.204</span></span>
<span data-ttu-id="b8d84-354">url</span><span class="sxs-lookup"><span data-stu-id="b8d84-354">url</span></span> | <span data-ttu-id="b8d84-355">Доступно, если entityType имеет *URL-адрес.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="b8d84-356">URL-адрес оповещений, связанных с сетевыми событиями, например, *"Связь с вредоносным сетевым пунктом назначения".*</span><span class="sxs-lookup"><span data-stu-id="b8d84-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="b8d84-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="b8d84-357">down.esales360.cn</span></span>
<span data-ttu-id="b8d84-358">accountName</span><span class="sxs-lookup"><span data-stu-id="b8d84-358">accountName</span></span> | <span data-ttu-id="b8d84-359">Доступно, если entityType — *пользователь.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="b8d84-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="b8d84-360">testUser2</span></span>
<span data-ttu-id="b8d84-361">domainName</span><span class="sxs-lookup"><span data-stu-id="b8d84-361">domainName</span></span> | <span data-ttu-id="b8d84-362">Доступно, если entityType — *пользователь.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="b8d84-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="b8d84-363">europe.corp.contoso</span></span>
<span data-ttu-id="b8d84-364">userSid</span><span class="sxs-lookup"><span data-stu-id="b8d84-364">userSid</span></span> | <span data-ttu-id="b8d84-365">Доступно, если entityType — *пользователь.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="b8d84-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="b8d84-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="b8d84-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="b8d84-367">aadUserId</span></span> | <span data-ttu-id="b8d84-368">Доступно, если entityType — *пользователь.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="b8d84-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="b8d84-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="b8d84-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="b8d84-370">userPrincipalName</span></span> | <span data-ttu-id="b8d84-371">Доступно, если entityType —  /  / *mailMessage* почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="b8d84-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="b8d84-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8d84-372">testUser2@contoso.com</span></span>
<span data-ttu-id="b8d84-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="b8d84-373">mailboxDisplayName</span></span> | <span data-ttu-id="b8d84-374">Доступно, если entityType — *MailBox.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="b8d84-375">test User2</span><span class="sxs-lookup"><span data-stu-id="b8d84-375">test User2</span></span>
<span data-ttu-id="b8d84-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="b8d84-376">mailboxAddress</span></span> | <span data-ttu-id="b8d84-377">Доступно, если entityType —  /  / *mailMessage* почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="b8d84-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="b8d84-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8d84-378">testUser2@contoso.com</span></span>
<span data-ttu-id="b8d84-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="b8d84-379">clusterBy</span></span> | <span data-ttu-id="b8d84-380">Доступно, если entityType — *MailCluster.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="b8d84-381">Тема; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="b8d84-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="b8d84-382">sender</span><span class="sxs-lookup"><span data-stu-id="b8d84-382">sender</span></span> | <span data-ttu-id="b8d84-383">Доступно, если entityType —  /  / *mailMessage* почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="b8d84-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="b8d84-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="b8d84-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="b8d84-385">получатель;</span><span class="sxs-lookup"><span data-stu-id="b8d84-385">recipient</span></span> | <span data-ttu-id="b8d84-386">Доступно, если entityType — *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="b8d84-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8d84-387">testUser2@contoso.com</span></span>
<span data-ttu-id="b8d84-388">subject</span><span class="sxs-lookup"><span data-stu-id="b8d84-388">subject</span></span> | <span data-ttu-id="b8d84-389">Доступно, если entityType — *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="b8d84-390">\[ВНЕШНЕЕ \] внимание</span><span class="sxs-lookup"><span data-stu-id="b8d84-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="b8d84-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="b8d84-391">deliveryAction</span></span> | <span data-ttu-id="b8d84-392">Доступно, если entityType — *MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="b8d84-393">Доставлено</span><span class="sxs-lookup"><span data-stu-id="b8d84-393">Delivered</span></span>
<span data-ttu-id="b8d84-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="b8d84-394">securityGroupId</span></span> | <span data-ttu-id="b8d84-395">Доступно, если entityType имеет *тип SecurityGroup.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="b8d84-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="b8d84-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="b8d84-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="b8d84-397">securityGroupName</span></span> | <span data-ttu-id="b8d84-398">Доступно, если entityType имеет *тип SecurityGroup.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="b8d84-399">Операторы конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="b8d84-399">Network Configuration Operators</span></span>
<span data-ttu-id="b8d84-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="b8d84-400">registryHive</span></span> | <span data-ttu-id="b8d84-401">Доступно, если entityType имеет *тип Registry.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="b8d84-402">ЛОКАЛЬНЫЙ КОМПЬЮТЕР HKEY \_ \_</span><span class="sxs-lookup"><span data-stu-id="b8d84-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="b8d84-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="b8d84-403">registryKey</span></span> | <span data-ttu-id="b8d84-404">Доступно, если entityType имеет *тип Registry.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="b8d84-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="b8d84-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="b8d84-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="b8d84-406">registryValueType</span></span> | <span data-ttu-id="b8d84-407">Доступно, если entityType имеет *тип Registry.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="b8d84-408">String</span><span class="sxs-lookup"><span data-stu-id="b8d84-408">String</span></span>
<span data-ttu-id="b8d84-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="b8d84-409">registryValue</span></span> | <span data-ttu-id="b8d84-410">Доступно, если entityType имеет *тип Registry.*</span><span class="sxs-lookup"><span data-stu-id="b8d84-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="b8d84-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="b8d84-411">31-00-00-00</span></span>
<span data-ttu-id="b8d84-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="b8d84-412">deviceId</span></span> | <span data-ttu-id="b8d84-413">ИД устройства, связанного с сущностью( если он имеется).</span><span class="sxs-lookup"><span data-stu-id="b8d84-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="b8d84-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="b8d84-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="b8d84-415">Пример</span><span class="sxs-lookup"><span data-stu-id="b8d84-415">Example</span></span>

<span data-ttu-id="b8d84-416">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="b8d84-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="b8d84-417">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="b8d84-417">**Response**</span></span>

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="b8d84-418">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b8d84-418">Related articles</span></span>

- [<span data-ttu-id="b8d84-419">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8d84-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="b8d84-420">Узнайте об ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="b8d84-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="b8d84-421">Коды ошибок</span><span class="sxs-lookup"><span data-stu-id="b8d84-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="b8d84-422">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="b8d84-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b8d84-423">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="b8d84-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="b8d84-424">Обновление API инцидентов</span><span class="sxs-lookup"><span data-stu-id="b8d84-424">Update incident API</span></span>](api-update-incidents.md)
