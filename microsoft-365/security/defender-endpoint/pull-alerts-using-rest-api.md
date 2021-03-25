---
title: Pull Microsoft Defender для обнаружения конечных точек с помощью API REST
description: Узнайте, как вызвать конечную точку API API Microsoft Defender для конечной точки, чтобы вытащить обнаружения в формате JSON с помощью API SIEM REST.
keywords: обнаружения, обнаружения тяги, api отдыха, запроса, ответа
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: a7d13da6abfb2cd6c829b6fd04fdf94de8cd20b8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186873"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="0e0e4-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span><span class="sxs-lookup"><span data-stu-id="0e0e4-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0e0e4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0e0e4-105">**Applies to:**</span></span>
- [<span data-ttu-id="0e0e4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0e0e4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0e0e4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e0e4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0e0e4-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0e0e4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0e0e4-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="0e0e4-110">[Microsoft Defender for Endpoint Alert](alerts.md) состоит из одного или нескольких обнаружений.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="0e0e4-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) состоит из подозрительного события, произошедшего на устройстве, и связанных с ним сведений оповещения.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="0e0e4-112">-API оповещений Microsoft Defender для конечной точки является последним API для потребления оповещений и содержит подробный список связанных данных для каждого оповещения.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="0e0e4-113">Дополнительные сведения см. в [дополнительных сведениях о](alerts.md) методах и свойствах alert и [list alerts.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="0e0e4-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="0e0e4-114">Microsoft Defender для конечной точки поддерживает протокол OAuth 2.0, чтобы вытащить обнаружения из API.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="0e0e4-115">Как правило, протокол OAuth 2.0 поддерживает четыре типа потоков:</span><span class="sxs-lookup"><span data-stu-id="0e0e4-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="0e0e4-116">Поток грантов авторизации</span><span class="sxs-lookup"><span data-stu-id="0e0e4-116">Authorization grant flow</span></span>
- <span data-ttu-id="0e0e4-117">Неявный поток</span><span class="sxs-lookup"><span data-stu-id="0e0e4-117">Implicit flow</span></span>
- <span data-ttu-id="0e0e4-118">Поток клиентских учетных данных</span><span class="sxs-lookup"><span data-stu-id="0e0e4-118">Client credentials flow</span></span>
- <span data-ttu-id="0e0e4-119">Поток владельцев ресурсов</span><span class="sxs-lookup"><span data-stu-id="0e0e4-119">Resource owner flow</span></span>

<span data-ttu-id="0e0e4-120">Дополнительные сведения о спецификациях OAuth см. на сайте [OAuth.](http://www.oauth.net)</span><span class="sxs-lookup"><span data-stu-id="0e0e4-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="0e0e4-121">Microsoft Defender для конечной  точки  поддерживает поток грантов авторизации и поток учетных данных клиента для получения доступа к обнаружениям тяги, а Azure Active Directory (AAD) является сервером авторизации.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="0e0e4-122">Поток _грантов авторизации_ использует учетные данные пользователей для получения кода авторизации, который затем используется для получения маркера доступа.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="0e0e4-123">Поток _учетных данных клиента_ использует учетные данные клиента для проверки подлинности в отношении URL-адреса конечной точки Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="0e0e4-124">Этот поток подходит для сценариев, когда клиент OAuth создает запросы в API, не требуя учетных данных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="0e0e4-125">Используйте следующий метод в API Microsoft Defender для конечной точки, чтобы вытащить обнаружения в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="0e0e4-126">Центр безопасности Microsoft Defender объединяет аналогичные обнаружения оповещений в единое оповещение.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="0e0e4-127">Этот API извлекает обнаружение оповещений в сыром виде на основе заданных параметров запроса, что позволяет применять собственную группировку и фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="0e0e4-128">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="0e0e4-128">Before you begin</span></span>
- <span data-ttu-id="0e0e4-129">Прежде чем вызывать конечную точку Microsoft Defender для конечной точки для обнаружения, необходимо включить приложение интеграции SIEM в Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="0e0e4-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="0e0e4-130">Дополнительные сведения см. в [веб-сайте Включить интеграцию SIEM в Microsoft Defender для конечной точки.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="0e0e4-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="0e0e4-p106">Запишите указанные ниже значения при регистрации приложения Azure. Эти значения понадобятся для настройки потока OAuth в вашей службе или управляющей программе.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-p106">Take note of the following values in your Azure application registration. You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="0e0e4-133">Идентификатор клиента (уникальный для приложения)</span><span class="sxs-lookup"><span data-stu-id="0e0e4-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="0e0e4-134">Ключ, или секрет, клиента (уникальный для приложения)</span><span class="sxs-lookup"><span data-stu-id="0e0e4-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="0e0e4-135">Конечная точка маркера OAuth 2.0 приложения</span><span class="sxs-lookup"><span data-stu-id="0e0e4-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="0e0e4-p107">Чтобы найти это значение, нажмите **Просмотр конечных точек** в нижней части портала управления Azure на странице приложения. Конечная точка будет представлена в формате `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-p107">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page. The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="0e0e4-138">Получение токена доступа</span><span class="sxs-lookup"><span data-stu-id="0e0e4-138">Get an access token</span></span>
<span data-ttu-id="0e0e4-139">Перед созданием вызовов в конечную точку необходимо получить маркер доступа.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="0e0e4-140">Маркер доступа используется для доступа к защищенного ресурса, который является обнаружением в Microsoft Defender для endpoint.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="0e0e4-141">Чтобы получить маркер доступа, необходимо сделать запрос POST в конечной точке выдачи маркера.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="0e0e4-142">Вот пример запроса:</span><span class="sxs-lookup"><span data-stu-id="0e0e4-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="0e0e4-143">Ответ будет содержать маркер доступа и сведения об истечении срока действия.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-143">The response will include an access token and expiry information.</span></span>

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
<span data-ttu-id="0e0e4-144">Теперь вы можете использовать значение в *поле access_token* в запросе в API Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="0e0e4-145">Запрос</span><span class="sxs-lookup"><span data-stu-id="0e0e4-145">Request</span></span>
<span data-ttu-id="0e0e4-146">С помощью маркера доступа ваше приложение может делать запросы на проверку подлинности в API Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="0e0e4-147">Приложение должно добавлять токен доступа в заголовок Authorization каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="0e0e4-148">Запрос синтаксиса</span><span class="sxs-lookup"><span data-stu-id="0e0e4-148">Request syntax</span></span>
<span data-ttu-id="0e0e4-149">Метод</span><span class="sxs-lookup"><span data-stu-id="0e0e4-149">Method</span></span> | <span data-ttu-id="0e0e4-150">Запрос URI</span><span class="sxs-lookup"><span data-stu-id="0e0e4-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="0e0e4-151">GET</span><span class="sxs-lookup"><span data-stu-id="0e0e4-151">GET</span></span>| <span data-ttu-id="0e0e4-152">Используйте URI, применимый к вашему региону.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="0e0e4-153">**Для ЕС**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="0e0e4-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="0e0e4-154">**Для США**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="0e0e4-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="0e0e4-155">**Для Великобритании**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="0e0e4-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="0e0e4-156">Заготвка запроса</span><span class="sxs-lookup"><span data-stu-id="0e0e4-156">Request header</span></span>
<span data-ttu-id="0e0e4-157">Верхний колонтитул</span><span class="sxs-lookup"><span data-stu-id="0e0e4-157">Header</span></span> | <span data-ttu-id="0e0e4-158">Тип</span><span class="sxs-lookup"><span data-stu-id="0e0e4-158">Type</span></span> | <span data-ttu-id="0e0e4-159">Описание</span><span class="sxs-lookup"><span data-stu-id="0e0e4-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="0e0e4-160">Authorization</span><span class="sxs-lookup"><span data-stu-id="0e0e4-160">Authorization</span></span> | <span data-ttu-id="0e0e4-161">string</span><span class="sxs-lookup"><span data-stu-id="0e0e4-161">string</span></span> | <span data-ttu-id="0e0e4-162">Обязательное.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-162">Required.</span></span> <span data-ttu-id="0e0e4-163">Маркер доступа Azure AD в маркере **Bearer** &lt; *формы.* &gt;</span><span class="sxs-lookup"><span data-stu-id="0e0e4-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="0e0e4-164">Параметры запроса</span><span class="sxs-lookup"><span data-stu-id="0e0e4-164">Request parameters</span></span>

<span data-ttu-id="0e0e4-165">Используйте необязательные параметры запроса для указания и управления объемом данных, возвращаемого в ответ.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="0e0e4-166">Если вызвать этот метод без параметров, ответ содержит все оповещения в организации за последние 2 часа.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="0e0e4-167">Имя</span><span class="sxs-lookup"><span data-stu-id="0e0e4-167">Name</span></span> | <span data-ttu-id="0e0e4-168">Значение</span><span class="sxs-lookup"><span data-stu-id="0e0e4-168">Value</span></span>| <span data-ttu-id="0e0e4-169">Описание</span><span class="sxs-lookup"><span data-stu-id="0e0e4-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="0e0e4-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="0e0e4-170">sinceTimeUtc</span></span> | <span data-ttu-id="0e0e4-171">DateTime</span><span class="sxs-lookup"><span data-stu-id="0e0e4-171">DateTime</span></span> | <span data-ttu-id="0e0e4-172">Определяет меньшее время, связанное оповещений извлекаются из, на основе поля:</span><span class="sxs-lookup"><span data-stu-id="0e0e4-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="0e0e4-173">Диапазон времени будет: от времени sinceTimeUtc до текущего времени.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="0e0e4-174">**ПРИМЕЧАНИЕ.** Если не указано, все оповещения, созданные за последние два часа, извлекаются.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="0e0e4-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="0e0e4-175">untilTimeUtc</span></span> | <span data-ttu-id="0e0e4-176">DateTime</span><span class="sxs-lookup"><span data-stu-id="0e0e4-176">DateTime</span></span> | <span data-ttu-id="0e0e4-177">Определяет, как извлекаются оповещений, связанных с верхним временем.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="0e0e4-178">Диапазон времени будет: `sinceTimeUtc` время от `untilTimeUtc` времени.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="0e0e4-179">**ПРИМЕЧАНИЕ.** Если не указано, значение по умолчанию будет текущим.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="0e0e4-180">ago</span><span class="sxs-lookup"><span data-stu-id="0e0e4-180">ago</span></span> | <span data-ttu-id="0e0e4-181">строка</span><span class="sxs-lookup"><span data-stu-id="0e0e4-181">string</span></span> | <span data-ttu-id="0e0e4-182">Время от времени вытягивает оповещений в следующем `(current_time - ago)` `current_time` диапазоне времени.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="0e0e4-183">Значение должно быть установлено в соответствии **с форматом длительности ISO 8601**</span><span class="sxs-lookup"><span data-stu-id="0e0e4-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="0e0e4-184">Пример: `ago=PT10M` будет тянуть оповещения, полученные в течение последних 10 минут.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="0e0e4-185">limit</span><span class="sxs-lookup"><span data-stu-id="0e0e4-185">limit</span></span> | <span data-ttu-id="0e0e4-186">int</span><span class="sxs-lookup"><span data-stu-id="0e0e4-186">int</span></span> | <span data-ttu-id="0e0e4-187">Определяет количество извлеченных оповещений.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="0e0e4-188">Последние оповещений будут извлечены на основе определенного числа.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="0e0e4-189">**ПРИМЕЧАНИЕ.** Если не указано, все оповещения, доступные в диапазоне времени, будут извлечены.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="0e0e4-190">машинные группы</span><span class="sxs-lookup"><span data-stu-id="0e0e4-190">machinegroups</span></span> | <span data-ttu-id="0e0e4-191">строка</span><span class="sxs-lookup"><span data-stu-id="0e0e4-191">string</span></span> | <span data-ttu-id="0e0e4-192">Указывает группы устройств, чтобы вывести оповещения из.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="0e0e4-193">**ПРИМЕЧАНИЕ.** Если не указано, оповещения из всех групп устройств будут извлечены.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="0e0e4-194">Пример.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/Alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="0e0e4-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="0e0e4-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="0e0e4-196">строка</span><span class="sxs-lookup"><span data-stu-id="0e0e4-196">string</span></span> | <span data-ttu-id="0e0e4-197">Тег одного устройства из реестра.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-197">Single device tag from the registry.</span></span>
<span data-ttu-id="0e0e4-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="0e0e4-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="0e0e4-199">строка</span><span class="sxs-lookup"><span data-stu-id="0e0e4-199">string</span></span> | <span data-ttu-id="0e0e4-200">Теги устройств, созданные в Центре безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="0e0e4-201">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="0e0e4-201">Request example</span></span>
<span data-ttu-id="0e0e4-202">В следующем примере показано, как получить все обнаружения в организации.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="0e0e4-203">В следующем примере демонстрируется запрос на последние 20 обнаружения с 2016-09-12 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="0e0e4-204">Отклик</span><span class="sxs-lookup"><span data-stu-id="0e0e4-204">Response</span></span>
<span data-ttu-id="0e0e4-205">Возвращаемая величина — это массив объектов оповещения в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="0e0e4-206">Вот пример возвращаемой стоимости:</span><span class="sxs-lookup"><span data-stu-id="0e0e4-206">Here is an example return value:</span></span>

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a><span data-ttu-id="0e0e4-207">Примеры кода</span><span class="sxs-lookup"><span data-stu-id="0e0e4-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="0e0e4-208">Получить маркер доступа</span><span class="sxs-lookup"><span data-stu-id="0e0e4-208">Get access token</span></span>
<span data-ttu-id="0e0e4-209">В следующих примерах кода показано, как получить маркер доступа для вызова API СИЕМ Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="0e0e4-210">Использование маркера для подключения к конечной точке обнаружения</span><span class="sxs-lookup"><span data-stu-id="0e0e4-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="0e0e4-211">В следующих примерах кода показано, как использовать маркер доступа для вызова API SIEM Defender для конечной точки для получения оповещений.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a><span data-ttu-id="0e0e4-212">Коды ошибок</span><span class="sxs-lookup"><span data-stu-id="0e0e4-212">Error codes</span></span>
<span data-ttu-id="0e0e4-213">API rest API Для защитника Конечной точки возвращает следующие коды ошибок, вызванные недействительным запросом.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="0e0e4-214">Код ошибки HTTP</span><span class="sxs-lookup"><span data-stu-id="0e0e4-214">HTTP error code</span></span> | <span data-ttu-id="0e0e4-215">Описание</span><span class="sxs-lookup"><span data-stu-id="0e0e4-215">Description</span></span>
:---|:---
<span data-ttu-id="0e0e4-216">401</span><span class="sxs-lookup"><span data-stu-id="0e0e4-216">401</span></span> | <span data-ttu-id="0e0e4-217">Недействительный запрос или недействительный маркер.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="0e0e4-218">403</span><span class="sxs-lookup"><span data-stu-id="0e0e4-218">403</span></span> | <span data-ttu-id="0e0e4-219">Несанкционированное исключение — любой из доменов не управляется администратором клиента или состоянием клиента удаляется.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="0e0e4-220">500</span><span class="sxs-lookup"><span data-stu-id="0e0e4-220">500</span></span> | <span data-ttu-id="0e0e4-221">Ошибка в службе.</span><span class="sxs-lookup"><span data-stu-id="0e0e4-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0e0e4-222">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0e0e4-222">Related topics</span></span>
- [<span data-ttu-id="0e0e4-223">Включение интеграции SIEM в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0e0e4-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="0e0e4-224">Настройте ArcSight, чтобы вытащить Microsoft Defender для обнаружения конечных точек</span><span class="sxs-lookup"><span data-stu-id="0e0e4-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="0e0e4-225">Притягивать обнаружения к средствам SIEM</span><span class="sxs-lookup"><span data-stu-id="0e0e4-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="0e0e4-226">Microsoft Defender для полей обнаружения конечных точек</span><span class="sxs-lookup"><span data-stu-id="0e0e4-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="0e0e4-227">Устранение неполадок в интеграции инструментов SIEM</span><span class="sxs-lookup"><span data-stu-id="0e0e4-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)