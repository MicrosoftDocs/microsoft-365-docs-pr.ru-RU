---
title: Развертывание соединителя для архивации данных Twitter
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
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Администраторы могут настроить собственный соединитель для импорта и архивации данных Twitter в Microsoft 365. После импорта этих данных в Microsoft 365 вы можете использовать такие функции обеспечения соответствия, как судебное хранение, поиск контента и политики хранения, для управления управлением данными Twitter Организации.
ms.openlocfilehash: 9951040335a2dcacc90ac4dc7a6f3e5079bf5692
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595284"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="f94cd-104">Развертывание соединителя для архивации данных Twitter</span><span class="sxs-lookup"><span data-stu-id="f94cd-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="f94cd-105">В этой статье представлено пошаговое руководство по развертыванию соединителя, использующего службу импорта Office 365 для импорта данных из учетной записи Twitter вашей организации в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f94cd-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="f94cd-106">Общий обзор этого процесса и список необходимых компонентов, необходимых для развертывания соединителя Twitter, приведены в разделе [Настройка соединителя для архивации данных Twitter ](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="f94cd-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="f94cd-107">Шаг 1: создание приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f94cd-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="f94cd-108">Перейдите на <https://portal.azure.com> страницу и войдите, используя учетные данные глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="f94cd-108">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![Вход в Azure](media/TCimage01.png)

2. <span data-ttu-id="f94cd-110">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Перейдите в Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="f94cd-112">В левой области навигации щелкните **Регистрация приложений (Предварительная версия)** , а затем нажмите кнопку **создать регистрацию**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Создание регистрации нового приложения](media/TCimage03.png)

4. <span data-ttu-id="f94cd-114">Зарегистрируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="f94cd-114">Register the application.</span></span> <span data-ttu-id="f94cd-115">В разделе **URI перенаправления (необязательно)** в раскрывающемся списке Тип приложения выберите пункт **веб-сайт** , а затем введите `https://portal.azure.com` в поле для URI.</span><span class="sxs-lookup"><span data-stu-id="f94cd-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="f94cd-116">Тип https://portal.azure.com для URI перенаправления</span><span class="sxs-lookup"><span data-stu-id="f94cd-116">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="f94cd-117">Скопируйте идентификатор **приложения (идентификатор клиента)** и **идентификатор каталога (клиента)** и сохраните их в текстовый файл или другое надежное расположение.</span><span class="sxs-lookup"><span data-stu-id="f94cd-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="f94cd-118">Эти идентификаторы используются на последующих этапах.</span><span class="sxs-lookup"><span data-stu-id="f94cd-118">You use these IDs in later steps.</span></span>

    ![Копирование и сохранение идентификатора приложения и идентификатора каталога](media/TCimage05.png)

6. <span data-ttu-id="f94cd-120">Перейдите к разделу **сертификаты & секреты для нового приложения** и в разделе **секреты клиента** нажмите **новый секрет клиента**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Создание нового секрета клиента](media/TCimage06.png)

7. <span data-ttu-id="f94cd-122">Создайте новый секрет.</span><span class="sxs-lookup"><span data-stu-id="f94cd-122">Create a new secret.</span></span> <span data-ttu-id="f94cd-123">В поле Описание введите секрет, а затем выберите срок действия.</span><span class="sxs-lookup"><span data-stu-id="f94cd-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Введите секрет и выберите срок действия](media/TCimage08.png)

8. <span data-ttu-id="f94cd-125">Скопируйте значение секрета и сохраните его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="f94cd-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="f94cd-126">Это секрет приложения AAD, который вы используете в дальнейших действиях.</span><span class="sxs-lookup"><span data-stu-id="f94cd-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Копирование и сохранение секрета](media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="f94cd-128">Шаг 2: разверните веб-службу соединителя из GitHub в учетную запись Azure.</span><span class="sxs-lookup"><span data-stu-id="f94cd-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="f94cd-129">Перейдите на [этот сайт GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) и нажмите кнопку **развернуть в Azure**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Переход на домашнюю страницу Azure](media/FBCimage11.png)

2. <span data-ttu-id="f94cd-131">После нажатия кнопки **развернуть в Azure**вы будете перенаправлены на портал Azure с настраиваемой страницей шаблона.</span><span class="sxs-lookup"><span data-stu-id="f94cd-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="f94cd-132">Заполните сведения о **основных** **параметрах и параметрах** , а затем щелкните **купить**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Нажмите кнопку Создать ресурс и введите учетную запись хранения.](media/FBCimage12.png)

    - <span data-ttu-id="f94cd-134">**Подписка:** Выберите свою подписку на Azure, в которую вы хотите развернуть веб-службу соединителя Twitter.</span><span class="sxs-lookup"><span data-stu-id="f94cd-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="f94cd-135">**Группа ресурсов:** Выберите или создайте новую группу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f94cd-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="f94cd-136">Группа ресурсов — это контейнер, в котором хранятся связанные ресурсы для решения Azure.</span><span class="sxs-lookup"><span data-stu-id="f94cd-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="f94cd-137">**Расположение:** Выберите расположение.</span><span class="sxs-lookup"><span data-stu-id="f94cd-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="f94cd-138">**Имя веб-приложения:** Укажите уникальное имя для веб-приложения соединителя.</span><span class="sxs-lookup"><span data-stu-id="f94cd-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="f94cd-139">Длина имени должна составлять от 3 до 18 символов.</span><span class="sxs-lookup"><span data-stu-id="f94cd-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="f94cd-140">Это имя используется для создания URL-адреса службы приложений Azure; Например, если указать имя веб-приложения **твиттерконнектор** , URL-адрес службы приложений Azure будет **twitterconnector.azurewebsites.NET**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="f94cd-141">**tenantId:** Идентификатор клиента вашей организации Microsoft 365, который вы скопировали после создания приложения соединителя Facebook в Azure Active Directory на этапе 1.</span><span class="sxs-lookup"><span data-stu-id="f94cd-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="f94cd-142">**Аписекреткэй:** В качестве секрета можно ввести любое значение.</span><span class="sxs-lookup"><span data-stu-id="f94cd-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="f94cd-143">Он используется для доступа к веб-приложению Connector в действии 5.</span><span class="sxs-lookup"><span data-stu-id="f94cd-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="f94cd-144">После успешного развертывания страница будет выглядеть примерно так, как показано на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="f94cd-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Щелкните хранилище, а затем выберите Учетная запись хранилища.](media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="f94cd-146">Шаг 3: создание приложения Twitter</span><span class="sxs-lookup"><span data-stu-id="f94cd-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="f94cd-147">Перейдите к https://developer.twitter.com, войдите в систему, используя учетные данные для учетной записи разработчика для вашей организации, а затем щелкните элемент **приложения**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Перейдите к https://developer.twitter.com разделу и войдите в него.](media/TCimage25-5.png)
2. <span data-ttu-id="f94cd-149">Нажмите кнопку **создать приложение**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-149">Click **Create an app**.</span></span>
   
   ![Переход на страницу "приложения" для создания приложения](media/TCimage26.png)

3. <span data-ttu-id="f94cd-151">В разделе **сведения**о приложении добавьте сведения о приложении.</span><span class="sxs-lookup"><span data-stu-id="f94cd-151">Under **App details**, add information about the application.</span></span>

   ![Введите сведения о приложении](media/TCimage27.png)

4. <span data-ttu-id="f94cd-153">На панели мониторинга разработчика Twitter выберите приложение, которое вы только что создали и скопируйте отображаемый Идентификатор приложения, и сохраните его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="f94cd-153">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="f94cd-154">Затем нажмите кнопку **сведения**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-154">Then click **Details**.</span></span>
   
   ![Копирование и сохранение идентификатора приложения](media/TCimage28.png)

5. <span data-ttu-id="f94cd-156">На вкладке **ключи и маркеры** в разделе **ключи API потребителей** СКОПИРУЙТЕ секретный ключ API и сохраните его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="f94cd-156">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="f94cd-157">Затем нажмите кнопку **создать** , чтобы создать маркер доступа и секрет маркера доступа, а затем скопируйте его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="f94cd-157">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![Секретный ключ для копирования и сохранения в API](media/TCimage29.png)

   <span data-ttu-id="f94cd-159">Затем нажмите кнопку **создать** , чтобы создать маркер доступа и секрет маркера доступа, а затем скопируйте его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="f94cd-159">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="f94cd-160">Перейдите на вкладку **разрешения** и настройте разрешения, как показано на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="f94cd-160">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Настройка разрешений](media/TCimage30.png)

7. <span data-ttu-id="f94cd-162">После сохранения параметров разрешений перейдите на вкладку **сведения о приложении** и нажмите кнопку **изменить > изменить сведения**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-162">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Изменение сведений о приложении](media/TCimage31.png)

8. <span data-ttu-id="f94cd-164">Выполните следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f94cd-164">Do the following tasks:</span></span>

   - <span data-ttu-id="f94cd-165">Установите флажок, чтобы разрешить приложению Connector вход в Twitter.</span><span class="sxs-lookup"><span data-stu-id="f94cd-165">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="f94cd-166">Добавьте URI перенаправления OAuth, используя следующий формат: \*\* \<коннекторсервицеури>/виевс/твиттероаус\*\*, где значением *коннекторсервицеури* является URL-адрес службы приложений Azure для вашей организации; Пример: https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span><span class="sxs-lookup"><span data-stu-id="f94cd-166">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Разрешить приложению Connector вход в Twitter и добавить URI перенаправления OAuth](media/TCimage32.png)

<span data-ttu-id="f94cd-168">Теперь приложение для разработчиков Twitter готово к использованию.</span><span class="sxs-lookup"><span data-stu-id="f94cd-168">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="f94cd-169">Шаг 4: Настройка веб-приложения соединителя</span><span class="sxs-lookup"><span data-stu-id="f94cd-169">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="f94cd-170">Перейдите в раздел\<https://азуреаппресаурценаме>. azurewebsites.NET (где **азуреаппресаурценаме** — это имя ресурса приложения Azure, имя которого указано в шаге 4).</span><span class="sxs-lookup"><span data-stu-id="f94cd-170">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="f94cd-171">Например, если имя — **твиттерконнектор**, перейдите на https://twitterconnector.azurewebsites.netстраницу.</span><span class="sxs-lookup"><span data-stu-id="f94cd-171">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="f94cd-172">Домашняя страница приложения выглядит как на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="f94cd-172">The home page of the app looks like the following screenshot:</span></span>

   ![Перейдите на страницу ресурсов приложения Azure](media/FBCimage41.png)

2. <span data-ttu-id="f94cd-174">Нажмите кнопку **настроить** , чтобы отобразить страницу входа.</span><span class="sxs-lookup"><span data-stu-id="f94cd-174">Click **Configure** to display a sign in page.</span></span>

   ![Нажмите кнопку настроить для отображения страницы входа](media/FBCimage42.png)

3. <span data-ttu-id="f94cd-176">В поле Идентификатор клиента введите или вставьте идентификатор клиента (полученный на шаге 2).</span><span class="sxs-lookup"><span data-stu-id="f94cd-176">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="f94cd-177">В поле Пароль введите или вставьте Аписекреткэй (полученное в действии 2), а затем нажмите кнопку **Настройка параметров конфигурации** , чтобы отобразить страницу сведений о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f94cd-177">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Вход с использованием идентификатора клиента и секретного ключа API](media/TCimage35.png)

4. <span data-ttu-id="f94cd-179">Введите следующие параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="f94cd-179">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="f94cd-180">**Ключ API Twitter:** Идентификатор приложения для приложения Twitter, созданного на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="f94cd-180">**Twitter Api Key:** The app ID for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="f94cd-181">**Секретный ключ API Twitter:** Секретный ключ API для приложения Twitter, созданного на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="f94cd-181">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="f94cd-182">**Маркер доступа Twitter:** Маркер доступа, созданный на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="f94cd-182">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="f94cd-183">**Секрет маркера доступа Twitter:** Секрет маркера доступа, созданный на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="f94cd-183">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="f94cd-184">**Идентификатор приложения AAD:** Идентификатор приложения для приложения Azure Active Directory, созданного в действии 1.</span><span class="sxs-lookup"><span data-stu-id="f94cd-184">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="f94cd-185">**Секрет приложения AAD:** Значение секрета Аписекреткэй, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="f94cd-185">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="f94cd-186">Нажмите кнопку **сохранить** , чтобы сохранить параметры соединителя.</span><span class="sxs-lookup"><span data-stu-id="f94cd-186">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="f94cd-187">Шаг 5: Настройка соединителя Twitter в центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f94cd-187">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="f94cd-188">В левой [https://compliance.microsoft.com](https://compliance.microsoft.com) панели навигации выберите элемент **соединители данных и нажмите кнопку соединители данных** .</span><span class="sxs-lookup"><span data-stu-id="f94cd-188">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="f94cd-189">На странице " **соединители данных (Предварительная версия)** " в разделе **Twitter**нажмите кнопку **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-189">On the **Data connectors (preview)** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="f94cd-190">На странице **Twitter** нажмите **Добавить соединитель**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-190">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="f94cd-191">На странице **условия обслуживания** нажмите кнопку **принять**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-191">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="f94cd-192">На странице " **Добавление учетных данных для приложения соединителя** " введите следующие сведения и нажмите кнопку **проверить подключение**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-192">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Введите учетные данные приложения соединителя](media/TCimage38.png)

    - <span data-ttu-id="f94cd-194">В поле **имя** введите имя соединителя, например, " **Справка по Twitter**".</span><span class="sxs-lookup"><span data-stu-id="f94cd-194">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="f94cd-195">В поле **URL-адрес соединителя** введите или вставьте URL-адрес службы приложений Azure; например `https://twitterconnector.azurewebsites.net`:.</span><span class="sxs-lookup"><span data-stu-id="f94cd-195">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="f94cd-196">В поле **пароль** введите или вставьте значение аписекреткэй, созданное в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="f94cd-196">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="f94cd-197">В поле **идентификатор приложения Azure** введите или вставьте значение идентификатора приложения Azure App ID (также НАЗЫВАЕМое *идентификатором клиента*), полученное на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="f94cd-197">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="f94cd-198">После успешной проверки подключения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-198">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="f94cd-199">На странице **авторизовать Microsoft 365 to Import Data (разрешить Microsoft** ) введите или вставьте аписекреткэй еще раз, а затем нажмите кнопку **Login Web App**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-199">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="f94cd-200">Щелкните **имя входа с помощью Twitter**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-200">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="f94cd-201">На странице входа в Twitter Войдите в систему, используя учетные данные для учетной записи Twitter вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f94cd-201">On the Twitter sign in page, sign in using the credentials for your organization’s Twitter account.</span></span>

   ![Вход в учетную запись Twitter](media/TCimage42.png)

   <span data-ttu-id="f94cd-203">После входа на странице Twitter отобразится следующее сообщение: "Задание соединителя Twitter успешно настроено".</span><span class="sxs-lookup"><span data-stu-id="f94cd-203">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="f94cd-204">Нажмите кнопку **продолжить** , чтобы завершить настройку соединителя Twitter.</span><span class="sxs-lookup"><span data-stu-id="f94cd-204">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="f94cd-205">На странице " **Настройка фильтров** " можно применить фильтр для начального импорта элементов с определенным сроком хранения.</span><span class="sxs-lookup"><span data-stu-id="f94cd-205">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="f94cd-206">Выберите возраст, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-206">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="f94cd-207">На странице **Выбор места хранения** введите адрес электронной почты почтового ящика Microsoft 365, в который будут импортированы элементы Twitter, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f94cd-207">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="f94cd-208">На странице **предоставление разрешений администратора**щелкните **предоставить согласие** и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="f94cd-208">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="f94cd-209">Вы должны быть глобальным администратором, чтобы предоставить разрешение службе импорта Office 365 для доступа к данным в Организации.</span><span class="sxs-lookup"><span data-stu-id="f94cd-209">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="f94cd-210">Нажмите кнопку **Далее** , чтобы проверить параметры соединителя, а затем нажмите кнопку **Готово** , чтобы завершить настройку соединителя.</span><span class="sxs-lookup"><span data-stu-id="f94cd-210">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="f94cd-211">В центре соответствия требованиям откройте страницу " **соединители данных** " и перейдите на вкладку **соединители** , чтобы просмотреть ход процесса импорта.</span><span class="sxs-lookup"><span data-stu-id="f94cd-211">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
