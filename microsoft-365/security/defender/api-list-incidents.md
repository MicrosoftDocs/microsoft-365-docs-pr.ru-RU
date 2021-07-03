---
title: API инцидентов списка в Microsoft 365 Defender
description: Узнайте, как перечислить API инцидентов в Microsoft 365 Defender
keywords: список, инциденты, инциденты, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 038879e77dfa26d82add20d043a32de117f95b19
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287835"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="1fa85-104">API инцидентов списка в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fa85-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1fa85-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1fa85-105">**Applies to:**</span></span>

- [<span data-ttu-id="1fa85-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fa85-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="1fa85-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="1fa85-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1fa85-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="1fa85-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="1fa85-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="1fa85-109">API description</span></span>

<span data-ttu-id="1fa85-110">API инцидентов списка позволяет сортировать инциденты, чтобы создать обоснованный ответ на кибербезопасность.</span><span class="sxs-lookup"><span data-stu-id="1fa85-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="1fa85-111">Он предоставляет коллекцию инцидентов, которые были помечены в сети, в диапазоне времени, указанном в политике хранения среды.</span><span class="sxs-lookup"><span data-stu-id="1fa85-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="1fa85-112">Последние инциденты отображаются в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="1fa85-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="1fa85-113">Каждый инцидент содержит массив связанных оповещений и связанных с ними сущностями.</span><span class="sxs-lookup"><span data-stu-id="1fa85-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="1fa85-114">API поддерживает следующих **операторов OData:**</span><span class="sxs-lookup"><span data-stu-id="1fa85-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="1fa85-115">`$filter` на `lastUpdateTime` `createdTime` свойствах и `status` `assignedTo` свойствах</span><span class="sxs-lookup"><span data-stu-id="1fa85-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="1fa85-116">`$top`с максимальным значением **100**</span><span class="sxs-lookup"><span data-stu-id="1fa85-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="1fa85-117">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1fa85-117">Limitations</span></span>

1. <span data-ttu-id="1fa85-118">Максимальный размер страницы **— 100 инцидентов.**</span><span class="sxs-lookup"><span data-stu-id="1fa85-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="1fa85-119">Максимальная скорость запросов — **50 вызовов в минуту** и **1500 вызовов в час.**</span><span class="sxs-lookup"><span data-stu-id="1fa85-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="1fa85-120">Разрешения</span><span class="sxs-lookup"><span data-stu-id="1fa85-120">Permissions</span></span>

<span data-ttu-id="1fa85-121">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="1fa85-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1fa85-122">Дополнительные возможности, в том числе выбор разрешений, см. в Microsoft 365 Defender [API Access Microsoft 365 Defender.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="1fa85-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="1fa85-123">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="1fa85-123">Permission type</span></span> | <span data-ttu-id="1fa85-124">Разрешение</span><span class="sxs-lookup"><span data-stu-id="1fa85-124">Permission</span></span> | <span data-ttu-id="1fa85-125">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="1fa85-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="1fa85-126">Application</span><span class="sxs-lookup"><span data-stu-id="1fa85-126">Application</span></span> | <span data-ttu-id="1fa85-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="1fa85-127">Incident.Read.All</span></span> | <span data-ttu-id="1fa85-128">Чтение всех инцидентов</span><span class="sxs-lookup"><span data-stu-id="1fa85-128">Read all incidents</span></span>
<span data-ttu-id="1fa85-129">Application</span><span class="sxs-lookup"><span data-stu-id="1fa85-129">Application</span></span> | <span data-ttu-id="1fa85-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1fa85-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="1fa85-131">Чтение и написание всех инцидентов</span><span class="sxs-lookup"><span data-stu-id="1fa85-131">Read and write all incidents</span></span>
<span data-ttu-id="1fa85-132">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="1fa85-132">Delegated (work or school account)</span></span> | <span data-ttu-id="1fa85-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="1fa85-133">Incident.Read</span></span> | <span data-ttu-id="1fa85-134">Чтение инцидентов</span><span class="sxs-lookup"><span data-stu-id="1fa85-134">Read incidents</span></span>
<span data-ttu-id="1fa85-135">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="1fa85-135">Delegated (work or school account)</span></span> | <span data-ttu-id="1fa85-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1fa85-136">Incident.ReadWrite</span></span> | <span data-ttu-id="1fa85-137">Чтение и написание инцидентов</span><span class="sxs-lookup"><span data-stu-id="1fa85-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="1fa85-138">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="1fa85-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="1fa85-139">Пользователь должен иметь разрешение просмотра инцидентов на портале.</span><span class="sxs-lookup"><span data-stu-id="1fa85-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="1fa85-140">Ответ будет включать только инциденты, с которые пользователь подвергается действию.</span><span class="sxs-lookup"><span data-stu-id="1fa85-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="1fa85-141">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="1fa85-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="1fa85-142">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="1fa85-142">Request headers</span></span>

<span data-ttu-id="1fa85-143">Имя</span><span class="sxs-lookup"><span data-stu-id="1fa85-143">Name</span></span> | <span data-ttu-id="1fa85-144">Тип</span><span class="sxs-lookup"><span data-stu-id="1fa85-144">Type</span></span> | <span data-ttu-id="1fa85-145">Описание</span><span class="sxs-lookup"><span data-stu-id="1fa85-145">Description</span></span>
-|-|-
<span data-ttu-id="1fa85-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="1fa85-146">Authorization</span></span> | <span data-ttu-id="1fa85-147">Строка</span><span class="sxs-lookup"><span data-stu-id="1fa85-147">String</span></span> | <span data-ttu-id="1fa85-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1fa85-148">Bearer {token}.</span></span> <span data-ttu-id="1fa85-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="1fa85-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="1fa85-150">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="1fa85-150">Request body</span></span>

<span data-ttu-id="1fa85-151">Нет.</span><span class="sxs-lookup"><span data-stu-id="1fa85-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="1fa85-152">Отклик</span><span class="sxs-lookup"><span data-stu-id="1fa85-152">Response</span></span>

<span data-ttu-id="1fa85-153">В случае успешной работы этот метод возвращается и список инцидентов `200 OK` в теле [](api-incident.md) отклика.</span><span class="sxs-lookup"><span data-stu-id="1fa85-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="1fa85-154">Сопоставление схемы</span><span class="sxs-lookup"><span data-stu-id="1fa85-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="1fa85-155">Метаданные инцидента</span><span class="sxs-lookup"><span data-stu-id="1fa85-155">Incident metadata</span></span>

<span data-ttu-id="1fa85-156">Имя поля</span><span class="sxs-lookup"><span data-stu-id="1fa85-156">Field name</span></span> | <span data-ttu-id="1fa85-157">Описание</span><span class="sxs-lookup"><span data-stu-id="1fa85-157">Description</span></span> | <span data-ttu-id="1fa85-158">Пример значения</span><span class="sxs-lookup"><span data-stu-id="1fa85-158">Example value</span></span>
-|-|-
<span data-ttu-id="1fa85-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="1fa85-159">incidentId</span></span> | <span data-ttu-id="1fa85-160">Уникальный идентификатор для представления инцидента</span><span class="sxs-lookup"><span data-stu-id="1fa85-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="1fa85-161">924565</span><span class="sxs-lookup"><span data-stu-id="1fa85-161">924565</span></span>
<span data-ttu-id="1fa85-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="1fa85-162">redirectIncidentId</span></span> | <span data-ttu-id="1fa85-163">Заполняется только в том случае, если инцидент сгруппировали вместе с другим инцидентом, как часть логики обработки инцидента.</span><span class="sxs-lookup"><span data-stu-id="1fa85-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="1fa85-164">924569</span><span class="sxs-lookup"><span data-stu-id="1fa85-164">924569</span></span>
<span data-ttu-id="1fa85-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="1fa85-165">incidentName</span></span> | <span data-ttu-id="1fa85-166">Строковая стоимость, доступная для каждого инцидента.</span><span class="sxs-lookup"><span data-stu-id="1fa85-166">String value available for every incident.</span></span> | <span data-ttu-id="1fa85-167">Действия программы-шантажиста.</span><span class="sxs-lookup"><span data-stu-id="1fa85-167">Ransomware activity</span></span>
<span data-ttu-id="1fa85-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="1fa85-168">createdTime</span></span> | <span data-ttu-id="1fa85-169">Время создания инцидента.</span><span class="sxs-lookup"><span data-stu-id="1fa85-169">Time when incident was first created.</span></span> | <span data-ttu-id="1fa85-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="1fa85-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="1fa85-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="1fa85-171">lastUpdateTime</span></span> | <span data-ttu-id="1fa85-172">Время последнего обновления инцидента на задней части.</span><span class="sxs-lookup"><span data-stu-id="1fa85-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="1fa85-173">Это поле можно использовать при настройке параметра запроса для диапазона времени получения инцидентов.</span><span class="sxs-lookup"><span data-stu-id="1fa85-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="1fa85-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="1fa85-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="1fa85-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="1fa85-175">assignedTo</span></span> | <span data-ttu-id="1fa85-176">Владелец инцидента или *null,* если не назначен владелец.</span><span class="sxs-lookup"><span data-stu-id="1fa85-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="1fa85-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fa85-177">secop2@contoso.com</span></span>
<span data-ttu-id="1fa85-178">classification</span><span class="sxs-lookup"><span data-stu-id="1fa85-178">classification</span></span> | <span data-ttu-id="1fa85-179">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="1fa85-179">The specification for the incident.</span></span> <span data-ttu-id="1fa85-180">Значения свойств: *Неизвестный,* *FalsePositive,* *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="1fa85-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="1fa85-181">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="1fa85-181">Unknown</span></span>
<span data-ttu-id="1fa85-182">определение</span><span class="sxs-lookup"><span data-stu-id="1fa85-182">determination</span></span> | <span data-ttu-id="1fa85-183">Указывает определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="1fa85-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="1fa85-184">Значения свойств: *NotAvailable*, *Apt*, *Вредоносные* программы , *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Другие*</span><span class="sxs-lookup"><span data-stu-id="1fa85-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="1fa85-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="1fa85-185">NotAvailable</span></span>
<span data-ttu-id="1fa85-186">status</span><span class="sxs-lookup"><span data-stu-id="1fa85-186">status</span></span> | <span data-ttu-id="1fa85-187">Классифицировать инциденты *(как Active* или *Resolved).*</span><span class="sxs-lookup"><span data-stu-id="1fa85-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="1fa85-188">Это поможет вам организовать и управлять реагированием на инциденты.</span><span class="sxs-lookup"><span data-stu-id="1fa85-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="1fa85-189">Активное</span><span class="sxs-lookup"><span data-stu-id="1fa85-189">Active</span></span>
<span data-ttu-id="1fa85-190">severity</span><span class="sxs-lookup"><span data-stu-id="1fa85-190">severity</span></span> | <span data-ttu-id="1fa85-191">Указывает возможное влияние на активы.</span><span class="sxs-lookup"><span data-stu-id="1fa85-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="1fa85-192">Чем больше серьезность, тем больше влияние.</span><span class="sxs-lookup"><span data-stu-id="1fa85-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="1fa85-193">Как правило, элементы с более высокой степенью серьезности требуют непосредственного внимания.</span><span class="sxs-lookup"><span data-stu-id="1fa85-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="1fa85-194">Одно из следующих значений: *Informational,* *Low*, \*Medium и *High*.</span><span class="sxs-lookup"><span data-stu-id="1fa85-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="1fa85-195">Средняя</span><span class="sxs-lookup"><span data-stu-id="1fa85-195">Medium</span></span>
<span data-ttu-id="1fa85-196">tags</span><span class="sxs-lookup"><span data-stu-id="1fa85-196">tags</span></span> | <span data-ttu-id="1fa85-197">Массив пользовательских тегов, связанных с инцидентом, например для флага группы инцидентов с общей характеристикой.</span><span class="sxs-lookup"><span data-stu-id="1fa85-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="1fa85-198">comments</span><span class="sxs-lookup"><span data-stu-id="1fa85-198">comments</span></span> | <span data-ttu-id="1fa85-199">Массив комментариев, созданных секопами при управлении инцидентом, например дополнительные сведения о выборе классификации.</span><span class="sxs-lookup"><span data-stu-id="1fa85-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="1fa85-200">оповещения</span><span class="sxs-lookup"><span data-stu-id="1fa85-200">alerts</span></span> | <span data-ttu-id="1fa85-201">Массив, содержащий все оповещения, связанные с инцидентом, а также другие сведения, такие как серьезность, объекты, которые были вовлечены в оповещение, и источник оповещений.</span><span class="sxs-lookup"><span data-stu-id="1fa85-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="1fa85-202">\[\] (см. сведения о полях оповещений ниже)</span><span class="sxs-lookup"><span data-stu-id="1fa85-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="1fa85-203">Оповещения метаданных</span><span class="sxs-lookup"><span data-stu-id="1fa85-203">Alerts metadata</span></span>

<span data-ttu-id="1fa85-204">Имя поля</span><span class="sxs-lookup"><span data-stu-id="1fa85-204">Field name</span></span> | <span data-ttu-id="1fa85-205">Описание</span><span class="sxs-lookup"><span data-stu-id="1fa85-205">Description</span></span> | <span data-ttu-id="1fa85-206">Пример значения</span><span class="sxs-lookup"><span data-stu-id="1fa85-206">Example value</span></span>
-|-|-
<span data-ttu-id="1fa85-207">alertId</span><span class="sxs-lookup"><span data-stu-id="1fa85-207">alertId</span></span> | <span data-ttu-id="1fa85-208">Уникальный идентификатор для представления оповещений</span><span class="sxs-lookup"><span data-stu-id="1fa85-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="1fa85-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="1fa85-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="1fa85-210">incidentId</span><span class="sxs-lookup"><span data-stu-id="1fa85-210">incidentId</span></span> | <span data-ttu-id="1fa85-211">Уникальный идентификатор для представления инцидента, с котором связано это оповещение</span><span class="sxs-lookup"><span data-stu-id="1fa85-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="1fa85-212">924565</span><span class="sxs-lookup"><span data-stu-id="1fa85-212">924565</span></span>
<span data-ttu-id="1fa85-213">serviceSource</span><span class="sxs-lookup"><span data-stu-id="1fa85-213">serviceSource</span></span> | <span data-ttu-id="1fa85-214">Служба, откуда исходит оповещение, например Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity или Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="1fa85-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="1fa85-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="1fa85-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="1fa85-216">creationTime</span><span class="sxs-lookup"><span data-stu-id="1fa85-216">creationTime</span></span> | <span data-ttu-id="1fa85-217">Время создания оповещений.</span><span class="sxs-lookup"><span data-stu-id="1fa85-217">Time when alert was first created.</span></span> | <span data-ttu-id="1fa85-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="1fa85-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="1fa85-219">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="1fa85-219">lastUpdatedTime</span></span> | <span data-ttu-id="1fa85-220">Время последнего обновления оповещений в задней части.</span><span class="sxs-lookup"><span data-stu-id="1fa85-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="1fa85-221">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="1fa85-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="1fa85-222">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="1fa85-222">resolvedTime</span></span> | <span data-ttu-id="1fa85-223">Время, когда оповещение было разрешено.</span><span class="sxs-lookup"><span data-stu-id="1fa85-223">Time when alert was resolved.</span></span> | <span data-ttu-id="1fa85-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="1fa85-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="1fa85-225">firstActivity</span><span class="sxs-lookup"><span data-stu-id="1fa85-225">firstActivity</span></span> | <span data-ttu-id="1fa85-226">Время, когда оповещение впервые сообщило об обновлении активности в задней части.</span><span class="sxs-lookup"><span data-stu-id="1fa85-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="1fa85-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="1fa85-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="1fa85-228">title</span><span class="sxs-lookup"><span data-stu-id="1fa85-228">title</span></span> | <span data-ttu-id="1fa85-229">Краткое определение строки, доступной для каждого оповещения.</span><span class="sxs-lookup"><span data-stu-id="1fa85-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="1fa85-230">Действия программы-шантажиста.</span><span class="sxs-lookup"><span data-stu-id="1fa85-230">Ransomware activity</span></span>
<span data-ttu-id="1fa85-231">description</span><span class="sxs-lookup"><span data-stu-id="1fa85-231">description</span></span> | <span data-ttu-id="1fa85-232">Строковая величина, описываемая каждое оповещение.</span><span class="sxs-lookup"><span data-stu-id="1fa85-232">String value describing each alert.</span></span> | <span data-ttu-id="1fa85-233">Пользователь Test User2 (testUser2@contoso.com) манипулировал 99 файлами с несколькими расширениями, заканчивающийся необычным *расширением herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="1fa85-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="1fa85-234">Это необычное количество манипуляций с файлами и указывает на потенциальную атаку вымогателей.</span><span class="sxs-lookup"><span data-stu-id="1fa85-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="1fa85-235">category</span><span class="sxs-lookup"><span data-stu-id="1fa85-235">category</span></span> | <span data-ttu-id="1fa85-236">Визуальное и числовое представление о том, как далеко продвинулась атака по цепочке убийств.</span><span class="sxs-lookup"><span data-stu-id="1fa85-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="1fa85-237">Согласовано с [структурой ATT MITRE&CK™](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="1fa85-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="1fa85-238">Влияние</span><span class="sxs-lookup"><span data-stu-id="1fa85-238">Impact</span></span>
<span data-ttu-id="1fa85-239">status</span><span class="sxs-lookup"><span data-stu-id="1fa85-239">status</span></span> | <span data-ttu-id="1fa85-240">Классификация оповещений *(как New,* *Active* или *Resolved).*</span><span class="sxs-lookup"><span data-stu-id="1fa85-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="1fa85-241">Это может помочь вам организовать и управлять вашим ответом на оповещения.</span><span class="sxs-lookup"><span data-stu-id="1fa85-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="1fa85-242">Новое</span><span class="sxs-lookup"><span data-stu-id="1fa85-242">New</span></span>
<span data-ttu-id="1fa85-243">severity</span><span class="sxs-lookup"><span data-stu-id="1fa85-243">severity</span></span> | <span data-ttu-id="1fa85-244">Указывает возможное влияние на активы.</span><span class="sxs-lookup"><span data-stu-id="1fa85-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="1fa85-245">Чем больше серьезность, тем больше влияние.</span><span class="sxs-lookup"><span data-stu-id="1fa85-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="1fa85-246">Как правило, элементы с более высокой степенью серьезности требуют непосредственного внимания.</span><span class="sxs-lookup"><span data-stu-id="1fa85-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="1fa85-247">Одно из следующих значений: *Informational,* *Low*, \*Medium и *High*.</span><span class="sxs-lookup"><span data-stu-id="1fa85-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="1fa85-248">Средняя</span><span class="sxs-lookup"><span data-stu-id="1fa85-248">Medium</span></span>
<span data-ttu-id="1fa85-249">investigationId</span><span class="sxs-lookup"><span data-stu-id="1fa85-249">investigationId</span></span> | <span data-ttu-id="1fa85-250">Автоматический ИД расследования, срабатываем этим оповещением.</span><span class="sxs-lookup"><span data-stu-id="1fa85-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="1fa85-251">1234</span><span class="sxs-lookup"><span data-stu-id="1fa85-251">1234</span></span>
<span data-ttu-id="1fa85-252">investigationState</span><span class="sxs-lookup"><span data-stu-id="1fa85-252">investigationState</span></span> | <span data-ttu-id="1fa85-253">Сведения о текущем состоянии расследования.</span><span class="sxs-lookup"><span data-stu-id="1fa85-253">Information on the investigation's current status.</span></span> <span data-ttu-id="1fa85-254">Одно из следующих *значений:* Unknown *,* Terminated , *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedAlertType*, *SuppressedAlert*. </span><span class="sxs-lookup"><span data-stu-id="1fa85-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="1fa85-255">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="1fa85-255">UnsupportedAlertType</span></span>
<span data-ttu-id="1fa85-256">classification</span><span class="sxs-lookup"><span data-stu-id="1fa85-256">classification</span></span> | <span data-ttu-id="1fa85-257">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="1fa85-257">The specification for the incident.</span></span> <span data-ttu-id="1fa85-258">Значения свойств: *Неизвестный,* *FalsePositive,* *TruePositive* или *null*</span><span class="sxs-lookup"><span data-stu-id="1fa85-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="1fa85-259">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="1fa85-259">Unknown</span></span>
<span data-ttu-id="1fa85-260">определение</span><span class="sxs-lookup"><span data-stu-id="1fa85-260">determination</span></span> | <span data-ttu-id="1fa85-261">Указывает определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="1fa85-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="1fa85-262">Значения свойств: *NotAvailable*, *Apt*, *Вредоносные* программы , *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Другие* или  *null*</span><span class="sxs-lookup"><span data-stu-id="1fa85-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="1fa85-263">Apt</span><span class="sxs-lookup"><span data-stu-id="1fa85-263">Apt</span></span>
<span data-ttu-id="1fa85-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="1fa85-264">assignedTo</span></span> | <span data-ttu-id="1fa85-265">Владелец инцидента или *null,* если не назначен владелец.</span><span class="sxs-lookup"><span data-stu-id="1fa85-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="1fa85-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fa85-266">secop2@contoso.com</span></span>
<span data-ttu-id="1fa85-267">actorName</span><span class="sxs-lookup"><span data-stu-id="1fa85-267">actorName</span></span> | <span data-ttu-id="1fa85-268">Группа действий, если таково, связанная с этим оповещением.</span><span class="sxs-lookup"><span data-stu-id="1fa85-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="1fa85-269">BORON</span><span class="sxs-lookup"><span data-stu-id="1fa85-269">BORON</span></span>
<span data-ttu-id="1fa85-270">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="1fa85-270">threatFamilyName</span></span> | <span data-ttu-id="1fa85-271">Семейство угроз, связанное с этим оповещением.</span><span class="sxs-lookup"><span data-stu-id="1fa85-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="1fa85-272">null</span><span class="sxs-lookup"><span data-stu-id="1fa85-272">null</span></span>
<span data-ttu-id="1fa85-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="1fa85-273">mitreTechniques</span></span> | <span data-ttu-id="1fa85-274">Методы атаки, в соответствие с структурой [ATT MITRE&CK](https://attack.mitre.org/)™.</span><span class="sxs-lookup"><span data-stu-id="1fa85-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="1fa85-275">устройства</span><span class="sxs-lookup"><span data-stu-id="1fa85-275">devices</span></span> | <span data-ttu-id="1fa85-276">Все устройства, на которых были отправлены оповещения, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="1fa85-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="1fa85-277">\[\] (см. сведения о полях сущности ниже)</span><span class="sxs-lookup"><span data-stu-id="1fa85-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="1fa85-278">Формат устройства</span><span class="sxs-lookup"><span data-stu-id="1fa85-278">Device format</span></span>

<span data-ttu-id="1fa85-279">Имя поля</span><span class="sxs-lookup"><span data-stu-id="1fa85-279">Field name</span></span> | <span data-ttu-id="1fa85-280">Описание</span><span class="sxs-lookup"><span data-stu-id="1fa85-280">Description</span></span> | <span data-ttu-id="1fa85-281">Пример значения</span><span class="sxs-lookup"><span data-stu-id="1fa85-281">Example value</span></span>
-|-|-
<span data-ttu-id="1fa85-282">DeviceId</span><span class="sxs-lookup"><span data-stu-id="1fa85-282">DeviceId</span></span> | <span data-ttu-id="1fa85-283">ID устройства, указанный в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1fa85-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="1fa85-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="1fa85-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="1fa85-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="1fa85-285">aadDeviceId</span></span> |  <span data-ttu-id="1fa85-286">ID устройства, указанный в [Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="1fa85-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="1fa85-287">Доступно только для устройств, присоединимых к домену.</span><span class="sxs-lookup"><span data-stu-id="1fa85-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="1fa85-288">null</span><span class="sxs-lookup"><span data-stu-id="1fa85-288">null</span></span>
<span data-ttu-id="1fa85-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="1fa85-289">deviceDnsName</span></span> | <span data-ttu-id="1fa85-290">Полное доменное имя для устройства.</span><span class="sxs-lookup"><span data-stu-id="1fa85-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="1fa85-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fa85-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="1fa85-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="1fa85-292">osPlatform</span></span> | <span data-ttu-id="1fa85-293">Платформа ОС, на которой работает устройство.</span><span class="sxs-lookup"><span data-stu-id="1fa85-293">The OS platform the device is running.</span></span>| <span data-ttu-id="1fa85-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="1fa85-294">WindowsServer2016</span></span>
<span data-ttu-id="1fa85-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="1fa85-295">osBuild</span></span> | <span data-ttu-id="1fa85-296">Версия сборки для ОС, запущенная устройством.</span><span class="sxs-lookup"><span data-stu-id="1fa85-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="1fa85-297">14393</span><span class="sxs-lookup"><span data-stu-id="1fa85-297">14393</span></span>
<span data-ttu-id="1fa85-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="1fa85-298">rbacGroupName</span></span> | <span data-ttu-id="1fa85-299">Группа [управления доступом](/azure/role-based-access-control/overview) на основе ролей (RBAC), связанная с устройством.</span><span class="sxs-lookup"><span data-stu-id="1fa85-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="1fa85-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="1fa85-300">WDATP-Ring0</span></span>
<span data-ttu-id="1fa85-301">firstSeen</span><span class="sxs-lookup"><span data-stu-id="1fa85-301">firstSeen</span></span> | <span data-ttu-id="1fa85-302">Время, когда устройство было впервые замечено.</span><span class="sxs-lookup"><span data-stu-id="1fa85-302">Time when device was first seen.</span></span> | <span data-ttu-id="1fa85-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="1fa85-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="1fa85-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="1fa85-304">healthStatus</span></span> | <span data-ttu-id="1fa85-305">Состояние здоровья устройства.</span><span class="sxs-lookup"><span data-stu-id="1fa85-305">The health state of the device.</span></span> | <span data-ttu-id="1fa85-306">Активное</span><span class="sxs-lookup"><span data-stu-id="1fa85-306">Active</span></span>
<span data-ttu-id="1fa85-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="1fa85-307">riskScore</span></span> | <span data-ttu-id="1fa85-308">Оценка риска для устройства.</span><span class="sxs-lookup"><span data-stu-id="1fa85-308">The risk score for the  device.</span></span> | <span data-ttu-id="1fa85-309">Высокая</span><span class="sxs-lookup"><span data-stu-id="1fa85-309">High</span></span>
<span data-ttu-id="1fa85-310">сущности</span><span class="sxs-lookup"><span data-stu-id="1fa85-310">entities</span></span> | <span data-ttu-id="1fa85-311">Все сущностями, которые были идентифицированы как часть или связанные с данным оповещением.</span><span class="sxs-lookup"><span data-stu-id="1fa85-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="1fa85-312">\[\] (см. сведения о полях сущности ниже)</span><span class="sxs-lookup"><span data-stu-id="1fa85-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="1fa85-313">Формат сущности</span><span class="sxs-lookup"><span data-stu-id="1fa85-313">Entity Format</span></span>

<span data-ttu-id="1fa85-314">Имя поля</span><span class="sxs-lookup"><span data-stu-id="1fa85-314">Field name</span></span> | <span data-ttu-id="1fa85-315">Описание</span><span class="sxs-lookup"><span data-stu-id="1fa85-315">Description</span></span> | <span data-ttu-id="1fa85-316">Пример значения</span><span class="sxs-lookup"><span data-stu-id="1fa85-316">Example value</span></span>
-|-|-
<span data-ttu-id="1fa85-317">entityType</span><span class="sxs-lookup"><span data-stu-id="1fa85-317">entityType</span></span> | <span data-ttu-id="1fa85-318">Объекты, которые были идентифицированы как часть или связанные с данным оповещением.</span><span class="sxs-lookup"><span data-stu-id="1fa85-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="1fa85-319">Значения *свойств:* Пользователь , *Ip*, *URL*, *файл*, *процесс* *,* Почтовый ящик , *MailMessage*, *MailCluster*, *реестр*</span><span class="sxs-lookup"><span data-stu-id="1fa85-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="1fa85-320">User</span><span class="sxs-lookup"><span data-stu-id="1fa85-320">User</span></span>
<span data-ttu-id="1fa85-321">sha1</span><span class="sxs-lookup"><span data-stu-id="1fa85-321">sha1</span></span> | <span data-ttu-id="1fa85-322">Доступно, если entityType — *файл.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="1fa85-323">Hash файла для оповещений, связанных с файлом или процессом.</span><span class="sxs-lookup"><span data-stu-id="1fa85-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="1fa85-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6ddd</span><span class="sxs-lookup"><span data-stu-id="1fa85-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="1fa85-325">sha256</span><span class="sxs-lookup"><span data-stu-id="1fa85-325">sha256</span></span> | <span data-ttu-id="1fa85-326">Доступно, если entityType — *файл.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="1fa85-327">Hash файла для оповещений, связанных с файлом или процессом.</span><span class="sxs-lookup"><span data-stu-id="1fa85-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="1fa85-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="1fa85-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="1fa85-329">fileName</span><span class="sxs-lookup"><span data-stu-id="1fa85-329">fileName</span></span> | <span data-ttu-id="1fa85-330">Доступно, если entityType — *файл.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="1fa85-331">Имя файла для оповещений, связанных с файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="1fa85-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="1fa85-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="1fa85-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="1fa85-333">filePath</span><span class="sxs-lookup"><span data-stu-id="1fa85-333">filePath</span></span> | <span data-ttu-id="1fa85-334">Доступно, если entityType — *файл.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="1fa85-335">Путь к файлам для оповещений, связанных с файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="1fa85-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="1fa85-336">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="1fa85-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="1fa85-337">processId</span><span class="sxs-lookup"><span data-stu-id="1fa85-337">processId</span></span> | <span data-ttu-id="1fa85-338">Доступно, если entityType — *процесс.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="1fa85-339">24348</span><span class="sxs-lookup"><span data-stu-id="1fa85-339">24348</span></span>
<span data-ttu-id="1fa85-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="1fa85-340">processCommandLine</span></span> | <span data-ttu-id="1fa85-341">Доступно, если entityType — *процесс.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="1fa85-342">"Файл готов к загрузке \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="1fa85-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="1fa85-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="1fa85-343">processCreationTime</span></span> | <span data-ttu-id="1fa85-344">Доступно, если entityType — *процесс.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="1fa85-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="1fa85-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="1fa85-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="1fa85-346">parentProcessId</span></span> | <span data-ttu-id="1fa85-347">Доступно, если entityType — *процесс.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="1fa85-348">16840</span><span class="sxs-lookup"><span data-stu-id="1fa85-348">16840</span></span>
<span data-ttu-id="1fa85-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="1fa85-349">parentProcessCreationTime</span></span> | <span data-ttu-id="1fa85-350">Доступно, если entityType — *процесс.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="1fa85-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="1fa85-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="1fa85-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="1fa85-352">ipAddress</span></span> | <span data-ttu-id="1fa85-353">Доступно, если entityType *— ip.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="1fa85-354">IP-адрес для оповещений, связанных с сетевыми событиями, такими как *связь с вредоносным сетевым назначением.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="1fa85-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="1fa85-355">62.216.203.204</span></span>
<span data-ttu-id="1fa85-356">url</span><span class="sxs-lookup"><span data-stu-id="1fa85-356">url</span></span> | <span data-ttu-id="1fa85-357">Доступно, если entityType *— url.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="1fa85-358">URL-адрес для оповещений, связанных с сетевыми событиями, такими как Сообщение *с вредоносным сетевым назначением.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="1fa85-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="1fa85-359">down.esales360.cn</span></span>
<span data-ttu-id="1fa85-360">имя учетной записи</span><span class="sxs-lookup"><span data-stu-id="1fa85-360">accountName</span></span> | <span data-ttu-id="1fa85-361">Доступно, если entityType — *пользователь.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="1fa85-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="1fa85-362">testUser2</span></span>
<span data-ttu-id="1fa85-363">domainName</span><span class="sxs-lookup"><span data-stu-id="1fa85-363">domainName</span></span> | <span data-ttu-id="1fa85-364">Доступно, если entityType — *пользователь.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="1fa85-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="1fa85-365">europe.corp.contoso</span></span>
<span data-ttu-id="1fa85-366">userSid</span><span class="sxs-lookup"><span data-stu-id="1fa85-366">userSid</span></span> | <span data-ttu-id="1fa85-367">Доступно, если entityType — *пользователь.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="1fa85-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="1fa85-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="1fa85-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="1fa85-369">aadUserId</span></span> | <span data-ttu-id="1fa85-370">Доступно, если entityType — *пользователь.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="1fa85-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="1fa85-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="1fa85-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="1fa85-372">userPrincipalName</span></span> | <span data-ttu-id="1fa85-373">Доступно, если entityType *— это почтовый* / *ящик* / *пользователя MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="1fa85-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fa85-374">testUser2@contoso.com</span></span>
<span data-ttu-id="1fa85-375">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="1fa85-375">mailboxDisplayName</span></span> | <span data-ttu-id="1fa85-376">Доступно, если entityType — *это MailBox.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="1fa85-377">test User2</span><span class="sxs-lookup"><span data-stu-id="1fa85-377">test User2</span></span>
<span data-ttu-id="1fa85-378">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="1fa85-378">mailboxAddress</span></span> | <span data-ttu-id="1fa85-379">Доступно, если entityType *— это почтовый* / *ящик* / *пользователя MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="1fa85-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fa85-380">testUser2@contoso.com</span></span>
<span data-ttu-id="1fa85-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="1fa85-381">clusterBy</span></span> | <span data-ttu-id="1fa85-382">Доступно, если entityType *— это MailCluster.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="1fa85-383">Subject; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="1fa85-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="1fa85-384">sender</span><span class="sxs-lookup"><span data-stu-id="1fa85-384">sender</span></span> | <span data-ttu-id="1fa85-385">Доступно, если entityType *— это почтовый* / *ящик* / *пользователя MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="1fa85-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="1fa85-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="1fa85-387">получатель;</span><span class="sxs-lookup"><span data-stu-id="1fa85-387">recipient</span></span> | <span data-ttu-id="1fa85-388">Доступно, если entityType *— это MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="1fa85-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fa85-389">testUser2@contoso.com</span></span>
<span data-ttu-id="1fa85-390">subject</span><span class="sxs-lookup"><span data-stu-id="1fa85-390">subject</span></span> | <span data-ttu-id="1fa85-391">Доступно, если entityType *— это MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="1fa85-392">\[ВНЕШНЕЕ \] внимание</span><span class="sxs-lookup"><span data-stu-id="1fa85-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="1fa85-393">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="1fa85-393">deliveryAction</span></span> | <span data-ttu-id="1fa85-394">Доступно, если entityType *— это MailMessage.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="1fa85-395">Доставлено</span><span class="sxs-lookup"><span data-stu-id="1fa85-395">Delivered</span></span>
<span data-ttu-id="1fa85-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="1fa85-396">securityGroupId</span></span> | <span data-ttu-id="1fa85-397">Доступно, если entityType — *это SecurityGroup.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="1fa85-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="1fa85-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="1fa85-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="1fa85-399">securityGroupName</span></span> | <span data-ttu-id="1fa85-400">Доступно, если entityType — *это SecurityGroup.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="1fa85-401">Операторы конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="1fa85-401">Network Configuration Operators</span></span>
<span data-ttu-id="1fa85-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="1fa85-402">registryHive</span></span> | <span data-ttu-id="1fa85-403">Доступно, если entityType *является реестром.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="1fa85-404">ЛОКАЛЬНЫЙ КОМПЬЮТЕР \_ HKEY \_</span><span class="sxs-lookup"><span data-stu-id="1fa85-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="1fa85-405">registryKey</span><span class="sxs-lookup"><span data-stu-id="1fa85-405">registryKey</span></span> | <span data-ttu-id="1fa85-406">Доступно, если entityType *является реестром.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="1fa85-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="1fa85-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="1fa85-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="1fa85-408">registryValueType</span></span> | <span data-ttu-id="1fa85-409">Доступно, если entityType *является реестром.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="1fa85-410">Строка</span><span class="sxs-lookup"><span data-stu-id="1fa85-410">String</span></span>
<span data-ttu-id="1fa85-411">registryValue</span><span class="sxs-lookup"><span data-stu-id="1fa85-411">registryValue</span></span> | <span data-ttu-id="1fa85-412">Доступно, если entityType *является реестром.*</span><span class="sxs-lookup"><span data-stu-id="1fa85-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="1fa85-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="1fa85-413">31-00-00-00</span></span>
<span data-ttu-id="1fa85-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="1fa85-414">deviceId</span></span> | <span data-ttu-id="1fa85-415">ID, если таково, устройства, связанного с объектом.</span><span class="sxs-lookup"><span data-stu-id="1fa85-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="1fa85-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="1fa85-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="1fa85-417">Пример</span><span class="sxs-lookup"><span data-stu-id="1fa85-417">Example</span></span>

### <a name="request"></a><span data-ttu-id="1fa85-418">Запрос</span><span class="sxs-lookup"><span data-stu-id="1fa85-418">Request</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

### <a name="response"></a><span data-ttu-id="1fa85-419">Отклик</span><span class="sxs-lookup"><span data-stu-id="1fa85-419">Response</span></span>

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
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
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
            "comments": [],
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
            "comments": [],
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

## <a name="related-articles"></a><span data-ttu-id="1fa85-420">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="1fa85-420">Related articles</span></span>

- [<span data-ttu-id="1fa85-421">Доступ к Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="1fa85-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="1fa85-422">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="1fa85-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="1fa85-423">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="1fa85-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="1fa85-424">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="1fa85-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1fa85-425">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="1fa85-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="1fa85-426">Обновление API инцидента</span><span class="sxs-lookup"><span data-stu-id="1fa85-426">Update incident API</span></span>](api-update-incidents.md)
