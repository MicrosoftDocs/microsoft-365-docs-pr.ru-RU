---
title: Развертывание соединитетеля для архива данных Twitter
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
description: Администраторы могут настроить родной соединитель для импорта и архива данных Twitter для Microsoft 365. После импорта этих данных в Microsoft 365 можно использовать такие функции соответствия требованиям, как юридические удержания, поиск контента и политики хранения для управления данными Twitter организации.
ms.openlocfilehash: 0dd996802964b2a2fc58d26e23af57193c89ee8c
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619915"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="4baf3-104">Развертывание соединитетеля для архива данных Twitter</span><span class="sxs-lookup"><span data-stu-id="4baf3-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="4baf3-105">В этой статье пошаговая процедура развертывания соединитетеля, использующего службу импорта Office 365 для импорта данных из учетной записи Twitter организации в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4baf3-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="4baf3-106">Обзор этого процесса на высоком уровне и список необходимых условий для развертывания соединитетеля Twitter см. в странице Настройка соединитетеля для архивации [данных Twitter. ](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="4baf3-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="4baf3-107">Шаг 1. Создание приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4baf3-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="4baf3-108">Перейдите к учетным данным глобальной учетной записи администратора и войдите в <https://portal.azure.com> нее.</span><span class="sxs-lookup"><span data-stu-id="4baf3-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Вход в Azure](../media/TCimage01.png)

2. <span data-ttu-id="4baf3-110">В области навигации слева щелкните **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Перейдите в Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="4baf3-112">В левой области навигации нажмите **кнопку Регистрация приложения (Предварительная версия)** и нажмите **кнопку Новая регистрация**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Создание новой регистрации приложения](../media/TCimage03.png)

4. <span data-ttu-id="4baf3-114">Регистрация приложения.</span><span class="sxs-lookup"><span data-stu-id="4baf3-114">Register the application.</span></span> <span data-ttu-id="4baf3-115">В **статье Перенаправление URI (необязательный)** выберите **Веб** в списке выпаданий типа приложения и введите в поле `https://portal.azure.com` для URI.</span><span class="sxs-lookup"><span data-stu-id="4baf3-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="4baf3-116">Введите https://portal.azure.com для URI перенаправления</span><span class="sxs-lookup"><span data-stu-id="4baf3-116">Type https://portal.azure.com for the redirect URI</span></span> ](../media/TCimage04.png)

5. <span data-ttu-id="4baf3-117">**Скопируйте ID приложения (клиента)** и **ID каталога (клиента)** и сохраните их в текстовом файле или другом безопасном расположении.</span><span class="sxs-lookup"><span data-stu-id="4baf3-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="4baf3-118">Эти ID используются в последующих действиях.</span><span class="sxs-lookup"><span data-stu-id="4baf3-118">You use these IDs in later steps.</span></span>

    ![Копирование и сохранение ID приложения и каталога](../media/TCimage05.png)

6. <span data-ttu-id="4baf3-120">Перейдите **к сертификатам & для** нового приложения и в статье Секреты **клиента** нажмите **кнопку Новый секрет клиента**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Создание нового секрета клиента](../media/TCimage06.png)

7. <span data-ttu-id="4baf3-122">Создайте новый секрет.</span><span class="sxs-lookup"><span data-stu-id="4baf3-122">Create a new secret.</span></span> <span data-ttu-id="4baf3-123">В поле описания введите секрет и выберите срок действия.</span><span class="sxs-lookup"><span data-stu-id="4baf3-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Введите секрет и выберите срок действия](../media/TCimage08.png)

8. <span data-ttu-id="4baf3-125">Скопируйте значение секрета и сохраните его в текстовом файле или другом расположении хранилища.</span><span class="sxs-lookup"><span data-stu-id="4baf3-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="4baf3-126">Это секрет приложения AAD, который используется в последующих действиях.</span><span class="sxs-lookup"><span data-stu-id="4baf3-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Копирование и сохранение секрета](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="4baf3-128">Шаг 2. Развертывание веб-службы соединиттеля GitHub учетной записи Azure</span><span class="sxs-lookup"><span data-stu-id="4baf3-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="4baf3-129">Перейдите [на этот GitHub и](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) нажмите **кнопку Развертывание в Azure.**</span><span class="sxs-lookup"><span data-stu-id="4baf3-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Перейдите на домашную страницу Azure](../media/FBCimage11.png)

2. <span data-ttu-id="4baf3-131">После нажатия **кнопки Развертывание в Azure** вы будете перенаправлены на портал Azure с настраиваемой страницей шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4baf3-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="4baf3-132">Заполните **основные** и **Параметры,** а затем нажмите кнопку **Покупка**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Нажмите кнопку Создание учетной записи хранилища ресурсов и типа](../media/FBCimage12.png)

    - <span data-ttu-id="4baf3-134">**Подписка:** Выберите подписку Azure, в которую необходимо развернуть веб-службу соединители Twitter.</span><span class="sxs-lookup"><span data-stu-id="4baf3-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="4baf3-135">**Группа ресурсов:** Выберите или создайте новую группу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4baf3-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="4baf3-136">Группа ресурсов — это контейнер, который содержит соответствующие ресурсы для решения Azure.</span><span class="sxs-lookup"><span data-stu-id="4baf3-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="4baf3-137">**Расположение:** Выберите расположение.</span><span class="sxs-lookup"><span data-stu-id="4baf3-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="4baf3-138">**Имя веб-приложения:** Укажет уникальное имя для веб-приложения соединители.</span><span class="sxs-lookup"><span data-stu-id="4baf3-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="4baf3-139">Имя должно быть от 3 до 18 символов в длину.</span><span class="sxs-lookup"><span data-stu-id="4baf3-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="4baf3-140">Это имя используется для создания URL-адреса службы приложений Azure; например, если вы предоставите имя **twitterconnector** **веб-приложения, URL-адрес** службы приложений Azure будет twitterconnector.azurewebsites.net .</span><span class="sxs-lookup"><span data-stu-id="4baf3-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="4baf3-141">**tenantId:** ID клиента вашей Microsoft 365, который вы скопировали после создания приложения-соединиттеля Facebook в Azure Active Directory на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="4baf3-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="4baf3-142">**APISecretKey:** Вы можете ввести любое значение как секрет.</span><span class="sxs-lookup"><span data-stu-id="4baf3-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="4baf3-143">Это используется для доступа к веб-приложению соединители в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="4baf3-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="4baf3-144">После успешного развертывания страница будет выглядеть аналогично следующему скриншоту:</span><span class="sxs-lookup"><span data-stu-id="4baf3-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Щелкните служба хранилища и нажмите служба хранилища учетную запись](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="4baf3-146">Шаг 3. Создание приложения Twitter</span><span class="sxs-lookup"><span data-stu-id="4baf3-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="4baf3-147">Перейдите в систему, войдите в систему с помощью учетных данных учетной записи разработчика для организации, а затем https://developer.twitter.com нажмите **кнопку Apps**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Перейдите https://developer.twitter.com в систему и войдите в систему](../media/TCimage25-5.png)
2. <span data-ttu-id="4baf3-149">Нажмите **кнопку Создать приложение**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-149">Click **Create an app**.</span></span>
   
   ![Перейдите на страницу Приложения для создания приложения](../media/TCimage26.png)

3. <span data-ttu-id="4baf3-151">В **статье Сведения о приложении** добавьте сведения о приложении.</span><span class="sxs-lookup"><span data-stu-id="4baf3-151">Under **App details**, add information about the application.</span></span>

   ![Ввод информации о приложении](../media/TCimage27.png)

4. <span data-ttu-id="4baf3-153">На панели мониторинга разработчиков Twitter выберите только что созданное приложение и нажмите кнопку **Подробные сведения**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>
   
   ![Копирование и сохранение ID приложения](../media/TCimage28.png)

5. <span data-ttu-id="4baf3-155">На **вкладке Ключи** и маркеры в ключах **API** для потребителей скопируйте ключ API и секретный ключ API и сохраните их в текстовом файле или другом расположении хранилища.</span><span class="sxs-lookup"><span data-stu-id="4baf3-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="4baf3-156">Затем нажмите **кнопку Создать** для создания маркера доступа и секрета маркера доступа и скопировать их в текстовый файл или другое расположение хранилища.</span><span class="sxs-lookup"><span data-stu-id="4baf3-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>
   
   ![Копирование и сохранение секретного ключа API](../media/TCimage29.png)

   <span data-ttu-id="4baf3-158">Затем нажмите **кнопку Создать,** чтобы создать маркер доступа и секрет маркера доступа, и скопируйте их в текстовый файл или другое расположение хранилища.</span><span class="sxs-lookup"><span data-stu-id="4baf3-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="4baf3-159">Щелкните **вкладку Permissions** и настройте разрешения, как показано на следующем скриншоте:</span><span class="sxs-lookup"><span data-stu-id="4baf3-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Настройка разрешений](../media/TCimage30.png)

7. <span data-ttu-id="4baf3-161">После сохранения параметров разрешений щелкните вкладку **Сведения о приложении,** а затем нажмите **кнопку Изменить > изменить сведения**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Изменение сведений о приложении](../media/TCimage31.png)

8. <span data-ttu-id="4baf3-163">Выполнение следующих задач:</span><span class="sxs-lookup"><span data-stu-id="4baf3-163">Do the following tasks:</span></span>

   - <span data-ttu-id="4baf3-164">Выберите почтовый ящик, чтобы разрешить приложению соединители войти в Twitter.</span><span class="sxs-lookup"><span data-stu-id="4baf3-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="4baf3-165">Добавьте Uri перенаправления OAuth с помощью следующего формата: **\<connectorserviceuri> /Views/TwitterOAuth**, где значение *connectorserviceuri* — URL-адрес службы приложений Azure для вашей организации; https://twitterconnector.azurewebsites.net/Views/TwitterOAuth например, .</span><span class="sxs-lookup"><span data-stu-id="4baf3-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Разрешить приложению соединителю войти в Twitter и добавить Uri перенаправления OAuth](../media/TCimage32.png)

<span data-ttu-id="4baf3-167">Приложение разработчика Twitter теперь готово к использованию.</span><span class="sxs-lookup"><span data-stu-id="4baf3-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="4baf3-168">Шаг 4. Настройка веб-приложения соединители</span><span class="sxs-lookup"><span data-stu-id="4baf3-168">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="4baf3-169">Перейдите https:// \<AzureAppResourceName> .azurewebsites.net (где **AzureAppResourceName** — это имя ресурса приложения Azure, который вы назвали в шаге 4).</span><span class="sxs-lookup"><span data-stu-id="4baf3-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="4baf3-170">Например, если имя **twitterconnector,** перейдите к https://twitterconnector.azurewebsites.net .</span><span class="sxs-lookup"><span data-stu-id="4baf3-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="4baf3-171">Главная страница приложения выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4baf3-171">The home page of the app looks like the following screenshot:</span></span>

   ![Перейдите на страницу ресурсов приложения Azure](../media/FBCimage41.png)

2. <span data-ttu-id="4baf3-173">Щелкните **Настройка** для отображения знака на странице.</span><span class="sxs-lookup"><span data-stu-id="4baf3-173">Click **Configure** to display a sign in page.</span></span>

   ![Щелкните Настройка для отображения знака на странице](../media/FBCimage42.png)

3. <span data-ttu-id="4baf3-175">В поле "Id tenant" введите или введите свой id клиента (полученный в шаге 2).</span><span class="sxs-lookup"><span data-stu-id="4baf3-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="4baf3-176">В поле пароль введите или введите APISecretKey (полученный в шаге 2), а затем нажмите кнопку **Set Configuration Параметры,** чтобы отобразить страницу сведений о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4baf3-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Вход с помощью секретного ключа клиента и API](../media/TCimage35.png)

4. <span data-ttu-id="4baf3-178">Введите следующие параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="4baf3-178">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="4baf3-179">**Ключ API Twitter:** Ключ API для приложения Twitter, созданного в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="4baf3-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="4baf3-180">**Секретный ключ Api Twitter:** Секретный ключ API для приложения Twitter, созданного в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="4baf3-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="4baf3-181">**Маркер доступа к Twitter:** Маркер доступа, созданный в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="4baf3-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="4baf3-182">**Секрет маркера доступа к Twitter:** Секрет маркера доступа, созданный в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="4baf3-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="4baf3-183">**AAD Application ID:** ID приложения для Azure Active Directory, созданного в шаге 1</span><span class="sxs-lookup"><span data-stu-id="4baf3-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="4baf3-184">**Секрет приложения AAD:** Значение секрета APISecretKey, созданного в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="4baf3-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="4baf3-185">Щелкните **Сохранить,** чтобы сохранить параметры соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="4baf3-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="4baf3-186">Шаг 5. Настройка соединитетеля Twitter в центре Microsoft 365 соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="4baf3-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="4baf3-187">Перейдите [https://compliance.microsoft.com](https://compliance.microsoft.com) к и нажмите **соединители данных** в левом nav.</span><span class="sxs-lookup"><span data-stu-id="4baf3-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="4baf3-188">На странице **Соединители данных** в **Twitter** нажмите кнопку **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="4baf3-189">На странице **Twitter** нажмите **кнопку Добавить соединителю**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="4baf3-190">На странице **Условия службы нажмите** кнопку **Принять**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="4baf3-191">На странице **Добавление учетных данных для приложения соединителю** введите следующую информацию и нажмите кнопку **Проверка подключения.**</span><span class="sxs-lookup"><span data-stu-id="4baf3-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Ввод учетных данных приложения соединитела](../media/TCimage38.png)

    - <span data-ttu-id="4baf3-193">В поле **Имя** введите имя соединитетеля, например **для обработки справки Twitter.**</span><span class="sxs-lookup"><span data-stu-id="4baf3-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="4baf3-194">В поле **URL-адрес соединителя** введите или введите URL-адрес службы приложений Azure; например `https://twitterconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="4baf3-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="4baf3-195">В поле **Пароль** введите или введите значение APISecretKey, созданного в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="4baf3-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="4baf3-196">В поле **Azure App ID** введите или введите значение ID приложения Azure (также называемого ИД *клиента),* полученного в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="4baf3-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="4baf3-197">После успешной проверки подключения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="4baf3-198">На странице **Авторизации Microsoft 365** импортировать данные, введите или введите APISecretKey снова, а затем щелкните веб-приложение **Login**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="4baf3-199">Нажмите **кнопку Войти в Twitter**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="4baf3-200">Во входе в Twitter впишитесь с помощью учетных данных для учетной записи Twitter организации.</span><span class="sxs-lookup"><span data-stu-id="4baf3-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Вход в учетную запись Twitter](../media/TCimage42.png)

   <span data-ttu-id="4baf3-202">После регистрации на странице Twitter будет отображаться следующее сообщение: "Успешно настроена работа соединиттеля Twitter".</span><span class="sxs-lookup"><span data-stu-id="4baf3-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="4baf3-203">Нажмите **кнопку Продолжить,** чтобы завершить настройку соединитетеля Twitter.</span><span class="sxs-lookup"><span data-stu-id="4baf3-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="4baf3-204">На странице **Set filters** можно применить фильтр для первоначального импорта элементов определенного возраста.</span><span class="sxs-lookup"><span data-stu-id="4baf3-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="4baf3-205">Выберите возраст, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="4baf3-206">На странице **Выбор расположения** хранилища введите адрес электронной почты Microsoft 365 почтового ящика, в который будут импортироваться элементы Twitter, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="4baf3-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="4baf3-207">Нажмите **кнопку Далее,** чтобы просмотреть параметры соединитетеля, а затем нажмите **кнопку Готово,** чтобы завершить настройку соединитетеля.</span><span class="sxs-lookup"><span data-stu-id="4baf3-207">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="4baf3-208">В центре соответствия требованиям перейдите на страницу **соединители** данных и щелкните вкладку **Соединители,** чтобы увидеть ход процесса импорта.</span><span class="sxs-lookup"><span data-stu-id="4baf3-208">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
