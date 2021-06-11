---
title: Использование Microsoft Defender для API конечных точек
ms.reviewer: ''
description: Узнайте, как создать родной Windows, чтобы получить программный доступ к Microsoft Defender для конечной точки без пользователя.
keywords: apis, api graph, supported apis, actor, alerts, device, user, domain, ip, file, advanced hunting, query
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
ms.openlocfilehash: 876dddf7a68b9844dea6a30ff4ebbbe3c2b75b69
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844554"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="0ed62-104">Использование Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="0ed62-104">Use Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0ed62-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="0ed62-105">**Applies to:**</span></span>
- [<span data-ttu-id="0ed62-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="0ed62-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="0ed62-107">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="0ed62-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0ed62-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="0ed62-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="0ed62-109">На этой странице описывается создание приложения для получения программного доступа к Защитнику для конечной точки от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="0ed62-109">This page describes how to create an application to get programmatic access to Defender for Endpoint on behalf of a user.</span></span>

<span data-ttu-id="0ed62-110">Если вам нужен программный доступ Microsoft Defender для конечной точки без пользователя, обратитесь к Access Microsoft Defender для конечной точки [с контекстом приложений.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="0ed62-110">If you need programmatic access Microsoft Defender for Endpoint without a user, refer to [Access Microsoft Defender for Endpoint with application context](exposed-apis-create-app-webapp.md).</span></span>

<span data-ttu-id="0ed62-111">Если вы не уверены, какой доступ вам нужен, прочитайте страницу [Введение](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="0ed62-111">If you are not sure which access you need, read the [Introduction page](apis-intro.md).</span></span>

<span data-ttu-id="0ed62-112">Microsoft Defender для конечной точки предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="0ed62-112">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="0ed62-113">Эти API позволят автоматизировать потоки работы и вносимые новации на основе возможностей Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="0ed62-113">Those APIs will enable you to automate work flows and innovate based on Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="0ed62-114">Доступ к API требует проверки подлинности OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="0ed62-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="0ed62-115">Дополнительные сведения см. [в тексте OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="0ed62-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="0ed62-116">В общем, для использования API необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0ed62-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="0ed62-117">Создание приложения AAD</span><span class="sxs-lookup"><span data-stu-id="0ed62-117">Create an AAD application</span></span>
- <span data-ttu-id="0ed62-118">Получение маркера доступа с помощью этого приложения</span><span class="sxs-lookup"><span data-stu-id="0ed62-118">Get an access token using this application</span></span>
- <span data-ttu-id="0ed62-119">Использование маркера для доступа к API Defender для endpoint</span><span class="sxs-lookup"><span data-stu-id="0ed62-119">Use the token to access Defender for Endpoint API</span></span>

<span data-ttu-id="0ed62-120">На этой странице рассказывается, как создать приложение AAD, получить маркер доступа в Microsoft Defender для конечной точки и проверить маркер.</span><span class="sxs-lookup"><span data-stu-id="0ed62-120">This page explains how to create an AAD application, get an access token to Microsoft Defender for Endpoint and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="0ed62-121">При доступе к API Microsoft Defender для конечной точки от имени пользователя вам потребуется правильное разрешение приложения и разрешение пользователя.</span><span class="sxs-lookup"><span data-stu-id="0ed62-121">When accessing Microsoft Defender for Endpoint API on behalf of a user, you will need the correct Application permission and user permission.</span></span>
> <span data-ttu-id="0ed62-122">Если вы не знакомы с разрешениями пользователей в Microsoft Defender для конечной точки, см. в рублях Управление доступом к порталу с помощью управления доступом на основе [ролей.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="0ed62-122">If you are not familiar with user permissions on Microsoft Defender for Endpoint, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="0ed62-123">Если у вас есть разрешение на выполнение действия на портале, у вас есть разрешение на выполнение действия в API.</span><span class="sxs-lookup"><span data-stu-id="0ed62-123">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="0ed62-124">Создать приложение</span><span class="sxs-lookup"><span data-stu-id="0ed62-124">Create an app</span></span>

1. <span data-ttu-id="0ed62-125">Войдите в [Azure](https://portal.azure.com) с учетной записью пользователя, которая имеет роль **глобального администратора.**</span><span class="sxs-lookup"><span data-stu-id="0ed62-125">Log on to [Azure](https://portal.azure.com) with a user account that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="0ed62-126">Перейдите **к Azure Active Directory**  >  **регистрации Приложений** Новая  >  **регистрация**.</span><span class="sxs-lookup"><span data-stu-id="0ed62-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Изображение Microsoft Azure и навигации для регистрации приложений](images/atp-azure-new-app2.png)

3. <span data-ttu-id="0ed62-128">После появления страницы **Регистрация приложения** введите сведения о регистрации приложения:</span><span class="sxs-lookup"><span data-stu-id="0ed62-128">When the **Register an application** page appears, enter your application's registration information:</span></span>

   - <span data-ttu-id="0ed62-129">**Имя** — введите информативное имя приложения, которое будет отображаться пользователям приложения.</span><span class="sxs-lookup"><span data-stu-id="0ed62-129">**Name** - Enter a meaningful application name that will be displayed to users of the app.</span></span>
   - <span data-ttu-id="0ed62-130">**Поддерживаемые типы учетных записей** — выберите учетные записи, которые должно поддерживать приложение.</span><span class="sxs-lookup"><span data-stu-id="0ed62-130">**Supported account types** - Select which accounts you would like your application to support.</span></span>

       | <span data-ttu-id="0ed62-131">Поддерживаемые типы учетных записей</span><span class="sxs-lookup"><span data-stu-id="0ed62-131">Supported account types</span></span> | <span data-ttu-id="0ed62-132">Описание</span><span class="sxs-lookup"><span data-stu-id="0ed62-132">Description</span></span> |
       |-------------------------|-------------|
       | <span data-ttu-id="0ed62-133">**Учетные записи только в этом каталоге организации**</span><span class="sxs-lookup"><span data-stu-id="0ed62-133">**Accounts in this organizational directory only**</span></span> | <span data-ttu-id="0ed62-134">Этот вариант подходит для создания бизнес-приложений.</span><span class="sxs-lookup"><span data-stu-id="0ed62-134">Select this option if you're building a line-of-business (LOB) application.</span></span> <span data-ttu-id="0ed62-135">Он будет недоступен, если приложение не регистрируется в каталоге.</span><span class="sxs-lookup"><span data-stu-id="0ed62-135">This option is not available if you're not registering the application in a directory.</span></span><br><br><span data-ttu-id="0ed62-136">Этот параметр сопоставляется с Azure AD только одного клиента.</span><span class="sxs-lookup"><span data-stu-id="0ed62-136">This option maps to Azure AD only single-tenant.</span></span><br><br><span data-ttu-id="0ed62-137">Этот параметр используется по умолчанию, если только приложение не регистрируется за пределами каталога.</span><span class="sxs-lookup"><span data-stu-id="0ed62-137">This is the default option unless you're registering the app outside of a directory.</span></span> <span data-ttu-id="0ed62-138">Если приложение зарегистрировано за пределами каталога, по умолчанию используются личные учетные записи Майкрософт и учетные записи с несколькими клиентами Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0ed62-138">In cases where the app is registered outside of a directory, the default is Azure AD multi-tenant and personal Microsoft accounts.</span></span> |
       | <span data-ttu-id="0ed62-139">**Учетные записи в любом каталоге организации**</span><span class="sxs-lookup"><span data-stu-id="0ed62-139">**Accounts in any organizational directory**</span></span> | <span data-ttu-id="0ed62-140">Выберите этот параметр, если вы хотите выбрать в качестве целевой аудитории предприятия и учебные заведения.</span><span class="sxs-lookup"><span data-stu-id="0ed62-140">Select this option if you would like to target all business and educational customers.</span></span><br><br><span data-ttu-id="0ed62-141">Этот параметр сопоставляется с Azure AD только для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="0ed62-141">This option maps to an Azure AD only multi-tenant.</span></span><br><br><span data-ttu-id="0ed62-142">Если вы зарегистрировали приложение как приложение AAD с одним клиентом, можно обновить его до AAD с несколькими клиентами, а затем вернуться к отдельному клиенту с помощью колонки **Проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="0ed62-142">If you registered the app as Azure AD only single-tenant, you can update it to be Azure AD multi-tenant and back to single-tenant through the **Authentication** blade.</span></span> |
       | <span data-ttu-id="0ed62-143">**Учетные записи в любом каталоге организации и личные учетные записи Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="0ed62-143">**Accounts in any organizational directory and personal Microsoft accounts**</span></span> | <span data-ttu-id="0ed62-144">Выберите этот параметр для широкого круга пользователей.</span><span class="sxs-lookup"><span data-stu-id="0ed62-144">Select this option to target the widest set of customers.</span></span><br><br><span data-ttu-id="0ed62-145">Этот параметр сопоставляется с Azure AD с несколькими клиентами и личными учетными записями Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0ed62-145">This option maps to Azure AD multi-tenant and personal Microsoft accounts.</span></span><br><br><span data-ttu-id="0ed62-146">Если вы зарегистрировали приложение как личные учетные записи Майкрософт и Azure AD с несколькими клиентами, это нельзя изменить в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="0ed62-146">If you registered the app as Azure AD multi-tenant and personal Microsoft accounts, you cannot change this in the UI.</span></span> <span data-ttu-id="0ed62-147">Вместо этого необходимо использовать редактор манифеста приложения для изменения типов поддерживаемых учетных записей.</span><span class="sxs-lookup"><span data-stu-id="0ed62-147">Instead, you must use the application manifest editor to change the supported account types.</span></span> |

   - <span data-ttu-id="0ed62-148">**URI перенаправления (необязательно)** — выберите тип приложения, которое вы создаете — **Веб** или **Общедоступный клиент (мобильный и классический)**, а затем введите универсальный код ресурса (URI) перенаправления (или URL-адрес ответа) приложения.</span><span class="sxs-lookup"><span data-stu-id="0ed62-148">**Redirect URI (optional)** - Select the type of app you're building, **Web** or **Public client (mobile & desktop)**, and then enter the redirect URI (or reply URL) for your application.</span></span>
       - <span data-ttu-id="0ed62-149">Для веб-приложений укажите основной URL-адрес приложения.</span><span class="sxs-lookup"><span data-stu-id="0ed62-149">For web applications, provide the base URL of your app.</span></span> <span data-ttu-id="0ed62-150">Например, `http://localhost:31544` может быть URL-адресом веб-приложения, выполняемого на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0ed62-150">For example, `http://localhost:31544` might be the URL for a web app running on your local machine.</span></span> <span data-ttu-id="0ed62-151">Пользователи будут использовать этот URL-адрес для входа в приложение веб-клиента.</span><span class="sxs-lookup"><span data-stu-id="0ed62-151">Users would use this URL to sign in to a web client application.</span></span>
       - <span data-ttu-id="0ed62-152">Для общедоступных клиентских приложений укажите универсальный код ресурса (URI), который использует AAD для возвращения ответов маркера.</span><span class="sxs-lookup"><span data-stu-id="0ed62-152">For public client applications, provide the URI used by Azure AD to return token responses.</span></span> <span data-ttu-id="0ed62-153">Укажите значение, специфичное для вашего приложения, например `myapp://auth`.</span><span class="sxs-lookup"><span data-stu-id="0ed62-153">Enter a value specific to your application, such as `myapp://auth`.</span></span>

     <span data-ttu-id="0ed62-154">Конкретные примеры для веб-приложений или собственных приложений см. в наших [кратких руководствах](/azure/active-directory/develop/#quickstarts).</span><span class="sxs-lookup"><span data-stu-id="0ed62-154">To see specific examples for web applications or native applications, check out our [quickstarts](/azure/active-directory/develop/#quickstarts).</span></span>

     <span data-ttu-id="0ed62-155">По завершении щелкните **Зарегистрировать**.</span><span class="sxs-lookup"><span data-stu-id="0ed62-155">When finished, select **Register**.</span></span>

4. <span data-ttu-id="0ed62-156">Разрешить приложению доступ к Microsoft Defender для конечной точки и назначить ему разрешение на чтение оповещений:</span><span class="sxs-lookup"><span data-stu-id="0ed62-156">Allow your Application to access Microsoft Defender for Endpoint and assign it 'Read alerts' permission:</span></span>

    - <span data-ttu-id="0ed62-157">На странице приложения выберите **API Permissions** Add  >  **permissionS** my  >  **organization uses** > **WindowsDefenderATP** и выберите в **WindowsDefenderATP**.</span><span class="sxs-lookup"><span data-stu-id="0ed62-157">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and select on **WindowsDefenderATP**.</span></span>

    - <span data-ttu-id="0ed62-158">**Примечание.** *WindowsDefenderATP* не появляется в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="0ed62-158">**Note**: *WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="0ed62-159">Начните писать свое имя в текстовом окне, чтобы увидеть его.</span><span class="sxs-lookup"><span data-stu-id="0ed62-159">Start writing its name in the text box to see it appear.</span></span>

      ![добавление разрешений](images/add-permission.png)

    - <span data-ttu-id="0ed62-161">Выберите **делегирование разрешений**  >  **Alert.Read** > добавление **разрешений**</span><span class="sxs-lookup"><span data-stu-id="0ed62-161">Choose **Delegated permissions** > **Alert.Read** > select **Add permissions**</span></span>

      ![разрешения приложения](images/application-permissions-public-client.png)

    - <span data-ttu-id="0ed62-163">**Важное примечание.** Выберите соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="0ed62-163">**Important note**: Select the relevant permissions.</span></span> <span data-ttu-id="0ed62-164">Чтение оповещений — это только пример.</span><span class="sxs-lookup"><span data-stu-id="0ed62-164">Read alerts is only an example.</span></span>

      <span data-ttu-id="0ed62-165">Например,</span><span class="sxs-lookup"><span data-stu-id="0ed62-165">For instance,</span></span>

      - <span data-ttu-id="0ed62-166">Чтобы [запускать расширенные запросы,](run-advanced-query-api.md)выберите разрешение "Запуск расширенных запросов"</span><span class="sxs-lookup"><span data-stu-id="0ed62-166">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
      - <span data-ttu-id="0ed62-167">Чтобы [изолировать устройство,](isolate-machine.md)выберите разрешение "Изолировать машину"</span><span class="sxs-lookup"><span data-stu-id="0ed62-167">To [isolate a device](isolate-machine.md), select 'Isolate machine' permission</span></span>
      - <span data-ttu-id="0ed62-168">Чтобы определить, какое разрешение вам нужно, просмотреть раздел **Разрешения** в API, который вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="0ed62-168">To determine which permission you need, view the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="0ed62-169">Выберите **согласие гранта**</span><span class="sxs-lookup"><span data-stu-id="0ed62-169">Select **Grant consent**</span></span>

      <span data-ttu-id="0ed62-170">**Примечание.** Каждый раз, когда вы добавляете разрешение, необходимо выбрать по согласию **гранта,** чтобы новое разрешение вступает в силу.</span><span class="sxs-lookup"><span data-stu-id="0ed62-170">**Note**: Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

      ![Изображение разрешений гранта](images/grant-consent.png)

6. <span data-ttu-id="0ed62-172">Запишите свой ИД приложения и его клиента:</span><span class="sxs-lookup"><span data-stu-id="0ed62-172">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="0ed62-173">На странице приложения перейдите в **Обзор и** скопируйте следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="0ed62-173">On your application page, go to **Overview** and copy the following information:</span></span>

   ![Изображение созданного id приложения](images/app-and-tenant-ids.png)


## <a name="get-an-access-token"></a><span data-ttu-id="0ed62-175">Получение токена доступа</span><span class="sxs-lookup"><span data-stu-id="0ed62-175">Get an access token</span></span>

<span data-ttu-id="0ed62-176">Дополнительные сведения о маркерах AAD см. в [учебнике Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="0ed62-176">For more information on AAD tokens, see [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-c"></a><span data-ttu-id="0ed62-177">Использование C #</span><span class="sxs-lookup"><span data-stu-id="0ed62-177">Using C#</span></span>

- <span data-ttu-id="0ed62-178">Copy/Paste the below class in your application.</span><span class="sxs-lookup"><span data-stu-id="0ed62-178">Copy/Paste the below class in your application.</span></span>
- <span data-ttu-id="0ed62-179">Чтобы приобрести маркер, используйте метод **AcquireUserTokenAsync** с кодом приложения, ИД клиента, именем пользователя и паролем.</span><span class="sxs-lookup"><span data-stu-id="0ed62-179">Use **AcquireUserTokenAsync** method with your application ID, tenant ID, user name, and password to acquire a token.</span></span>

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a><span data-ttu-id="0ed62-180">Проверка маркера</span><span class="sxs-lookup"><span data-stu-id="0ed62-180">Validate the token</span></span>

<span data-ttu-id="0ed62-181">Убедитесь, что вы получили правильный маркер:</span><span class="sxs-lookup"><span data-stu-id="0ed62-181">Verify to make sure you got a correct token:</span></span>
- <span data-ttu-id="0ed62-182">Копирование/вклейка [в JWT](https://jwt.ms) маркера, который вы получили на предыдущем шаге, чтобы расшифровать его</span><span class="sxs-lookup"><span data-stu-id="0ed62-182">Copy/paste into [JWT](https://jwt.ms) the token you got in the previous step in order to decode it</span></span>
- <span data-ttu-id="0ed62-183">Проверка получения утверждения "scp" с нужными разрешениями приложения</span><span class="sxs-lookup"><span data-stu-id="0ed62-183">Validate you get a 'scp' claim with the desired app permissions</span></span>
- <span data-ttu-id="0ed62-184">На приведенной ниже скриншоте вы можете увидеть расшифровав маркер, приобретенный из приложения в учебнике:</span><span class="sxs-lookup"><span data-stu-id="0ed62-184">In the screenshot below you can see a decoded token acquired from the app in the tutorial:</span></span>

![Изображение проверки маркеров](images/nativeapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="0ed62-186">С помощью маркера можно получить доступ к API Endpoint Defender для Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0ed62-186">Use the token to access Microsoft Defender for Endpoint API</span></span>

- <span data-ttu-id="0ed62-187">Выберите API, который вы хотите использовать . [Поддерживаемый Microsoft Defender для API конечных точек](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="0ed62-187">Choose the API you want to use - [Supported Microsoft Defender for Endpoint APIs](exposed-apis-list.md)</span></span>
- <span data-ttu-id="0ed62-188">Установите заглавную запись авторизации в http-запросе, который вы отправляете в "Bearer {token}" (Bearer — это схема авторизации)</span><span class="sxs-lookup"><span data-stu-id="0ed62-188">Set the Authorization header in the HTTP request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="0ed62-189">Срок действия маркера составляет 1 час (вы можете отправить несколько запросов с одним и тем же маркером)</span><span class="sxs-lookup"><span data-stu-id="0ed62-189">The Expiration time of the token is 1 hour (you can send more than one request with the same token)</span></span>

- <span data-ttu-id="0ed62-190">Пример отправки запроса для получения списка оповещений **с помощью C#**</span><span class="sxs-lookup"><span data-stu-id="0ed62-190">Example of sending a request to get a list of alerts **using C#**</span></span> 

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a><span data-ttu-id="0ed62-191">См. также</span><span class="sxs-lookup"><span data-stu-id="0ed62-191">See also</span></span>
- [<span data-ttu-id="0ed62-192">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="0ed62-192">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="0ed62-193">Доступ к Microsoft Defender для конечной точки с контекстом приложений</span><span class="sxs-lookup"><span data-stu-id="0ed62-193">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
