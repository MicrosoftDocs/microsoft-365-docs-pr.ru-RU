---
title: Развертывание соединителя для архивации данных Twitter
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
description: Администраторы могут настроить собственный соединитель для импорта и архивации данных Twitter в Office 365. После импорта этих данных в Office 365 вы можете использовать такие функции обеспечения соответствия, как судебное удержание, поиск контента и политики хранения, для управления управлением данными Twitter Организации.
ms.openlocfilehash: ee15086c6389fa2d2e7d07412ab533301cd8a842
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247472"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="8a937-104">Развертывание соединителя для архивации данных Twitter</span><span class="sxs-lookup"><span data-stu-id="8a937-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="8a937-105">В этой статье представлено пошаговое руководство по развертыванию соединителя, использующего службу импорта Office 365 для импорта данных из учетной записи Twitter вашей организации в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a937-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="8a937-106">Общий обзор этого процесса и список необходимых компонентов, необходимых для развертывания соединителя Twitter, приведены в разделе [Использование соединителя для архивации данных Twitter в Office 365 (Предварительная версия)](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8a937-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="8a937-107">Шаг 1: Загрузка пакета</span><span class="sxs-lookup"><span data-stu-id="8a937-107">Step 1: Download the package</span></span>

<span data-ttu-id="8a937-108">Скачайте готовый пакет из раздела Release репозитория GitHub по адресу [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span><span class="sxs-lookup"><span data-stu-id="8a937-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="8a937-109">В последнем выпуске Скачайте ZIP-файл с именем **самплеконнектор. zip**.</span><span class="sxs-lookup"><span data-stu-id="8a937-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="8a937-110">Вы отправляете этот ZIP-файл в Azure на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="8a937-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="8a937-111">Шаг 2: создание приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8a937-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="8a937-112">Перейдите на <https://portal.azure.com> страницу и войдите, используя учетные данные глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a937-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![Вход в Azure](media/TCimage01.png)

2. <span data-ttu-id="8a937-114">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="8a937-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Перейдите в Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="8a937-116">В левой области навигации щелкните **Регистрация приложений (Предварительная версия)** , а затем нажмите кнопку **создать регистрацию**.</span><span class="sxs-lookup"><span data-stu-id="8a937-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Создание регистрации нового приложения](media/TCimage03.png)

4. <span data-ttu-id="8a937-118">Зарегистрируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="8a937-118">Register the application.</span></span> <span data-ttu-id="8a937-119">В разделе **URI перенаправления (необязательно)** в раскрывающемся списке Тип приложения выберите пункт **веб-сайт** , а затем введите `https://portal.azure.com` в поле для URI.</span><span class="sxs-lookup"><span data-stu-id="8a937-119">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="8a937-120">Тип https://portal.azure.com для URI перенаправления</span><span class="sxs-lookup"><span data-stu-id="8a937-120">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="8a937-121">Скопируйте идентификатор **приложения (идентификатор клиента)** и **идентификатор каталога (клиента)** и сохраните их в текстовый файл или другое надежное расположение.</span><span class="sxs-lookup"><span data-stu-id="8a937-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="8a937-122">Эти идентификаторы используются на последующих этапах.</span><span class="sxs-lookup"><span data-stu-id="8a937-122">You use these IDs in later steps.</span></span>

    ![Копирование и сохранение идентификатора приложения и идентификатора каталога](media/TCimage05.png)

6. <span data-ttu-id="8a937-124">Перейдите к разделу **сертификаты & секреты для нового приложения** и в разделе **секреты клиента** нажмите **новый секрет клиента**.</span><span class="sxs-lookup"><span data-stu-id="8a937-124">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Создание нового секрета клиента](media/TCimage06.png)

7. <span data-ttu-id="8a937-126">Создайте новый секрет.</span><span class="sxs-lookup"><span data-stu-id="8a937-126">Create a new secret.</span></span> <span data-ttu-id="8a937-127">В поле Описание введите секрет, а затем выберите срок действия.</span><span class="sxs-lookup"><span data-stu-id="8a937-127">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Введите секрет и выберите срок действия](media/TCimage08.png)

8. <span data-ttu-id="8a937-129">Скопируйте значение секрета и сохраните его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8a937-129">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="8a937-130">Это секрет приложения AAD, который вы используете в дальнейших действиях.</span><span class="sxs-lookup"><span data-stu-id="8a937-130">This is the AAD application secret that you use in later steps.</span></span>

   ![Копирование и сохранение секрета](media/TCimage09.png)

9. <span data-ttu-id="8a937-132">Перейдите к **манифесту** и скопируйте с identifieruris (который также называется URI приложения AAD), выделенный на следующем снимке экрана.</span><span class="sxs-lookup"><span data-stu-id="8a937-132">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="8a937-133">Скопируйте универсальный код ресурса (URI) приложения AAD в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8a937-133">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="8a937-134">Его можно использовать на шаге 6.</span><span class="sxs-lookup"><span data-stu-id="8a937-134">You use it in Step 6.</span></span>

    ![Копирование и сохранение URI приложения AAD](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="8a937-136">Шаг 3: создание учетной записи хранения Azure</span><span class="sxs-lookup"><span data-stu-id="8a937-136">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="8a937-137">Перейдите на домашнюю страницу Azure для своей организации.</span><span class="sxs-lookup"><span data-stu-id="8a937-137">Go to the Azure home page for your organization.</span></span>

    ![С переадресом на домашнюю страницу Azure](media/TCimage11.png)

2. <span data-ttu-id="8a937-139">Выберите **создать ресурс** и введите **учетную запись хранения** в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="8a937-139">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![Создание ресурса учетной записи хранения](media/TCimage12.png)

3. <span data-ttu-id="8a937-141">Щелкните **хранилище**, а затем выберите **учетная запись хранилища**.</span><span class="sxs-lookup"><span data-stu-id="8a937-141">Click **Storage**, and then click **Storage account**.</span></span>

   ![Щелкните хранилище, а затем выберите Учетная запись хранилища.](media/TCimage13.png)

4. <span data-ttu-id="8a937-143">На странице " **Создание учетной записи хранения** " в поле подписка выберите вариант **Оплата от имени** или **бесплатной пробной версии** в зависимости от того, какой тип подписки Azure вы используете.</span><span class="sxs-lookup"><span data-stu-id="8a937-143">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![Выбор типа учетной записи хранения](media/TCimage14.png)

5. <span data-ttu-id="8a937-145">Выберите или создайте группу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8a937-145">Select or create a resource group.</span></span>

   ![Выбор или создание группы ресурсов](media/TCimage15.png)

6. <span data-ttu-id="8a937-147">Введите имя учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="8a937-147">Type a name for the storage account.</span></span>

   ![Имя учетной записи хранения](media/TCimage16.png)

7. <span data-ttu-id="8a937-149">Просмотрите, а затем нажмите кнопку **создать** , чтобы создать учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="8a937-149">Review and then click **Create** to create the storage account.</span></span>

   ![Просмотрите параметры и затем создайте учетную запись хранения.](media/TCimage17.png)

8. <span data-ttu-id="8a937-151">Через несколько секунд нажмите кнопку **Обновить** , а затем выберите **Перейти к ресурсу** , чтобы перейти к учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="8a937-151">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![Перейдите к только что созданной учетной записи хранения](media/TCimage18.png)

9. <span data-ttu-id="8a937-153">Нажмите **клавиши доступа** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="8a937-153">Click **Access keys** in the left navigation pane.</span></span>

   ![Нажмите клавиши доступа](media/TCimage19.png)

10. <span data-ttu-id="8a937-155">Скопируйте **строку подключения** и сохраните ее в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8a937-155">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="8a937-156">Это используется при создании ресурса веб-приложения на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="8a937-156">You use this when creating a web app resource in Step 4.</span></span>

    ![Копирование строки подключения](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="8a937-158">Шаг 4: создание нового ресурса веб-приложения в Azure</span><span class="sxs-lookup"><span data-stu-id="8a937-158">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="8a937-159">На **домашней** странице на портале Azure выберите **создать веб-приложение " \> все \> ресурсы**".</span><span class="sxs-lookup"><span data-stu-id="8a937-159">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="8a937-160">На странице **веб-приложение** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="8a937-160">On the **Web app** page, click **Create**.</span></span>

   ![Создание ресурса веб-приложения в Azure](media/TCimage21.png)

2. <span data-ttu-id="8a937-162">Заполните сведения (как показано ниже) и создайте веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="8a937-162">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="8a937-163">Имя, введенное в поле **имя приложения** , используется для создания URL-адреса службы приложений Azure; Например, twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="8a937-163">The name that you enter in the **App name** box is used to create the Azure app service URL; for example, twitterconnector.azurewebsites.net.</span></span>

   ![<span data-ttu-id="8a937-164">Имя типа для ресурса веб-приложения; Например, twitterconnector.azurewebsites.net</span><span class="sxs-lookup"><span data-stu-id="8a937-164">Type name for the web app resource; for example twitterconnector.azurewebsites.net</span></span> ](media/TCimage22.png)

3. <span data-ttu-id="8a937-165">Перейдите к созданному ресурсу веб-приложения и щелкните **Параметры приложения** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="8a937-165">Go to the newly created web app resource and click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="8a937-166">В разделе **Параметры приложения**щелкните **Добавить новый параметр** и добавьте следующие три параметра.</span><span class="sxs-lookup"><span data-stu-id="8a937-166">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="8a937-167">Используйте значения (скопированные в текстовый файл из предыдущих шагов):</span><span class="sxs-lookup"><span data-stu-id="8a937-167">Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="8a937-168">**Аписекреткэй** — в качестве секрета можно ввести любое значение.</span><span class="sxs-lookup"><span data-stu-id="8a937-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="8a937-169">Он используется для доступа к веб-приложению Connector на шаге 7.</span><span class="sxs-lookup"><span data-stu-id="8a937-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="8a937-170">**Сторажеаккаунтконнектионстринг** — универсальный код ресурса (URI) строки подключения, скопированный после создания учетной записи хранилища Azure на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="8a937-170">**StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="8a937-171">**tenantId** — идентификатор клиента организации Office 365, который вы скопировали после создания приложения соединителя Twitter в Azure Active Directory в действии 2.</span><span class="sxs-lookup"><span data-stu-id="8a937-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![Добавление параметров приложения](media/TCimage23.png)

4. <span data-ttu-id="8a937-173">В разделе **Общие параметры**нажмите **кнопку рядом с** параметром **Always On (включено**).</span><span class="sxs-lookup"><span data-stu-id="8a937-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="8a937-174">В верхней части страницы нажмите кнопку **сохранить** , чтобы сохранить параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="8a937-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![Включите ресурс веб-приложения, а затем сохраните его](media/TCimage24.png)

5. <span data-ttu-id="8a937-176">Последним шагом является отправка исходного кода приложения соединителя в Azure, который был загружен в действии 1.</span><span class="sxs-lookup"><span data-stu-id="8a937-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="8a937-177">В веб-браузере перейдите по адресу<AzureAppResourceName>https://. SCM.azurewebsites.NET/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="8a937-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="8a937-178">Например, если имя ресурса приложения Azure (с именем, указанным в шаге 2 в этом разделе) — **твиттерконнектор**, перейдите на https://twitterconnector.scm.azurewebsites.net/ZipDeployUiстраницу.</span><span class="sxs-lookup"><span data-stu-id="8a937-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="8a937-179">Перетащите Самплеконнектор. zip (, скачанный на шаге 1) на эту страницу.</span><span class="sxs-lookup"><span data-stu-id="8a937-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="8a937-180">После отправки файлов и успешного развертывания страница будет выглядеть аналогично следующему снимку экрана:</span><span class="sxs-lookup"><span data-stu-id="8a937-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Перетащите файл Самплеконнектор. zip на эту страницу](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="8a937-182">Шаг 5: создание приложения Twitter</span><span class="sxs-lookup"><span data-stu-id="8a937-182">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="8a937-183">Перейдите к https://developer.twitter.com, войдите в систему, используя учетные данные для учетной записи разработчика для вашей организации, а затем щелкните элемент **приложения**.</span><span class="sxs-lookup"><span data-stu-id="8a937-183">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Перейдите к https://developer.twitter.com разделу и войдите в него.](media/TCimage25-5.png)
2. <span data-ttu-id="8a937-185">Нажмите кнопку **создать приложение**.</span><span class="sxs-lookup"><span data-stu-id="8a937-185">Click **Create an app**.</span></span>
   
   ![Переход на страницу "приложения" для создания приложения](media/TCimage26.png)

3. <span data-ttu-id="8a937-187">В разделе **сведения**о приложении добавьте сведения о приложении.</span><span class="sxs-lookup"><span data-stu-id="8a937-187">Under **App details**, add information about the application.</span></span>

   ![Введите сведения о приложении](media/TCimage27.png)

4. <span data-ttu-id="8a937-189">На панели мониторинга разработчика Twitter выберите приложение, которое вы только что создали и скопируйте отображаемый Идентификатор приложения, и сохраните его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8a937-189">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="8a937-190">Затем нажмите кнопку **сведения**.</span><span class="sxs-lookup"><span data-stu-id="8a937-190">Then click **Details**.</span></span>
   
   ![Копирование и сохранение идентификатора приложения](media/TCimage28.png)

5. <span data-ttu-id="8a937-192">На вкладке **ключи и маркеры** в разделе **ключи API потребителей** СКОПИРУЙТЕ секретный ключ API и сохраните его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8a937-192">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="8a937-193">Затем нажмите кнопку **создать** , чтобы создать маркер доступа и секрет маркера доступа, а затем скопируйте его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8a937-193">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![Секретный ключ для копирования и сохранения в API](media/TCimage29.png)

   <span data-ttu-id="8a937-195">Затем нажмите кнопку **создать** , чтобы создать маркер доступа и секрет маркера доступа, а затем скопируйте его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8a937-195">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="8a937-196">Перейдите на вкладку **разрешения** и настройте разрешения, как показано на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="8a937-196">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Настройка разрешений](media/TCimage30.png)

7. <span data-ttu-id="8a937-198">После сохранения параметров разрешений перейдите на вкладку **сведения о приложении** и нажмите кнопку **изменить > изменить сведения**.</span><span class="sxs-lookup"><span data-stu-id="8a937-198">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Изменение сведений о приложении](media/TCimage31.png)

8. <span data-ttu-id="8a937-200">Выполните следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="8a937-200">Do the following tasks:</span></span>

   - <span data-ttu-id="8a937-201">Установите флажок, чтобы разрешить приложению Connector вход в Twitter.</span><span class="sxs-lookup"><span data-stu-id="8a937-201">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="8a937-202">Добавьте URI перенаправления OAuth, используя следующий формат: \*\* \<коннекторсервицеури>/виевс/твиттероаус\*\*, где значением *коннекторсервицеури* является URL-адрес службы приложений Azure для вашей организации; Пример: https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span><span class="sxs-lookup"><span data-stu-id="8a937-202">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Разрешить приложению Connector вход в Twitter и добавить URI перенаправления OAuth](media/TCimage32.png)

<span data-ttu-id="8a937-204">Теперь приложение для разработчиков Twitter готово к использованию.</span><span class="sxs-lookup"><span data-stu-id="8a937-204">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="8a937-205">Шаг 6: Настройка соединительного веб-приложения</span><span class="sxs-lookup"><span data-stu-id="8a937-205">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="8a937-206">Перейдите в раздел\<https://азуреаппресаурценаме>. azurewebsites.NET (где **азуреаппресаурценаме** — это имя ресурса приложения Azure, имя которого указано в шаге 4).</span><span class="sxs-lookup"><span data-stu-id="8a937-206">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="8a937-207">Например, если имя — **твиттерконнектор**, перейдите на https://twitterconnector.azurewebsites.netстраницу.</span><span class="sxs-lookup"><span data-stu-id="8a937-207">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="8a937-208">Домашняя страница приложения выглядит как на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="8a937-208">The home page of the app looks like the following screenshot:</span></span>

   ![Перейдите на страницу ресурсов приложения Azure](media/FBCimage41.png)

2. <span data-ttu-id="8a937-210">Нажмите кнопку **настроить** , чтобы отобразить страницу входа.</span><span class="sxs-lookup"><span data-stu-id="8a937-210">Click **Configure** to display a sign in page.</span></span>

   ![Нажмите кнопку настроить для отображения страницы входа](media/FBCimage42.png)

3. <span data-ttu-id="8a937-212">В поле Идентификатор клиента введите или вставьте идентификатор клиента (полученный на шаге 2).</span><span class="sxs-lookup"><span data-stu-id="8a937-212">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="8a937-213">В поле Пароль введите или вставьте Аписекреткэй (полученное в действии 2), а затем нажмите кнопку **Настройка параметров конфигурации** , чтобы отобразить страницу **сведений о конфигурации** .</span><span class="sxs-lookup"><span data-stu-id="8a937-213">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![Вход с использованием идентификатора клиента и секретного ключа API](media/TCimage35.png)

4. <span data-ttu-id="8a937-215">В разделе **сведения о конфигурации**введите следующие параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8a937-215">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="8a937-216">**Ключ API Twitter** — идентификатор приложения для приложения Twitter, созданного в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="8a937-216">**Twitter Api Key** – The app ID for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="8a937-217">**Секретный ключ API Twitter** — секретный ключ API для приложения Twitter, созданного в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="8a937-217">**Twitter Api Secret Key** – The API secret key for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="8a937-218">**Маркер доступа Twitter** — маркер доступа, созданный в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="8a937-218">**Twitter Access Token** – The access token that you created in Step 5.</span></span>
   - <span data-ttu-id="8a937-219">**Секрет маркера доступа Twitter** — секрет маркера доступа, созданный в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="8a937-219">**Twitter Access Token Secret** – The access token secret that you created in Step 5.</span></span>
   - <span data-ttu-id="8a937-220">**Идентификатор приложения AAD** — идентификатор приложения для приложения Azure Active Directory, созданного в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="8a937-220">**AAD Application ID** – The application ID for the Azure Active Directory app that you created in Step 2</span></span>
   - <span data-ttu-id="8a937-221">**Секрет приложения AAD** — значение для секрета аписекреткэй, созданного на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="8a937-221">**AAD Application Secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="8a937-222">**URI приложения AAD** — URI приложения AAD, полученный в шаге 2. Пример: `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span><span class="sxs-lookup"><span data-stu-id="8a937-222">**AAD Application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="8a937-223">**Ключ инструментирования App Insights** — оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="8a937-223">**App Insights Instrumentation Key** – Leave this box blank.</span></span>

5. <span data-ttu-id="8a937-224">Нажмите кнопку **сохранить** , чтобы сохранить параметры соединителя.</span><span class="sxs-lookup"><span data-stu-id="8a937-224">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="8a937-225">Шаг 7: Настройка настраиваемого соединителя в центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="8a937-225">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="8a937-226">Перейдите в <https://protection.office.com> раздел \*\* \> Управление сведениями и выберите \> пункт архивы импорта данных сторонних поставщиков\*\*.</span><span class="sxs-lookup"><span data-stu-id="8a937-226">Go to <https://protection.office.com> and then click **Information governance \> Import \> Archive third-party data**.</span></span>

    ![Переход на страницу "Архивация сторонних данных" в центре безопасности и соответствия требованиям](media/TCimage36.png)

2. <span data-ttu-id="8a937-228">Нажмите кнопку **Добавить соединитель** , а затем выберите элемент **Twitter**.</span><span class="sxs-lookup"><span data-stu-id="8a937-228">Click **Add a connector** and then click **Twitter**.</span></span>

   ![Нажмите кнопку Добавить соединитель, чтобы добавить соединитель Twitter](media/TCimage37.png)

3. <span data-ttu-id="8a937-230">На странице **Добавление приложения соединителя** введите следующие сведения и нажмите кнопку **проверить соединитель**.</span><span class="sxs-lookup"><span data-stu-id="8a937-230">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="8a937-231">В первом поле введите имя соединителя, например **Twitter**.</span><span class="sxs-lookup"><span data-stu-id="8a937-231">In the first box, type a name for the connector, such as **Twitter**.</span></span>
    - <span data-ttu-id="8a937-232">Во втором поле введите или вставьте значение Аписекреткэй, добавленное на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="8a937-232">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="8a937-233">В третьем поле введите или вставьте URL-адрес службы приложений Azure; Пример: **https://twitterconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="8a937-233">In the third box, type or paste the Azure app service URL; for example, **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="8a937-234">После успешной проверки соединителя нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8a937-234">After the connector is successfully validated, click **Next**.</span></span>

   ![Введите параметры приложения соединителя](media/TCimage38.png)

4. <span data-ttu-id="8a937-236">Щелкните **имя входа с приложением Connector Connector**.</span><span class="sxs-lookup"><span data-stu-id="8a937-236">Click **Login with Connector App**.</span></span>

   ![Приложение для входа в приложение Connector](media/TCimage39.png)

5. <span data-ttu-id="8a937-238">Введите или вставьте Аписекреткэй еще раз, а затем щелкните **Вход в службу соединителя**.</span><span class="sxs-lookup"><span data-stu-id="8a937-238">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![Введите секретный ключ API для входа в службу соединителя](media/TCimage40.png)

6. <span data-ttu-id="8a937-240">Щелкните **продолжить с помощью Twitter**.</span><span class="sxs-lookup"><span data-stu-id="8a937-240">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="8a937-241">На странице входа в Twitter Войдите в систему, используя учетные данные для учетной записи Twitter вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8a937-241">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![Вход в учетную запись Twitter](media/TCimage42.png)

   <span data-ttu-id="8a937-243">После входа на странице Twitter отобразится следующее сообщение: "Задание соединителя Twitter успешно настроено".</span><span class="sxs-lookup"><span data-stu-id="8a937-243">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="8a937-244">Нажмите кнопку **Готово** , чтобы завершить настройку соединителя Twitter.</span><span class="sxs-lookup"><span data-stu-id="8a937-244">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="8a937-245">На странице " **Настройка фильтров** " можно применить фильтр для импорта (и архивирования) элементов с определенным сроком хранения.</span><span class="sxs-lookup"><span data-stu-id="8a937-245">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="8a937-246">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8a937-246">Click **Next**.</span></span>

   ![Настройка фильтра для импорта элементов определенного срока хранения](media/TCimage44.png)

10. <span data-ttu-id="8a937-248">На странице " **Задание учетной записи хранения** " введите адрес электронной почты почтового ящика Office 365, в который будут импортированы элементы Twitter.</span><span class="sxs-lookup"><span data-stu-id="8a937-248">On the **Set Storage Account** page, type the email address of an Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![Указание почтового ящика Office 365 для импорта элементов Twitter в](media/TCimage45.png)

11. <span data-ttu-id="8a937-250">Проверьте параметры и нажмите кнопку **Готово** , чтобы завершить настройку соединителя в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="8a937-250">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![Проверьте параметры и нажмите кнопку Готово.](media/TCimage46.png)

    ![Экран, на котором показано, что установка соединителя завершена](media/TCimage47.png)

12. <span data-ttu-id="8a937-253">Перейдите на страницу **архивации сторонних данных** , чтобы просмотреть ход процесса импорта.</span><span class="sxs-lookup"><span data-stu-id="8a937-253">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![Новый соединитель, отображаемый в центре безопасности и соответствия требованиям](media/TCimage48.png)
