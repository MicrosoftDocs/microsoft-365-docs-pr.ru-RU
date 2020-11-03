---
title: API обновления инцидентов
description: Сведения об обновлении инцидентов с помощью API защитника Microsoft 365
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
ms.openlocfilehash: 3f77980863b0c232166d736a6b557444df98c8ac
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844840"
---
# <a name="update-incidents-api"></a><span data-ttu-id="a0762-104">API обновления инцидентов</span><span class="sxs-lookup"><span data-stu-id="a0762-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a0762-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a0762-105">**Applies to:**</span></span>
- <span data-ttu-id="a0762-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a0762-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="a0762-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="a0762-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a0762-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="a0762-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="a0762-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="a0762-109">API description</span></span>
<span data-ttu-id="a0762-110">Обновляет свойства существующего инцидента.</span><span class="sxs-lookup"><span data-stu-id="a0762-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="a0762-111">Обновляемые свойства: ```status``` , ```determination``` , ```classification``` ```assignedTo``` и ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="a0762-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="a0762-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a0762-112">Limitations</span></span>
1. <span data-ttu-id="a0762-113">Ограничения частоты для этого API: 50 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="a0762-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="a0762-114">Можно задать значение только в том ```determination``` случае, если для классификации задано значение труепоситиве.</span><span class="sxs-lookup"><span data-stu-id="a0762-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="a0762-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="a0762-115">Permissions</span></span>
<span data-ttu-id="a0762-116">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="a0762-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a0762-117">Чтобы узнать больше, в том числе как выбирать разрешения, ознакомьтесь со статьей [доступ к API защитника Microsoft 365](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="a0762-117">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="a0762-118">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="a0762-118">Permission type</span></span> |   <span data-ttu-id="a0762-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="a0762-119">Permission</span></span>  |   <span data-ttu-id="a0762-120">Отображаемое имя разрешения</span><span class="sxs-lookup"><span data-stu-id="a0762-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a0762-121">Для приложений</span><span class="sxs-lookup"><span data-stu-id="a0762-121">Application</span></span> |   <span data-ttu-id="a0762-122">Инцидент. ReadWrite. ALL</span><span class="sxs-lookup"><span data-stu-id="a0762-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="a0762-123">"Чтение и запись всех инцидентов"</span><span class="sxs-lookup"><span data-stu-id="a0762-123">'Read and write all incidents'</span></span>
<span data-ttu-id="a0762-124">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="a0762-124">Delegated (work or school account)</span></span> | <span data-ttu-id="a0762-125">Инцидент. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a0762-125">Incident.ReadWrite</span></span> | <span data-ttu-id="a0762-126">"Чтение и запись происшествий"</span><span class="sxs-lookup"><span data-stu-id="a0762-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="a0762-127">При получении маркера с использованием учетных данных пользователя:</span><span class="sxs-lookup"><span data-stu-id="a0762-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a0762-128">Пользователь должен иметь разрешение на обновление инцидента на портале.</span><span class="sxs-lookup"><span data-stu-id="a0762-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="a0762-129">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="a0762-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="a0762-130">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="a0762-130">Request headers</span></span>

<span data-ttu-id="a0762-131">Имя</span><span class="sxs-lookup"><span data-stu-id="a0762-131">Name</span></span> | <span data-ttu-id="a0762-132">Тип</span><span class="sxs-lookup"><span data-stu-id="a0762-132">Type</span></span> | <span data-ttu-id="a0762-133">Описание</span><span class="sxs-lookup"><span data-stu-id="a0762-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="a0762-134">Авторизация</span><span class="sxs-lookup"><span data-stu-id="a0762-134">Authorization</span></span> | <span data-ttu-id="a0762-135">String</span><span class="sxs-lookup"><span data-stu-id="a0762-135">String</span></span> | <span data-ttu-id="a0762-136">Bearer {Token}.</span><span class="sxs-lookup"><span data-stu-id="a0762-136">Bearer {token}.</span></span> <span data-ttu-id="a0762-137">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="a0762-137">**Required**.</span></span>
<span data-ttu-id="a0762-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a0762-138">Content-Type</span></span> | <span data-ttu-id="a0762-139">String</span><span class="sxs-lookup"><span data-stu-id="a0762-139">String</span></span> | <span data-ttu-id="a0762-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="a0762-140">application/json.</span></span> <span data-ttu-id="a0762-141">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="a0762-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a0762-142">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="a0762-142">Request body</span></span>
<span data-ttu-id="a0762-143">В тексте запроса укажите значения для соответствующих полей, которые необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="a0762-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="a0762-144">Предыдущие значения существующих свойств, не включенных в текст запроса, будут сохранены или вычислены повторно с учетом изменений, внесенных в значения других свойств.</span><span class="sxs-lookup"><span data-stu-id="a0762-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="a0762-145">Для лучшей производительности не следует включать существующие значения, которые не были изменены.</span><span class="sxs-lookup"><span data-stu-id="a0762-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="a0762-146">Свойство</span><span class="sxs-lookup"><span data-stu-id="a0762-146">Property</span></span> | <span data-ttu-id="a0762-147">Тип</span><span class="sxs-lookup"><span data-stu-id="a0762-147">Type</span></span> | <span data-ttu-id="a0762-148">Описание</span><span class="sxs-lookup"><span data-stu-id="a0762-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="a0762-149">status</span><span class="sxs-lookup"><span data-stu-id="a0762-149">status</span></span> | <span data-ttu-id="a0762-150">Перечисление</span><span class="sxs-lookup"><span data-stu-id="a0762-150">Enum</span></span> | <span data-ttu-id="a0762-151">Указывает текущее состояние оповещения.</span><span class="sxs-lookup"><span data-stu-id="a0762-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="a0762-152">Возможные значения: ```Active``` ```Resolved``` и ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="a0762-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="a0762-153">assignedTo</span><span class="sxs-lookup"><span data-stu-id="a0762-153">assignedTo</span></span> | <span data-ttu-id="a0762-154">string</span><span class="sxs-lookup"><span data-stu-id="a0762-154">string</span></span> | <span data-ttu-id="a0762-155">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="a0762-155">Owner of the incident.</span></span>
<span data-ttu-id="a0762-156">classification</span><span class="sxs-lookup"><span data-stu-id="a0762-156">classification</span></span> | <span data-ttu-id="a0762-157">Перечисление</span><span class="sxs-lookup"><span data-stu-id="a0762-157">Enum</span></span> | <span data-ttu-id="a0762-158">Спецификация оповещения.</span><span class="sxs-lookup"><span data-stu-id="a0762-158">Specification of the alert.</span></span> <span data-ttu-id="a0762-159">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="a0762-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="a0762-160">решение</span><span class="sxs-lookup"><span data-stu-id="a0762-160">determination</span></span> | <span data-ttu-id="a0762-161">Перечисление</span><span class="sxs-lookup"><span data-stu-id="a0762-161">Enum</span></span> | <span data-ttu-id="a0762-162">Задает определение оповещения.</span><span class="sxs-lookup"><span data-stu-id="a0762-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="a0762-163">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="a0762-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="a0762-164">tags</span><span class="sxs-lookup"><span data-stu-id="a0762-164">tags</span></span> | <span data-ttu-id="a0762-165">Список строк</span><span class="sxs-lookup"><span data-stu-id="a0762-165">string List</span></span> | <span data-ttu-id="a0762-166">Список тегов инцидента.</span><span class="sxs-lookup"><span data-stu-id="a0762-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="a0762-167">Отклик</span><span class="sxs-lookup"><span data-stu-id="a0762-167">Response</span></span>
<span data-ttu-id="a0762-168">В случае успешного выполнения этот метод возвращает 200 ОК, а сущность инцидента в тексте отклика с обновленными свойствами.</span><span class="sxs-lookup"><span data-stu-id="a0762-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="a0762-169">Если инцидент с указанным идентификатором не найден — 404 не найдено.</span><span class="sxs-lookup"><span data-stu-id="a0762-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="a0762-170">Пример</span><span class="sxs-lookup"><span data-stu-id="a0762-170">Example</span></span>

<span data-ttu-id="a0762-171">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="a0762-171">**Request**</span></span>

<span data-ttu-id="a0762-172">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="a0762-172">Here is an example of the request.</span></span>

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


## <a name="related-topic"></a><span data-ttu-id="a0762-173">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="a0762-173">Related topic</span></span>
- [<span data-ttu-id="a0762-174">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="a0762-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="a0762-175">Получение списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="a0762-175">List incidents</span></span>](api-list-incidents.md)
