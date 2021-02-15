---
title: API обновления инцидентов
description: Узнайте, как обновлять инциденты с помощью API Защитника Microsoft 365
keywords: обновление, API, инцидент
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929074"
---
# <a name="update-incidents-api"></a><span data-ttu-id="a6107-104">API обновления инцидентов</span><span class="sxs-lookup"><span data-stu-id="a6107-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a6107-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a6107-105">**Applies to:**</span></span>

- <span data-ttu-id="a6107-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6107-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6107-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="a6107-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a6107-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="a6107-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="a6107-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="a6107-109">API description</span></span>

<span data-ttu-id="a6107-110">Обновляет свойства существующего инцидента.</span><span class="sxs-lookup"><span data-stu-id="a6107-110">Updates properties of existing incident.</span></span> <span data-ttu-id="a6107-111">Updatable properties are: ```status``` , , , , и ```determination``` ```classification``` ```assignedTo``` ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="a6107-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="a6107-112">Квоты, выделение ресурсов и другие ограничения</span><span class="sxs-lookup"><span data-stu-id="a6107-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="a6107-113">Вы можете делать до 50 вызовов в минуту или 1500 вызовов в час, прежде чем нажать порог регулирования.</span><span class="sxs-lookup"><span data-stu-id="a6107-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="a6107-114">Вы можете установить `determination` свойство, только если `classification` установлено свойство TruePositive.</span><span class="sxs-lookup"><span data-stu-id="a6107-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="a6107-115">Если ваш запрос регулирование, он возвращает `429` код ответа.</span><span class="sxs-lookup"><span data-stu-id="a6107-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="a6107-116">В теле ответа будет указано время начала новых вызовов.</span><span class="sxs-lookup"><span data-stu-id="a6107-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="a6107-117">Разрешения</span><span class="sxs-lookup"><span data-stu-id="a6107-117">Permissions</span></span>

<span data-ttu-id="a6107-118">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="a6107-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a6107-119">Чтобы узнать больше, включая выбор разрешений, [см. API Access в Microsoft 365 Defender.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="a6107-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="a6107-120">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="a6107-120">Permission type</span></span> | <span data-ttu-id="a6107-121">Разрешение</span><span class="sxs-lookup"><span data-stu-id="a6107-121">Permission</span></span> | <span data-ttu-id="a6107-122">Отображаемая имя разрешения</span><span class="sxs-lookup"><span data-stu-id="a6107-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="a6107-123">Для приложений</span><span class="sxs-lookup"><span data-stu-id="a6107-123">Application</span></span> | <span data-ttu-id="a6107-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="a6107-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="a6107-125">Чтение и написание всех инцидентов</span><span class="sxs-lookup"><span data-stu-id="a6107-125">Read and write all incidents</span></span>
<span data-ttu-id="a6107-126">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="a6107-126">Delegated (work or school account)</span></span> | <span data-ttu-id="a6107-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a6107-127">Incident.ReadWrite</span></span> | <span data-ttu-id="a6107-128">Чтение и написание инцидентов</span><span class="sxs-lookup"><span data-stu-id="a6107-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="a6107-129">При получении маркера с использованием учетных данных пользователя у пользователя должно быть разрешение на обновление инцидента на портале.</span><span class="sxs-lookup"><span data-stu-id="a6107-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="a6107-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="a6107-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="a6107-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="a6107-131">Request headers</span></span>

<span data-ttu-id="a6107-132">Имя</span><span class="sxs-lookup"><span data-stu-id="a6107-132">Name</span></span> | <span data-ttu-id="a6107-133">Тип</span><span class="sxs-lookup"><span data-stu-id="a6107-133">Type</span></span> | <span data-ttu-id="a6107-134">Описание</span><span class="sxs-lookup"><span data-stu-id="a6107-134">Description</span></span>
-|-|-
<span data-ttu-id="a6107-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="a6107-135">Authorization</span></span> | <span data-ttu-id="a6107-136">String</span><span class="sxs-lookup"><span data-stu-id="a6107-136">String</span></span> | <span data-ttu-id="a6107-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a6107-137">Bearer {token}.</span></span> <span data-ttu-id="a6107-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="a6107-138">**Required**.</span></span>
<span data-ttu-id="a6107-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a6107-139">Content-Type</span></span> | <span data-ttu-id="a6107-140">String</span><span class="sxs-lookup"><span data-stu-id="a6107-140">String</span></span> | <span data-ttu-id="a6107-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="a6107-141">application/json.</span></span> <span data-ttu-id="a6107-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="a6107-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a6107-143">Основной текст запроса</span><span class="sxs-lookup"><span data-stu-id="a6107-143">Request body</span></span>

<span data-ttu-id="a6107-144">В теле запроса укавите значения для полей, которые необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="a6107-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="a6107-145">Существующие свойства, не включенные в тело запроса, сохраняют свои значения, если их не придется пересчитывать из-за изменений связанных значений.</span><span class="sxs-lookup"><span data-stu-id="a6107-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="a6107-146">Для лучшей производительности следует опустить существующие значения, которые не изменились.</span><span class="sxs-lookup"><span data-stu-id="a6107-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="a6107-147">Свойство</span><span class="sxs-lookup"><span data-stu-id="a6107-147">Property</span></span> | <span data-ttu-id="a6107-148">Тип</span><span class="sxs-lookup"><span data-stu-id="a6107-148">Type</span></span> | <span data-ttu-id="a6107-149">Описание</span><span class="sxs-lookup"><span data-stu-id="a6107-149">Description</span></span>
-|-|-
<span data-ttu-id="a6107-150">status</span><span class="sxs-lookup"><span data-stu-id="a6107-150">status</span></span> | <span data-ttu-id="a6107-151">Перечисление</span><span class="sxs-lookup"><span data-stu-id="a6107-151">Enum</span></span> | <span data-ttu-id="a6107-152">Указывает текущее состояние оповещения.</span><span class="sxs-lookup"><span data-stu-id="a6107-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="a6107-153">Возможные значения: ```Active``` , ```Resolved``` и ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="a6107-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="a6107-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="a6107-154">assignedTo</span></span> | <span data-ttu-id="a6107-155">string</span><span class="sxs-lookup"><span data-stu-id="a6107-155">string</span></span> | <span data-ttu-id="a6107-156">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="a6107-156">Owner of the incident.</span></span>
<span data-ttu-id="a6107-157">classification</span><span class="sxs-lookup"><span data-stu-id="a6107-157">classification</span></span> | <span data-ttu-id="a6107-158">Перечисление</span><span class="sxs-lookup"><span data-stu-id="a6107-158">Enum</span></span> | <span data-ttu-id="a6107-159">Спецификация оповещения.</span><span class="sxs-lookup"><span data-stu-id="a6107-159">Specification of the alert.</span></span> <span data-ttu-id="a6107-160">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="a6107-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="a6107-161">определение</span><span class="sxs-lookup"><span data-stu-id="a6107-161">determination</span></span> | <span data-ttu-id="a6107-162">Перечисление</span><span class="sxs-lookup"><span data-stu-id="a6107-162">Enum</span></span> | <span data-ttu-id="a6107-163">Определяет определение оповещения.</span><span class="sxs-lookup"><span data-stu-id="a6107-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="a6107-164">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="a6107-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="a6107-165">tags</span><span class="sxs-lookup"><span data-stu-id="a6107-165">tags</span></span> | <span data-ttu-id="a6107-166">string List</span><span class="sxs-lookup"><span data-stu-id="a6107-166">string List</span></span> | <span data-ttu-id="a6107-167">Список тегов инцидента.</span><span class="sxs-lookup"><span data-stu-id="a6107-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="a6107-168">Отклик</span><span class="sxs-lookup"><span data-stu-id="a6107-168">Response</span></span>

<span data-ttu-id="a6107-169">В случае успеха этот метод возвращает `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="a6107-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="a6107-170">Тело ответа будет содержать сущность инцидента с обновленными свойствами.</span><span class="sxs-lookup"><span data-stu-id="a6107-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="a6107-171">Если инцидент с указанным ИД не найден, метод `404 Not Found` возвращается.</span><span class="sxs-lookup"><span data-stu-id="a6107-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="a6107-172">Пример</span><span class="sxs-lookup"><span data-stu-id="a6107-172">Example</span></span>

<span data-ttu-id="a6107-173">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="a6107-173">**Request**</span></span>

<span data-ttu-id="a6107-174">Вот пример запроса.</span><span class="sxs-lookup"><span data-stu-id="a6107-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="a6107-175">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="a6107-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="a6107-176">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a6107-176">Related articles</span></span>

- [<span data-ttu-id="a6107-177">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6107-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="a6107-178">Узнайте об ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="a6107-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="a6107-179">Коды ошибок</span><span class="sxs-lookup"><span data-stu-id="a6107-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="a6107-180">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="a6107-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="a6107-181">Получение списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="a6107-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="a6107-182">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="a6107-182">Incidents overview</span></span>](incidents-overview.md)
