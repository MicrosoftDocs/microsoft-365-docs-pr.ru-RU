---
title: Развертывание соединитела для архива данных Twitter
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
description: Администраторы могут настроить нативный соединитель для импорта и архива данных Twitter в Microsoft 365. После импорта этих данных в Microsoft 365 вы можете использовать такие функции соответствия требованиям, как удержание по юридическим вопросам, поиск контента и политики хранения для управления данными Twitter вашей организации.
ms.openlocfilehash: 0dd996802964b2a2fc58d26e23af57193c89ee8c
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619915"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="d23c9-104">Развертывание соединитела для архива данных Twitter</span><span class="sxs-lookup"><span data-stu-id="d23c9-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="d23c9-105">В этой статье содержится пошаговые процедуры развертывания соединители, использующие службу импорта Office 365 для импорта данных из учетной записи Twitter вашей организации в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d23c9-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="d23c9-106">Общие сведения об этом процессе и список предварительных условий, необходимых для развертывания соединители Twitter, см. в настройках соединитела для архивации [данных Twitter. ](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="d23c9-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="d23c9-107">Шаг 1. Создание приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d23c9-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="d23c9-108">Войдите в учетную запись глобального администратора и <https://portal.azure.com> войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="d23c9-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Вход в Azure](../media/TCimage01.png)

2. <span data-ttu-id="d23c9-110">В левой области навигации щелкните **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="d23c9-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Перейдите в Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="d23c9-112">В левой области навигации щелкните регистрацию приложений **(предварительная версия)** и нажмите кнопку **"Новая регистрация".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Создание регистрации приложения](../media/TCimage03.png)

4. <span data-ttu-id="d23c9-114">Зарегистрируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="d23c9-114">Register the application.</span></span> <span data-ttu-id="d23c9-115">В **поле "URI перенаправления" (необязательно)** выберите "Интернет" в списке типов приложений, а затем введите поле для  `https://portal.azure.com` URI.</span><span class="sxs-lookup"><span data-stu-id="d23c9-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="d23c9-116">Тип https://portal.azure.com URI перенаправления</span><span class="sxs-lookup"><span data-stu-id="d23c9-116">Type https://portal.azure.com for the redirect URI</span></span> ](../media/TCimage04.png)

5. <span data-ttu-id="d23c9-117">**Скопируйте ИД приложения (клиента)** и каталог **(клиент)** и сохраните их в текстовом файле или другом безопасном расположении.</span><span class="sxs-lookup"><span data-stu-id="d23c9-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="d23c9-118">Эти ИД будут применяться на последующих шагах.</span><span class="sxs-lookup"><span data-stu-id="d23c9-118">You use these IDs in later steps.</span></span>

    ![Копирование и сохранение ИД приложения и каталога](../media/TCimage05.png)

6. <span data-ttu-id="d23c9-120">Go to **Certificates & secrets for the new app** and under Client **secrets** click New **client secret**.</span><span class="sxs-lookup"><span data-stu-id="d23c9-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Создание секрета клиента](../media/TCimage06.png)

7. <span data-ttu-id="d23c9-122">Создайте новый секрет.</span><span class="sxs-lookup"><span data-stu-id="d23c9-122">Create a new secret.</span></span> <span data-ttu-id="d23c9-123">В поле описания введите секрет и выберите срок действия.</span><span class="sxs-lookup"><span data-stu-id="d23c9-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Введите секрет и выберите срок действия](../media/TCimage08.png)

8. <span data-ttu-id="d23c9-125">Скопируйте значение секрета и сохраните его в текстовом файле или другом хранилище.</span><span class="sxs-lookup"><span data-stu-id="d23c9-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="d23c9-126">Это секрет приложения AAD, который будет применяться на последующих шагах.</span><span class="sxs-lookup"><span data-stu-id="d23c9-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Копирование и сохранение секрета](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="d23c9-128">Шаг 2. Развертывание веб-службы соединителя из GitHub в учетной записи Azure</span><span class="sxs-lookup"><span data-stu-id="d23c9-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="d23c9-129">Перейдите [на этот сайт GitHub и](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) нажмите кнопку **"Развернуть в Azure".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Перейдите на домашней странице Azure](../media/FBCimage11.png)

2. <span data-ttu-id="d23c9-131">После нажатия кнопки **"Развернуть в Azure"** вы будете перенаправлены на портал Azure с настраиваемой страницей шаблона.</span><span class="sxs-lookup"><span data-stu-id="d23c9-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="d23c9-132">Заполните сведения **об основах** **и параметрах** и нажмите кнопку **"Купить".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Нажмите кнопку "Создать ресурс" и введите учетную запись хранения](../media/FBCimage12.png)

    - <span data-ttu-id="d23c9-134">**Подписка:** Выберите свою подписку Azure, в которую вы хотите развернуть веб-службу соединители Twitter.</span><span class="sxs-lookup"><span data-stu-id="d23c9-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="d23c9-135">**Группа ресурсов:** Выберите или создайте новую группу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d23c9-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="d23c9-136">Группа ресурсов — это контейнер, который содержит связанные ресурсы для решения Azure.</span><span class="sxs-lookup"><span data-stu-id="d23c9-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="d23c9-137">**Расположение:** Выберите расположение.</span><span class="sxs-lookup"><span data-stu-id="d23c9-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="d23c9-138">**Имя веб-приложения:** Укажет уникальное имя для веб-приложения соединители.</span><span class="sxs-lookup"><span data-stu-id="d23c9-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="d23c9-139">Длина имени должна быть от 3 до 18 символов.</span><span class="sxs-lookup"><span data-stu-id="d23c9-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="d23c9-140">Это имя используется для создания URL-адреса службы приложений Azure; например, если у вас есть имя веб-приложения **twitterconnector,** URL-адрес службы приложений Azure будет **twitterconnector.azurewebsites.net.**</span><span class="sxs-lookup"><span data-stu-id="d23c9-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="d23c9-141">**tenantId:** ИД клиента вашей организации Microsoft 365, который вы скопировали после создания приложения соединители Facebook в Azure Active Directory на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="d23c9-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="d23c9-142">**APISecretKey:** В качестве секрета можно ввести любое значение.</span><span class="sxs-lookup"><span data-stu-id="d23c9-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="d23c9-143">Это используется для доступа к веб-приложению соединители на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="d23c9-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="d23c9-144">После успешного развертывания страница будет выглядеть примерно так, как по снимку экрана:</span><span class="sxs-lookup"><span data-stu-id="d23c9-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Щелкните "Хранилище" и выберите "Учетная запись хранилища"](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="d23c9-146">Шаг 3. Создание приложения Twitter</span><span class="sxs-lookup"><span data-stu-id="d23c9-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="d23c9-147">Go to https://developer.twitter.com , log in using the credentials for the developer account for your organization, and then click **Apps**.</span><span class="sxs-lookup"><span data-stu-id="d23c9-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Go to https://developer.twitter.com and log in](../media/TCimage25-5.png)
2. <span data-ttu-id="d23c9-149">Нажмите **кнопку "Создать приложение"**.</span><span class="sxs-lookup"><span data-stu-id="d23c9-149">Click **Create an app**.</span></span>
   
   ![Чтобы создать приложение, перейдите на страницу "Приложения"](../media/TCimage26.png)

3. <span data-ttu-id="d23c9-151">В **области сведений о приложении** добавьте сведения о приложении.</span><span class="sxs-lookup"><span data-stu-id="d23c9-151">Under **App details**, add information about the application.</span></span>

   ![Ввод информации о приложении](../media/TCimage27.png)

4. <span data-ttu-id="d23c9-153">На информационной панели разработчика Twitter выберите только что созданное приложение и нажмите кнопку **"Сведения".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>
   
   ![Копирование и сохранение ИД приложения](../media/TCimage28.png)

5. <span data-ttu-id="d23c9-155">На **вкладке "Ключи** и маркеры" в ключах API потребителя скопируйте ключ **API** и секретный ключ API и сохраните их в текстовом файле или другом хранилище.</span><span class="sxs-lookup"><span data-stu-id="d23c9-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="d23c9-156">Затем нажмите **кнопку "Создать",** чтобы создать маркер доступа и секрет маркера доступа и скопировать их в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="d23c9-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>
   
   ![Копирование и сохранение секретного ключа API](../media/TCimage29.png)

   <span data-ttu-id="d23c9-158">Затем нажмите **кнопку "Создать",** чтобы создать маркер доступа и секрет маркера доступа, и скопируйте их в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="d23c9-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="d23c9-159">Перейдите **на вкладку "Разрешения"** и настройте разрешения, как показано на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="d23c9-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Настройка разрешений](../media/TCimage30.png)

7. <span data-ttu-id="d23c9-161">После сохранения параметров разрешений  перейдите на вкладку "Сведения о приложении" и нажмите кнопку **"Изменить > Изменить сведения".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Изменение сведений о приложении](../media/TCimage31.png)

8. <span data-ttu-id="d23c9-163">Сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="d23c9-163">Do the following tasks:</span></span>

   - <span data-ttu-id="d23c9-164">Select the checkbox to allow the connector app to sign in to Twitter.</span><span class="sxs-lookup"><span data-stu-id="d23c9-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="d23c9-165">Добавьте URI перенаправления OAuth в следующем формате: **\<connectorserviceuri> /Views/TwitterOAuth,** где *значением connectorserviceuri* является URL-адрес службы приложений Azure для вашей организации, например https://twitterconnector.azurewebsites.net/Views/TwitterOAuth .</span><span class="sxs-lookup"><span data-stu-id="d23c9-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Разрешить приложению соединителю войти в Twitter и добавить URI перенаправления OAuth](../media/TCimage32.png)

<span data-ttu-id="d23c9-167">Теперь приложение разработчика Twitter готово к использованию.</span><span class="sxs-lookup"><span data-stu-id="d23c9-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="d23c9-168">Шаг 4. Настройка веб-приложения соединители</span><span class="sxs-lookup"><span data-stu-id="d23c9-168">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="d23c9-169">Перейдите https:// \<AzureAppResourceName> .azurewebsites.net (где **AzureAppResourceName** — это имя ресурса приложения Azure, имя которого вы назначили в шаге 4).</span><span class="sxs-lookup"><span data-stu-id="d23c9-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="d23c9-170">Например, если имя **twitterconnector,** перейдите к https://twitterconnector.azurewebsites.net .</span><span class="sxs-lookup"><span data-stu-id="d23c9-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="d23c9-171">Домашняя страница приложения выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d23c9-171">The home page of the app looks like the following screenshot:</span></span>

   ![Перейти на страницу ресурсов приложения Azure](../media/FBCimage41.png)

2. <span data-ttu-id="d23c9-173">Нажмите **кнопку** "Настроить", чтобы отобразить страницу для входов.</span><span class="sxs-lookup"><span data-stu-id="d23c9-173">Click **Configure** to display a sign in page.</span></span>

   ![Click Configure to display sign in page](../media/FBCimage42.png)

3. <span data-ttu-id="d23c9-175">В поле "ИД клиента" введите или введите свой ИД клиента (полученный на шаге 2).</span><span class="sxs-lookup"><span data-stu-id="d23c9-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="d23c9-176">В поле пароля введите или введите APISecretKey (полученный на шаге 2), а затем нажмите кнопку **"Установить** параметры конфигурации", чтобы отобразить страницу сведений о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d23c9-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Вход с использованием секретного ключа ИД клиента и API](../media/TCimage35.png)

4. <span data-ttu-id="d23c9-178">Введите следующие параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="d23c9-178">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="d23c9-179">**Ключ API Twitter:** Ключ API для приложения Twitter, созданного на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="d23c9-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="d23c9-180">**Секретный ключ API Twitter:** Секретный ключ API для приложения Twitter, созданного на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="d23c9-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="d23c9-181">**Маркер доступа Twitter:** Маркер доступа, созданный на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="d23c9-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="d23c9-182">**Секрет маркера доступа Twitter:** Секрет маркера доступа, созданный на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="d23c9-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="d23c9-183">**ИД приложения AAD:** ИД приложения Azure Active Directory, созданного на шаге 1</span><span class="sxs-lookup"><span data-stu-id="d23c9-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="d23c9-184">**Секрет приложения AAD:** Значение секрета APISecretKey, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="d23c9-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="d23c9-185">Нажмите **кнопку** "Сохранить", чтобы сохранить параметры соединители.</span><span class="sxs-lookup"><span data-stu-id="d23c9-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="d23c9-186">Шаг 5. Настройка соединители Twitter в Центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d23c9-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="d23c9-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click Data **connectors** in the left nav.</span><span class="sxs-lookup"><span data-stu-id="d23c9-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d23c9-188">На странице **"Соединители данных"** в **Twitter** нажмите кнопку **"Просмотреть".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="d23c9-189">На странице **Twitter** нажмите кнопку **"Добавить соединителю".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="d23c9-190">На странице **"Условия обслуживания" нажмите** кнопку **"Принять".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="d23c9-191">На странице **"Добавление учетных** данных для приложения соединителю" введите следующие сведения и нажмите кнопку **"Проверить подключение".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Ввод учетных данных приложения соединитела](../media/TCimage38.png)

    - <span data-ttu-id="d23c9-193">В поле **"Имя"** введите имя соединитела, например, справку **Twitter.**</span><span class="sxs-lookup"><span data-stu-id="d23c9-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="d23c9-194">В поле **"URL-адрес** соединителя" введите или введите URL-адрес службы приложений Azure; например. `https://twitterconnector.azurewebsites.net`</span><span class="sxs-lookup"><span data-stu-id="d23c9-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="d23c9-195">В поле **"Пароль"** введите или введите значение APISecretKey, созданное на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="d23c9-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="d23c9-196">В поле **"ИД** приложения Azure" введите или введите или введите значение ИД приложения приложения Azure (также называемый ИД клиента), полученный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="d23c9-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="d23c9-197">После успешной проверки подключения нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="d23c9-198">На странице **авторизации Microsoft 365** для импорта данных введите или введите или введите APISecretKey еще раз, а затем щелкните веб-приложение для **входа.**</span><span class="sxs-lookup"><span data-stu-id="d23c9-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="d23c9-199">Click **Login with Twitter**.</span><span class="sxs-lookup"><span data-stu-id="d23c9-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="d23c9-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span><span class="sxs-lookup"><span data-stu-id="d23c9-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Вход в учетную запись Twitter](../media/TCimage42.png)

   <span data-ttu-id="d23c9-202">После этого на странице Twitter отобразится следующее сообщение: "Задание соединители Twitter успешно настроено".</span><span class="sxs-lookup"><span data-stu-id="d23c9-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="d23c9-203">Нажмите **кнопку** "Продолжить", чтобы завершить настройку соединители Twitter.</span><span class="sxs-lookup"><span data-stu-id="d23c9-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="d23c9-204">На странице **"Настройка фильтров"** можно применить фильтр для первоначального импорта элементов определенного возраста.</span><span class="sxs-lookup"><span data-stu-id="d23c9-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="d23c9-205">Выберите возраст и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="d23c9-206">На странице **"Выбор места** хранения" введите адрес электронной почты почтового ящика Microsoft 365, в который будут импортироваться элементы Twitter, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="d23c9-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="d23c9-207">Нажмите **кнопку** "Далее", чтобы просмотреть параметры соединители, а затем нажмите кнопку **"Готово",** чтобы завершить настройку соединители.</span><span class="sxs-lookup"><span data-stu-id="d23c9-207">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="d23c9-208">В Центре соответствия требованиям перейдите на страницу **"Соединители** данных" и перейдите на вкладку **"Соединители",** чтобы увидеть ход процесса импорта.</span><span class="sxs-lookup"><span data-stu-id="d23c9-208">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
