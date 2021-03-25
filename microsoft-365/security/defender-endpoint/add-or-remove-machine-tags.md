---
title: Добавление или удаление API тегов машин
description: Узнайте, как использовать API тегов добавить или удалить для добавления или удаления тега для машины в Microsoft Defender для конечной точки.
keywords: apis, graph api, supported apis, tags, machine tags
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
ms.technology: mde
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199781"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="d2505-104">Добавление или удаление API тегов машин</span><span class="sxs-lookup"><span data-stu-id="d2505-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="d2505-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d2505-105">**Applies to:**</span></span>

- [<span data-ttu-id="d2505-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d2505-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="d2505-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d2505-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d2505-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d2505-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="d2505-109">Описание API</span><span class="sxs-lookup"><span data-stu-id="d2505-109">API description</span></span>

<span data-ttu-id="d2505-110">Добавляет или удаляет тег в определенный [компьютер.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="d2505-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="d2505-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d2505-111">Limitations</span></span>

1. <span data-ttu-id="d2505-112">Вы можете размещать сообщения на компьютерах в последний раз в соответствии с настроенным периодом хранения.</span><span class="sxs-lookup"><span data-stu-id="d2505-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="d2505-113">Ограничения скорости для этого API : 100 вызовов в минуту и 1500 вызовов в час.</span><span class="sxs-lookup"><span data-stu-id="d2505-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d2505-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="d2505-114">Permissions</span></span>

<span data-ttu-id="d2505-115">Для вызова этого API требуется одно из следующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="d2505-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d2505-116">Дополнительные новости, в том числе выбор разрешений, см. в этой [ссылке: Use Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d2505-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d2505-117">Тип разрешения</span><span class="sxs-lookup"><span data-stu-id="d2505-117">Permission type</span></span> |    <span data-ttu-id="d2505-118">Разрешение</span><span class="sxs-lookup"><span data-stu-id="d2505-118">Permission</span></span>    |    <span data-ttu-id="d2505-119">Имя отображения разрешений</span><span class="sxs-lookup"><span data-stu-id="d2505-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d2505-120">Application</span><span class="sxs-lookup"><span data-stu-id="d2505-120">Application</span></span> |    <span data-ttu-id="d2505-121">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d2505-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="d2505-122">'Read and write all machine information'</span><span class="sxs-lookup"><span data-stu-id="d2505-122">'Read and write all machine information'</span></span>
<span data-ttu-id="d2505-123">Делегированное (рабочая или учебная учетная запись)</span><span class="sxs-lookup"><span data-stu-id="d2505-123">Delegated (work or school account)</span></span> | <span data-ttu-id="d2505-124">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d2505-124">Machine.ReadWrite</span></span> | <span data-ttu-id="d2505-125">'Read and write machine information'</span><span class="sxs-lookup"><span data-stu-id="d2505-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="d2505-126">При получении маркера с помощью учетных данных пользователей:</span><span class="sxs-lookup"><span data-stu-id="d2505-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="d2505-127">У пользователя должно быть по крайней мере следующее разрешение на роль: "Управление параметром безопасности".</span><span class="sxs-lookup"><span data-stu-id="d2505-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="d2505-128">Дополнительные сведения (см. [дополнительные сведения](user-roles.md) о создании ролей и управлении ими)</span><span class="sxs-lookup"><span data-stu-id="d2505-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="d2505-129">Пользователь должен иметь доступ к машине на основе параметров группы машин (см. дополнительные сведения о создании и управлении [группами](machine-groups.md) машин).</span><span class="sxs-lookup"><span data-stu-id="d2505-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d2505-130">HTTP-запрос</span><span class="sxs-lookup"><span data-stu-id="d2505-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="d2505-131">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="d2505-131">Request headers</span></span>

<span data-ttu-id="d2505-132">Имя</span><span class="sxs-lookup"><span data-stu-id="d2505-132">Name</span></span> | <span data-ttu-id="d2505-133">Тип</span><span class="sxs-lookup"><span data-stu-id="d2505-133">Type</span></span> | <span data-ttu-id="d2505-134">Описание</span><span class="sxs-lookup"><span data-stu-id="d2505-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="d2505-135">Авторизация</span><span class="sxs-lookup"><span data-stu-id="d2505-135">Authorization</span></span> | <span data-ttu-id="d2505-136">Строка</span><span class="sxs-lookup"><span data-stu-id="d2505-136">String</span></span> | <span data-ttu-id="d2505-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="d2505-137">Bearer {token}.</span></span> <span data-ttu-id="d2505-138">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="d2505-138">**Required**.</span></span>
<span data-ttu-id="d2505-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d2505-139">Content-Type</span></span> | <span data-ttu-id="d2505-140">string</span><span class="sxs-lookup"><span data-stu-id="d2505-140">string</span></span> | <span data-ttu-id="d2505-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="d2505-141">application/json.</span></span> <span data-ttu-id="d2505-142">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="d2505-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d2505-143">Текст запроса</span><span class="sxs-lookup"><span data-stu-id="d2505-143">Request body</span></span>

<span data-ttu-id="d2505-144">В теле запроса поставляем объект JSON со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="d2505-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="d2505-145">Параметр</span><span class="sxs-lookup"><span data-stu-id="d2505-145">Parameter</span></span> |    <span data-ttu-id="d2505-146">Тип</span><span class="sxs-lookup"><span data-stu-id="d2505-146">Type</span></span>    | <span data-ttu-id="d2505-147">Описание</span><span class="sxs-lookup"><span data-stu-id="d2505-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="d2505-148">Значение</span><span class="sxs-lookup"><span data-stu-id="d2505-148">Value</span></span> |    <span data-ttu-id="d2505-149">Строка</span><span class="sxs-lookup"><span data-stu-id="d2505-149">String</span></span> |    <span data-ttu-id="d2505-150">Имя тега.</span><span class="sxs-lookup"><span data-stu-id="d2505-150">The tag name.</span></span> <span data-ttu-id="d2505-151">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="d2505-151">**Required**.</span></span>
<span data-ttu-id="d2505-152">Действие</span><span class="sxs-lookup"><span data-stu-id="d2505-152">Action</span></span>    | <span data-ttu-id="d2505-153">Перечисление</span><span class="sxs-lookup"><span data-stu-id="d2505-153">Enum</span></span> |    <span data-ttu-id="d2505-154">Добавление или удаление.</span><span class="sxs-lookup"><span data-stu-id="d2505-154">Add or Remove.</span></span> <span data-ttu-id="d2505-155">Допустимые значения: "Добавить" или "Удалить".</span><span class="sxs-lookup"><span data-stu-id="d2505-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="d2505-156">**Обязательное поле**.</span><span class="sxs-lookup"><span data-stu-id="d2505-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="d2505-157">Отклик</span><span class="sxs-lookup"><span data-stu-id="d2505-157">Response</span></span>

<span data-ttu-id="d2505-158">В случае успешной работы этот метод возвращает код ответа 200 — Ok и обновленный компьютер в тексте отклика.</span><span class="sxs-lookup"><span data-stu-id="d2505-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="d2505-159">Пример</span><span class="sxs-lookup"><span data-stu-id="d2505-159">Example</span></span>

<span data-ttu-id="d2505-160">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="d2505-160">**Request**</span></span>

<span data-ttu-id="d2505-161">Вот пример запроса, который добавляет тег машины.</span><span class="sxs-lookup"><span data-stu-id="d2505-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="d2505-162">Чтобы удалить тег машины, установите действие "Удалить", а не "Добавить" в теле запроса.</span><span class="sxs-lookup"><span data-stu-id="d2505-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>
