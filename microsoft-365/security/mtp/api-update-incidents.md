---
title: API обновления инцидентов
description: Узнайте, как обновлять инциденты с помощью API защиты от угроз Майкрософт
keywords: обновление, API, инцидент
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
ms.openlocfilehash: 8ad47453c7163bfac99c17f42986b818cdca603f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203644"
---
# <a name="update-incidents-api"></a><span data-ttu-id="3cbd6-104">API обновления инцидентов</span><span class="sxs-lookup"><span data-stu-id="3cbd6-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3cbd6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3cbd6-105">**Applies to:**</span></span>
- <span data-ttu-id="3cbd6-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="3cbd6-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="3cbd6-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3cbd6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="3cbd6-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="3cbd6-109">API description</span></span>
<span data-ttu-id="3cbd6-110">Обновляет свойства существующего инцидента.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="3cbd6-111">Обновляемые свойства: ```status``` , ```determination``` , ```classification``` ```assignedTo``` и ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="3cbd6-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="3cbd6-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3cbd6-112">Limitations</span></span>
1. <span data-ttu-id="3cbd6-113">Ограничения частоты для этого API: 50 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="3cbd6-114">Можно задать значение только в том ```determination``` случае, если для классификации задано значение труепоситиве.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="3cbd6-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="3cbd6-115">Permissions</span></span>
<span data-ttu-id="3cbd6-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3cbd6-117">Чтобы узнать больше, в том числе как выбирать разрешения, ознакомьтесь со статьей [доступ к API Microsoft Threat protection](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="3cbd6-117">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="3cbd6-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="3cbd6-118">Permission type</span></span> |   <span data-ttu-id="3cbd6-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="3cbd6-119">Permission</span></span>  |   <span data-ttu-id="3cbd6-120">Отображаемое имя разрешения</span><span class="sxs-lookup"><span data-stu-id="3cbd6-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3cbd6-121">Для приложений</span><span class="sxs-lookup"><span data-stu-id="3cbd6-121">Application</span></span> |   <span data-ttu-id="3cbd6-122">Инцидент. ReadWrite. ALL</span><span class="sxs-lookup"><span data-stu-id="3cbd6-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="3cbd6-123">"Чтение и запись всех инцидентов"</span><span class="sxs-lookup"><span data-stu-id="3cbd6-123">'Read and write all incidents'</span></span>
<span data-ttu-id="3cbd6-124">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="3cbd6-124">Delegated (work or school account)</span></span> | <span data-ttu-id="3cbd6-125">Инцидент. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3cbd6-125">Incident.ReadWrite</span></span> | <span data-ttu-id="3cbd6-126">"Чтение и запись происшествий"</span><span class="sxs-lookup"><span data-stu-id="3cbd6-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="3cbd6-127">При получении маркера с использованием учетных данных пользователя:</span><span class="sxs-lookup"><span data-stu-id="3cbd6-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3cbd6-128">Пользователь должен иметь разрешение на обновление инцидента на портале.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="3cbd6-129">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="3cbd6-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="3cbd6-130">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="3cbd6-130">Request headers</span></span>

<span data-ttu-id="3cbd6-131">Имя</span><span class="sxs-lookup"><span data-stu-id="3cbd6-131">Name</span></span> | <span data-ttu-id="3cbd6-132">Тип</span><span class="sxs-lookup"><span data-stu-id="3cbd6-132">Type</span></span> | <span data-ttu-id="3cbd6-133">Описание</span><span class="sxs-lookup"><span data-stu-id="3cbd6-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="3cbd6-134">Авторизация</span><span class="sxs-lookup"><span data-stu-id="3cbd6-134">Authorization</span></span> | <span data-ttu-id="3cbd6-135">String</span><span class="sxs-lookup"><span data-stu-id="3cbd6-135">String</span></span> | <span data-ttu-id="3cbd6-136">Bearer {Token}.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-136">Bearer {token}.</span></span> <span data-ttu-id="3cbd6-137">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-137">**Required**.</span></span>
<span data-ttu-id="3cbd6-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3cbd6-138">Content-Type</span></span> | <span data-ttu-id="3cbd6-139">String</span><span class="sxs-lookup"><span data-stu-id="3cbd6-139">String</span></span> | <span data-ttu-id="3cbd6-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-140">application/json.</span></span> <span data-ttu-id="3cbd6-141">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3cbd6-142">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="3cbd6-142">Request body</span></span>
<span data-ttu-id="3cbd6-143">В тексте запроса укажите значения для соответствующих полей, которые необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="3cbd6-144">Предыдущие значения существующих свойств, не включенных в текст запроса, будут сохранены или вычислены повторно с учетом изменений, внесенных в значения других свойств.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="3cbd6-145">Для лучшей производительности не следует включать существующие значения, которые не были изменены.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="3cbd6-146">Свойство</span><span class="sxs-lookup"><span data-stu-id="3cbd6-146">Property</span></span> | <span data-ttu-id="3cbd6-147">Тип</span><span class="sxs-lookup"><span data-stu-id="3cbd6-147">Type</span></span> | <span data-ttu-id="3cbd6-148">Описание</span><span class="sxs-lookup"><span data-stu-id="3cbd6-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="3cbd6-149">status</span><span class="sxs-lookup"><span data-stu-id="3cbd6-149">status</span></span> | <span data-ttu-id="3cbd6-150">Перечисление</span><span class="sxs-lookup"><span data-stu-id="3cbd6-150">Enum</span></span> | <span data-ttu-id="3cbd6-151">Указывает текущее состояние оповещения.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="3cbd6-152">Возможные значения: ```Active``` ```Resolved``` и ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="3cbd6-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="3cbd6-153">assignedTo</span><span class="sxs-lookup"><span data-stu-id="3cbd6-153">assignedTo</span></span> | <span data-ttu-id="3cbd6-154">string</span><span class="sxs-lookup"><span data-stu-id="3cbd6-154">string</span></span> | <span data-ttu-id="3cbd6-155">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-155">Owner of the incident.</span></span>
<span data-ttu-id="3cbd6-156">classification</span><span class="sxs-lookup"><span data-stu-id="3cbd6-156">classification</span></span> | <span data-ttu-id="3cbd6-157">Перечисление</span><span class="sxs-lookup"><span data-stu-id="3cbd6-157">Enum</span></span> | <span data-ttu-id="3cbd6-158">Спецификация оповещения.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-158">Specification of the alert.</span></span> <span data-ttu-id="3cbd6-159">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="3cbd6-160">решение</span><span class="sxs-lookup"><span data-stu-id="3cbd6-160">determination</span></span> | <span data-ttu-id="3cbd6-161">Перечисление</span><span class="sxs-lookup"><span data-stu-id="3cbd6-161">Enum</span></span> | <span data-ttu-id="3cbd6-162">Задает определение оповещения.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="3cbd6-163">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="3cbd6-164">tags</span><span class="sxs-lookup"><span data-stu-id="3cbd6-164">tags</span></span> | <span data-ttu-id="3cbd6-165">Список строк</span><span class="sxs-lookup"><span data-stu-id="3cbd6-165">string List</span></span> | <span data-ttu-id="3cbd6-166">Список тегов инцидента.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="3cbd6-167">Отклик</span><span class="sxs-lookup"><span data-stu-id="3cbd6-167">Response</span></span>
<span data-ttu-id="3cbd6-168">В случае успешного выполнения этот метод возвращает 200 ОК, а сущность инцидента в тексте отклика с обновленными свойствами.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="3cbd6-169">Если инцидент с указанным идентификатором не найден — 404 не найдено.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3cbd6-170">Пример</span><span class="sxs-lookup"><span data-stu-id="3cbd6-170">Example</span></span>

<span data-ttu-id="3cbd6-171">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="3cbd6-171">**Request**</span></span>

<span data-ttu-id="3cbd6-172">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="3cbd6-172">Here is an example of the request.</span></span>

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a><span data-ttu-id="3cbd6-173">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="3cbd6-173">Related topic</span></span>
- [<span data-ttu-id="3cbd6-174">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="3cbd6-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="3cbd6-175">Получение списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="3cbd6-175">List incidents</span></span>](api-list-incidents.md)
