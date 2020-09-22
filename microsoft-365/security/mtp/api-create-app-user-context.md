---
title: Доступ к API Microsoft Threat protection с использованием от имени пользователя
description: Узнайте, как получить доступ к API защиты от угроз Майкрософт с помощью от имени пользователя
keywords: доступ, от имени пользователя, API, приложения, пользователя, маркер доступа, маркер,
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
ms.openlocfilehash: a62d90004d00e8c553f1b011e77b871df7cd94f4
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197801"
---
# <a name="access-microsoft-threat-protection-apis-on-behalf-of-user"></a><span data-ttu-id="1b3cb-104">Доступ к API Microsoft Threat protection от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="1b3cb-104">Access Microsoft Threat Protection APIs on behalf of user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1b3cb-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1b3cb-105">**Applies to:**</span></span>
- <span data-ttu-id="1b3cb-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1b3cb-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="1b3cb-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1b3cb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="1b3cb-109">На этой странице описывается, как создать приложение для получения программного доступа к защите от угроз Майкрософт от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-109">This page describes how to create an application to get programmatic access to Microsoft Threat Protection on behalf of a user.</span></span>

<span data-ttu-id="1b3cb-110">Если вам требуется программный доступ к защите угроз Майкрософт без пользователя, обратитесь к разделу [Создание приложения для доступа к защите от угроз Майкрософт без участия пользователя](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="1b3cb-110">If you need programmatic access Microsoft Threat Protection without a user, refer to [Create an app to access Microsoft Threat Protection without a user](api-create-app-web.md).</span></span>

<span data-ttu-id="1b3cb-111">Если вы не знаете, какой необходим доступ, ознакомьтесь со сведениями о том, как [получить доступ к API Microsoft Threat protection](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="1b3cb-111">If you are not sure which access you need, read the [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="1b3cb-112">Защита от угроз Майкрософт предоставляет множество своих данных и действий через набор программных интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-112">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="1b3cb-113">Эти API позволяют автоматизировать рабочие процессы и внедрять их на основе возможностей защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-113">Those APIs will enable you to automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="1b3cb-114">Для доступа к API требуется проверка подлинности OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="1b3cb-115">Для получения дополнительных сведений см [код авторизации OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="1b3cb-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="1b3cb-116">В общем случае необходимо выполнить следующие действия, чтобы использовать API:</span><span class="sxs-lookup"><span data-stu-id="1b3cb-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="1b3cb-117">Создание приложения AAD</span><span class="sxs-lookup"><span data-stu-id="1b3cb-117">Create an AAD application</span></span>
- <span data-ttu-id="1b3cb-118">Получение маркера доступа с помощью этого приложения</span><span class="sxs-lookup"><span data-stu-id="1b3cb-118">Get an access token using this application</span></span>
- <span data-ttu-id="1b3cb-119">Использование маркера для доступа к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1b3cb-119">Use the token to access Microsoft Threat Protection API</span></span>

<span data-ttu-id="1b3cb-120">На этой странице объясняется, как создать приложение AAD, получить маркер доступа к защите от угроз Майкрософт и проверить маркер.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-120">This page explains how to create an AAD application, get an access token to Microsoft Threat Protection and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="1b3cb-121">При доступе к API Microsoft Threat protection от имени пользователя вам потребуется соответствующее разрешение приложения и разрешение пользователя.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-121">When accessing Microsoft Threat Protection API on behalf of a user, you will need the correct Application permission and user permission.</span></span>


>[!TIP]
> <span data-ttu-id="1b3cb-122">Если у вас есть разрешение на выполнение действий на портале, у вас есть разрешение на выполнение действия в API.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-122">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="1b3cb-123">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="1b3cb-123">Create an app</span></span>

1. <span data-ttu-id="1b3cb-124">Войдите в [Azure](https://portal.azure.com) с помощью учетной записи пользователя с ролью **глобального администратора** .</span><span class="sxs-lookup"><span data-stu-id="1b3cb-124">Log on to [Azure](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="1b3cb-125">Перейдите к разделу Регистрация приложений **Azure Active Directory**с  >  **App registrations**  >  **новой регистрацией**.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-125">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Изображение Microsoft Azure и переход к регистрации приложения](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="1b3cb-127">В поле регистрация из введите следующие сведения, а затем нажмите кнопку **Регистрация**.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-127">In the registration from, enter the following information then click **Register**.</span></span>

   ![Изображение окна "Создание приложения"](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="1b3cb-129">**Имя:** Имя приложения</span><span class="sxs-lookup"><span data-stu-id="1b3cb-129">**Name:** Your application name</span></span>
   - <span data-ttu-id="1b3cb-130">**Тип приложения:** Общедоступный клиент</span><span class="sxs-lookup"><span data-stu-id="1b3cb-130">**Application type:** Public client</span></span>
   - <span data-ttu-id="1b3cb-131">**URI перенаправления:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="1b3cb-131">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="1b3cb-132">Чтобы разрешить приложению доступ к защите от угроз Майкрософт и назначить ей разрешения, на странице приложения выберите **разрешения API**  >  **Добавление**разрешений  >  **API "Моя организация использует** >", введите **Microsoft Threat protection**, а затем выберите **Microsoft Threat protection**.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-132">To enable your app to access Microsoft Threat Protection and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and then select **Microsoft Threat Protection**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="1b3cb-133">Защита от угроз Майкрософт не отображается в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-133">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="1b3cb-134">Чтобы отобразить его имя, необходимо сначала начать его ввод в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-134">You need to start writing its name in the text box to see it appear.</span></span>

      ![Изображение доступа к API и выбора API](../../media/apis-in-my-org-tab.PNG)

    - <span data-ttu-id="1b3cb-136">Выберите **делегированные разрешения** > выберите соответствующие разрешения для вашего сценария, например " **инцидент. чтение**", а затем нажмите кнопку **Добавить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-136">Choose **Delegated permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read**, and then select **Add permissions**.</span></span>

      ![Изображение доступа к API и выбора API](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     ><span data-ttu-id="1b3cb-138">Необходимо выбрать соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-138">You need to select the relevant permissions.</span></span> 

    -  <span data-ttu-id="1b3cb-139">Чтобы определить, какое разрешение необходимо, просмотрите раздел **разрешения** в API, который вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-139">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="1b3cb-140">Щелкните **разрешение GRANT**</span><span class="sxs-lookup"><span data-stu-id="1b3cb-140">Click **Grant consent**</span></span>

      >[!NOTE]
      ><span data-ttu-id="1b3cb-141">Каждый раз при добавлении разрешения необходимо щелкнуть разрешение **Grant** , чтобы новое разрешение вступило в силу.</span><span class="sxs-lookup"><span data-stu-id="1b3cb-141">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

      ![Изображение разрешений GRANT](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="1b3cb-143">Запишите идентификатор своего приложения и идентификатор клиента:</span><span class="sxs-lookup"><span data-stu-id="1b3cb-143">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="1b3cb-144">На странице приложения перейдите в раздел **Overview (обзор** ) и скопируйте следующее:</span><span class="sxs-lookup"><span data-stu-id="1b3cb-144">On your application page, go to **Overview** and copy the following:</span></span>

   ![Изображение идентификатора созданного приложения](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="1b3cb-146">Получение маркера доступа с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b3cb-146">Get an access token using PowerShell</span></span>

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a><span data-ttu-id="1b3cb-147">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="1b3cb-147">Related topics</span></span>
- [<span data-ttu-id="1b3cb-148">Доступ к API защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1b3cb-148">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="1b3cb-149">Доступ к защите от угроз Майкрософт с помощью контекста приложения</span><span class="sxs-lookup"><span data-stu-id="1b3cb-149">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
