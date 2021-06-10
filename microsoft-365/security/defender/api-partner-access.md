---
title: Доступ партнеров Microsoft 365 API Defender
description: Узнайте, как создать приложение, чтобы получить программный доступ к Microsoft 365 Defender от имени пользователей.
keywords: партнер, доступ, api, мульти-клиент, согласие, маркер доступа, приложение
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
ms.openlocfilehash: 46876fef8a0279ee350d57fdc85aeced82696656
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070077"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="7bedf-104">Создание приложения с партнерским доступом Microsoft 365 API Defender</span><span class="sxs-lookup"><span data-stu-id="7bedf-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7bedf-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7bedf-105">**Applies to:**</span></span>

- <span data-ttu-id="7bedf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bedf-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7bedf-107">Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="7bedf-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7bedf-108">Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.</span><span class="sxs-lookup"><span data-stu-id="7bedf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="7bedf-109">На этой странице описывается создание приложения Azure Active Directory, которое имеет программный доступ к Microsoft 365 Defender от имени пользователей нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="7bedf-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="7bedf-110">Приложения с несколькими клиентами полезны для обслуживания больших групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="7bedf-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="7bedf-111">Если вам необходим программный доступ к Microsoft 365 Defender от имени одного пользователя, см. в раздел Создание приложения для доступа Microsoft 365 API Defender от [имени пользователя.](api-create-app-user-context.md)</span><span class="sxs-lookup"><span data-stu-id="7bedf-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="7bedf-112">Если вам необходим доступ без явно определенного пользователя (например, если вы пишете фоновое приложение или daemon), см. статью Создание приложения для доступа к Microsoft 365 Defender без [пользователя](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="7bedf-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="7bedf-113">Если вы не уверены, какой доступ вам нужен, см. [в этой ленте Начало](api-access.md)работы.</span><span class="sxs-lookup"><span data-stu-id="7bedf-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="7bedf-114">Microsoft 365 Defender предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="7bedf-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="7bedf-115">Эти API помогают автоматизировать рабочий процесс и использовать возможности Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7bedf-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="7bedf-116">Этот доступ к API требует проверки подлинности OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="7bedf-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="7bedf-117">Дополнительные сведения см. [в тексте OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="7bedf-117">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="7bedf-118">В общем, для использования этих API необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7bedf-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="7bedf-119">Создание приложения Azure Active Directory Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7bedf-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="7bedf-120">Получение маркера доступа с помощью этого приложения.</span><span class="sxs-lookup"><span data-stu-id="7bedf-120">Get an access token using this application.</span></span>
- <span data-ttu-id="7bedf-121">Используйте маркер для доступа к API Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7bedf-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="7bedf-122">Так как это приложение является нескольким клиентом, вам также потребуется согласие администратора от каждого клиента от имени его пользователей. [](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant)</span><span class="sxs-lookup"><span data-stu-id="7bedf-122">Since this app is multi-tenant, you'll also need [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="7bedf-123">В этой статье объясняется, как:</span><span class="sxs-lookup"><span data-stu-id="7bedf-123">This article explains how to:</span></span>

- <span data-ttu-id="7bedf-124">Создание **многоканального приложения** Azure AD</span><span class="sxs-lookup"><span data-stu-id="7bedf-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="7bedf-125">Получите авторизованный согласие администратора пользователя на доступ к необходимому Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7bedf-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="7bedf-126">Получите маркер доступа к Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bedf-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="7bedf-127">Проверка маркера</span><span class="sxs-lookup"><span data-stu-id="7bedf-127">Validate the token</span></span>

<span data-ttu-id="7bedf-128">Microsoft 365 Defender предоставляет большую часть своих данных и действий с помощью набора программных API.</span><span class="sxs-lookup"><span data-stu-id="7bedf-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="7bedf-129">Эти API помогут автоматизировать потоки работы и вносимые Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7bedf-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="7bedf-130">Доступ к API требует проверки подлинности OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="7bedf-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="7bedf-131">Дополнительные сведения см. [в тексте OAuth 2.0 Authorization Code Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="7bedf-131">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="7bedf-132">В общем, для использования API необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7bedf-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="7bedf-133">Создание приложения Azure AD с **несколькими** клиентами.</span><span class="sxs-lookup"><span data-stu-id="7bedf-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="7bedf-134">Получите авторизованный (согласие) администратор пользователя для приложения для доступа Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7bedf-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="7bedf-135">Получение маркера доступа с помощью этого приложения.</span><span class="sxs-lookup"><span data-stu-id="7bedf-135">Get an access token using this application.</span></span>
- <span data-ttu-id="7bedf-136">Используйте маркер для доступа к API Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7bedf-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="7bedf-137">В следующих действиях вы можете узнать, как создать многоканальный приложение Azure AD, получить маркер доступа Microsoft 365 Defender и проверить маркер.</span><span class="sxs-lookup"><span data-stu-id="7bedf-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="7bedf-138">Создание приложения с несколькими клиентами</span><span class="sxs-lookup"><span data-stu-id="7bedf-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="7bedf-139">Во входе [в Azure](https://portal.azure.com) в качестве пользователя с **ролью глобального администратора.**</span><span class="sxs-lookup"><span data-stu-id="7bedf-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="7bedf-140">Перейдите **к Azure Active Directory**  >  **регистрации Приложений** Новая  >  **регистрация**.</span><span class="sxs-lookup"><span data-stu-id="7bedf-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Изображение Microsoft Azure и навигации для регистрации приложений](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="7bedf-142">В форме регистрации:</span><span class="sxs-lookup"><span data-stu-id="7bedf-142">In the registration form:</span></span>

   - <span data-ttu-id="7bedf-143">Выберите имя приложения.</span><span class="sxs-lookup"><span data-stu-id="7bedf-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="7bedf-144">Из **поддерживаемых типов учетных** записей выберите учетные записи в любом организационном каталоге **(любой каталог Azure AD) — Multitenant**.</span><span class="sxs-lookup"><span data-stu-id="7bedf-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="7bedf-145">Заполните раздел **URI перенаправления.**</span><span class="sxs-lookup"><span data-stu-id="7bedf-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="7bedf-146">Выберите **веб-тип** и дайте URI перенаправления как **https://portal.azure.com** .</span><span class="sxs-lookup"><span data-stu-id="7bedf-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="7bedf-147">После заполнения формы выберите Register **.**</span><span class="sxs-lookup"><span data-stu-id="7bedf-147">After you're done filling out the form, select **Register**.</span></span>

   ![Изображение формы приложения Register](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="7bedf-149">На странице приложения выберите **API Permissions** Add permission API, которые моя организация использует  >    >   >, **введите** Защита от угроз (Майкрософт) и выберите **Защита от угроз (Майкрософт)**.</span><span class="sxs-lookup"><span data-stu-id="7bedf-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="7bedf-150">Теперь приложение может получить доступ к Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7bedf-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="7bedf-151">*Защита от угроз (Майкрософт)* является прежним именем Microsoft 365 Defender и не будет отображаться в исходном списке.</span><span class="sxs-lookup"><span data-stu-id="7bedf-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="7bedf-152">Чтобы увидеть его, необходимо приступить к написанию его имени в текстовом окне.</span><span class="sxs-lookup"><span data-stu-id="7bedf-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![Изображение выбора разрешений API](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="7bedf-154">Выберите **разрешения приложения.**</span><span class="sxs-lookup"><span data-stu-id="7bedf-154">Select **Application permissions**.</span></span> <span data-ttu-id="7bedf-155">Выберите соответствующие разрешения для сценария (например, **Incident.Read.All),** а затем добавьте **разрешения.**</span><span class="sxs-lookup"><span data-stu-id="7bedf-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Изображение доступа к API и выбора API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="7bedf-157">Необходимо выбрать соответствующие разрешения для сценария.</span><span class="sxs-lookup"><span data-stu-id="7bedf-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="7bedf-158">*Чтение всех инцидентов* — это только пример.</span><span class="sxs-lookup"><span data-stu-id="7bedf-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="7bedf-159">Чтобы определить, какое разрешение вам нужно, обратите внимание на раздел **Разрешения** в API, который вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="7bedf-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="7bedf-160">Например, для [запуска расширенных запросов](api-advanced-hunting.md)выберите разрешение "Запуск расширенных запросов"; чтобы [изолировать устройство,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)выберите разрешение "Изолировать машину".</span><span class="sxs-lookup"><span data-stu-id="7bedf-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="7bedf-161">Выберите **согласие администратора Гранта**.</span><span class="sxs-lookup"><span data-stu-id="7bedf-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="7bedf-162">Каждый раз, когда вы добавляете разрешение, необходимо выбрать согласие администратора **Гранта,** чтобы оно вступает в силу.</span><span class="sxs-lookup"><span data-stu-id="7bedf-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Изображение разрешений гранта](../../media/grant-consent.PNG)

7. <span data-ttu-id="7bedf-164">Чтобы добавить секрет в приложение, выберите сертификаты **&,** добавьте описание в секрет, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7bedf-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="7bedf-165">После выбора **Добавить** выберите **скопируйте сгенерированную секретную ценность.**</span><span class="sxs-lookup"><span data-stu-id="7bedf-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="7bedf-166">Вы не сможете получить секретное значение после того, как вы уйдете.</span><span class="sxs-lookup"><span data-stu-id="7bedf-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Изображение ключа создания приложения](../../media/webapp-create-key2.png)

8. <span data-ttu-id="7bedf-168">Запись ID приложения и ID клиента в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="7bedf-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="7bedf-169">Они перечислены в статье **Обзор на** странице приложения.</span><span class="sxs-lookup"><span data-stu-id="7bedf-169">They're listed under **Overview** on your application page.</span></span>

   ![Изображение созданного id приложения](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="7bedf-171">Добавьте приложение в клиент пользователя.</span><span class="sxs-lookup"><span data-stu-id="7bedf-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="7bedf-172">Так как приложение взаимодействует с Microsoft 365 Defender от имени пользователей, оно должно быть утверждено для каждого клиента, на котором вы собираетесь его использовать.</span><span class="sxs-lookup"><span data-stu-id="7bedf-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="7bedf-173">Глобальный **администратор** из клиента пользователя должен просмотреть ссылку согласия и утвердить ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="7bedf-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="7bedf-174">Ссылка согласие имеет форму:</span><span class="sxs-lookup"><span data-stu-id="7bedf-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="7bedf-175">Цифры `00000000-0000-0000-0000-000000000000` должны быть заменены на код приложения.</span><span class="sxs-lookup"><span data-stu-id="7bedf-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="7bedf-176">Нажав на ссылку согласие, войдите в глобальный администратор клиента пользователя и согласите приложение.</span><span class="sxs-lookup"><span data-stu-id="7bedf-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![Изображение согласия](../../media/app-consent-partner.png)

   <span data-ttu-id="7bedf-178">Кроме того, необходимо задать пользователю свой ID клиента.</span><span class="sxs-lookup"><span data-stu-id="7bedf-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="7bedf-179">Идентификатор клиента является одним из идентификаторов, используемых для приобретения маркеров доступа.</span><span class="sxs-lookup"><span data-stu-id="7bedf-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="7bedf-180">**Договорились!**</span><span class="sxs-lookup"><span data-stu-id="7bedf-180">**Done!**</span></span> <span data-ttu-id="7bedf-181">Вы успешно зарегистрировали приложение!</span><span class="sxs-lookup"><span data-stu-id="7bedf-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="7bedf-182">Ниже приведены примеры приобретения и проверки маркеров.</span><span class="sxs-lookup"><span data-stu-id="7bedf-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="7bedf-183">Получение токена доступа</span><span class="sxs-lookup"><span data-stu-id="7bedf-183">Get an access token</span></span>

<span data-ttu-id="7bedf-184">Дополнительные сведения о маркерах Azure AD см. в руководстве [Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="7bedf-184">For more information on Azure AD tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7bedf-185">Хотя в примерах этого раздела рекомендуется вклеить секретные значения  для целей тестирования, никогда не следует секретов жесткого кода в приложение, запущенное в производстве.</span><span class="sxs-lookup"><span data-stu-id="7bedf-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="7bedf-186">Третья сторона может использовать ваш секрет для доступа к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="7bedf-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="7bedf-187">Вы можете помочь сохранить секреты вашего приложения в безопасности с помощью [Хранилища ключей Azure.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="7bedf-187">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="7bedf-188">Пример того, как защитить приложение, см. в примере Управление секретами в серверных приложениях [с помощью хранилища ключей Azure.](/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="7bedf-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="7bedf-189">В следующих примерах используйте пользовательский ID клиента, чтобы проверить, работает ли сценарий.</span><span class="sxs-lookup"><span data-stu-id="7bedf-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="7bedf-190">Получить маркер доступа с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="7bedf-190">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="7bedf-191">Получить маркер доступа с помощью C\#</span><span class="sxs-lookup"><span data-stu-id="7bedf-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="7bedf-192">Следующий код был протестирован с помощью Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="7bedf-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="7bedf-193">Создайте новое консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="7bedf-193">Create a new console application.</span></span>
1. <span data-ttu-id="7bedf-194">Установка NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="7bedf-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="7bedf-195">Добавьте следующую строку:</span><span class="sxs-lookup"><span data-stu-id="7bedf-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="7bedf-196">Скопируйте и вклейте в приложение следующий код (не забудьте обновить три переменные: `tenantId` `clientId` , , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="7bedf-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="7bedf-197">Получить маркер доступа с помощью Python</span><span class="sxs-lookup"><span data-stu-id="7bedf-197">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="7bedf-198">Получить маркер доступа с помощью завитка</span><span class="sxs-lookup"><span data-stu-id="7bedf-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="7bedf-199">Curl предварительно установлен на Windows 10 версии 1803 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="7bedf-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="7bedf-200">Для других версий Windows скачайте и установите средство непосредственно с [официального веб-сайта curl.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="7bedf-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="7bedf-201">Откройте командную подсказку и установите CLIENT_ID к вашему ID приложения Azure.</span><span class="sxs-lookup"><span data-stu-id="7bedf-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="7bedf-202">Установите CLIENT_SECRET для секрета приложения Azure.</span><span class="sxs-lookup"><span data-stu-id="7bedf-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="7bedf-203">Установите TENANT_ID имя клиента Azure для пользователя, который хочет использовать приложение для доступа к Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7bedf-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="7bedf-204">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7bedf-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="7bedf-205">Успешный ответ будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="7bedf-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="7bedf-206">Проверка маркера</span><span class="sxs-lookup"><span data-stu-id="7bedf-206">Validate the token</span></span>

1. <span data-ttu-id="7bedf-207">Скопируйте и вклеите маркер на веб-сайт валидатора веб-маркеров [JSON JWT,](https://jwt.ms) чтобы расшифровать его.</span><span class="sxs-lookup"><span data-stu-id="7bedf-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="7bedf-208">Убедитесь, что *утверждение ролей* в расшифроваемом маркере содержит нужные разрешения.</span><span class="sxs-lookup"><span data-stu-id="7bedf-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="7bedf-209">На следующем изображении можно увидеть расшифровав маркер, приобретенный из приложения, с разрешениями и ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` разрешениями:</span><span class="sxs-lookup"><span data-stu-id="7bedf-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Изображение проверки маркеров](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="7bedf-211">Используйте маркер для доступа к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bedf-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="7bedf-212">Выберите API, который вы хотите использовать (инциденты или расширенный поиск).</span><span class="sxs-lookup"><span data-stu-id="7bedf-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="7bedf-213">Дополнительные сведения см. в [Microsoft 365 API Defender.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="7bedf-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="7bedf-214">В http-запросе, который вы отправляете, задайте загон авторизации , Bearer является схемой авторизации, а маркер - `"Bearer" <token>` проверенным маркером.  </span><span class="sxs-lookup"><span data-stu-id="7bedf-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="7bedf-215">Срок действия маркера истекает в течение одного часа.</span><span class="sxs-lookup"><span data-stu-id="7bedf-215">The token will expire within one hour.</span></span> <span data-ttu-id="7bedf-216">За это время вы можете отправить несколько запросов с одним маркером.</span><span class="sxs-lookup"><span data-stu-id="7bedf-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="7bedf-217">В следующем примере показано, как отправить запрос для получения списка инцидентов **с C#**.</span><span class="sxs-lookup"><span data-stu-id="7bedf-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="7bedf-218">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="7bedf-218">Related articles</span></span>

- [<span data-ttu-id="7bedf-219">Microsoft 365 Обзор API defender</span><span class="sxs-lookup"><span data-stu-id="7bedf-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="7bedf-220">Доступ к API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bedf-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="7bedf-221">Создание приложения "Hello world"</span><span class="sxs-lookup"><span data-stu-id="7bedf-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="7bedf-222">Создание приложения для доступа Microsoft 365 Defender без пользователя</span><span class="sxs-lookup"><span data-stu-id="7bedf-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="7bedf-223">Создание приложения для доступа Microsoft 365 API Defender от имени пользователя</span><span class="sxs-lookup"><span data-stu-id="7bedf-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="7bedf-224">Узнайте о ограничениях API и лицензировании</span><span class="sxs-lookup"><span data-stu-id="7bedf-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="7bedf-225">Понимание кодов ошибок</span><span class="sxs-lookup"><span data-stu-id="7bedf-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="7bedf-226">Управление секретами в приложениях сервера с помощью хранилища ключей Azure</span><span class="sxs-lookup"><span data-stu-id="7bedf-226">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="7bedf-227">Авторизация OAuth 2.0 для входов пользователей и доступа к API</span><span class="sxs-lookup"><span data-stu-id="7bedf-227">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)