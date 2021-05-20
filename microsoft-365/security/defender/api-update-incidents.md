---
title: Обновление API инцидента
description: Узнайте, как обновлять инциденты с помощью Microsoft 365 Defender API
keywords: обновление, api, инцидент
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
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571785"
---
# <a name="update-incident-api"></a><span data-ttu-id="e5288-104">Обновление API инцидента</span><span class="sxs-lookup"><span data-stu-id="e5288-104">Update incident API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e5288-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e5288-105">**Applies to:**</span></span>

- <span data-ttu-id="e5288-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5288-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5288-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="e5288-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e5288-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="e5288-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="e5288-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="e5288-109">API description</span></span>

<span data-ttu-id="e5288-110">Обновляет свойства существующего инцидента.</span><span class="sxs-lookup"><span data-stu-id="e5288-110">Updates properties of existing incident.</span></span> <span data-ttu-id="e5288-111">Updatable свойства: ```status``` , ```determination``` , , , ```classification``` и ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="e5288-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="e5288-112">Квоты, распределение ресурсов и другие ограничения</span><span class="sxs-lookup"><span data-stu-id="e5288-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="e5288-113">Вы можете сделать до 50 звонков в минуту или 1500 звонков в час, прежде чем вы нажмете порог регулирования.</span><span class="sxs-lookup"><span data-stu-id="e5288-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="e5288-114">Вы можете установить свойство только `determination` в том случае, `classification` если настроено на TruePositive.</span><span class="sxs-lookup"><span data-stu-id="e5288-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="e5288-115">Если ваш запрос будет задушен, он вернет `429` код ответа.</span><span class="sxs-lookup"><span data-stu-id="e5288-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="e5288-116">Орган ответа укажет время, когда вы можете начать делать новые звонки.</span><span class="sxs-lookup"><span data-stu-id="e5288-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="e5288-117">Разрешения</span><span class="sxs-lookup"><span data-stu-id="e5288-117">Permissions</span></span>

<span data-ttu-id="e5288-118">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="e5288-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e5288-119">Чтобы узнать больше, в том числе о том, как выбрать разрешения, [Microsoft 365 API Defender.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="e5288-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="e5288-120">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="e5288-120">Permission type</span></span> | <span data-ttu-id="e5288-121">Разрешение</span><span class="sxs-lookup"><span data-stu-id="e5288-121">Permission</span></span> | <span data-ttu-id="e5288-122">Имя дисплея разрешения</span><span class="sxs-lookup"><span data-stu-id="e5288-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="e5288-123">Приложение</span><span class="sxs-lookup"><span data-stu-id="e5288-123">Application</span></span> | <span data-ttu-id="e5288-124">Инцидент.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e5288-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="e5288-125">Читать и писать все инциденты</span><span class="sxs-lookup"><span data-stu-id="e5288-125">Read and write all incidents</span></span>
<span data-ttu-id="e5288-126">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="e5288-126">Delegated (work or school account)</span></span> | <span data-ttu-id="e5288-127">Инцидент.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e5288-127">Incident.ReadWrite</span></span> | <span data-ttu-id="e5288-128">Инциденты чтения и записи</span><span class="sxs-lookup"><span data-stu-id="e5288-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="e5288-129">При получении токена с помощью учетных данных пользователя необходимо иметь разрешение на обновление инцидента на портале.</span><span class="sxs-lookup"><span data-stu-id="e5288-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="e5288-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="e5288-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="e5288-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="e5288-131">Request headers</span></span>

<span data-ttu-id="e5288-132">Имя</span><span class="sxs-lookup"><span data-stu-id="e5288-132">Name</span></span> | <span data-ttu-id="e5288-133">Тип</span><span class="sxs-lookup"><span data-stu-id="e5288-133">Type</span></span> | <span data-ttu-id="e5288-134">Описание</span><span class="sxs-lookup"><span data-stu-id="e5288-134">Description</span></span>
-|-|-
<span data-ttu-id="e5288-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="e5288-135">Authorization</span></span> | <span data-ttu-id="e5288-136">String</span><span class="sxs-lookup"><span data-stu-id="e5288-136">String</span></span> | <span data-ttu-id="e5288-137">Носитель (токен).</span><span class="sxs-lookup"><span data-stu-id="e5288-137">Bearer {token}.</span></span> <span data-ttu-id="e5288-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="e5288-138">**Required**.</span></span>
<span data-ttu-id="e5288-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e5288-139">Content-Type</span></span> | <span data-ttu-id="e5288-140">String</span><span class="sxs-lookup"><span data-stu-id="e5288-140">String</span></span> | <span data-ttu-id="e5288-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="e5288-141">application/json.</span></span> <span data-ttu-id="e5288-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="e5288-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e5288-143">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="e5288-143">Request body</span></span>

<span data-ttu-id="e5288-144">В органе запроса утетете значения полей, которые должны быть обновлены.</span><span class="sxs-lookup"><span data-stu-id="e5288-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="e5288-145">Существующие свойства, не включенные в тело запроса, сохранят свои значения, если только они не должны быть пересчитаны из-за изменений связанных значений.</span><span class="sxs-lookup"><span data-stu-id="e5288-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="e5288-146">Для лучшей производительности следует опустить существующие значения, которые не изменились.</span><span class="sxs-lookup"><span data-stu-id="e5288-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="e5288-147">Свойство</span><span class="sxs-lookup"><span data-stu-id="e5288-147">Property</span></span> | <span data-ttu-id="e5288-148">Тип</span><span class="sxs-lookup"><span data-stu-id="e5288-148">Type</span></span> | <span data-ttu-id="e5288-149">Описание</span><span class="sxs-lookup"><span data-stu-id="e5288-149">Description</span></span>
-|-|-
<span data-ttu-id="e5288-150">status</span><span class="sxs-lookup"><span data-stu-id="e5288-150">status</span></span> | <span data-ttu-id="e5288-151">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e5288-151">Enum</span></span> | <span data-ttu-id="e5288-152">Уточняется текущее состояние происшествия.</span><span class="sxs-lookup"><span data-stu-id="e5288-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="e5288-153">Возможные значения: ```Active``` ```Resolved``` , и ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="e5288-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="e5288-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="e5288-154">assignedTo</span></span> | <span data-ttu-id="e5288-155">Строка</span><span class="sxs-lookup"><span data-stu-id="e5288-155">string</span></span> | <span data-ttu-id="e5288-156">Владелец инцидента.</span><span class="sxs-lookup"><span data-stu-id="e5288-156">Owner of the incident.</span></span>
<span data-ttu-id="e5288-157">classification</span><span class="sxs-lookup"><span data-stu-id="e5288-157">classification</span></span> | <span data-ttu-id="e5288-158">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e5288-158">Enum</span></span> | <span data-ttu-id="e5288-159">Спецификация инцидента.</span><span class="sxs-lookup"><span data-stu-id="e5288-159">Specification of the incident.</span></span> <span data-ttu-id="e5288-160">Возможные значения: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="e5288-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="e5288-161">решимость</span><span class="sxs-lookup"><span data-stu-id="e5288-161">determination</span></span> | <span data-ttu-id="e5288-162">Перечисление</span><span class="sxs-lookup"><span data-stu-id="e5288-162">Enum</span></span> | <span data-ttu-id="e5288-163">Уточняется определение инцидента.</span><span class="sxs-lookup"><span data-stu-id="e5288-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="e5288-164">Возможные значения: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="e5288-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="e5288-165">tags</span><span class="sxs-lookup"><span data-stu-id="e5288-165">tags</span></span> | <span data-ttu-id="e5288-166">строка Список</span><span class="sxs-lookup"><span data-stu-id="e5288-166">string List</span></span> | <span data-ttu-id="e5288-167">Список тегов инцидента.</span><span class="sxs-lookup"><span data-stu-id="e5288-167">List of Incident tags.</span></span>
<span data-ttu-id="e5288-168">comment</span><span class="sxs-lookup"><span data-stu-id="e5288-168">comment</span></span> | <span data-ttu-id="e5288-169">string</span><span class="sxs-lookup"><span data-stu-id="e5288-169">string</span></span> | <span data-ttu-id="e5288-170">Комментарий, который будет добавлен к инциденту.</span><span class="sxs-lookup"><span data-stu-id="e5288-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="e5288-171">Отклик</span><span class="sxs-lookup"><span data-stu-id="e5288-171">Response</span></span>

<span data-ttu-id="e5288-172">В случае успеха этот метод `200 OK` возвращается.</span><span class="sxs-lookup"><span data-stu-id="e5288-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="e5288-173">Орган реагирования будет содержать сущность инцидента с обновленными свойствами.</span><span class="sxs-lookup"><span data-stu-id="e5288-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="e5288-174">Если инцидент с указанным идентификатором не найден, метод `404 Not Found` возвращается.</span><span class="sxs-lookup"><span data-stu-id="e5288-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="e5288-175">Пример</span><span class="sxs-lookup"><span data-stu-id="e5288-175">Example</span></span>

<span data-ttu-id="e5288-176">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="e5288-176">**Request**</span></span>

<span data-ttu-id="e5288-177">Вот пример запроса.</span><span class="sxs-lookup"><span data-stu-id="e5288-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="e5288-178">**Отклик**</span><span class="sxs-lookup"><span data-stu-id="e5288-178">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="e5288-179">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="e5288-179">Related articles</span></span>

- [<span data-ttu-id="e5288-180">Доступ к Microsoft 365-имуме защитника</span><span class="sxs-lookup"><span data-stu-id="e5288-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="e5288-181">Узнайте об ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="e5288-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="e5288-182">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="e5288-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="e5288-183">Программные интерфейсы, относящиеся к инцидентам</span><span class="sxs-lookup"><span data-stu-id="e5288-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="e5288-184">Получение списка инцидентов</span><span class="sxs-lookup"><span data-stu-id="e5288-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="e5288-185">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="e5288-185">Incidents overview</span></span>](incidents-overview.md)
