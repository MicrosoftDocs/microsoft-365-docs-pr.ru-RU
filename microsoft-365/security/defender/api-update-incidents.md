---
title: Обновление API инцидента
description: Узнайте, как обновлять инциденты с Microsoft 365 Defender API
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 60f1209331862eb21d3b1949265f0873dcf2e5a7
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287823"
---
# <a name="update-incidents-api"></a><span data-ttu-id="ad88b-104">Обновление API инцидентов</span><span class="sxs-lookup"><span data-stu-id="ad88b-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ad88b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ad88b-105">**Applies to:**</span></span>

- [<span data-ttu-id="ad88b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad88b-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="ad88b-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="ad88b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ad88b-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="ad88b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="ad88b-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="ad88b-109">API description</span></span>

<span data-ttu-id="ad88b-110">Обновляет свойства существующего инцидента.</span><span class="sxs-lookup"><span data-stu-id="ad88b-110">Updates properties of existing incident.</span></span> <span data-ttu-id="ad88b-111">Updatable свойства: ```status``` ```determination``` , , , ```classification``` и ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="ad88b-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="ad88b-112">Квоты, распределение ресурсов и другие ограничения</span><span class="sxs-lookup"><span data-stu-id="ad88b-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="ad88b-113">Вы можете сделать до 50 вызовов в минуту или 1500 вызовов в час, прежде чем нажать порог регулирования.</span><span class="sxs-lookup"><span data-stu-id="ad88b-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="ad88b-114">Свойство можно установить `determination` только в том `classification` случае, если установлено truePositive.</span><span class="sxs-lookup"><span data-stu-id="ad88b-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="ad88b-115">Если ваш запрос будет отламыт, он вернет `429` код ответа.</span><span class="sxs-lookup"><span data-stu-id="ad88b-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="ad88b-116">В теле ответа будет указано время, когда можно приступить к новым вызовам.</span><span class="sxs-lookup"><span data-stu-id="ad88b-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="ad88b-117">Разрешения</span><span class="sxs-lookup"><span data-stu-id="ad88b-117">Permissions</span></span>

<span data-ttu-id="ad88b-118">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="ad88b-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ad88b-119">Дополнительные возможности, в том числе выбор разрешений, см. в Microsoft 365 Defender [API.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="ad88b-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="ad88b-120">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="ad88b-120">Permission type</span></span> | <span data-ttu-id="ad88b-121">Разрешение</span><span class="sxs-lookup"><span data-stu-id="ad88b-121">Permission</span></span> | <span data-ttu-id="ad88b-122">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="ad88b-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="ad88b-123">Application</span><span class="sxs-lookup"><span data-stu-id="ad88b-123">Application</span></span> | <span data-ttu-id="ad88b-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="ad88b-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="ad88b-125">Чтение и написание всех инцидентов</span><span class="sxs-lookup"><span data-stu-id="ad88b-125">Read and write all incidents</span></span>
<span data-ttu-id="ad88b-126">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="ad88b-126">Delegated (work or school account)</span></span> | <span data-ttu-id="ad88b-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ad88b-127">Incident.ReadWrite</span></span> | <span data-ttu-id="ad88b-128">Чтение и написание инцидентов</span><span class="sxs-lookup"><span data-stu-id="ad88b-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="ad88b-129">При получении маркера с помощью учетных данных пользователей пользователю необходимо иметь разрешение на обновление инцидента на портале.</span><span class="sxs-lookup"><span data-stu-id="ad88b-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="ad88b-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="ad88b-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="ad88b-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="ad88b-131">Request headers</span></span>

<span data-ttu-id="ad88b-132">Имя</span><span class="sxs-lookup"><span data-stu-id="ad88b-132">Name</span></span> | <span data-ttu-id="ad88b-133">Тип</span><span class="sxs-lookup"><span data-stu-id="ad88b-133">Type</span></span> | <span data-ttu-id="ad88b-134">Описание</span><span class="sxs-lookup"><span data-stu-id="ad88b-134">Description</span></span>
-|-|-
<span data-ttu-id="ad88b-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="ad88b-135">Authorization</span></span> | <span data-ttu-id="ad88b-136">Строка</span><span class="sxs-lookup"><span data-stu-id="ad88b-136">String</span></span> | <span data-ttu-id="ad88b-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ad88b-137">Bearer {token}.</span></span> <span data-ttu-id="ad88b-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="ad88b-138">**Required**.</span></span>
<span data-ttu-id="ad88b-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ad88b-139">Content-Type</span></span> | <span data-ttu-id="ad88b-140">String</span><span class="sxs-lookup"><span data-stu-id="ad88b-140">String</span></span> | <span data-ttu-id="ad88b-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="ad88b-141">application/json.</span></span> <span data-ttu-id="ad88b-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="ad88b-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ad88b-143">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="ad88b-143">Request body</span></span>

<span data-ttu-id="ad88b-144">В теле запроса укажи значения для полей, которые должны быть обновлены.</span><span class="sxs-lookup"><span data-stu-id="ad88b-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="ad88b-145">Существующие свойства, не включенные в тело запроса, будут поддерживать свои значения, если их не пересчитать из-за изменений связанных значений.</span><span class="sxs-lookup"><span data-stu-id="ad88b-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="ad88b-146">Для лучшей производительности следует не использовать существующие значения, которые не изменились.</span><span class="sxs-lookup"><span data-stu-id="ad88b-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="ad88b-147">Свойство</span><span class="sxs-lookup"><span data-stu-id="ad88b-147">Property</span></span> | <span data-ttu-id="ad88b-148">Тип</span><span class="sxs-lookup"><span data-stu-id="ad88b-148">Type</span></span> | <span data-ttu-id="ad88b-149">Описание</span><span class="sxs-lookup"><span data-stu-id="ad88b-149">Description</span></span>
-|-|-
<span data-ttu-id="ad88b-150">status</span><span class="sxs-lookup"><span data-stu-id="ad88b-150">status</span></span> | <span data-ttu-id="ad88b-151">Перечисление</span><span class="sxs-lookup"><span data-stu-id="ad88b-151">Enum</span></span> | <span data-ttu-id="ad88b-152">Указывает текущее состояние инцидента.</span><span class="sxs-lookup"><span data-stu-id="ad88b-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="ad88b-153">Возможные значения: ```Active``` , ```Resolved``` и ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="ad88b-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="ad88b-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="ad88b-154">assignedTo</span></span> | <span data-ttu-id="ad88b-155">Строка</span><span class="sxs-lookup"><span data-stu-id="ad88b-155">string</span></span> | <span data-ttu-id="ad88b-156">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="ad88b-156">Owner of the incident.</span></span>
<span data-ttu-id="ad88b-157">classification</span><span class="sxs-lookup"><span data-stu-id="ad88b-157">classification</span></span> | <span data-ttu-id="ad88b-158">Перечисление</span><span class="sxs-lookup"><span data-stu-id="ad88b-158">Enum</span></span> | <span data-ttu-id="ad88b-159">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="ad88b-159">Specification of the incident.</span></span> <span data-ttu-id="ad88b-160">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="ad88b-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="ad88b-161">определение</span><span class="sxs-lookup"><span data-stu-id="ad88b-161">determination</span></span> | <span data-ttu-id="ad88b-162">Перечисление</span><span class="sxs-lookup"><span data-stu-id="ad88b-162">Enum</span></span> | <span data-ttu-id="ad88b-163">Указывает определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="ad88b-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="ad88b-164">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="ad88b-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="ad88b-165">tags</span><span class="sxs-lookup"><span data-stu-id="ad88b-165">tags</span></span> | <span data-ttu-id="ad88b-166">строка Список</span><span class="sxs-lookup"><span data-stu-id="ad88b-166">string List</span></span> | <span data-ttu-id="ad88b-167">Список тегов Инцидент.</span><span class="sxs-lookup"><span data-stu-id="ad88b-167">List of Incident tags.</span></span>
<span data-ttu-id="ad88b-168">comment</span><span class="sxs-lookup"><span data-stu-id="ad88b-168">comment</span></span> | <span data-ttu-id="ad88b-169">string</span><span class="sxs-lookup"><span data-stu-id="ad88b-169">string</span></span> | <span data-ttu-id="ad88b-170">Комментарий, который следует добавить к инциденту.</span><span class="sxs-lookup"><span data-stu-id="ad88b-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="ad88b-171">Отклик</span><span class="sxs-lookup"><span data-stu-id="ad88b-171">Response</span></span>

<span data-ttu-id="ad88b-172">В случае успешной работы этот метод `200 OK` возвращается.</span><span class="sxs-lookup"><span data-stu-id="ad88b-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="ad88b-173">Тело ответа будет содержать объект инцидента с обновленными свойствами.</span><span class="sxs-lookup"><span data-stu-id="ad88b-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="ad88b-174">Если инцидент с указанным ID не найден, метод `404 Not Found` возвращается.</span><span class="sxs-lookup"><span data-stu-id="ad88b-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="ad88b-175">Пример</span><span class="sxs-lookup"><span data-stu-id="ad88b-175">Example</span></span>

<span data-ttu-id="ad88b-176">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="ad88b-176">**Request**</span></span>

<span data-ttu-id="ad88b-177">Вот пример запроса.</span><span class="sxs-lookup"><span data-stu-id="ad88b-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="ad88b-178">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="ad88b-178">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a><span data-ttu-id="ad88b-179">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="ad88b-179">Related articles</span></span>

- [<span data-ttu-id="ad88b-180">Доступ к Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="ad88b-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="ad88b-181">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="ad88b-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="ad88b-182">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="ad88b-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="ad88b-183">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="ad88b-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="ad88b-184">Получение списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="ad88b-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="ad88b-185">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="ad88b-185">Incidents overview</span></span>](incidents-overview.md)
