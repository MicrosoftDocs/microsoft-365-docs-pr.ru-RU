---
title: Тип ресурса индикатора
description: Укажите сведения об объекте и определите срок действия индикатора с помощью Microsoft Defender для конечной точки.
keywords: apis, поддерживаемые apis, get, TiIndicator, Indicator, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771385"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="bcdca-104">Тип ресурса индикатора</span><span class="sxs-lookup"><span data-stu-id="bcdca-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bcdca-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bcdca-105">**Applies to:**</span></span>
- [<span data-ttu-id="bcdca-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="bcdca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bcdca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bcdca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bcdca-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="bcdca-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bcdca-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="bcdca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="bcdca-110">См. [соответствующую страницу Индикаторы](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) на портале.</span><span class="sxs-lookup"><span data-stu-id="bcdca-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="bcdca-111">Метод</span><span class="sxs-lookup"><span data-stu-id="bcdca-111">Method</span></span>|<span data-ttu-id="bcdca-112">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="bcdca-112">Return Type</span></span> |<span data-ttu-id="bcdca-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bcdca-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="bcdca-114">Список индикаторов</span><span class="sxs-lookup"><span data-stu-id="bcdca-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="bcdca-115">[Индикатор](ti-indicator.md) Коллекция</span><span class="sxs-lookup"><span data-stu-id="bcdca-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="bcdca-116">[Сущностями индикатора](ti-indicator.md) списка.</span><span class="sxs-lookup"><span data-stu-id="bcdca-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="bcdca-117">Индикатор отправки</span><span class="sxs-lookup"><span data-stu-id="bcdca-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="bcdca-118">Индикатор</span><span class="sxs-lookup"><span data-stu-id="bcdca-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="bcdca-119">Отправка или обновление [объекта индикатора.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="bcdca-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="bcdca-120">Импорт индикаторов</span><span class="sxs-lookup"><span data-stu-id="bcdca-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="bcdca-121">[Индикатор](ti-indicator.md) Коллекция</span><span class="sxs-lookup"><span data-stu-id="bcdca-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="bcdca-122">Отправка или [обновление сущностями](ti-indicator.md) Индикаторы.</span><span class="sxs-lookup"><span data-stu-id="bcdca-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="bcdca-123">Удалить индикатор</span><span class="sxs-lookup"><span data-stu-id="bcdca-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="bcdca-124">Содержимое отсутствует</span><span class="sxs-lookup"><span data-stu-id="bcdca-124">No Content</span></span> | <span data-ttu-id="bcdca-125">Удаляет объект [Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="bcdca-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="bcdca-126">Свойства</span><span class="sxs-lookup"><span data-stu-id="bcdca-126">Properties</span></span>
<span data-ttu-id="bcdca-127">Свойство</span><span class="sxs-lookup"><span data-stu-id="bcdca-127">Property</span></span> |  <span data-ttu-id="bcdca-128">Тип</span><span class="sxs-lookup"><span data-stu-id="bcdca-128">Type</span></span>    |   <span data-ttu-id="bcdca-129">Описание</span><span class="sxs-lookup"><span data-stu-id="bcdca-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="bcdca-130">id</span><span class="sxs-lookup"><span data-stu-id="bcdca-130">id</span></span> | <span data-ttu-id="bcdca-131">String</span><span class="sxs-lookup"><span data-stu-id="bcdca-131">String</span></span> | <span data-ttu-id="bcdca-132">Удостоверение сущности [индикатора.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="bcdca-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="bcdca-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="bcdca-133">indicatorValue</span></span> | <span data-ttu-id="bcdca-134">String</span><span class="sxs-lookup"><span data-stu-id="bcdca-134">String</span></span> | <span data-ttu-id="bcdca-135">Значение [индикатора](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="bcdca-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="bcdca-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="bcdca-136">indicatorType</span></span> | <span data-ttu-id="bcdca-137">Перечисление</span><span class="sxs-lookup"><span data-stu-id="bcdca-137">Enum</span></span> | <span data-ttu-id="bcdca-138">Тип индикатора.</span><span class="sxs-lookup"><span data-stu-id="bcdca-138">Type of the indicator.</span></span> <span data-ttu-id="bcdca-139">Возможные значения: "FileSha1", "FileSha256", "IpAddress", "DomainName" и "URL".</span><span class="sxs-lookup"><span data-stu-id="bcdca-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="bcdca-140">приложение</span><span class="sxs-lookup"><span data-stu-id="bcdca-140">application</span></span> | <span data-ttu-id="bcdca-141">String</span><span class="sxs-lookup"><span data-stu-id="bcdca-141">String</span></span> | <span data-ttu-id="bcdca-142">Приложение, связанное с индикатором.</span><span class="sxs-lookup"><span data-stu-id="bcdca-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="bcdca-143">action</span><span class="sxs-lookup"><span data-stu-id="bcdca-143">action</span></span> | <span data-ttu-id="bcdca-144">Перечисление</span><span class="sxs-lookup"><span data-stu-id="bcdca-144">Enum</span></span> | <span data-ttu-id="bcdca-145">Действие, которое будет принято, если индикатор будет обнаружен в организации.</span><span class="sxs-lookup"><span data-stu-id="bcdca-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="bcdca-146">Возможные значения: "Alert", "AlertAndBlock" и "Allowed".</span><span class="sxs-lookup"><span data-stu-id="bcdca-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="bcdca-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="bcdca-147">sourceType</span></span> | <span data-ttu-id="bcdca-148">Перечисление</span><span class="sxs-lookup"><span data-stu-id="bcdca-148">Enum</span></span> | <span data-ttu-id="bcdca-149">"Пользователь" в случае, если индикатор, созданный пользователем (например, с портала), "AadApp" в случае его отправки с помощью автоматического приложения через API.</span><span class="sxs-lookup"><span data-stu-id="bcdca-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="bcdca-150">source</span><span class="sxs-lookup"><span data-stu-id="bcdca-150">source</span></span> | <span data-ttu-id="bcdca-151">Строка</span><span class="sxs-lookup"><span data-stu-id="bcdca-151">string</span></span> | <span data-ttu-id="bcdca-152">Имя пользователя или приложения, которое представило индикатор.</span><span class="sxs-lookup"><span data-stu-id="bcdca-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="bcdca-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="bcdca-153">createdBy</span></span> | <span data-ttu-id="bcdca-154">String</span><span class="sxs-lookup"><span data-stu-id="bcdca-154">String</span></span> | <span data-ttu-id="bcdca-155">Уникальный идентификатор пользователя или приложения, подающего индикатор.</span><span class="sxs-lookup"><span data-stu-id="bcdca-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="bcdca-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="bcdca-156">lastUpdatedBy</span></span> | <span data-ttu-id="bcdca-157">String</span><span class="sxs-lookup"><span data-stu-id="bcdca-157">String</span></span> | <span data-ttu-id="bcdca-158">Удостоверение пользователя или приложения, который последний раз обновлял индикатор.</span><span class="sxs-lookup"><span data-stu-id="bcdca-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="bcdca-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="bcdca-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="bcdca-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="bcdca-160">DateTimeOffset</span></span> | <span data-ttu-id="bcdca-161">Дата и время создания индикатора.</span><span class="sxs-lookup"><span data-stu-id="bcdca-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="bcdca-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="bcdca-162">expirationTime</span></span> | <span data-ttu-id="bcdca-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="bcdca-163">DateTimeOffset</span></span> | <span data-ttu-id="bcdca-164">Срок действия индикатора.</span><span class="sxs-lookup"><span data-stu-id="bcdca-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="bcdca-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="bcdca-165">lastUpdateTime</span></span> | <span data-ttu-id="bcdca-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="bcdca-166">DateTimeOffset</span></span> | <span data-ttu-id="bcdca-167">Последний раз индикатор обновлялся.</span><span class="sxs-lookup"><span data-stu-id="bcdca-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="bcdca-168">severity</span><span class="sxs-lookup"><span data-stu-id="bcdca-168">severity</span></span> | <span data-ttu-id="bcdca-169">Перечисление</span><span class="sxs-lookup"><span data-stu-id="bcdca-169">Enum</span></span> | <span data-ttu-id="bcdca-170">Серьезность индикатора.</span><span class="sxs-lookup"><span data-stu-id="bcdca-170">The severity of the indicator.</span></span> <span data-ttu-id="bcdca-171">Возможные значения: "Информационная", "Низкая", "Средняя" и "Высокая".</span><span class="sxs-lookup"><span data-stu-id="bcdca-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="bcdca-172">title</span><span class="sxs-lookup"><span data-stu-id="bcdca-172">title</span></span> | <span data-ttu-id="bcdca-173">String</span><span class="sxs-lookup"><span data-stu-id="bcdca-173">String</span></span> | <span data-ttu-id="bcdca-174">Название индикатора.</span><span class="sxs-lookup"><span data-stu-id="bcdca-174">Indicator title.</span></span>
<span data-ttu-id="bcdca-175">description</span><span class="sxs-lookup"><span data-stu-id="bcdca-175">description</span></span> | <span data-ttu-id="bcdca-176">String</span><span class="sxs-lookup"><span data-stu-id="bcdca-176">String</span></span> | <span data-ttu-id="bcdca-177">Описание индикатора.</span><span class="sxs-lookup"><span data-stu-id="bcdca-177">Description of the indicator.</span></span>
<span data-ttu-id="bcdca-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="bcdca-178">recommendedActions</span></span> | <span data-ttu-id="bcdca-179">String</span><span class="sxs-lookup"><span data-stu-id="bcdca-179">String</span></span> | <span data-ttu-id="bcdca-180">Рекомендуемые действия для индикатора.</span><span class="sxs-lookup"><span data-stu-id="bcdca-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="bcdca-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="bcdca-181">rbacGroupNames</span></span> | <span data-ttu-id="bcdca-182">Список строк</span><span class="sxs-lookup"><span data-stu-id="bcdca-182">List of strings</span></span> | <span data-ttu-id="bcdca-183">Имена групп устройств RBAC, в которых индикатор выставлен и активен.</span><span class="sxs-lookup"><span data-stu-id="bcdca-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="bcdca-184">Пустой список в случае, если он будет выставлен на все устройства.</span><span class="sxs-lookup"><span data-stu-id="bcdca-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="bcdca-185">Представление Json</span><span class="sxs-lookup"><span data-stu-id="bcdca-185">Json representation</span></span>

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
