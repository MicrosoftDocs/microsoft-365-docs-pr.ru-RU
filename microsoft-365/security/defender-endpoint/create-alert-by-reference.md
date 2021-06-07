---
title: Создание оповещений из API событий
description: Узнайте, как использовать API создания оповещений для создания нового оповещения в верхней части события в Microsoft Defender для конечной точки.
keywords: apis, api graph, supported apis, get, alert, information, id
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
ms.openlocfilehash: 8b05dde015bc96e1ccd3f80e25c416a371e03199
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772393"
---
# <a name="create-alert-api"></a><span data-ttu-id="24fed-104">Создание API оповещений</span><span class="sxs-lookup"><span data-stu-id="24fed-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="24fed-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="24fed-105">**Applies to:**</span></span>
- [<span data-ttu-id="24fed-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="24fed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24fed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24fed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="24fed-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="24fed-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="24fed-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="24fed-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="24fed-110">Описание API</span><span class="sxs-lookup"><span data-stu-id="24fed-110">API description</span></span>
<span data-ttu-id="24fed-111">Создает новое [оповещение](alerts.md) в верхней части **события**.</span><span class="sxs-lookup"><span data-stu-id="24fed-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>
<br><span data-ttu-id="24fed-112">**Для создания оповещений** требуется microsoft Defender for Endpoint Event.</span><span class="sxs-lookup"><span data-stu-id="24fed-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
<br><span data-ttu-id="24fed-113">Вам потребуется предоставить 3 параметра события в запросе: **Время** события, **машинный ИД** и **ID отчета.**</span><span class="sxs-lookup"><span data-stu-id="24fed-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="24fed-114">См. приведенный ниже пример.</span><span class="sxs-lookup"><span data-stu-id="24fed-114">See example below.</span></span>
<br><span data-ttu-id="24fed-115">Вы можете использовать событие, найденное в API advanced Hunting или Portal.</span><span class="sxs-lookup"><span data-stu-id="24fed-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
<br><span data-ttu-id="24fed-116">Если на том же устройстве существует открытое оповещение с тем же названием, новое созданное оповещение будет объединено с ним.</span><span class="sxs-lookup"><span data-stu-id="24fed-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
<br><span data-ttu-id="24fed-117">Автоматическое расследование запускается автоматически при оповещениях, созданных с помощью API.</span><span class="sxs-lookup"><span data-stu-id="24fed-117">An automatic investigation starts automatically on alerts created via the API.</span></span>


## <a name="limitations"></a><span data-ttu-id="24fed-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="24fed-118">Limitations</span></span>
1. <span data-ttu-id="24fed-119">Ограничения скорости для этого API — 15 вызовов в минуту.</span><span class="sxs-lookup"><span data-stu-id="24fed-119">Rate limitations for this API are 15 calls per minute.</span></span>


## <a name="permissions"></a><span data-ttu-id="24fed-120">Разрешения</span><span class="sxs-lookup"><span data-stu-id="24fed-120">Permissions</span></span>

<span data-ttu-id="24fed-121">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="24fed-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="24fed-122">Дополнительные дополнительные информации, в том числе о выборе разрешений, см. в этой [ссылке: Использование API endpoint Defender для Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="24fed-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="24fed-123">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="24fed-123">Permission type</span></span> |   <span data-ttu-id="24fed-124">Разрешение</span><span class="sxs-lookup"><span data-stu-id="24fed-124">Permission</span></span>  |   <span data-ttu-id="24fed-125">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="24fed-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="24fed-126">Приложение</span><span class="sxs-lookup"><span data-stu-id="24fed-126">Application</span></span> |   <span data-ttu-id="24fed-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="24fed-127">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="24fed-128">'Read and write all alerts'</span><span class="sxs-lookup"><span data-stu-id="24fed-128">'Read and write all alerts'</span></span>
<span data-ttu-id="24fed-129">Делегированные (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="24fed-129">Delegated (work or school account)</span></span> | <span data-ttu-id="24fed-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="24fed-130">Alert.ReadWrite</span></span> | <span data-ttu-id="24fed-131">'Read and write alerts'</span><span class="sxs-lookup"><span data-stu-id="24fed-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="24fed-132">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="24fed-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="24fed-133">У пользователя должно быть по крайней мере следующее разрешение на роль: "Оповещение о расследовании" (см. в рублях [Создание](user-roles.md) ролей и управление ими для получения дополнительных сведений)</span><span class="sxs-lookup"><span data-stu-id="24fed-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="24fed-134">Пользователь должен иметь доступ к устройству, связанному с оповещением, на основе параметров группы устройств (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) устройств).</span><span class="sxs-lookup"><span data-stu-id="24fed-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="24fed-135">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="24fed-135">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="24fed-136">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="24fed-136">Request headers</span></span>

<span data-ttu-id="24fed-137">Имя</span><span class="sxs-lookup"><span data-stu-id="24fed-137">Name</span></span> | <span data-ttu-id="24fed-138">Тип</span><span class="sxs-lookup"><span data-stu-id="24fed-138">Type</span></span> | <span data-ttu-id="24fed-139">Описание</span><span class="sxs-lookup"><span data-stu-id="24fed-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="24fed-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="24fed-140">Authorization</span></span> | <span data-ttu-id="24fed-141">String</span><span class="sxs-lookup"><span data-stu-id="24fed-141">String</span></span> | <span data-ttu-id="24fed-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="24fed-142">Bearer {token}.</span></span> <span data-ttu-id="24fed-143">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="24fed-143">**Required**.</span></span>
<span data-ttu-id="24fed-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="24fed-144">Content-Type</span></span> | <span data-ttu-id="24fed-145">String</span><span class="sxs-lookup"><span data-stu-id="24fed-145">String</span></span> | <span data-ttu-id="24fed-146">application/json.</span><span class="sxs-lookup"><span data-stu-id="24fed-146">application/json.</span></span> <span data-ttu-id="24fed-147">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="24fed-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="24fed-148">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="24fed-148">Request body</span></span>

<span data-ttu-id="24fed-149">В теле запроса укажи следующие значения (все необходимые):</span><span class="sxs-lookup"><span data-stu-id="24fed-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="24fed-150">Свойство</span><span class="sxs-lookup"><span data-stu-id="24fed-150">Property</span></span> | <span data-ttu-id="24fed-151">Тип</span><span class="sxs-lookup"><span data-stu-id="24fed-151">Type</span></span> | <span data-ttu-id="24fed-152">Описание</span><span class="sxs-lookup"><span data-stu-id="24fed-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="24fed-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="24fed-153">eventTime</span></span> | <span data-ttu-id="24fed-154">DateTime (UTC)</span><span class="sxs-lookup"><span data-stu-id="24fed-154">DateTime(UTC)</span></span> | <span data-ttu-id="24fed-155">Точное время события в качестве строки, полученной из продвинутой охоты.</span><span class="sxs-lookup"><span data-stu-id="24fed-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="24fed-156">например. ```2018-08-03T16:45:21.7115183Z``` **Обязательно**.</span><span class="sxs-lookup"><span data-stu-id="24fed-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="24fed-157">reportId</span><span class="sxs-lookup"><span data-stu-id="24fed-157">reportId</span></span> | <span data-ttu-id="24fed-158">String</span><span class="sxs-lookup"><span data-stu-id="24fed-158">String</span></span> | <span data-ttu-id="24fed-159">ReportId события, полученный из продвинутой охоты.</span><span class="sxs-lookup"><span data-stu-id="24fed-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="24fed-160">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="24fed-160">**Required**.</span></span>
<span data-ttu-id="24fed-161">machineId</span><span class="sxs-lookup"><span data-stu-id="24fed-161">machineId</span></span> | <span data-ttu-id="24fed-162">String</span><span class="sxs-lookup"><span data-stu-id="24fed-162">String</span></span> | <span data-ttu-id="24fed-163">Id устройства, на котором было идентифицировано событие.</span><span class="sxs-lookup"><span data-stu-id="24fed-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="24fed-164">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="24fed-164">**Required**.</span></span>
<span data-ttu-id="24fed-165">severity</span><span class="sxs-lookup"><span data-stu-id="24fed-165">severity</span></span> | <span data-ttu-id="24fed-166">String</span><span class="sxs-lookup"><span data-stu-id="24fed-166">String</span></span> | <span data-ttu-id="24fed-167">Степень серьезности оповещения.</span><span class="sxs-lookup"><span data-stu-id="24fed-167">Severity of the alert.</span></span> <span data-ttu-id="24fed-168">Значения свойств: "Low", "Medium" и "High".</span><span class="sxs-lookup"><span data-stu-id="24fed-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="24fed-169">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="24fed-169">**Required**.</span></span>
<span data-ttu-id="24fed-170">title</span><span class="sxs-lookup"><span data-stu-id="24fed-170">title</span></span> | <span data-ttu-id="24fed-171">String</span><span class="sxs-lookup"><span data-stu-id="24fed-171">String</span></span> | <span data-ttu-id="24fed-172">Название для оповещений.</span><span class="sxs-lookup"><span data-stu-id="24fed-172">Title for the alert.</span></span> <span data-ttu-id="24fed-173">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="24fed-173">**Required**.</span></span>
<span data-ttu-id="24fed-174">description</span><span class="sxs-lookup"><span data-stu-id="24fed-174">description</span></span> | <span data-ttu-id="24fed-175">String</span><span class="sxs-lookup"><span data-stu-id="24fed-175">String</span></span> | <span data-ttu-id="24fed-176">Описание оповещений.</span><span class="sxs-lookup"><span data-stu-id="24fed-176">Description of the alert.</span></span> <span data-ttu-id="24fed-177">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="24fed-177">**Required**.</span></span>
<span data-ttu-id="24fed-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="24fed-178">recommendedAction</span></span>| <span data-ttu-id="24fed-179">String</span><span class="sxs-lookup"><span data-stu-id="24fed-179">String</span></span> | <span data-ttu-id="24fed-180">Действия, которые рекомендуется принимать сотрудником службы безопасности при анализе оповещения.</span><span class="sxs-lookup"><span data-stu-id="24fed-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="24fed-181">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="24fed-181">**Required**.</span></span>
<span data-ttu-id="24fed-182">category</span><span class="sxs-lookup"><span data-stu-id="24fed-182">category</span></span>| <span data-ttu-id="24fed-183">String</span><span class="sxs-lookup"><span data-stu-id="24fed-183">String</span></span> | <span data-ttu-id="24fed-184">Категория оповещения.</span><span class="sxs-lookup"><span data-stu-id="24fed-184">Category of the alert.</span></span> <span data-ttu-id="24fed-185">Значения свойств: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **required**.</span><span class="sxs-lookup"><span data-stu-id="24fed-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="24fed-186">Отклик</span><span class="sxs-lookup"><span data-stu-id="24fed-186">Response</span></span>

<span data-ttu-id="24fed-187">В случае успеха этот метод возвращает 200 [](alerts.md) ОК и новый объект оповещений в теле ответа.</span><span class="sxs-lookup"><span data-stu-id="24fed-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="24fed-188">Если событие с указанными свойствами _(reportId,_ _eventTime_ и _machineId)_ не было найдено - 404 Не найдено.</span><span class="sxs-lookup"><span data-stu-id="24fed-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="24fed-189">Пример</span><span class="sxs-lookup"><span data-stu-id="24fed-189">Example</span></span>

<span data-ttu-id="24fed-190">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="24fed-190">**Request**</span></span>

<span data-ttu-id="24fed-191">Ниже приведен пример запроса.</span><span class="sxs-lookup"><span data-stu-id="24fed-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
