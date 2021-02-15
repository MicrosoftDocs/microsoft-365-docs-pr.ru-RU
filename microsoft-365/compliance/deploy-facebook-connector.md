---
title: Развертывание соединитела для архива данных страниц Facebook business
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Администраторы могут настроить нативный соединитель для импорта и архива страниц Facebook Business в Microsoft 365. После импорта этих данных в Microsoft 365 вы можете использовать такие функции соответствия требованиям, как удержание по юридическим вопросам, поиск контента и политики хранения для управления данными Facebook вашей организации.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619955"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="da64f-104">Развертывание соединитела для архива данных бизнес-страниц Facebook</span><span class="sxs-lookup"><span data-stu-id="da64f-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="da64f-105">В этой статье содержится пошаговые процедуры развертывания соединители, использующие службу импорта Office 365 для импорта данных со страниц Facebook бизнес в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="da64f-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="da64f-106">Общие сведения об этом процессе и список предварительных условий, необходимых для развертывания соединители Facebook, см. в настройках соединитела для архивации [данных Facebook.](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="da64f-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="da64f-107">Шаг 1. Создание приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="da64f-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="da64f-108">Войдите в учетную запись глобального администратора и войдите в <https://portal.azure.com> нее.</span><span class="sxs-lookup"><span data-stu-id="da64f-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![Создание приложения в AAD](../media/FBCimage1.png)

2. <span data-ttu-id="da64f-110">В левой области навигации щелкните **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="da64f-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Щелкните Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="da64f-112">В левой области навигации щелкните регистрацию приложений **(предварительная версия)** и нажмите кнопку **"Новая регистрация".**</span><span class="sxs-lookup"><span data-stu-id="da64f-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Click **App registrations (Preview)** and then click **New registration**](../media/FBCimage3.png)

4. <span data-ttu-id="da64f-114">Зарегистрируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="da64f-114">Register the application.</span></span> <span data-ttu-id="da64f-115">В поле "URI перенаправления" выберите "Интернет" в списке типов приложений, а затем введите поле <https://portal.azure.com> для URI.</span><span class="sxs-lookup"><span data-stu-id="da64f-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Регистрация приложения](../media/FBCimage4.png)

5. <span data-ttu-id="da64f-117">**Скопируйте ИД приложения (клиента)** и каталог **(клиент)** и сохраните их в текстовом файле или другом безопасном расположении.</span><span class="sxs-lookup"><span data-stu-id="da64f-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="da64f-118">Эти ИД будут применяться на последующих шагах.</span><span class="sxs-lookup"><span data-stu-id="da64f-118">You use these IDs in later steps.</span></span>

   ![Скопируйте ИД приложения и каталог и сохраните их](../media/FBCimage5.png)

6. <span data-ttu-id="da64f-120">Перейдите **к & сертификатов для нового приложения.**</span><span class="sxs-lookup"><span data-stu-id="da64f-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Перейдите к & сертификатов для нового приложения](../media/FBCimage6.png)

7. <span data-ttu-id="da64f-122">Click **New client secret**</span><span class="sxs-lookup"><span data-stu-id="da64f-122">Click **New client secret**</span></span>

   ![Click New client secret](../media/FBCimage7.png)

8. <span data-ttu-id="da64f-124">Создайте новый секрет.</span><span class="sxs-lookup"><span data-stu-id="da64f-124">Create a new secret.</span></span> <span data-ttu-id="da64f-125">В поле описания введите секрет и выберите срок действия.</span><span class="sxs-lookup"><span data-stu-id="da64f-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![Введите секрет и выберите срок действия](../media/FBCimage8.png)

9. <span data-ttu-id="da64f-127">Скопируйте значение секрета и сохраните его в текстовом файле или другом хранилище.</span><span class="sxs-lookup"><span data-stu-id="da64f-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="da64f-128">Это секрет приложения AAD, который будет применяться на последующих шагах.</span><span class="sxs-lookup"><span data-stu-id="da64f-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Скопируйте значение секрета и сохраните его](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="da64f-130">Шаг 2. Развертывание веб-службы соединителя из GitHub в учетной записи Azure</span><span class="sxs-lookup"><span data-stu-id="da64f-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="da64f-131">Перейдите [на этот сайт GitHub и](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) нажмите кнопку **"Развернуть в Azure".**</span><span class="sxs-lookup"><span data-stu-id="da64f-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Нажмите кнопку "Развернуть в Azure"](../media/FBCGithubApp.png)

2. <span data-ttu-id="da64f-133">После нажатия кнопки **"Развернуть в Azure"** вы будете перенаправлены на портал Azure с настраиваемой страницей шаблона.</span><span class="sxs-lookup"><span data-stu-id="da64f-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="da64f-134">Заполните сведения **об основах** **и параметрах** и нажмите кнопку **"Купить".**</span><span class="sxs-lookup"><span data-stu-id="da64f-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="da64f-135">**Подписка:** Выберите свою подписку Azure, в которую вы хотите развернуть веб-службу соединители страниц Facebook для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="da64f-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="da64f-136">**Группа ресурсов:** Выберите или создайте новую группу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="da64f-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="da64f-137">Группа ресурсов — это контейнер, который содержит связанные ресурсы для решения Azure.</span><span class="sxs-lookup"><span data-stu-id="da64f-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="da64f-138">**Расположение:** Выберите расположение.</span><span class="sxs-lookup"><span data-stu-id="da64f-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="da64f-139">**Имя веб-приложения:** Укажет уникальное имя для веб-приложения соединители.</span><span class="sxs-lookup"><span data-stu-id="da64f-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="da64f-140">Длина имени должна быть от 3 до 18 символов.</span><span class="sxs-lookup"><span data-stu-id="da64f-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="da64f-141">Это имя используется для создания URL-адреса службы приложений Azure; Например, если у вас есть имя **fbconnector** для **веб-приложения,** URL-адрес службы приложений Azure будет fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="da64f-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="da64f-142">**tenantId:** ИД клиента вашей организации Microsoft 365, который вы скопировали после создания приложения соединители Facebook в Azure Active Directory на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="da64f-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="da64f-143">**APISecretKey:** В качестве секрета можно ввести любое значение.</span><span class="sxs-lookup"><span data-stu-id="da64f-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="da64f-144">Это используется для доступа к веб-приложению соединители на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="da64f-144">This is used to access the connector web app in Step 5.</span></span>

     ![Нажмите кнопку "Создать ресурс" и введите учетную запись хранения](../media/FBCimage12.png)

3. <span data-ttu-id="da64f-146">После успешного развертывания страница будет выглядеть примерно так, как по снимку экрана:</span><span class="sxs-lookup"><span data-stu-id="da64f-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Щелкните "Хранилище", а затем выберите учетную запись хранилища](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="da64f-148">Шаг 3. Регистрация приложения Facebook</span><span class="sxs-lookup"><span data-stu-id="da64f-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="da64f-149">Go to <https://developers.facebook.com> , log in using the credentials for the account for your organization's Facebook Business pages, and then click Add New **App**.</span><span class="sxs-lookup"><span data-stu-id="da64f-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Добавление новой страницы приложения для Facebook для бизнеса](../media/FBCimage25.png)

2. <span data-ttu-id="da64f-151">Создайте новый ИД приложения.</span><span class="sxs-lookup"><span data-stu-id="da64f-151">Create a new app ID.</span></span>

   ![Создание нового ИД приложения](../media/FBCimage26.png)

3. <span data-ttu-id="da64f-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span><span class="sxs-lookup"><span data-stu-id="da64f-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Нажмите кнопку "Добавить продукты"](../media/FBCimage27.png)

4. <span data-ttu-id="da64f-155">On the Integrate Facebook Login page, click **Web**.</span><span class="sxs-lookup"><span data-stu-id="da64f-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Click Web on the Integrate Facebook Login page](../media/FBCimage28.png)

5. <span data-ttu-id="da64f-157">Добавление URL-адреса службы приложений Azure; например. `https://fbconnector.azurewebsites.net`</span><span class="sxs-lookup"><span data-stu-id="da64f-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Добавление URL-адреса службы приложений Azure](../media/FBCimage29.png)

6. <span data-ttu-id="da64f-159">Завершите раздел QuickStart настройки входа в Facebook.</span><span class="sxs-lookup"><span data-stu-id="da64f-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Завершение раздела QuickStart](../media/FBCimage30.png)

7. <span data-ttu-id="da64f-161">In the left navigation pane under **Facebook Login,** click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URI** box.</span><span class="sxs-lookup"><span data-stu-id="da64f-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="da64f-162">Используйте формат **\<connectorserviceuri> /Views/FacebookOAuth,** где значением connectorserviceuri является URL-адрес службы приложений Azure для вашей организации, например `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="da64f-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Добавление URI перенаправления OAuth в поле "Допустимые URI перенаправления OAuth"](../media/FBCimage31.png)

8. <span data-ttu-id="da64f-164">В левой области навигации  щелкните "Добавить продукты", а затем щелкните **"Веб-hooks".**</span><span class="sxs-lookup"><span data-stu-id="da64f-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="da64f-165">В  оттягиваемом меню "Страница" щелкните **"Страница".**</span><span class="sxs-lookup"><span data-stu-id="da64f-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![Click Add Products and then click \*\*Webhooks](../media/FBCimage32.png)

9. <span data-ttu-id="da64f-167">Добавьте URL-адрес веб-вызова и маркер проверки.</span><span class="sxs-lookup"><span data-stu-id="da64f-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="da64f-168">В формате URL-адреса для вызова используйте формат **<connectorserviceuri> /api/FbPageWebhook,** где значением соединителяserviceuri является URL-адрес службы приложений Azure для вашей организации, например `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="da64f-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="da64f-169">Маркер проверки должен быть похож на надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="da64f-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="da64f-170">Скопируйте маркер проверки в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="da64f-170">Copy the verify token to a text file or other storage location.</span></span>

   ![Добавление маркера проверки](../media/FBCimage33.png)

10. <span data-ttu-id="da64f-172">Протестировать и подписаться на конечную точку для веб-канала.</span><span class="sxs-lookup"><span data-stu-id="da64f-172">Test and subscribe to the endpoint for feed.</span></span>

    ![Тестирование и подписка на конечную точку](../media/FBCimage34.png)

11. <span data-ttu-id="da64f-174">Добавьте URL-адрес конфиденциальности, значок приложения и бизнес-использование.</span><span class="sxs-lookup"><span data-stu-id="da64f-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="da64f-175">Кроме того, скопируйте ИД приложения и секрет приложения в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="da64f-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Добавление URL-адреса конфиденциальности, значка приложения и бизнес-использования](../media/FBCimage35.png)

12. <span data-ttu-id="da64f-177">Сделайте приложение общедоступным.</span><span class="sxs-lookup"><span data-stu-id="da64f-177">Make the app public.</span></span>

    ![Сделать приложение общедоступным](../media/FBCimage36.png)

13. <span data-ttu-id="da64f-179">Добавление пользователя в роль администратора или тестера.</span><span class="sxs-lookup"><span data-stu-id="da64f-179">Add user to the admin or tester role.</span></span>

    ![Добавление пользователя в роль администратора или тестера](../media/FBCimage37.png)

14. <span data-ttu-id="da64f-181">Добавьте разрешение **на доступ к общедоступным содержимым** страницы.</span><span class="sxs-lookup"><span data-stu-id="da64f-181">Add the **Page Public Content Access** permission.</span></span>

    ![dd the Page Public Content Access permission](../media/FBCimage38.png)

15. <span data-ttu-id="da64f-183">Добавление разрешения на управление страницами.</span><span class="sxs-lookup"><span data-stu-id="da64f-183">Add Manage Pages permission.</span></span>

    ![Добавление разрешения на управление страницами](../media/FBCimage39.png)

16. <span data-ttu-id="da64f-185">Просмотр приложения в Facebook.</span><span class="sxs-lookup"><span data-stu-id="da64f-185">Get the application reviewed by Facebook.</span></span>

    ![Просмотр приложения в Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="da64f-187">Шаг 4. Настройка веб-приложения соединители</span><span class="sxs-lookup"><span data-stu-id="da64f-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="da64f-188">Перейдите `https://<AzureAppResourceName>.azurewebsites.net` к этому ресурсу (где AzureAppResourceName — это имя ресурса приложения Azure, имя которого было названо в шаге 4).</span><span class="sxs-lookup"><span data-stu-id="da64f-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="da64f-189">Например, если имя **fbconnector,** перейдите к `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="da64f-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="da64f-190">Домашняя страница приложения будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="da64f-190">The home page of the app will look like the following screenshot:</span></span>

   ![Go to you connector web app](../media/FBCimage41.png)

2. <span data-ttu-id="da64f-192">Нажмите **кнопку** "Настроить", чтобы отобразить страницу для входов.</span><span class="sxs-lookup"><span data-stu-id="da64f-192">Click **Configure** to display a sign in page.</span></span>

   ![Click Configure to display a sign in page](../media/FBCimage42.png)

3. <span data-ttu-id="da64f-194">В поле "ИД клиента" введите или введите свой ИД клиента (полученный на шаге 2).</span><span class="sxs-lookup"><span data-stu-id="da64f-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="da64f-195">В поле пароля введите или введите APISecretKey (полученный на шаге 2), а затем нажмите кнопку **"Установить** параметры конфигурации", чтобы отобразить страницу сведений о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="da64f-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Войдите, используя свой ИД клиента и пароль, и перейдите на страницу сведений о конфигурации](../media/FBCimage43.png)

4. <span data-ttu-id="da64f-197">Введите следующие параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="da64f-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="da64f-198">**ИД приложения Facebook:** ИД приложения Facebook, полученного на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="da64f-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="da64f-199">**Секрет приложения Facebook:** Секрет приложения Facebook, полученный на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="da64f-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="da64f-200">**Веб-hooks Facebook проверяют маркер:** Маркер проверки, созданный на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="da64f-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="da64f-201">**ИД приложения AAD:** ИД приложения Azure Active Directory, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="da64f-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="da64f-202">**Секрет приложения AAD:** Значение секрета APISecretKey, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="da64f-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="da64f-203">Нажмите **кнопку** "Сохранить", чтобы сохранить параметры соединители.</span><span class="sxs-lookup"><span data-stu-id="da64f-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="da64f-204">Шаг 5. Настройка соединители Facebook в Центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da64f-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="da64f-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click Data **connectors** in the left nav.</span><span class="sxs-lookup"><span data-stu-id="da64f-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="da64f-206">On the **Data connectors** page under **Facebook Business pages,** click **View**.</span><span class="sxs-lookup"><span data-stu-id="da64f-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="da64f-207">На странице **"Бизнес-страницы Facebook"** нажмите кнопку **"Добавить соединителю".**</span><span class="sxs-lookup"><span data-stu-id="da64f-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="da64f-208">На странице **"Условия обслуживания" нажмите** кнопку **"Принять".**</span><span class="sxs-lookup"><span data-stu-id="da64f-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="da64f-209">На странице **"Добавление учетных** данных для приложения соединителю" введите следующие сведения и нажмите кнопку **"Проверить подключение".**</span><span class="sxs-lookup"><span data-stu-id="da64f-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Ввод учетных данных приложения соединитела](../media/TCimage38.png)

   - <span data-ttu-id="da64f-211">В поле **"Имя"** введите имя соединитела, например страницу новостей **Facebook.**</span><span class="sxs-lookup"><span data-stu-id="da64f-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="da64f-212">В поле **"URL-адрес** подключения" введите или введите URL-адрес службы приложений Azure; например. `https://fbconnector.azurewebsites.net`</span><span class="sxs-lookup"><span data-stu-id="da64f-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="da64f-213">В поле **"Пароль"** введите или введите значение APISecretKey, добавленное на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="da64f-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="da64f-214">В поле **"ИД** приложения Azure" введите или введите или введите значение ИД приложения (клиента), также называемого ИД приложения AAD, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="da64f-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="da64f-215">После успешной проверки подключения нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="da64f-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="da64f-216">На странице **авторизации Microsoft 365** для импорта данных введите или введите или введите APISecretKey еще раз, а затем щелкните веб-приложение для **входа.**</span><span class="sxs-lookup"><span data-stu-id="da64f-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="da64f-217">На странице "Настройка соединители **Facebook"** нажмите кнопку "Войти в **Facebook"** и войдите в систему, используя учетные данные учетной записи для страниц вашей организации в Facebook для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="da64f-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="da64f-218">Убедитесь, что учетной записи Facebook, в которую вы вошли, назначена роль администратора для страниц Вашей организации в Facebook для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="da64f-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Войдите в Систему с помощью Facebook](../media/FBCimage50.png)

9. <span data-ttu-id="da64f-220">Отображается список бизнес-страниц, управляемых учетной записью Facebook, в которую вы вошли.</span><span class="sxs-lookup"><span data-stu-id="da64f-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="da64f-221">Выберите страницу для архива и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="da64f-221">Select the page to archive and then click **Next**.</span></span>

   ![Выберите бизнес-страницу организации, которую нужно заархивировать](../media/FBCimage52.png)

10. <span data-ttu-id="da64f-223">Нажмите **кнопку** "Продолжить", чтобы выйти из программы установки приложения-службы соединители.</span><span class="sxs-lookup"><span data-stu-id="da64f-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="da64f-224">На странице **"Настройка фильтров"** можно применить фильтр для первоначального импорта элементов определенного возраста.</span><span class="sxs-lookup"><span data-stu-id="da64f-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="da64f-225">Выберите возраст и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="da64f-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="da64f-226">На странице **"Выбор места** хранения" введите адрес электронной почты почтового ящика Microsoft 365, в который будут импортироваться элементы Facebook, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="da64f-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="da64f-227">Нажмите **кнопку** "Далее", чтобы просмотреть параметры соединители, а затем нажмите кнопку **"Готово",** чтобы завершить настройку соединители.</span><span class="sxs-lookup"><span data-stu-id="da64f-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="da64f-228">В Центре соответствия требованиям перейдите на страницу **"Соединители** данных" и перейдите на вкладку **"Соединители",** чтобы увидеть ход процесса импорта.</span><span class="sxs-lookup"><span data-stu-id="da64f-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
