---
title: Обновление API инцидента
description: Узнайте, как обновлять инциденты с Microsoft 365 API Defender
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
ms.openlocfilehash: b50fe4672dd4cd721464c7414297efcc4a4921b7
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861507"
---
# <a name="update-incidents-api"></a><span data-ttu-id="2034d-104">Обновление API инцидентов</span><span class="sxs-lookup"><span data-stu-id="2034d-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2034d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2034d-105">**Applies to:**</span></span>

- [<span data-ttu-id="2034d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2034d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="2034d-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="2034d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2034d-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="2034d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="2034d-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="2034d-109">API description</span></span>

<span data-ttu-id="2034d-110">Обновляет свойства существующего инцидента.</span><span class="sxs-lookup"><span data-stu-id="2034d-110">Updates properties of existing incident.</span></span> <span data-ttu-id="2034d-111">Updatable свойства: ```status``` ```determination``` , , , ```classification``` и ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="2034d-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="2034d-112">Квоты, распределение ресурсов и другие ограничения</span><span class="sxs-lookup"><span data-stu-id="2034d-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="2034d-113">Вы можете сделать до 50 вызовов в минуту или 1500 вызовов в час, прежде чем нажать порог регулирования.</span><span class="sxs-lookup"><span data-stu-id="2034d-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="2034d-114">Свойство можно установить `determination` только в том `classification` случае, если установлено truePositive.</span><span class="sxs-lookup"><span data-stu-id="2034d-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="2034d-115">Если ваш запрос будет отламыт, он вернет `429` код ответа.</span><span class="sxs-lookup"><span data-stu-id="2034d-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="2034d-116">В теле ответа будет указано время, когда можно приступить к новым вызовам.</span><span class="sxs-lookup"><span data-stu-id="2034d-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="2034d-117">Разрешения</span><span class="sxs-lookup"><span data-stu-id="2034d-117">Permissions</span></span>

<span data-ttu-id="2034d-118">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="2034d-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2034d-119">Дополнительные возможности, включая выбор разрешений, см. в Microsoft 365 [API Defender.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="2034d-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="2034d-120">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="2034d-120">Permission type</span></span> | <span data-ttu-id="2034d-121">Разрешение</span><span class="sxs-lookup"><span data-stu-id="2034d-121">Permission</span></span> | <span data-ttu-id="2034d-122">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="2034d-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="2034d-123">Приложение</span><span class="sxs-lookup"><span data-stu-id="2034d-123">Application</span></span> | <span data-ttu-id="2034d-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="2034d-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="2034d-125">Чтение и написание всех инцидентов</span><span class="sxs-lookup"><span data-stu-id="2034d-125">Read and write all incidents</span></span>
<span data-ttu-id="2034d-126">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="2034d-126">Delegated (work or school account)</span></span> | <span data-ttu-id="2034d-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="2034d-127">Incident.ReadWrite</span></span> | <span data-ttu-id="2034d-128">Чтение и написание инцидентов</span><span class="sxs-lookup"><span data-stu-id="2034d-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="2034d-129">При получении маркера с помощью учетных данных пользователей пользователю необходимо иметь разрешение на обновление инцидента на портале.</span><span class="sxs-lookup"><span data-stu-id="2034d-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="2034d-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="2034d-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="2034d-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="2034d-131">Request headers</span></span>

<span data-ttu-id="2034d-132">Имя</span><span class="sxs-lookup"><span data-stu-id="2034d-132">Name</span></span> | <span data-ttu-id="2034d-133">Тип</span><span class="sxs-lookup"><span data-stu-id="2034d-133">Type</span></span> | <span data-ttu-id="2034d-134">Описание</span><span class="sxs-lookup"><span data-stu-id="2034d-134">Description</span></span>
-|-|-
<span data-ttu-id="2034d-135">Авторизация</span><span class="sxs-lookup"><span data-stu-id="2034d-135">Authorization</span></span> | <span data-ttu-id="2034d-136">String</span><span class="sxs-lookup"><span data-stu-id="2034d-136">String</span></span> | <span data-ttu-id="2034d-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2034d-137">Bearer {token}.</span></span> <span data-ttu-id="2034d-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="2034d-138">**Required**.</span></span>
<span data-ttu-id="2034d-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2034d-139">Content-Type</span></span> | <span data-ttu-id="2034d-140">String</span><span class="sxs-lookup"><span data-stu-id="2034d-140">String</span></span> | <span data-ttu-id="2034d-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="2034d-141">application/json.</span></span> <span data-ttu-id="2034d-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="2034d-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2034d-143">Тело запроса</span><span class="sxs-lookup"><span data-stu-id="2034d-143">Request body</span></span>

<span data-ttu-id="2034d-144">В теле запроса укажи значения для полей, которые должны быть обновлены.</span><span class="sxs-lookup"><span data-stu-id="2034d-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="2034d-145">Существующие свойства, не включенные в тело запроса, будут поддерживать свои значения, если их не пересчитать из-за изменений связанных значений.</span><span class="sxs-lookup"><span data-stu-id="2034d-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="2034d-146">Для лучшей производительности следует не использовать существующие значения, которые не изменились.</span><span class="sxs-lookup"><span data-stu-id="2034d-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="2034d-147">Свойство</span><span class="sxs-lookup"><span data-stu-id="2034d-147">Property</span></span> | <span data-ttu-id="2034d-148">Тип</span><span class="sxs-lookup"><span data-stu-id="2034d-148">Type</span></span> | <span data-ttu-id="2034d-149">Описание</span><span class="sxs-lookup"><span data-stu-id="2034d-149">Description</span></span>
-|-|-
<span data-ttu-id="2034d-150">status</span><span class="sxs-lookup"><span data-stu-id="2034d-150">status</span></span> | <span data-ttu-id="2034d-151">Перечисление</span><span class="sxs-lookup"><span data-stu-id="2034d-151">Enum</span></span> | <span data-ttu-id="2034d-152">Указывает текущее состояние инцидента.</span><span class="sxs-lookup"><span data-stu-id="2034d-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="2034d-153">Возможные значения: ```Active``` , ```Resolved``` и ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="2034d-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="2034d-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="2034d-154">assignedTo</span></span> | <span data-ttu-id="2034d-155">Строка</span><span class="sxs-lookup"><span data-stu-id="2034d-155">string</span></span> | <span data-ttu-id="2034d-156">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="2034d-156">Owner of the incident.</span></span>
<span data-ttu-id="2034d-157">classification</span><span class="sxs-lookup"><span data-stu-id="2034d-157">classification</span></span> | <span data-ttu-id="2034d-158">Перечисление</span><span class="sxs-lookup"><span data-stu-id="2034d-158">Enum</span></span> | <span data-ttu-id="2034d-159">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="2034d-159">Specification of the incident.</span></span> <span data-ttu-id="2034d-160">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="2034d-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="2034d-161">определение</span><span class="sxs-lookup"><span data-stu-id="2034d-161">determination</span></span> | <span data-ttu-id="2034d-162">Перечисление</span><span class="sxs-lookup"><span data-stu-id="2034d-162">Enum</span></span> | <span data-ttu-id="2034d-163">Указывает определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="2034d-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="2034d-164">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="2034d-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="2034d-165">tags</span><span class="sxs-lookup"><span data-stu-id="2034d-165">tags</span></span> | <span data-ttu-id="2034d-166">строка Список</span><span class="sxs-lookup"><span data-stu-id="2034d-166">string List</span></span> | <span data-ttu-id="2034d-167">Список тегов Инцидент.</span><span class="sxs-lookup"><span data-stu-id="2034d-167">List of Incident tags.</span></span>
<span data-ttu-id="2034d-168">comment</span><span class="sxs-lookup"><span data-stu-id="2034d-168">comment</span></span> | <span data-ttu-id="2034d-169">string</span><span class="sxs-lookup"><span data-stu-id="2034d-169">string</span></span> | <span data-ttu-id="2034d-170">Комментарий, который следует добавить к инциденту.</span><span class="sxs-lookup"><span data-stu-id="2034d-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="2034d-171">Отклик</span><span class="sxs-lookup"><span data-stu-id="2034d-171">Response</span></span>

<span data-ttu-id="2034d-172">В случае успешной работы этот метод `200 OK` возвращается.</span><span class="sxs-lookup"><span data-stu-id="2034d-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="2034d-173">Тело ответа будет содержать объект инцидента с обновленными свойствами.</span><span class="sxs-lookup"><span data-stu-id="2034d-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="2034d-174">Если инцидент с указанным ID не найден, метод `404 Not Found` возвращается.</span><span class="sxs-lookup"><span data-stu-id="2034d-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="2034d-175">Пример</span><span class="sxs-lookup"><span data-stu-id="2034d-175">Example</span></span>

<span data-ttu-id="2034d-176">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="2034d-176">**Request**</span></span>

<span data-ttu-id="2034d-177">Вот пример запроса.</span><span class="sxs-lookup"><span data-stu-id="2034d-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="2034d-178">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="2034d-178">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="2034d-179">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="2034d-179">Related articles</span></span>

- [<span data-ttu-id="2034d-180">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2034d-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="2034d-181">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="2034d-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="2034d-182">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="2034d-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="2034d-183">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="2034d-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="2034d-184">Получение списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="2034d-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="2034d-185">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="2034d-185">Incidents overview</span></span>](incidents-overview.md)
