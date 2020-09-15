---
title: Перечисление API происшествий в защите от угроз Майкрософт
description: Сведения о том, как перечислить инциденты API в защите от угроз Майкрософт
keywords: список, инцидент, происшествия, API
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
ms.openlocfilehash: 54f5ba640ecc175e78c7087df8016e9b715f17f7
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775115"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a><span data-ttu-id="f5fa0-104">Перечисление API происшествий в защите от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f5fa0-104">List incidents API in Microsoft Threat Protection</span></span>

<span data-ttu-id="f5fa0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f5fa0-105">**Applies to:**</span></span>

- <span data-ttu-id="f5fa0-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f5fa0-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5fa0-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f5fa0-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="f5fa0-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="f5fa0-109">API description</span></span>

<span data-ttu-id="f5fa0-110">API инцидентов позволяет сортировать инциденты для определения приоритетов и создания отклика циберсекурити.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-110">The Incident API allows you to sort through incidents to prioritize and create an informed cybersecurity response.</span></span> <span data-ttu-id="f5fa0-111">Он предоставляет коллекцию инцидентов, которые были помечены устройствами, учетными записями электронной почты и пользователями в вашей сети, в диапазоне времени, указанном в политике хранения среды.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-111">It exposes a collection of incidents that were flagged from devices, email accounts, and users in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="f5fa0-112">Последние происшествия отображаются в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="f5fa0-113">Каждый инцидент содержит массив связанных оповещений и связанные с ними сущности.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<br><span data-ttu-id="f5fa0-114">API поддерживает следующие операторы **OData** :</span><span class="sxs-lookup"><span data-stu-id="f5fa0-114">The API supports the following **OData** operators:</span></span>
<br><span data-ttu-id="f5fa0-115">```$filter``` в: ```lastUpdateTime``` , ```createdTime``` ```status``` и ```assignedTo``` Свойства.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-115">```$filter``` on: ```lastUpdateTime```, ```createdTime```, ```status``` and ```assignedTo``` properties.</span></span>
<br><span data-ttu-id="f5fa0-116">```$top``` с максимальным значением **100**</span><span class="sxs-lookup"><span data-stu-id="f5fa0-116">```$top``` with max value of **100**</span></span>
<br>```$skip```

## <a name="limitations"></a><span data-ttu-id="f5fa0-117">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f5fa0-117">Limitations</span></span>

1. <span data-ttu-id="f5fa0-118">Максимальный размер страницы **100 происшествий**.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="f5fa0-119">Максимальная частота запросов — **50 вызовов в минуту** и **1500 вызовов в час**.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="f5fa0-120">Разрешения</span><span class="sxs-lookup"><span data-stu-id="f5fa0-120">Permissions</span></span>

<span data-ttu-id="f5fa0-121">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f5fa0-122">Дополнительные сведения, в том числе выбор разрешений, см [Microsoft Microsoft Threat Protection API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="f5fa0-122">To learn more, including how to choose permissions, see [Access Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="f5fa0-123">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="f5fa0-123">Permission type</span></span> |   <span data-ttu-id="f5fa0-124">Разрешение</span><span class="sxs-lookup"><span data-stu-id="f5fa0-124">Permission</span></span>  |   <span data-ttu-id="f5fa0-125">Отображаемое имя разрешения</span><span class="sxs-lookup"><span data-stu-id="f5fa0-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f5fa0-126">Для приложений</span><span class="sxs-lookup"><span data-stu-id="f5fa0-126">Application</span></span> |   <span data-ttu-id="f5fa0-127">Инцидент. Read. ALL</span><span class="sxs-lookup"><span data-stu-id="f5fa0-127">Incident.Read.All</span></span> | <span data-ttu-id="f5fa0-128">"Чтение всех инцидентов"</span><span class="sxs-lookup"><span data-stu-id="f5fa0-128">'Read all incidents'</span></span>
<span data-ttu-id="f5fa0-129">Для приложений</span><span class="sxs-lookup"><span data-stu-id="f5fa0-129">Application</span></span> |   <span data-ttu-id="f5fa0-130">Инцидент. ReadWrite. ALL</span><span class="sxs-lookup"><span data-stu-id="f5fa0-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="f5fa0-131">"Чтение и запись всех инцидентов"</span><span class="sxs-lookup"><span data-stu-id="f5fa0-131">'Read and write all incidents'</span></span>
<span data-ttu-id="f5fa0-132">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="f5fa0-132">Delegated (work or school account)</span></span> | <span data-ttu-id="f5fa0-133">Инцидент. Read</span><span class="sxs-lookup"><span data-stu-id="f5fa0-133">Incident.Read</span></span> | <span data-ttu-id="f5fa0-134">"Чтение инцидентов"</span><span class="sxs-lookup"><span data-stu-id="f5fa0-134">'Read incidents'</span></span>
<span data-ttu-id="f5fa0-135">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="f5fa0-135">Delegated (work or school account)</span></span> | <span data-ttu-id="f5fa0-136">Инцидент. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f5fa0-136">Incident.ReadWrite</span></span> | <span data-ttu-id="f5fa0-137">"Чтение и запись происшествий"</span><span class="sxs-lookup"><span data-stu-id="f5fa0-137">'Read and write incidents'</span></span>

> [!Note]
> <span data-ttu-id="f5fa0-138">При получении маркера с использованием учетных данных пользователя:</span><span class="sxs-lookup"><span data-stu-id="f5fa0-138">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="f5fa0-139">Пользователь должен иметь разрешение на просмотр инцидентов на портале.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="f5fa0-140">В ответ будут включены только те инциденты, к которым у пользователя есть доступ.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="f5fa0-141">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="f5fa0-141">HTTP request</span></span>

```
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="f5fa0-142">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="f5fa0-142">Request headers</span></span>

<span data-ttu-id="f5fa0-143">Имя</span><span class="sxs-lookup"><span data-stu-id="f5fa0-143">Name</span></span> | <span data-ttu-id="f5fa0-144">Тип</span><span class="sxs-lookup"><span data-stu-id="f5fa0-144">Type</span></span> | <span data-ttu-id="f5fa0-145">Описание</span><span class="sxs-lookup"><span data-stu-id="f5fa0-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="f5fa0-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="f5fa0-146">Authorization</span></span> | <span data-ttu-id="f5fa0-147">String</span><span class="sxs-lookup"><span data-stu-id="f5fa0-147">String</span></span> | <span data-ttu-id="f5fa0-148">Bearer {Token}.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-148">Bearer {token}.</span></span> <span data-ttu-id="f5fa0-149">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-149">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f5fa0-150">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="f5fa0-150">Request body</span></span>
<span data-ttu-id="f5fa0-151">Нет.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="f5fa0-152">Отклик</span><span class="sxs-lookup"><span data-stu-id="f5fa0-152">Response</span></span>
<span data-ttu-id="f5fa0-153">В случае успешного выполнения этот метод возвращает 200 ОК и список [инцидентов](api-incident.md) в тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-153">If successful, this method returns 200 OK, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="f5fa0-154">Сопоставление схемы</span><span class="sxs-lookup"><span data-stu-id="f5fa0-154">Schema mapping</span></span>

| <span data-ttu-id="f5fa0-155">Имя поля</span><span class="sxs-lookup"><span data-stu-id="f5fa0-155">Field name</span></span>                                | <span data-ttu-id="f5fa0-156">Описание</span><span class="sxs-lookup"><span data-stu-id="f5fa0-156">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="f5fa0-157">Пример значения</span><span class="sxs-lookup"><span data-stu-id="f5fa0-157">Example value</span></span>                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="f5fa0-158">**Метаданные инцидента**</span><span class="sxs-lookup"><span data-stu-id="f5fa0-158">**Incident metadata**</span></span>                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="f5fa0-159">инЦидентид</span><span class="sxs-lookup"><span data-stu-id="f5fa0-159">incidentId</span></span>                                | <span data-ttu-id="f5fa0-160">Уникальный идентификатор для представления инцидента.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-160">Unique identifier to represent the incident.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="f5fa0-161">924565</span><span class="sxs-lookup"><span data-stu-id="f5fa0-161">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-162">редиректинЦидентид</span><span class="sxs-lookup"><span data-stu-id="f5fa0-162">redirectIncidentId</span></span>                        | <span data-ttu-id="f5fa0-163">Заполняется только в том случае, если инцидент сгруппирован вместе с другим инцидентом в рамках логики обработки инцидентов.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span>                                                                                                                                                                                                                                                           | <span data-ttu-id="f5fa0-164">924569</span><span class="sxs-lookup"><span data-stu-id="f5fa0-164">924569</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-165">инЦидентнаме</span><span class="sxs-lookup"><span data-stu-id="f5fa0-165">incidentName</span></span>                              | <span data-ttu-id="f5fa0-166">Строковое значение, доступное для каждого происшествия.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-166">String value available for every incident.</span></span>                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="f5fa0-167">Действия с программой «шантажистом»</span><span class="sxs-lookup"><span data-stu-id="f5fa0-167">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="f5fa0-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="f5fa0-168">createdTime</span></span>                               | <span data-ttu-id="f5fa0-169">Время первоначального создания инцидента.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-169">Time when incident was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                      | <span data-ttu-id="f5fa0-170">2020 – 09 — 06T14:46:57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="f5fa0-170">2020-09-06T14:46:57.0733333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="f5fa0-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="f5fa0-171">lastUpdateTime</span></span>                            | <span data-ttu-id="f5fa0-172">Время последнего обновления инцидента в серверной части.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-172">Time when incident was last updated at the backend.</span></span><br> <span data-ttu-id="f5fa0-173">Это поле можно использовать при задании параметра Request для диапазона времени, в течение которого извлекаются происшествия.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-173">This field can be used when setting the request parameter for the range of time that incidents are retrieved.</span></span>                                                                                                                                                                                                                      | <span data-ttu-id="f5fa0-174">2020 – 09 — 06T14:46:57.29 Z</span><span class="sxs-lookup"><span data-stu-id="f5fa0-174">2020-09-06T14:46:57.29Z</span></span>                                                                                                                                                                                                                           |
| <span data-ttu-id="f5fa0-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="f5fa0-175">assignedTo</span></span>                                | <span data-ttu-id="f5fa0-176">Владелец инцидента или *значение NULL* , если владелец не назначен.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-176">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="f5fa0-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fa0-177">secop2@contoso.com</span></span>                                                                                                                                                                                                |
| <span data-ttu-id="f5fa0-178">classification</span><span class="sxs-lookup"><span data-stu-id="f5fa0-178">classification</span></span>                            | <span data-ttu-id="f5fa0-179">Спецификация для инцидента.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-179">The specification for the incident.</span></span> <span data-ttu-id="f5fa0-180">Значения свойств: *Unknown*, *FalsePositive*, *труепоситиве*</span><span class="sxs-lookup"><span data-stu-id="f5fa0-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span>                                                                                                                                                                                                                                                                           | <span data-ttu-id="f5fa0-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="f5fa0-181">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="f5fa0-182">решение</span><span class="sxs-lookup"><span data-stu-id="f5fa0-182">determination</span></span>                             | <span data-ttu-id="f5fa0-183">Указывает на определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="f5fa0-184">Значения свойства: *нотаваилабле*, *Апт*, *Malware*, *секуритиперсоннел*, *секурититестинг*, *унвантедсофтваре*, *other*</span><span class="sxs-lookup"><span data-stu-id="f5fa0-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span>                                                                                                                                                                                                                | <span data-ttu-id="f5fa0-185">нотаваилабле</span><span class="sxs-lookup"><span data-stu-id="f5fa0-185">NotAvailable</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="f5fa0-186">status</span><span class="sxs-lookup"><span data-stu-id="f5fa0-186">status</span></span>                                    | <span data-ttu-id="f5fa0-187">Категоризация инцидентов (как *активных*, так и *разрешенных*).</span><span class="sxs-lookup"><span data-stu-id="f5fa0-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="f5fa0-188">Это помогает организовывать реагирование на происшествия и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-188">This helps you organize and manage your response to incidents.</span></span>                                                                                                                                                                                                                                                                  | <span data-ttu-id="f5fa0-189">Активное</span><span class="sxs-lookup"><span data-stu-id="f5fa0-189">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-190">severity</span><span class="sxs-lookup"><span data-stu-id="f5fa0-190">severity</span></span>                                  | <span data-ttu-id="f5fa0-191">Указывает возможное воздействие на активы.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="f5fa0-192">Чем выше степень серьезности, тем больше степень воздействия.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="f5fa0-193">Обычно более высокая степень серьезности требует наиболее мгновенное внимание.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-193">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="f5fa0-194">Одно из следующих значений: *информационные*, *низкие*, \* средние и *высокие*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                | <span data-ttu-id="f5fa0-195">Средняя</span><span class="sxs-lookup"><span data-stu-id="f5fa0-195">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-196">tags</span><span class="sxs-lookup"><span data-stu-id="f5fa0-196">tags</span></span>                                      | <span data-ttu-id="f5fa0-197">Массив настраиваемых тегов, связанных с инцидентом, например, чтобы пометить группу инцидентов общей характеристикой.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span>                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-198">alerts</span><span class="sxs-lookup"><span data-stu-id="f5fa0-198">alerts</span></span>                                    | <span data-ttu-id="f5fa0-199">Массив всех оповещений, относящихся к инциденту, и другие сведения, такие как степень серьезности, объекты, которые участвовали в оповещении, источник оповещений.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-199">Array of all the alerts related to the incident and other information, such as severity, entities that were involved in the alert, the source of the alerts.</span></span>                                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-200">\[\] (подробные сведения о полях Alert см. ниже)</span><span class="sxs-lookup"><span data-stu-id="f5fa0-200">\[\] (see details on alert fields below)</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="f5fa0-201">**Метаданные Alerts**</span><span class="sxs-lookup"><span data-stu-id="f5fa0-201">**Alerts metadata**</span></span>                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="f5fa0-202">алертид</span><span class="sxs-lookup"><span data-stu-id="f5fa0-202">alertId</span></span>                                   | <span data-ttu-id="f5fa0-203">Уникальный идентификатор для представления оповещения</span><span class="sxs-lookup"><span data-stu-id="f5fa0-203">Unique identifier to represent the alert</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="f5fa0-204">caD70CFEE2 — 1F54 — 32DB – 9988 – 3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="f5fa0-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-205">инЦидентид</span><span class="sxs-lookup"><span data-stu-id="f5fa0-205">incidentId</span></span>                                | <span data-ttu-id="f5fa0-206">Уникальный идентификатор инцидента, с которым связано это оповещение</span><span class="sxs-lookup"><span data-stu-id="f5fa0-206">Unique identifier to represent the incident this alert is associated with</span></span>                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="f5fa0-207">924565</span><span class="sxs-lookup"><span data-stu-id="f5fa0-207">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-208">сервицесаурце</span><span class="sxs-lookup"><span data-stu-id="f5fa0-208">serviceSource</span></span>                             | <span data-ttu-id="f5fa0-209">Служба, от которой поступило оповещение, например: ATP, Microsoft Cloud App Security, Azure ATP или Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-209">Service that the alert originates from, such as Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, or Office 365 ATP.</span></span>                                                                                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-210">микрософтклаудаппсекурити</span><span class="sxs-lookup"><span data-stu-id="f5fa0-210">MicrosoftCloudAppSecurity</span></span>                                                                                                                                                                                                                         |
| <span data-ttu-id="f5fa0-211">creationTime</span><span class="sxs-lookup"><span data-stu-id="f5fa0-211">creationTime</span></span>                              | <span data-ttu-id="f5fa0-212">Время первого создания оповещения.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-212">Time when alert was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="f5fa0-213">2020 – 09 — 06T14:46:55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="f5fa0-213">2020-09-06T14:46:55.7182276Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="f5fa0-214">ластупдатедтиме</span><span class="sxs-lookup"><span data-stu-id="f5fa0-214">lastUpdatedTime</span></span>                           | <span data-ttu-id="f5fa0-215">Время последнего обновления оповещения в серверной части.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-215">Time when alert was last updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="f5fa0-216">2020 – 09 — 06T14:46:57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="f5fa0-216">2020-09-06T14:46:57.2433333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="f5fa0-217">ресолведтиме</span><span class="sxs-lookup"><span data-stu-id="f5fa0-217">resolvedTime</span></span>                              | <span data-ttu-id="f5fa0-218">Время, когда оповещение было разрешено.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-218">Time when alert was resolved.</span></span>                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="f5fa0-219">2020 — 09 — 10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="f5fa0-219">2020-09-10T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-220">фирстактивити</span><span class="sxs-lookup"><span data-stu-id="f5fa0-220">firstActivity</span></span>                             | <span data-ttu-id="f5fa0-221">Время, когда оповещение впервые сообщило об обновлении этого действия в серверной части.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-221">Time when alert first reported that activity was updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="f5fa0-222">2020 — 09 — 04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="f5fa0-222">2020-09-04T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-223">title</span><span class="sxs-lookup"><span data-stu-id="f5fa0-223">title</span></span>                                     | <span data-ttu-id="f5fa0-224">Краткое определение строкового значения, доступного для каждого оповещения.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-224">Brief identifying string value available for each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-225">Действия с программой «шантажистом»</span><span class="sxs-lookup"><span data-stu-id="f5fa0-225">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="f5fa0-226">description</span><span class="sxs-lookup"><span data-stu-id="f5fa0-226">description</span></span>                               | <span data-ttu-id="f5fa0-227">Строковое значение, описывающее каждое оповещение.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-227">String value describing each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="f5fa0-228">Пользовательский тест Пользователь2 (testUser2@contoso.com) с несколькими расширениями, заканчивающимися нераспространенным расширением *херунтерладен*, манипулирует файлами 99.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-228">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="f5fa0-229">Это необычное количество операций с файлами, которые свидетельствуют о потенциальной атаке с помощью атаки программой-шантажистом.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-229">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span> |
| <span data-ttu-id="f5fa0-230">category</span><span class="sxs-lookup"><span data-stu-id="f5fa0-230">category</span></span>                                  | <span data-ttu-id="f5fa0-231">Визуальное и числовое представление того, насколько продвигается атака в цепочке аннулирования.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-231">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="f5fa0-232">Выравниваются по [МИТРЕ ATT&а™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="f5fa0-232">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span>                                                                                                                                                                                                                           | <span data-ttu-id="f5fa0-233">Влияние</span><span class="sxs-lookup"><span data-stu-id="f5fa0-233">Impact</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-234">status</span><span class="sxs-lookup"><span data-stu-id="f5fa0-234">status</span></span>                                    | <span data-ttu-id="f5fa0-235">Категоризация оповещений (как *новых*, *активных*или *разрешенных*).</span><span class="sxs-lookup"><span data-stu-id="f5fa0-235">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="f5fa0-236">Это помогает организовывать и управлять ответами на оповещения.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-236">This helps you organize and manage your response to alerts.</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="f5fa0-237">Новое</span><span class="sxs-lookup"><span data-stu-id="f5fa0-237">New</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="f5fa0-238">severity</span><span class="sxs-lookup"><span data-stu-id="f5fa0-238">severity</span></span>                                  | <span data-ttu-id="f5fa0-239">Указывает возможное воздействие на активы.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-239">Indicates the possible impact on assets.</span></span> <span data-ttu-id="f5fa0-240">Чем выше степень серьезности, тем больше степень воздействия.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-240">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="f5fa0-241">Обычно более высокая степень серьезности требует наиболее мгновенное внимание.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-241">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="f5fa0-242">Одно из следующих значений: *информационные*, *низкие*, \* средние и *высокие*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-242">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                   | <span data-ttu-id="f5fa0-243">Средняя</span><span class="sxs-lookup"><span data-stu-id="f5fa0-243">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-244">инвестигатионид</span><span class="sxs-lookup"><span data-stu-id="f5fa0-244">investigationId</span></span>                           | <span data-ttu-id="f5fa0-245">Идентификатор автоматического исследования, инициированный этим предупреждением.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-245">The automated investigation id triggered by this alert.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="f5fa0-246">1234</span><span class="sxs-lookup"><span data-stu-id="f5fa0-246">1234</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-247">инвестигатионстате</span><span class="sxs-lookup"><span data-stu-id="f5fa0-247">investigationState</span></span>                        | <span data-ttu-id="f5fa0-248">Сведения о текущем состоянии расследования.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-248">Information on the investigation's current status.</span></span> <span data-ttu-id="f5fa0-249">Один из следующих: *Unknown*, *Terminate*, *сукцессфуллиремедиатед*, *мягкое*, *сбой*, *партиаллиремедиатед*, *выполнение*, *пендингаппровал*, *пендингресаурце*, *партиаллинвестигатед*, *TerminatedByUser*, *TerminatedBySystem*, *queued*, *InnerFailure*, PreexistingAlert *,* *UnsupportedOs*, *UnsupportedAlertType*, SuppressedAlert *.*</span><span class="sxs-lookup"><span data-stu-id="f5fa0-249">One of the following: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="f5fa0-250">унсуппортедалерттипе</span><span class="sxs-lookup"><span data-stu-id="f5fa0-250">UnsupportedAlertType</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-251">classification</span><span class="sxs-lookup"><span data-stu-id="f5fa0-251">classification</span></span>                            | <span data-ttu-id="f5fa0-252">Спецификация для инцидента.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-252">The specification for the incident.</span></span> <span data-ttu-id="f5fa0-253">Значения свойств: *Unknown*, *FalsePositive*, *труепоситиве* или *null*</span><span class="sxs-lookup"><span data-stu-id="f5fa0-253">The property values are: *Unknown*, *FalsePositive*, *TruePositive* or *null*</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="f5fa0-254">Unknown</span><span class="sxs-lookup"><span data-stu-id="f5fa0-254">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="f5fa0-255">решение</span><span class="sxs-lookup"><span data-stu-id="f5fa0-255">determination</span></span>                             | <span data-ttu-id="f5fa0-256">Указывает на определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-256">Specifies the determination of the incident.</span></span> <span data-ttu-id="f5fa0-257">Значения свойства: *нотаваилабле*, *Апт*, *Malware*, *секуритиперсоннел*, *секурититестинг*, *унвантедсофтваре*, *other* или  *null*</span><span class="sxs-lookup"><span data-stu-id="f5fa0-257">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-258">апт</span><span class="sxs-lookup"><span data-stu-id="f5fa0-258">Apt</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="f5fa0-259">assignedTo</span><span class="sxs-lookup"><span data-stu-id="f5fa0-259">assignedTo</span></span>                                | <span data-ttu-id="f5fa0-260">Владелец инцидента или *значение NULL* , если владелец не назначен.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-260">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                            | <span data-ttu-id="f5fa0-261">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fa0-261">secop2@contoso.com</span></span>                                                                                                                                                                                                 |
| <span data-ttu-id="f5fa0-262">акторнаме</span><span class="sxs-lookup"><span data-stu-id="f5fa0-262">actorName</span></span>                                 | <span data-ttu-id="f5fa0-263">Группа действий, связанная с этим предупреждением.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-263">The activity group, if any, the  associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="f5fa0-264">борон</span><span class="sxs-lookup"><span data-stu-id="f5fa0-264">BORON</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="f5fa0-265">среатфамилинаме</span><span class="sxs-lookup"><span data-stu-id="f5fa0-265">threatFamilyName</span></span>                          | <span data-ttu-id="f5fa0-266">Семейство угроз, связанное с этим предупреждением.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-266">Threat family associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="f5fa0-267">null</span><span class="sxs-lookup"><span data-stu-id="f5fa0-267">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-268">митретечникуес</span><span class="sxs-lookup"><span data-stu-id="f5fa0-268">mitreTechniques</span></span>                           | <span data-ttu-id="f5fa0-269">Способы атаки, выровненные с помощью [МИТРЕ ATT&а](https://attack.mitre.org/)™ Framework.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-269">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span>                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-270">драйверов</span><span class="sxs-lookup"><span data-stu-id="f5fa0-270">devices</span></span>                                   | <span data-ttu-id="f5fa0-271">Все устройства, на которые были отправлены оповещения, связанные с инцидентом.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-271">All devices where alerts related to the incident were sent.</span></span>                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-272">\[\] (Дополнительные сведения о полях сущностей см. ниже)</span><span class="sxs-lookup"><span data-stu-id="f5fa0-272">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="f5fa0-273">**Формат устройства**</span><span class="sxs-lookup"><span data-stu-id="f5fa0-273">**Device format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="f5fa0-274">Устройства</span><span class="sxs-lookup"><span data-stu-id="f5fa0-274">DeviceId</span></span>                                  | <span data-ttu-id="f5fa0-275">ИДЕНТИФИКАТОР устройства, указанный в разделе ATP для защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-275">The device ID as designated in Microsoft Defender ATP.</span></span>                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="f5fa0-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="f5fa0-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="f5fa0-277">ааддевицеид</span><span class="sxs-lookup"><span data-stu-id="f5fa0-277">aadDeviceId</span></span>                               |  <span data-ttu-id="f5fa0-278">Идентификатор устройства, назначенный в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span><span class="sxs-lookup"><span data-stu-id="f5fa0-278">The device Id as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span></span> <span data-ttu-id="f5fa0-279">Доступно только для устройств, присоединенных к домену.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-279">Only available for domain-joined devices.</span></span>                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="f5fa0-280">null</span><span class="sxs-lookup"><span data-stu-id="f5fa0-280">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-281">девицеднснаме</span><span class="sxs-lookup"><span data-stu-id="f5fa0-281">deviceDnsName</span></span>                             | <span data-ttu-id="f5fa0-282">Полное доменное имя устройства.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-282">The fully qualified domain name for the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="f5fa0-283">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fa0-283">user5cx.middleeast.corp.contoso.com</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="f5fa0-284">осплатформ</span><span class="sxs-lookup"><span data-stu-id="f5fa0-284">osPlatform</span></span>                                | <span data-ttu-id="f5fa0-285">Платформа операционной системы, в которой работает устройство.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-285">The OS platform the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-286">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="f5fa0-286">WindowsServer2016</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="f5fa0-287">осбуилд</span><span class="sxs-lookup"><span data-stu-id="f5fa0-287">osBuild</span></span>                                   | <span data-ttu-id="f5fa0-288">Версия сборки для ОС, в которой выполняется устройство.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-288">The build version for the OS the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="f5fa0-289">14393</span><span class="sxs-lookup"><span data-stu-id="f5fa0-289">14393</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="f5fa0-290">рбакграупнаме</span><span class="sxs-lookup"><span data-stu-id="f5fa0-290">rbacGroupName</span></span>                             | <span data-ttu-id="f5fa0-291">Группа [управления доступом на основе ролей](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC), связанная с устройством.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-291">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="f5fa0-292">ВДАТП — Ring0</span><span class="sxs-lookup"><span data-stu-id="f5fa0-292">WDATP-Ring0</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="f5fa0-293">фирстсин</span><span class="sxs-lookup"><span data-stu-id="f5fa0-293">firstSeen</span></span>                                 | <span data-ttu-id="f5fa0-294">Время первого появление устройства.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-294">Time when device was first seen.</span></span>                                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="f5fa0-295">2020 — 02 — 06T14:16:01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="f5fa0-295">2020-02-06T14:16:01.9330135Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="f5fa0-296">хеалсстатус</span><span class="sxs-lookup"><span data-stu-id="f5fa0-296">healthStatus</span></span>                              | <span data-ttu-id="f5fa0-297">Состояние работоспособности устройства.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-297">The health state of the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="f5fa0-298">Активное</span><span class="sxs-lookup"><span data-stu-id="f5fa0-298">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-299">riskScore</span><span class="sxs-lookup"><span data-stu-id="f5fa0-299">riskScore</span></span>                                 | <span data-ttu-id="f5fa0-300">Показатель риска для устройства.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-300">The risk score for the  device.</span></span>                                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="f5fa0-301">Высокая</span><span class="sxs-lookup"><span data-stu-id="f5fa0-301">High</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-302">организациями</span><span class="sxs-lookup"><span data-stu-id="f5fa0-302">entities</span></span>                                  | <span data-ttu-id="f5fa0-303">Все сущности, к которым относится данное оповещение, или связанные с ними.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-303">All entities that have been identified to be part of, or related to, a given alert.</span></span>                                                                                                                                                                                                                                                                                | <span data-ttu-id="f5fa0-304">\[\] (Дополнительные сведения о полях сущностей см. ниже)</span><span class="sxs-lookup"><span data-stu-id="f5fa0-304">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="f5fa0-305">**Формат объекта**</span><span class="sxs-lookup"><span data-stu-id="f5fa0-305">**Entity Format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="f5fa0-306">Сущности</span><span class="sxs-lookup"><span data-stu-id="f5fa0-306">entityType</span></span>                                | <span data-ttu-id="f5fa0-307">Объекты, которые были идентифицированы как часть или связанные с данным оповещением.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-307">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="f5fa0-308">Значения свойств: *User*, *IP*, *URL-адрес*, *файл*, *процесс*, *почтовый ящик*, *MailMessage*, *маилклустер*, *Реестр*</span><span class="sxs-lookup"><span data-stu-id="f5fa0-308">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-309">User</span><span class="sxs-lookup"><span data-stu-id="f5fa0-309">User</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-310">хэшем</span><span class="sxs-lookup"><span data-stu-id="f5fa0-310">sha1</span></span>                                      | <span data-ttu-id="f5fa0-311">Доступно, если entityType — *файл*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-311">Available if entityType is *File*.</span></span><br><span data-ttu-id="f5fa0-312">Хэш файла для оповещений, связанных с файлом или процессом.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-312">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="f5fa0-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="f5fa0-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="f5fa0-314">хэш</span><span class="sxs-lookup"><span data-stu-id="f5fa0-314">sha256</span></span>                                    | <span data-ttu-id="f5fa0-315">Доступно, если entityType — *файл*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-315">Available if entityType is *File*.</span></span><br><span data-ttu-id="f5fa0-316">Хэш файла для оповещений, связанных с файлом или процессом.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-316">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="f5fa0-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="f5fa0-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="f5fa0-318">fileName</span><span class="sxs-lookup"><span data-stu-id="f5fa0-318">fileName</span></span>                                  | <span data-ttu-id="f5fa0-319">Доступно, если entityType — *файл*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-319">Available if entityType is *File*.</span></span><br><span data-ttu-id="f5fa0-320">Имя файла для оповещений, связанных с файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="f5fa0-320">The file name for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="f5fa0-321">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="f5fa0-321">Detector.UnitTests.dll</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-322">Пути</span><span class="sxs-lookup"><span data-stu-id="f5fa0-322">filePath</span></span>                                  | <span data-ttu-id="f5fa0-323">Доступно, если entityType — *файл*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-323">Available if entityType is *File*.</span></span><br><span data-ttu-id="f5fa0-324">Путь к файлу оповещений, связанных с файлом или процессом</span><span class="sxs-lookup"><span data-stu-id="f5fa0-324">The file path for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="f5fa0-325">C: \\ \\ Агент \\ \\ \_ Work \\ \\ \_ temp \\ \\ deploy \_ System 2020-09-06 12 \_ 14 \_ 54 \\ \\</span><span class="sxs-lookup"><span data-stu-id="f5fa0-325">C:\\\\Agent\\\\\_work\\\\\_temp\\\\Deploy\_SYSTEM 2020-09-06 12\_14\_54\\\\Out</span></span>                                                                                                                                                                    |
| <span data-ttu-id="f5fa0-326">processId</span><span class="sxs-lookup"><span data-stu-id="f5fa0-326">processId</span></span>                                 | <span data-ttu-id="f5fa0-327">Доступно, если entityType *обрабатывается.*</span><span class="sxs-lookup"><span data-stu-id="f5fa0-327">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-328">24348</span><span class="sxs-lookup"><span data-stu-id="f5fa0-328">24348</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="f5fa0-329">процесскоммандлине</span><span class="sxs-lookup"><span data-stu-id="f5fa0-329">processCommandLine</span></span>                        | <span data-ttu-id="f5fa0-330">Доступно, если entityType *обрабатывается.*</span><span class="sxs-lookup"><span data-stu-id="f5fa0-330">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-331">" \\ " Файл готов к скачиванию \_1911150169.exe\\ ""</span><span class="sxs-lookup"><span data-stu-id="f5fa0-331">"\\"Your File Is Ready To Download\_1911150169.exe\\" "</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="f5fa0-332">процесскреатионтиме</span><span class="sxs-lookup"><span data-stu-id="f5fa0-332">processCreationTime</span></span>                       | <span data-ttu-id="f5fa0-333">Доступно, если entityType *обрабатывается.*</span><span class="sxs-lookup"><span data-stu-id="f5fa0-333">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-334">2020 — 07 – 18T03:25:38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="f5fa0-334">2020-07-18T03:25:38.5269993Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="f5fa0-335">парентпроцессид</span><span class="sxs-lookup"><span data-stu-id="f5fa0-335">parentProcessId</span></span>                           | <span data-ttu-id="f5fa0-336">Доступно, если entityType *обрабатывается.*</span><span class="sxs-lookup"><span data-stu-id="f5fa0-336">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="f5fa0-337">16840</span><span class="sxs-lookup"><span data-stu-id="f5fa0-337">16840</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="f5fa0-338">парентпроцесскреатионтиме</span><span class="sxs-lookup"><span data-stu-id="f5fa0-338">parentProcessCreationTime</span></span>                 | <span data-ttu-id="f5fa0-339">Доступно, если entityType *обрабатывается.*</span><span class="sxs-lookup"><span data-stu-id="f5fa0-339">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-340">2020 — 07 – 18T02:12:32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="f5fa0-340">2020-07-18T02:12:32.8616797Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="f5fa0-341">ipAddress</span><span class="sxs-lookup"><span data-stu-id="f5fa0-341">ipAddress</span></span>                                 | <span data-ttu-id="f5fa0-342">Доступно, если entityType имеет *IP*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-342">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="f5fa0-343">IP-адрес оповещений, связанных с сетевыми событиями, например *для связи с вредоносным сетевым адресом*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-343">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                   | <span data-ttu-id="f5fa0-344">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="f5fa0-344">62.216.203.204</span></span>                                                                                                                                                                                                                                    |
| <span data-ttu-id="f5fa0-345">url</span><span class="sxs-lookup"><span data-stu-id="f5fa0-345">url</span></span>                                       | <span data-ttu-id="f5fa0-346">Доступно, если entityType имеет *URL-адрес*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-346">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="f5fa0-347">URL-адрес оповещений, связанных с сетевыми событиями, таких как *связь с вредоносным сетевым адресом назначения*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-347">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                  | <span data-ttu-id="f5fa0-348">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="f5fa0-348">down.esales360.cn</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="f5fa0-349">accountName</span><span class="sxs-lookup"><span data-stu-id="f5fa0-349">accountName</span></span>                               | <span data-ttu-id="f5fa0-350">Доступно, если entityType — *User*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-350">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="f5fa0-351">testUser2</span><span class="sxs-lookup"><span data-stu-id="f5fa0-351">testUser2</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="f5fa0-352">domainName</span><span class="sxs-lookup"><span data-stu-id="f5fa0-352">domainName</span></span>                                | <span data-ttu-id="f5fa0-353">Доступно, если entityType — *User*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-353">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="f5fa0-354">Европа. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="f5fa0-354">europe.corp.contoso</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-355">О.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-355">userSid</span></span>                                   | <span data-ttu-id="f5fa0-356">Доступно, если entityType — *User*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-356">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="f5fa0-357">S – 1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="f5fa0-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="f5fa0-358">аадусерид</span><span class="sxs-lookup"><span data-stu-id="f5fa0-358">aadUserId</span></span>                                 | <span data-ttu-id="f5fa0-359">Доступно, если entityType — *User*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-359">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="f5fa0-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="f5fa0-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-361">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="f5fa0-361">userPrincipalName</span></span>                         | <span data-ttu-id="f5fa0-362">Доступно, если EntityType *User*является / *MailMessage почтовых ящиков*пользователей / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-362">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="f5fa0-363">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fa0-363">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="f5fa0-364">маилбоксдисплайнаме</span><span class="sxs-lookup"><span data-stu-id="f5fa0-364">mailboxDisplayName</span></span>                        | <span data-ttu-id="f5fa0-365">Доступно, если entityType имеет *почтовые ящики*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-365">Available if entityType is *MailBox*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-366">тест Пользователь2</span><span class="sxs-lookup"><span data-stu-id="f5fa0-366">test User2</span></span>                                                                                                                                                                                                                                        |
| <span data-ttu-id="f5fa0-367">маилбоксаддресс</span><span class="sxs-lookup"><span data-stu-id="f5fa0-367">mailboxAddress</span></span>                            | <span data-ttu-id="f5fa0-368">Доступно, если EntityType *User*является / *MailMessage почтовых ящиков*пользователей / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-368">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="f5fa0-369">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fa0-369">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="f5fa0-370">клустерби</span><span class="sxs-lookup"><span data-stu-id="f5fa0-370">clusterBy</span></span>                                 | <span data-ttu-id="f5fa0-371">Доступно, если entityType имеет  *маилклустер*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-371">Available if entityType is  *MailCluster*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="f5fa0-372">Эксперты P2SenderDomain; Следующий</span><span class="sxs-lookup"><span data-stu-id="f5fa0-372">Subject;P2SenderDomain;ContentType</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="f5fa0-373">отправитель;</span><span class="sxs-lookup"><span data-stu-id="f5fa0-373">sender</span></span>                                    | <span data-ttu-id="f5fa0-374">Доступно, если EntityType *User*является / *MailMessage почтовых ящиков*пользователей / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-374">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="f5fa0-375">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="f5fa0-375">user.abc@mail.contoso.co.in</span></span>                                                                                                                                                                 |
| <span data-ttu-id="f5fa0-376">получатель;</span><span class="sxs-lookup"><span data-stu-id="f5fa0-376">recipient</span></span>                                 | <span data-ttu-id="f5fa0-377">Доступно, если entityType имеет *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-377">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="f5fa0-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5fa0-378">testUser2@contoso.com</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="f5fa0-379">subject</span><span class="sxs-lookup"><span data-stu-id="f5fa0-379">subject</span></span>                                   | <span data-ttu-id="f5fa0-380">Доступно, если entityType имеет *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-380">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="f5fa0-381">\[ВНЕШНее \] внимание</span><span class="sxs-lookup"><span data-stu-id="f5fa0-381">\[EXTERNAL\] Attention</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-382">деливеряктион</span><span class="sxs-lookup"><span data-stu-id="f5fa0-382">deliveryAction</span></span>                            | <span data-ttu-id="f5fa0-383">Доступно, если entityType имеет *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-383">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="f5fa0-384">Отобран</span><span class="sxs-lookup"><span data-stu-id="f5fa0-384">Delivered</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="f5fa0-385">секуритиграупид</span><span class="sxs-lookup"><span data-stu-id="f5fa0-385">securityGroupId</span></span>                           | <span data-ttu-id="f5fa0-386">Доступно, если entityType имеет  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-386">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="f5fa0-387">301c47c8 — e15f – 4059 — ab09 – e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="f5fa0-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-388">секуритиграупнаме</span><span class="sxs-lookup"><span data-stu-id="f5fa0-388">securityGroupName</span></span>                         | <span data-ttu-id="f5fa0-389">Доступно, если entityType имеет  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-389">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="f5fa0-390">Операторы настройки сети</span><span class="sxs-lookup"><span data-stu-id="f5fa0-390">Network Configuration Operators</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="f5fa0-391">registryHive</span><span class="sxs-lookup"><span data-stu-id="f5fa0-391">registryHive</span></span>                              | <span data-ttu-id="f5fa0-392">Доступно, если entityType —  *Реестр*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-392">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="f5fa0-393">\_локальный \_ компьютер hKey</span><span class="sxs-lookup"><span data-stu-id="f5fa0-393">HKEY\_LOCAL\_MACHINE</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="f5fa0-394">registryKey</span><span class="sxs-lookup"><span data-stu-id="f5fa0-394">registryKey</span></span>                               | <span data-ttu-id="f5fa0-395">Доступно, если entityType —  *Реестр*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-395">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="f5fa0-396">Программное обеспечение \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon</span><span class="sxs-lookup"><span data-stu-id="f5fa0-396">SOFTWARE\\\\Microsoft\\\\Windows NT\\\\CurrentVersion\\\\Winlogon</span></span>                                                                                                                                                                                 |
| <span data-ttu-id="f5fa0-397">registryValueType</span><span class="sxs-lookup"><span data-stu-id="f5fa0-397">registryValueType</span></span>                         | <span data-ttu-id="f5fa0-398">Доступно, если entityType —  *Реестр*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-398">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="f5fa0-399">String</span><span class="sxs-lookup"><span data-stu-id="f5fa0-399">String</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="f5fa0-400">registryValue</span><span class="sxs-lookup"><span data-stu-id="f5fa0-400">registryValue</span></span>                             | <span data-ttu-id="f5fa0-401">Доступно, если entityType —  *Реестр*.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-401">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="f5fa0-402">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="f5fa0-402">31-00-00-00</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="f5fa0-403">deviceId</span><span class="sxs-lookup"><span data-stu-id="f5fa0-403">deviceId</span></span>                                  | <span data-ttu-id="f5fa0-404">ИДЕНТИФИКАТОР устройства, связанного с сущностью.</span><span class="sxs-lookup"><span data-stu-id="f5fa0-404">The ID, if any, of the device related to the entity.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="f5fa0-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="f5fa0-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>                                                                                                                                                                                                          |



## <a name="example"></a><span data-ttu-id="f5fa0-406">Пример</span><span class="sxs-lookup"><span data-stu-id="f5fa0-406">Example</span></span>

<span data-ttu-id="f5fa0-407">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="f5fa0-407">**Request**</span></span>

```
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="f5fa0-408">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="f5fa0-408">**Response**</span></span>
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

## <a name="related-topic"></a><span data-ttu-id="f5fa0-409">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="f5fa0-409">Related topic</span></span>
- [<span data-ttu-id="f5fa0-410">API инцидентов</span><span class="sxs-lookup"><span data-stu-id="f5fa0-410">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="f5fa0-411">Обновление инцидента</span><span class="sxs-lookup"><span data-stu-id="f5fa0-411">Update incident</span></span>](api-update-incidents.md)
