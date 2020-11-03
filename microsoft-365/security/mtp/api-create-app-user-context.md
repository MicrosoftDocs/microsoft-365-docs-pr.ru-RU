---
title: Доступ к API защитника Microsoft 365 с использованием от имени пользователя
description: Узнайте, как получить доступ к API защитника Microsoft 365 с помощью от имени пользователя
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
ms.openlocfilehash: a72bc7648045e5cc37a1d899f9e15237ce29ed37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847360"
---
# <a name="access-microsoft-365-defender-apis-on-behalf-of-user"></a><span data-ttu-id="c5321-104">Доступ к API-интерфейсам защитника Microsoft 365 от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="c5321-104">Access Microsoft 365 Defender APIs on behalf of user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c5321-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c5321-105">**Applies to:**</span></span>
- <span data-ttu-id="c5321-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5321-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="c5321-107">Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть значительно изменены до выпуска.</span><span class="sxs-lookup"><span data-stu-id="c5321-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c5321-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="c5321-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="c5321-109">На этой странице описано, как создать приложение для получения программного доступа к защитнику Microsoft 365 от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="c5321-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a user.</span></span>

<span data-ttu-id="c5321-110">Если вам нужен программный доступ к защитнику Microsoft 365 без пользователя, обратитесь к разделу [Создание приложения для доступа к защитнику microsoft 365 без пользователя](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="c5321-110">If you need programmatic access Microsoft 365 Defender without a user, refer to [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span>

<span data-ttu-id="c5321-111">Если вы не знаете, какой необходим доступ, ознакомьтесь со сведениями о том, как [получить доступ к API-интерфейсам защитника Microsoft 365](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="c5321-111">If you are not sure which access you need, read the [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="c5321-112">Защитник Microsoft 365 предоставляет множество своих данных и действий через набор программных интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="c5321-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="c5321-113">Эти API позволяют автоматизировать рабочие процессы и внедрять их на основе возможностей защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c5321-113">Those APIs will enable you to automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="c5321-114">Для доступа к API требуется проверка подлинности OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="c5321-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="c5321-115">Для получения дополнительных сведений см [код авторизации OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="c5321-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="c5321-116">В общем случае необходимо выполнить следующие действия, чтобы использовать API:</span><span class="sxs-lookup"><span data-stu-id="c5321-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="c5321-117">Создание приложения AAD</span><span class="sxs-lookup"><span data-stu-id="c5321-117">Create an AAD application</span></span>
- <span data-ttu-id="c5321-118">Получение маркера доступа с помощью этого приложения</span><span class="sxs-lookup"><span data-stu-id="c5321-118">Get an access token using this application</span></span>
- <span data-ttu-id="c5321-119">Использование маркера для доступа к API защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5321-119">Use the token to access Microsoft 365 Defender API</span></span>

<span data-ttu-id="c5321-120">На этой странице объясняется, как создать приложение AAD, получить маркер доступа для защитника Microsoft 365 и проверить маркер.</span><span class="sxs-lookup"><span data-stu-id="c5321-120">This page explains how to create an AAD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="c5321-121">При доступе к API защитника Microsoft 365 от имени пользователя вам потребуется разрешение приложения и разрешение пользователя.</span><span class="sxs-lookup"><span data-stu-id="c5321-121">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct Application permission and user permission.</span></span>


>[!TIP]
> <span data-ttu-id="c5321-122">Если у вас есть разрешение на выполнение действий на портале, у вас есть разрешение на выполнение действия в API.</span><span class="sxs-lookup"><span data-stu-id="c5321-122">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="c5321-123">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="c5321-123">Create an app</span></span>

1. <span data-ttu-id="c5321-124">Войдите в [Azure](https://portal.azure.com) с помощью учетной записи пользователя с ролью **глобального администратора** .</span><span class="sxs-lookup"><span data-stu-id="c5321-124">Log on to [Azure](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="c5321-125">Перейдите к разделу Регистрация приложений **Azure Active Directory** с  >  **App registrations**  >  **новой регистрацией**.</span><span class="sxs-lookup"><span data-stu-id="c5321-125">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Изображение Microsoft Azure и переход к регистрации приложения](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="c5321-127">В поле регистрация из введите следующие сведения, а затем нажмите кнопку **Регистрация**.</span><span class="sxs-lookup"><span data-stu-id="c5321-127">In the registration from, enter the following information then click **Register**.</span></span>

   ![Изображение окна "Создание приложения"](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="c5321-129">**Имя:** Имя приложения</span><span class="sxs-lookup"><span data-stu-id="c5321-129">**Name:** Your application name</span></span>
   - <span data-ttu-id="c5321-130">**Тип приложения:** Общедоступный клиент</span><span class="sxs-lookup"><span data-stu-id="c5321-130">**Application type:** Public client</span></span>
   - <span data-ttu-id="c5321-131">**URI перенаправления:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="c5321-131">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="c5321-132">Чтобы разрешить приложению доступ к защитнику Microsoft 365 и назначить ему разрешения, на странице приложения выберите **разрешения API**  >  **добавления разрешений**  >  **интерфейсы API** , которые использует >, введите **Microsoft 365 защитник** , а затем выберите **защитник Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="c5321-132">To enable your app to access Microsoft 365 Defender and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft 365 Defender** , and then select **Microsoft 365 Defender**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="c5321-133">Защитник Microsoft 365 не отображается в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="c5321-133">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="c5321-134">Чтобы отобразить его имя, необходимо сначала начать его ввод в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="c5321-134">You need to start writing its name in the text box to see it appear.</span></span>

      ![Изображение доступа к API и выбора API](../../media/apis-in-my-org-tab.PNG)

    - <span data-ttu-id="c5321-136">Выберите **делегированные разрешения** > выберите соответствующие разрешения для вашего сценария, например " **инцидент. чтение** ", а затем нажмите кнопку **Добавить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="c5321-136">Choose **Delegated permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read** , and then select **Add permissions**.</span></span>

      ![Изображение доступа к API и выбора API](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     ><span data-ttu-id="c5321-138">Необходимо выбрать соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="c5321-138">You need to select the relevant permissions.</span></span> 

    -  <span data-ttu-id="c5321-139">Чтобы определить, какое разрешение необходимо, просмотрите раздел **разрешения** в API, который вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="c5321-139">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="c5321-140">Щелкните **разрешение GRANT**</span><span class="sxs-lookup"><span data-stu-id="c5321-140">Click **Grant consent**</span></span>

      >[!NOTE]
      ><span data-ttu-id="c5321-141">Каждый раз при добавлении разрешения необходимо щелкнуть разрешение **Grant** , чтобы новое разрешение вступило в силу.</span><span class="sxs-lookup"><span data-stu-id="c5321-141">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

      ![Изображение разрешений GRANT](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="c5321-143">Запишите идентификатор своего приложения и идентификатор клиента:</span><span class="sxs-lookup"><span data-stu-id="c5321-143">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="c5321-144">На странице приложения перейдите в раздел **Overview (обзор** ) и скопируйте следующее:</span><span class="sxs-lookup"><span data-stu-id="c5321-144">On your application page, go to **Overview** and copy the following:</span></span>

   ![Изображение идентификатора созданного приложения](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="c5321-146">Получение маркера доступа с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5321-146">Get an access token using PowerShell</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="c5321-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c5321-147">Related topics</span></span>
- [<span data-ttu-id="c5321-148">Доступ к API-интерфейсам защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5321-148">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="c5321-149">Доступ к защитнику Microsoft 365 с контекстом приложения</span><span class="sxs-lookup"><span data-stu-id="c5321-149">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
