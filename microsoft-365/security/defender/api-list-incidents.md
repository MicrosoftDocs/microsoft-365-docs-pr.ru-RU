---
title: Список инцидентов API в Microsoft 365 Defender
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
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572157"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="618eb-104">Список инцидентов API в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="618eb-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="618eb-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="618eb-105">**Applies to:**</span></span>

- <span data-ttu-id="618eb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="618eb-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="618eb-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="618eb-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="618eb-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="618eb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="618eb-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="618eb-109">API description</span></span>

<span data-ttu-id="618eb-110">API списков инцидентов позволяет сортировать инциденты для создания обоснованных мер по кибербезопасности.</span><span class="sxs-lookup"><span data-stu-id="618eb-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="618eb-111">Он предоставляет набор инцидентов, которые были отмечены в вашей сети, в течение определенного времени в политике удержания среды.</span><span class="sxs-lookup"><span data-stu-id="618eb-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="618eb-112">Последние инциденты отображаются в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="618eb-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="618eb-113">Каждый инцидент содержит массив связанных оповещений и связанных с ними сущностей.</span><span class="sxs-lookup"><span data-stu-id="618eb-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="618eb-114">API поддерживает следующих **операторов OData:**</span><span class="sxs-lookup"><span data-stu-id="618eb-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="618eb-115">`$filter` на `lastUpdateTime` `createdTime` , `status` , и `assignedTo` свойства</span><span class="sxs-lookup"><span data-stu-id="618eb-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="618eb-116">`$top`, с максимальным значением **100**</span><span class="sxs-lookup"><span data-stu-id="618eb-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="618eb-117">Ограничения</span><span class="sxs-lookup"><span data-stu-id="618eb-117">Limitations</span></span>

1. <span data-ttu-id="618eb-118">Максимальный размер страницы **составляет 100 инцидентов.**</span><span class="sxs-lookup"><span data-stu-id="618eb-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="618eb-119">Максимальная скорость запросов **составляет 50 звонков в минуту** **и 1500 звонков в час.**</span><span class="sxs-lookup"><span data-stu-id="618eb-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="618eb-120">Разрешения</span><span class="sxs-lookup"><span data-stu-id="618eb-120">Permissions</span></span>

<span data-ttu-id="618eb-121">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="618eb-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="618eb-122">Чтобы узнать больше, в том числе как выбрать разрешения, смотрите [API Microsoft 365 Access Microsoft 365 Defender](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="618eb-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="618eb-123">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="618eb-123">Permission type</span></span> | <span data-ttu-id="618eb-124">Разрешение</span><span class="sxs-lookup"><span data-stu-id="618eb-124">Permission</span></span> | <span data-ttu-id="618eb-125">Имя дисплея разрешения</span><span class="sxs-lookup"><span data-stu-id="618eb-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="618eb-126">Приложение</span><span class="sxs-lookup"><span data-stu-id="618eb-126">Application</span></span> | <span data-ttu-id="618eb-127">Инцидент.Read.All</span><span class="sxs-lookup"><span data-stu-id="618eb-127">Incident.Read.All</span></span> | <span data-ttu-id="618eb-128">Прочитайте все инциденты</span><span class="sxs-lookup"><span data-stu-id="618eb-128">Read all incidents</span></span>
<span data-ttu-id="618eb-129">Приложение</span><span class="sxs-lookup"><span data-stu-id="618eb-129">Application</span></span> | <span data-ttu-id="618eb-130">Инцидент.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="618eb-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="618eb-131">Читать и писать все инциденты</span><span class="sxs-lookup"><span data-stu-id="618eb-131">Read and write all incidents</span></span>
<span data-ttu-id="618eb-132">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="618eb-132">Delegated (work or school account)</span></span> | <span data-ttu-id="618eb-133">Инцидент.Читайте</span><span class="sxs-lookup"><span data-stu-id="618eb-133">Incident.Read</span></span> | <span data-ttu-id="618eb-134">Читать инциденты</span><span class="sxs-lookup"><span data-stu-id="618eb-134">Read incidents</span></span>
<span data-ttu-id="618eb-135">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="618eb-135">Delegated (work or school account)</span></span> | <span data-ttu-id="618eb-136">Инцидент.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="618eb-136">Incident.ReadWrite</span></span> | <span data-ttu-id="618eb-137">Инциденты чтения и записи</span><span class="sxs-lookup"><span data-stu-id="618eb-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="618eb-138">При получении токена с использованием учетных данных пользователя:</span><span class="sxs-lookup"><span data-stu-id="618eb-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="618eb-139">Пользователь должен иметь разрешение на просмотр инцидентов на портале.</span><span class="sxs-lookup"><span data-stu-id="618eb-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="618eb-140">Ответ будет включать только инциденты, с которые пользователь подвергается.</span><span class="sxs-lookup"><span data-stu-id="618eb-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="618eb-141">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="618eb-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="618eb-142">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="618eb-142">Request headers</span></span>

<span data-ttu-id="618eb-143">Имя</span><span class="sxs-lookup"><span data-stu-id="618eb-143">Name</span></span> | <span data-ttu-id="618eb-144">Тип</span><span class="sxs-lookup"><span data-stu-id="618eb-144">Type</span></span> | <span data-ttu-id="618eb-145">Описание</span><span class="sxs-lookup"><span data-stu-id="618eb-145">Description</span></span>
-|-|-
<span data-ttu-id="618eb-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="618eb-146">Authorization</span></span> | <span data-ttu-id="618eb-147">String</span><span class="sxs-lookup"><span data-stu-id="618eb-147">String</span></span> | <span data-ttu-id="618eb-148">Носитель (токен).</span><span class="sxs-lookup"><span data-stu-id="618eb-148">Bearer {token}.</span></span> <span data-ttu-id="618eb-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="618eb-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="618eb-150">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="618eb-150">Request body</span></span>

<span data-ttu-id="618eb-151">Нет.</span><span class="sxs-lookup"><span data-stu-id="618eb-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="618eb-152">Отклик</span><span class="sxs-lookup"><span data-stu-id="618eb-152">Response</span></span>

<span data-ttu-id="618eb-153">В случае успеха, этот метод `200 OK` возвращается, и список [инцидентов](api-incident.md) в органе реагирования.</span><span class="sxs-lookup"><span data-stu-id="618eb-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="618eb-154">Схема отображение</span><span class="sxs-lookup"><span data-stu-id="618eb-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="618eb-155">Метаданные инцидентов</span><span class="sxs-lookup"><span data-stu-id="618eb-155">Incident metadata</span></span>

<span data-ttu-id="618eb-156">Имя поля</span><span class="sxs-lookup"><span data-stu-id="618eb-156">Field name</span></span> | <span data-ttu-id="618eb-157">Описание</span><span class="sxs-lookup"><span data-stu-id="618eb-157">Description</span></span> | <span data-ttu-id="618eb-158">Пример значения</span><span class="sxs-lookup"><span data-stu-id="618eb-158">Example value</span></span>
-|-|-
<span data-ttu-id="618eb-159">инцидентИд</span><span class="sxs-lookup"><span data-stu-id="618eb-159">incidentId</span></span> | <span data-ttu-id="618eb-160">Уникальный идентификатор для представления инцидента</span><span class="sxs-lookup"><span data-stu-id="618eb-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="618eb-161">924565</span><span class="sxs-lookup"><span data-stu-id="618eb-161">924565</span></span>
<span data-ttu-id="618eb-162">перенаправитьИдентид</span><span class="sxs-lookup"><span data-stu-id="618eb-162">redirectIncidentId</span></span> | <span data-ttu-id="618eb-163">Только населенные в случае инцидента в настоящее время сгруппированы вместе с другим инцидентом, как часть логики обработки инцидентов.</span><span class="sxs-lookup"><span data-stu-id="618eb-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="618eb-164">924569</span><span class="sxs-lookup"><span data-stu-id="618eb-164">924569</span></span>
<span data-ttu-id="618eb-165">инцидентИмя</span><span class="sxs-lookup"><span data-stu-id="618eb-165">incidentName</span></span> | <span data-ttu-id="618eb-166">Значение строки, доступное для каждого инцидента.</span><span class="sxs-lookup"><span data-stu-id="618eb-166">String value available for every incident.</span></span> | <span data-ttu-id="618eb-167">Действия программы-шантажиста.</span><span class="sxs-lookup"><span data-stu-id="618eb-167">Ransomware activity</span></span>
<span data-ttu-id="618eb-168">созданTime</span><span class="sxs-lookup"><span data-stu-id="618eb-168">createdTime</span></span> | <span data-ttu-id="618eb-169">Время, когда инцидент был впервые создан.</span><span class="sxs-lookup"><span data-stu-id="618eb-169">Time when incident was first created.</span></span> | <span data-ttu-id="618eb-170">2020-09-06T14:46:57.0733333</span><span class="sxs-lookup"><span data-stu-id="618eb-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="618eb-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="618eb-171">lastUpdateTime</span></span> | <span data-ttu-id="618eb-172">Время, когда инцидент был в последний раз обновлен на бэкэнде.</span><span class="sxs-lookup"><span data-stu-id="618eb-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="618eb-173">Это поле может быть использовано при настройке параметра запроса на диапазон времени извлечения инцидентов.</span><span class="sxs-lookup"><span data-stu-id="618eb-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="618eb-174">2020-09-06T14:46:57.29</span><span class="sxs-lookup"><span data-stu-id="618eb-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="618eb-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="618eb-175">assignedTo</span></span> | <span data-ttu-id="618eb-176">Владелец инцидента, или *нулевой,* если владелец не назначен.</span><span class="sxs-lookup"><span data-stu-id="618eb-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="618eb-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="618eb-177">secop2@contoso.com</span></span>
<span data-ttu-id="618eb-178">classification</span><span class="sxs-lookup"><span data-stu-id="618eb-178">classification</span></span> | <span data-ttu-id="618eb-179">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="618eb-179">The specification for the incident.</span></span> <span data-ttu-id="618eb-180">Значения свойств: Неизвестный *,* *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="618eb-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="618eb-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="618eb-181">Unknown</span></span>
<span data-ttu-id="618eb-182">решимость</span><span class="sxs-lookup"><span data-stu-id="618eb-182">determination</span></span> | <span data-ttu-id="618eb-183">Уточняется определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="618eb-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="618eb-184">Значения свойств: *Недоступно, Apt*, *Вредоносные* *программы*, *SecurityPersonnel*, *SecurityTesting*, *НежелательныеСофтвейд*, *Другие*</span><span class="sxs-lookup"><span data-stu-id="618eb-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="618eb-185">Недоступно</span><span class="sxs-lookup"><span data-stu-id="618eb-185">NotAvailable</span></span>
<span data-ttu-id="618eb-186">status</span><span class="sxs-lookup"><span data-stu-id="618eb-186">status</span></span> | <span data-ttu-id="618eb-187">Категоризация инцидентов (как *Active*, или *Разрешено).*</span><span class="sxs-lookup"><span data-stu-id="618eb-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="618eb-188">Это может помочь вам организовать и управлять вашим ответом на инциденты.</span><span class="sxs-lookup"><span data-stu-id="618eb-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="618eb-189">Активна</span><span class="sxs-lookup"><span data-stu-id="618eb-189">Active</span></span>
<span data-ttu-id="618eb-190">severity</span><span class="sxs-lookup"><span data-stu-id="618eb-190">severity</span></span> | <span data-ttu-id="618eb-191">Указывает на возможное влияние на активы.</span><span class="sxs-lookup"><span data-stu-id="618eb-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="618eb-192">Чем выше тяжесть, тем больше воздействие.</span><span class="sxs-lookup"><span data-stu-id="618eb-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="618eb-193">Обычно элементы более высокой степени тяжести требуют самого пристального внимания.</span><span class="sxs-lookup"><span data-stu-id="618eb-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="618eb-194">Одно из следующих значений: *Информационное,* *Низкое,*«Среднее» и *«Высокое».*</span><span class="sxs-lookup"><span data-stu-id="618eb-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="618eb-195">Средний</span><span class="sxs-lookup"><span data-stu-id="618eb-195">Medium</span></span>
<span data-ttu-id="618eb-196">tags</span><span class="sxs-lookup"><span data-stu-id="618eb-196">tags</span></span> | <span data-ttu-id="618eb-197">Массив пользовательских тегов, связанных с инцидентом, например, чтобы пометить группу инцидентов с общей характеристикой.</span><span class="sxs-lookup"><span data-stu-id="618eb-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="618eb-198">comments</span><span class="sxs-lookup"><span data-stu-id="618eb-198">comments</span></span> | <span data-ttu-id="618eb-199">Множество комментариев, созданных secops при управлении инцидентом, например дополнительная информация о выборе классификации.</span><span class="sxs-lookup"><span data-stu-id="618eb-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="618eb-200">alerts</span><span class="sxs-lookup"><span data-stu-id="618eb-200">alerts</span></span> | <span data-ttu-id="618eb-201">Массив, содержащий все оповещения, связанные с инцидентом, а также другую информацию, такую как серьезность, сущности, которые были вовлечены в оповещение, и источник предупреждений.</span><span class="sxs-lookup"><span data-stu-id="618eb-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="618eb-202">\[\] (см. подробную информацию о полях оповещения ниже)</span><span class="sxs-lookup"><span data-stu-id="618eb-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="618eb-203">Оповещения метаданных</span><span class="sxs-lookup"><span data-stu-id="618eb-203">Alerts metadata</span></span>

<span data-ttu-id="618eb-204">Имя поля</span><span class="sxs-lookup"><span data-stu-id="618eb-204">Field name</span></span> | <span data-ttu-id="618eb-205">Описание</span><span class="sxs-lookup"><span data-stu-id="618eb-205">Description</span></span> | <span data-ttu-id="618eb-206">Пример значения</span><span class="sxs-lookup"><span data-stu-id="618eb-206">Example value</span></span>
-|-|-
<span data-ttu-id="618eb-207">alertId</span><span class="sxs-lookup"><span data-stu-id="618eb-207">alertId</span></span> | <span data-ttu-id="618eb-208">Уникальный идентификатор для представления оповещения</span><span class="sxs-lookup"><span data-stu-id="618eb-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="618eb-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="618eb-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="618eb-210">инцидентИд</span><span class="sxs-lookup"><span data-stu-id="618eb-210">incidentId</span></span> | <span data-ttu-id="618eb-211">Уникальный идентификатор для представления инцидента, с который связано это предупреждение</span><span class="sxs-lookup"><span data-stu-id="618eb-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="618eb-212">924565</span><span class="sxs-lookup"><span data-stu-id="618eb-212">924565</span></span>
<span data-ttu-id="618eb-213">сервисИсточник</span><span class="sxs-lookup"><span data-stu-id="618eb-213">serviceSource</span></span> | <span data-ttu-id="618eb-214">Служба, от которого исходит оповещение, например, Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity или Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="618eb-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="618eb-215">MicrosoftCloudAppБезопасность</span><span class="sxs-lookup"><span data-stu-id="618eb-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="618eb-216">созданиеTime</span><span class="sxs-lookup"><span data-stu-id="618eb-216">creationTime</span></span> | <span data-ttu-id="618eb-217">Время, когда предупреждение было впервые создано.</span><span class="sxs-lookup"><span data-stu-id="618eb-217">Time when alert was first created.</span></span> | <span data-ttu-id="618eb-218">2020-09-06T14:46:55.7182276</span><span class="sxs-lookup"><span data-stu-id="618eb-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="618eb-219">последнееУченное время</span><span class="sxs-lookup"><span data-stu-id="618eb-219">lastUpdatedTime</span></span> | <span data-ttu-id="618eb-220">Время последнего обновления оповещения в бэкэнде.</span><span class="sxs-lookup"><span data-stu-id="618eb-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="618eb-221">2020-09-06T14:46:57.2433333</span><span class="sxs-lookup"><span data-stu-id="618eb-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="618eb-222">решеноTime</span><span class="sxs-lookup"><span data-stu-id="618eb-222">resolvedTime</span></span> | <span data-ttu-id="618eb-223">Время, когда тревога была решена.</span><span class="sxs-lookup"><span data-stu-id="618eb-223">Time when alert was resolved.</span></span> | <span data-ttu-id="618eb-224">2020-09-10T05:22:59</span><span class="sxs-lookup"><span data-stu-id="618eb-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="618eb-225">firstActivity</span><span class="sxs-lookup"><span data-stu-id="618eb-225">firstActivity</span></span> | <span data-ttu-id="618eb-226">Время, когда оповещение впервые сообщило, что активность была обновлена в бэкэнде.</span><span class="sxs-lookup"><span data-stu-id="618eb-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="618eb-227">2020-09-04T05:22:59</span><span class="sxs-lookup"><span data-stu-id="618eb-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="618eb-228">title</span><span class="sxs-lookup"><span data-stu-id="618eb-228">title</span></span> | <span data-ttu-id="618eb-229">Краткое определение значения строки, доступного для каждого предупреждения.</span><span class="sxs-lookup"><span data-stu-id="618eb-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="618eb-230">Действия программы-шантажиста.</span><span class="sxs-lookup"><span data-stu-id="618eb-230">Ransomware activity</span></span>
<span data-ttu-id="618eb-231">description</span><span class="sxs-lookup"><span data-stu-id="618eb-231">description</span></span> | <span data-ttu-id="618eb-232">Значение строки, описывающее каждое оповещение.</span><span class="sxs-lookup"><span data-stu-id="618eb-232">String value describing each alert.</span></span> | <span data-ttu-id="618eb-233">Пользователь Test User2 (testUser2@contoso.com) манипулировал 99 файлами с несколькими расширениями, *заканчивающимся необычным расширением herunterladen.*</span><span class="sxs-lookup"><span data-stu-id="618eb-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="618eb-234">Это необычное количество манипуляций с файлами и свидетельствует о потенциальной атаке вымогателей.</span><span class="sxs-lookup"><span data-stu-id="618eb-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="618eb-235">category</span><span class="sxs-lookup"><span data-stu-id="618eb-235">category</span></span> | <span data-ttu-id="618eb-236">Визуальное и числовое представление о том, как далеко продвинулась атака по цепочке убийства.</span><span class="sxs-lookup"><span data-stu-id="618eb-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="618eb-237">Приведены в [соответствие с рамками&CK™ MITRE.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="618eb-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="618eb-238">Влияние</span><span class="sxs-lookup"><span data-stu-id="618eb-238">Impact</span></span>
<span data-ttu-id="618eb-239">status</span><span class="sxs-lookup"><span data-stu-id="618eb-239">status</span></span> | <span data-ttu-id="618eb-240">Категоризация оповещений *(как новые,* *активные* или *разрешены).*</span><span class="sxs-lookup"><span data-stu-id="618eb-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="618eb-241">Это может помочь вам организовать и управлять вашим ответом на оповещения.</span><span class="sxs-lookup"><span data-stu-id="618eb-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="618eb-242">Новая</span><span class="sxs-lookup"><span data-stu-id="618eb-242">New</span></span>
<span data-ttu-id="618eb-243">severity</span><span class="sxs-lookup"><span data-stu-id="618eb-243">severity</span></span> | <span data-ttu-id="618eb-244">Указывает на возможное влияние на активы.</span><span class="sxs-lookup"><span data-stu-id="618eb-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="618eb-245">Чем выше тяжесть, тем больше воздействие.</span><span class="sxs-lookup"><span data-stu-id="618eb-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="618eb-246">Обычно элементы более высокой степени тяжести требуют самого пристального внимания.</span><span class="sxs-lookup"><span data-stu-id="618eb-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="618eb-247">Одно из следующих значений: *Информационное,* *Низкое,*«Среднее» и *«Высокое».*</span><span class="sxs-lookup"><span data-stu-id="618eb-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="618eb-248">Средний</span><span class="sxs-lookup"><span data-stu-id="618eb-248">Medium</span></span>
<span data-ttu-id="618eb-249">investigationId</span><span class="sxs-lookup"><span data-stu-id="618eb-249">investigationId</span></span> | <span data-ttu-id="618eb-250">Автоматизированное удостоверение личности расследования, вызванное этим предупреждением.</span><span class="sxs-lookup"><span data-stu-id="618eb-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="618eb-251">1234</span><span class="sxs-lookup"><span data-stu-id="618eb-251">1234</span></span>
<span data-ttu-id="618eb-252">расследованиеГосударство</span><span class="sxs-lookup"><span data-stu-id="618eb-252">investigationState</span></span> | <span data-ttu-id="618eb-253">Информация о текущем состоянии следствия.</span><span class="sxs-lookup"><span data-stu-id="618eb-253">Information on the investigation's current status.</span></span> <span data-ttu-id="618eb-254">Одно из следующих значений: *Неизвестный*, *Прекращено*, *УспешноВосстановлено* *,* Доброкачественные *,* Не удалось *,* *ЧастичноВосстановленный*, Запуск , *PendingApproval*, *PendingResource*, *ЧастичноInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Очередь*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, НеподдерживаемыйAlertType , *Подавленный.* </span><span class="sxs-lookup"><span data-stu-id="618eb-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="618eb-255">НеподдерживаемыйАлертТип</span><span class="sxs-lookup"><span data-stu-id="618eb-255">UnsupportedAlertType</span></span>
<span data-ttu-id="618eb-256">classification</span><span class="sxs-lookup"><span data-stu-id="618eb-256">classification</span></span> | <span data-ttu-id="618eb-257">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="618eb-257">The specification for the incident.</span></span> <span data-ttu-id="618eb-258">Значения свойств: Неизвестный *,* *FalsePositive*, *TruePositive*, или *нулевой*</span><span class="sxs-lookup"><span data-stu-id="618eb-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="618eb-259">Unknown</span><span class="sxs-lookup"><span data-stu-id="618eb-259">Unknown</span></span>
<span data-ttu-id="618eb-260">решимость</span><span class="sxs-lookup"><span data-stu-id="618eb-260">determination</span></span> | <span data-ttu-id="618eb-261">Уточняется определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="618eb-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="618eb-262">Значения свойств: *Недоступно, Apt* *,* *Вредоносные программы*, *SecurityPersonnel*, *SecurityTesting*, *НежелательныеСофтвейд*, *Другие или* *нулевой*</span><span class="sxs-lookup"><span data-stu-id="618eb-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="618eb-263">способный</span><span class="sxs-lookup"><span data-stu-id="618eb-263">Apt</span></span>
<span data-ttu-id="618eb-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="618eb-264">assignedTo</span></span> | <span data-ttu-id="618eb-265">Владелец инцидента, или *нулевой,* если владелец не назначен.</span><span class="sxs-lookup"><span data-stu-id="618eb-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="618eb-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="618eb-266">secop2@contoso.com</span></span>
<span data-ttu-id="618eb-267">актерИмя</span><span class="sxs-lookup"><span data-stu-id="618eb-267">actorName</span></span> | <span data-ttu-id="618eb-268">Группа действий, если таковые имеются, связанная с этим предупреждением.</span><span class="sxs-lookup"><span data-stu-id="618eb-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="618eb-269">бор</span><span class="sxs-lookup"><span data-stu-id="618eb-269">BORON</span></span>
<span data-ttu-id="618eb-270">угрозаСемейнаяимя</span><span class="sxs-lookup"><span data-stu-id="618eb-270">threatFamilyName</span></span> | <span data-ttu-id="618eb-271">Семейство угроз, связанное с этим предупреждением.</span><span class="sxs-lookup"><span data-stu-id="618eb-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="618eb-272">null</span><span class="sxs-lookup"><span data-stu-id="618eb-272">null</span></span>
<span data-ttu-id="618eb-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="618eb-273">mitreTechniques</span></span> | <span data-ttu-id="618eb-274">Методы атаки, как приведены в [соответствие с CK&CK](https://attack.mitre.org/)™ CK.</span><span class="sxs-lookup"><span data-stu-id="618eb-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="618eb-275">приборы</span><span class="sxs-lookup"><span data-stu-id="618eb-275">devices</span></span> | <span data-ttu-id="618eb-276">Все устройства, на которых были отправлены оповещения, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="618eb-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="618eb-277">\[\] (см. подробную информацию о полях сущности ниже)</span><span class="sxs-lookup"><span data-stu-id="618eb-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="618eb-278">Формат устройства</span><span class="sxs-lookup"><span data-stu-id="618eb-278">Device format</span></span>

<span data-ttu-id="618eb-279">Имя поля</span><span class="sxs-lookup"><span data-stu-id="618eb-279">Field name</span></span> | <span data-ttu-id="618eb-280">Описание</span><span class="sxs-lookup"><span data-stu-id="618eb-280">Description</span></span> | <span data-ttu-id="618eb-281">Пример значения</span><span class="sxs-lookup"><span data-stu-id="618eb-281">Example value</span></span>
-|-|-
<span data-ttu-id="618eb-282">УстройствоИд</span><span class="sxs-lookup"><span data-stu-id="618eb-282">DeviceId</span></span> | <span data-ttu-id="618eb-283">Идентификатор устройства, указанный в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="618eb-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="618eb-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="618eb-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="618eb-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="618eb-285">aadDeviceId</span></span> |  <span data-ttu-id="618eb-286">Идентификатор устройства, указанный в [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="618eb-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="618eb-287">Доступно только для устройств, подключенных к домену.</span><span class="sxs-lookup"><span data-stu-id="618eb-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="618eb-288">null</span><span class="sxs-lookup"><span data-stu-id="618eb-288">null</span></span>
<span data-ttu-id="618eb-289">устройствоДнсНайм</span><span class="sxs-lookup"><span data-stu-id="618eb-289">deviceDnsName</span></span> | <span data-ttu-id="618eb-290">Полностью квалифицированное доменное имя для устройства.</span><span class="sxs-lookup"><span data-stu-id="618eb-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="618eb-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="618eb-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="618eb-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="618eb-292">osPlatform</span></span> | <span data-ttu-id="618eb-293">Платформа ОС, на которую работает устройство.</span><span class="sxs-lookup"><span data-stu-id="618eb-293">The OS platform the device is running.</span></span>| <span data-ttu-id="618eb-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="618eb-294">WindowsServer2016</span></span>
<span data-ttu-id="618eb-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="618eb-295">osBuild</span></span> | <span data-ttu-id="618eb-296">Версия сборки для ОС, которую использует устройство.</span><span class="sxs-lookup"><span data-stu-id="618eb-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="618eb-297">14393</span><span class="sxs-lookup"><span data-stu-id="618eb-297">14393</span></span>
<span data-ttu-id="618eb-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="618eb-298">rbacGroupName</span></span> | <span data-ttu-id="618eb-299">Группа [управления доступом на основе](/azure/role-based-access-control/overview) роли (RBAC), связанная с устройством.</span><span class="sxs-lookup"><span data-stu-id="618eb-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="618eb-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="618eb-300">WDATP-Ring0</span></span>
<span data-ttu-id="618eb-301">первыйSeen</span><span class="sxs-lookup"><span data-stu-id="618eb-301">firstSeen</span></span> | <span data-ttu-id="618eb-302">Время, когда устройство было впервые замечено.</span><span class="sxs-lookup"><span data-stu-id="618eb-302">Time when device was first seen.</span></span> | <span data-ttu-id="618eb-303">2020-02-06T14:16:01.9330135</span><span class="sxs-lookup"><span data-stu-id="618eb-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="618eb-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="618eb-304">healthStatus</span></span> | <span data-ttu-id="618eb-305">Состояние здоровья устройства.</span><span class="sxs-lookup"><span data-stu-id="618eb-305">The health state of the device.</span></span> | <span data-ttu-id="618eb-306">Активна</span><span class="sxs-lookup"><span data-stu-id="618eb-306">Active</span></span>
<span data-ttu-id="618eb-307">рискСкор</span><span class="sxs-lookup"><span data-stu-id="618eb-307">riskScore</span></span> | <span data-ttu-id="618eb-308">Оценка риска для устройства.</span><span class="sxs-lookup"><span data-stu-id="618eb-308">The risk score for the  device.</span></span> | <span data-ttu-id="618eb-309">Высокая</span><span class="sxs-lookup"><span data-stu-id="618eb-309">High</span></span>
<span data-ttu-id="618eb-310">Объекты</span><span class="sxs-lookup"><span data-stu-id="618eb-310">entities</span></span> | <span data-ttu-id="618eb-311">Все организации, которые были определены как часть или связанные с данным предупреждением.</span><span class="sxs-lookup"><span data-stu-id="618eb-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="618eb-312">\[\] (см. подробную информацию о полях сущности ниже)</span><span class="sxs-lookup"><span data-stu-id="618eb-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="618eb-313">Формат сущности</span><span class="sxs-lookup"><span data-stu-id="618eb-313">Entity Format</span></span>

<span data-ttu-id="618eb-314">Имя поля</span><span class="sxs-lookup"><span data-stu-id="618eb-314">Field name</span></span> | <span data-ttu-id="618eb-315">Описание</span><span class="sxs-lookup"><span data-stu-id="618eb-315">Description</span></span> | <span data-ttu-id="618eb-316">Пример значения</span><span class="sxs-lookup"><span data-stu-id="618eb-316">Example value</span></span>
-|-|-
<span data-ttu-id="618eb-317">entityType</span><span class="sxs-lookup"><span data-stu-id="618eb-317">entityType</span></span> | <span data-ttu-id="618eb-318">Организации, которые были определены как часть или связанные с данным предупреждением.</span><span class="sxs-lookup"><span data-stu-id="618eb-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="618eb-319">Значения свойств: Пользователь *,* *Ip*, Url , *Файл*, *Процесс* *,* *MailBox*, *MailMessage*, *MailCluster*, *реестр*</span><span class="sxs-lookup"><span data-stu-id="618eb-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="618eb-320">Пользователь</span><span class="sxs-lookup"><span data-stu-id="618eb-320">User</span></span>
<span data-ttu-id="618eb-321">sha1</span><span class="sxs-lookup"><span data-stu-id="618eb-321">sha1</span></span> | <span data-ttu-id="618eb-322">Доступно, если entityType является *файл*.</span><span class="sxs-lookup"><span data-stu-id="618eb-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="618eb-323">Хэш файла для оповещений, связанных с файлом или процессом.</span><span class="sxs-lookup"><span data-stu-id="618eb-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="618eb-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="618eb-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="618eb-325">sha256</span><span class="sxs-lookup"><span data-stu-id="618eb-325">sha256</span></span> | <span data-ttu-id="618eb-326">Доступно, если entityType является *файл*.</span><span class="sxs-lookup"><span data-stu-id="618eb-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="618eb-327">Хэш файла для оповещений, связанных с файлом или процессом.</span><span class="sxs-lookup"><span data-stu-id="618eb-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="618eb-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="618eb-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="618eb-329">fileName</span><span class="sxs-lookup"><span data-stu-id="618eb-329">fileName</span></span> | <span data-ttu-id="618eb-330">Доступно, если entityType является *файл*.</span><span class="sxs-lookup"><span data-stu-id="618eb-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="618eb-331">Название файла для оповещений, связанных с файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="618eb-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="618eb-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="618eb-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="618eb-333">filePath</span><span class="sxs-lookup"><span data-stu-id="618eb-333">filePath</span></span> | <span data-ttu-id="618eb-334">Доступно, если entityType является *файл*.</span><span class="sxs-lookup"><span data-stu-id="618eb-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="618eb-335">Путь файла для оповещений, связанных с файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="618eb-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="618eb-336">C: \\ «agent_work_temp» Развертывание»SYSTEM»2020-09-06 12-14-54</span><span class="sxs-lookup"><span data-stu-id="618eb-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="618eb-337">processId</span><span class="sxs-lookup"><span data-stu-id="618eb-337">processId</span></span> | <span data-ttu-id="618eb-338">Доступно, если entityType является *процесс*.</span><span class="sxs-lookup"><span data-stu-id="618eb-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="618eb-339">24348</span><span class="sxs-lookup"><span data-stu-id="618eb-339">24348</span></span>
<span data-ttu-id="618eb-340">процессКомандЛайн</span><span class="sxs-lookup"><span data-stu-id="618eb-340">processCommandLine</span></span> | <span data-ttu-id="618eb-341">Доступно, если entityType является *процесс*.</span><span class="sxs-lookup"><span data-stu-id="618eb-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="618eb-342">"Ваш файл готов к загрузке \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="618eb-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="618eb-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="618eb-343">processCreationTime</span></span> | <span data-ttu-id="618eb-344">Доступно, если entityType является *процесс*.</span><span class="sxs-lookup"><span data-stu-id="618eb-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="618eb-345">2020-07-18T03:25:38.5269993</span><span class="sxs-lookup"><span data-stu-id="618eb-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="618eb-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="618eb-346">parentProcessId</span></span> | <span data-ttu-id="618eb-347">Доступно, если entityType является *процесс*.</span><span class="sxs-lookup"><span data-stu-id="618eb-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="618eb-348">16840</span><span class="sxs-lookup"><span data-stu-id="618eb-348">16840</span></span>
<span data-ttu-id="618eb-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="618eb-349">parentProcessCreationTime</span></span> | <span data-ttu-id="618eb-350">Доступно, если entityType является *процесс*.</span><span class="sxs-lookup"><span data-stu-id="618eb-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="618eb-351">2020-07-18T02:12:32.8616797</span><span class="sxs-lookup"><span data-stu-id="618eb-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="618eb-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="618eb-352">ipAddress</span></span> | <span data-ttu-id="618eb-353">Доступно, если entityType *является Ip*.</span><span class="sxs-lookup"><span data-stu-id="618eb-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="618eb-354">IP-адрес для оповещений, связанных с сетевыми событиями, *таких как связь с вредоносным сетевым пунктом назначения.*</span><span class="sxs-lookup"><span data-stu-id="618eb-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="618eb-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="618eb-355">62.216.203.204</span></span>
<span data-ttu-id="618eb-356">url</span><span class="sxs-lookup"><span data-stu-id="618eb-356">url</span></span> | <span data-ttu-id="618eb-357">Доступно, если entityType *является Url*.</span><span class="sxs-lookup"><span data-stu-id="618eb-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="618eb-358">Url для оповещений, связанных с сетевыми событиями, *такими как, Связь с вредоносным сетевым пунктом назначения.*</span><span class="sxs-lookup"><span data-stu-id="618eb-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="618eb-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="618eb-359">down.esales360.cn</span></span>
<span data-ttu-id="618eb-360">accountName</span><span class="sxs-lookup"><span data-stu-id="618eb-360">accountName</span></span> | <span data-ttu-id="618eb-361">Доступно, если entityType является *пользователем*.</span><span class="sxs-lookup"><span data-stu-id="618eb-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="618eb-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="618eb-362">testUser2</span></span>
<span data-ttu-id="618eb-363">domainName</span><span class="sxs-lookup"><span data-stu-id="618eb-363">domainName</span></span> | <span data-ttu-id="618eb-364">Доступно, если entityType является *пользователем*.</span><span class="sxs-lookup"><span data-stu-id="618eb-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="618eb-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="618eb-365">europe.corp.contoso</span></span>
<span data-ttu-id="618eb-366">пользовательСид</span><span class="sxs-lookup"><span data-stu-id="618eb-366">userSid</span></span> | <span data-ttu-id="618eb-367">Доступно, если entityType является *пользователем*.</span><span class="sxs-lookup"><span data-stu-id="618eb-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="618eb-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="618eb-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="618eb-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="618eb-369">aadUserId</span></span> | <span data-ttu-id="618eb-370">Доступно, если entityType является *пользователем*.</span><span class="sxs-lookup"><span data-stu-id="618eb-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="618eb-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="618eb-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="618eb-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="618eb-372">userPrincipalName</span></span> | <span data-ttu-id="618eb-373">Доступно, если entityType *является* / *пользователем* / *MailBox MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="618eb-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="618eb-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="618eb-374">testUser2@contoso.com</span></span>
<span data-ttu-id="618eb-375">почтовый ящикДисплейНайм</span><span class="sxs-lookup"><span data-stu-id="618eb-375">mailboxDisplayName</span></span> | <span data-ttu-id="618eb-376">Доступно, если entityType *является MailBox*.</span><span class="sxs-lookup"><span data-stu-id="618eb-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="618eb-377">тест Пользователя2</span><span class="sxs-lookup"><span data-stu-id="618eb-377">test User2</span></span>
<span data-ttu-id="618eb-378">почтовый ящикАдресуйт</span><span class="sxs-lookup"><span data-stu-id="618eb-378">mailboxAddress</span></span> | <span data-ttu-id="618eb-379">Доступно, если entityType *является* / *пользователем* / *MailBox MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="618eb-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="618eb-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="618eb-380">testUser2@contoso.com</span></span>
<span data-ttu-id="618eb-381">кластерБай</span><span class="sxs-lookup"><span data-stu-id="618eb-381">clusterBy</span></span> | <span data-ttu-id="618eb-382">Доступно, если entityType  *является MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="618eb-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="618eb-383">Тема; P2SenderDomain; СодержаниеТип</span><span class="sxs-lookup"><span data-stu-id="618eb-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="618eb-384">sender</span><span class="sxs-lookup"><span data-stu-id="618eb-384">sender</span></span> | <span data-ttu-id="618eb-385">Доступно, если entityType *является* / *пользователем* / *MailBox MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="618eb-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="618eb-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="618eb-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="618eb-387">получатель;</span><span class="sxs-lookup"><span data-stu-id="618eb-387">recipient</span></span> | <span data-ttu-id="618eb-388">Доступно, если entityType *является MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="618eb-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="618eb-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="618eb-389">testUser2@contoso.com</span></span>
<span data-ttu-id="618eb-390">subject</span><span class="sxs-lookup"><span data-stu-id="618eb-390">subject</span></span> | <span data-ttu-id="618eb-391">Доступно, если entityType *является MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="618eb-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="618eb-392">\[EXTERNAL \] Внимание</span><span class="sxs-lookup"><span data-stu-id="618eb-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="618eb-393">доставка Действий</span><span class="sxs-lookup"><span data-stu-id="618eb-393">deliveryAction</span></span> | <span data-ttu-id="618eb-394">Доступно, если entityType *является MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="618eb-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="618eb-395">доставленный</span><span class="sxs-lookup"><span data-stu-id="618eb-395">Delivered</span></span>
<span data-ttu-id="618eb-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="618eb-396">securityGroupId</span></span> | <span data-ttu-id="618eb-397">Доступно, если entityType  *является SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="618eb-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="618eb-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="618eb-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="618eb-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="618eb-399">securityGroupName</span></span> | <span data-ttu-id="618eb-400">Доступно, если entityType  *является SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="618eb-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="618eb-401">Операторы конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="618eb-401">Network Configuration Operators</span></span>
<span data-ttu-id="618eb-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="618eb-402">registryHive</span></span> | <span data-ttu-id="618eb-403">Доступно, если entityType является  *реестр*.</span><span class="sxs-lookup"><span data-stu-id="618eb-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="618eb-404">МЕСТНАЯ \_ МАШИНА \_ HKEY</span><span class="sxs-lookup"><span data-stu-id="618eb-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="618eb-405">registryKey</span><span class="sxs-lookup"><span data-stu-id="618eb-405">registryKey</span></span> | <span data-ttu-id="618eb-406">Доступно, если entityType является  *реестр*.</span><span class="sxs-lookup"><span data-stu-id="618eb-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="618eb-407">SOFTWARE-Microsoft Windows NT CurrentVersion-Winlogon</span><span class="sxs-lookup"><span data-stu-id="618eb-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="618eb-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="618eb-408">registryValueType</span></span> | <span data-ttu-id="618eb-409">Доступно, если entityType является  *реестр*.</span><span class="sxs-lookup"><span data-stu-id="618eb-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="618eb-410">String</span><span class="sxs-lookup"><span data-stu-id="618eb-410">String</span></span>
<span data-ttu-id="618eb-411">registryValue</span><span class="sxs-lookup"><span data-stu-id="618eb-411">registryValue</span></span> | <span data-ttu-id="618eb-412">Доступно, если entityType является  *реестр*.</span><span class="sxs-lookup"><span data-stu-id="618eb-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="618eb-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="618eb-413">31-00-00-00</span></span>
<span data-ttu-id="618eb-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="618eb-414">deviceId</span></span> | <span data-ttu-id="618eb-415">Идентификатор устройства, если таковые имеются, связанный с сущностью.</span><span class="sxs-lookup"><span data-stu-id="618eb-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="618eb-416">986e5df8b73d43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="618eb-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="618eb-417">Пример</span><span class="sxs-lookup"><span data-stu-id="618eb-417">Example</span></span>

<span data-ttu-id="618eb-418">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="618eb-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="618eb-419">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="618eb-419">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="618eb-420">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="618eb-420">Related articles</span></span>

- [<span data-ttu-id="618eb-421">Доступ к Microsoft 365-имуме защитника</span><span class="sxs-lookup"><span data-stu-id="618eb-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="618eb-422">Узнайте об ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="618eb-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="618eb-423">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="618eb-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="618eb-424">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="618eb-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="618eb-425">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="618eb-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="618eb-426">Обновление API инцидента</span><span class="sxs-lookup"><span data-stu-id="618eb-426">Update incident API</span></span>](api-update-incidents.md)
