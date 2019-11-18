---
title: Развертывание соединителя для архивации данных Facebook в Office 365
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
description: Администраторы могут настроить собственный соединитель для импорта и архивации бизнес-страниц Facebook в Office 365. После импорта этих данных в Office 365 вы можете использовать такие функции обеспечения соответствия, как судебное удержание, поиск контента и политики хранения, для управления управлением данными Facebook Организации.
ms.openlocfilehash: 786ff97c558a5618643783de803c742c50185f00
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "38687461"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a><span data-ttu-id="8233b-104">Развертывание соединителя для архивации данных Facebook в Office 365</span><span class="sxs-lookup"><span data-stu-id="8233b-104">Deploy a connector to archive Facebook data in Office 365</span></span>

<span data-ttu-id="8233b-105">В этой статье представлено пошаговое руководство по развертыванию соединителя, использующего службу импорта Office 365 для импорта данных из бизнес-страниц Facebook в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8233b-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="8233b-106">Общий обзор этого процесса и список необходимых компонентов, необходимых для развертывания соединителя Facebook, приведены в статье [Использование примера соединителя для архивации данных Facebook в Office 365 (Предварительная версия)](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8233b-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use a sample connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="8233b-107">Шаг 1: Загрузка пакета</span><span class="sxs-lookup"><span data-stu-id="8233b-107">Step 1: Download the package</span></span>

<span data-ttu-id="8233b-108">Скачайте готовый пакет из раздела Release репозитория GitHub по адресу <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span><span class="sxs-lookup"><span data-stu-id="8233b-108">Download the prebuilt package from the Release section in the GitHub repository at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="8233b-109">В последнем выпуске Скачайте ZIP-файл с именем **самплеконнектор. zip**.</span><span class="sxs-lookup"><span data-stu-id="8233b-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="8233b-110">Вы отправляете этот ZIP-файл в Azure на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="8233b-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="8233b-111">Шаг 2: создание приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8233b-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="8233b-112">Перейдите на <https://portal.azure.com> страницу и войдите, используя учетные данные глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="8233b-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![Создание приложения в AAD](media/FBCimage1.png)

2. <span data-ttu-id="8233b-114">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="8233b-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Выберите Azure Active Directory](media/FBCimage2.png)

3. <span data-ttu-id="8233b-116">В левой области навигации щелкните **Регистрация приложений (Предварительная версия)** , а затем нажмите кнопку **создать регистрацию**.</span><span class="sxs-lookup"><span data-stu-id="8233b-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Выберите \* \* регистрации приложений (Предварительная версия) \* \* и нажмите \* \* Новая регистрация \* \*](media/FBCimage3.png)

4. <span data-ttu-id="8233b-118">Зарегистрируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="8233b-118">Register the application.</span></span> <span data-ttu-id="8233b-119">В разделе URI перенаправления выберите пункт веб-сайт в раскрывающемся списке Тип <https://portal.azure.com> приложения, а затем введите в поле для URI.</span><span class="sxs-lookup"><span data-stu-id="8233b-119">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Регистрация приложения](media/FBCimage4.png)

5. <span data-ttu-id="8233b-121">Скопируйте идентификатор **приложения (идентификатор клиента)** и **идентификатор каталога (клиента)** и сохраните их в текстовый файл или другое надежное расположение.</span><span class="sxs-lookup"><span data-stu-id="8233b-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="8233b-122">Эти идентификаторы используются на последующих этапах.</span><span class="sxs-lookup"><span data-stu-id="8233b-122">You use these IDs in later steps.</span></span>

   ![Скопируйте идентификатор приложения и идентификатор каталога и сохраните их](media/FBCimage5.png)

6. <span data-ttu-id="8233b-124">Перейдите к разделу **сертификаты & секреты для нового приложения.**</span><span class="sxs-lookup"><span data-stu-id="8233b-124">Go to **Certificates & secrets for the new app.**</span></span>

   ![Перейти к сертификатам & секреты для нового приложения](media/FBCimage6.png)

7. <span data-ttu-id="8233b-126">Щелкните **новый секрет клиента**</span><span class="sxs-lookup"><span data-stu-id="8233b-126">Click **New client secret**</span></span>

   ![Щелкните новый секрет клиента](media/FBCimage7.png)

8. <span data-ttu-id="8233b-128">Создайте новый секрет.</span><span class="sxs-lookup"><span data-stu-id="8233b-128">Create a new secret.</span></span> <span data-ttu-id="8233b-129">В поле Описание введите секрет, а затем выберите срок действия.</span><span class="sxs-lookup"><span data-stu-id="8233b-129">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![Введите секрет, а затем выберите срок действия](media/FBCimage8.png)

9. <span data-ttu-id="8233b-131">Скопируйте значение секрета и сохраните его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8233b-131">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="8233b-132">Это секрет приложения AAD, который вы используете в дальнейших действиях.</span><span class="sxs-lookup"><span data-stu-id="8233b-132">This is the AAD application secret that you use in later steps.</span></span>

   ![Скопируйте значение секрета и сохраните его](media/FBCimage9.png)

10. <span data-ttu-id="8233b-134">Перейдите к **манифесту** и скопируйте с identifieruris (который также называется URI приложения AAD), выделенный на следующем снимке экрана.</span><span class="sxs-lookup"><span data-stu-id="8233b-134">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="8233b-135">Скопируйте универсальный код ресурса (URI) приложения AAD в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8233b-135">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="8233b-136">Его можно использовать на шаге 6.</span><span class="sxs-lookup"><span data-stu-id="8233b-136">You use it in Step 6.</span></span>

   ![Перейдите к манифесту и скопируйте URI приложения AAD](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="8233b-138">Шаг 3: создание учетной записи хранения Azure</span><span class="sxs-lookup"><span data-stu-id="8233b-138">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="8233b-139">Перейдите на домашнюю страницу Azure для своей организации.</span><span class="sxs-lookup"><span data-stu-id="8233b-139">Go to the Azure home page for your organization.</span></span>

    ![Переход на домашнюю страницу Azure](media/FBCimage11.png)

2. <span data-ttu-id="8233b-141">Щелкните **создать ресурс** и введите **учетную запись хранения** в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="8233b-141">Click **Create a resource** and then type **storage account** in the search box.</span></span>

    ![Нажмите кнопку Создать ресурс и введите учетную запись хранения.](media/FBCimage12.png)

3. <span data-ttu-id="8233b-143">Щелкните **хранилище**, а затем выберите **учетная запись хранилища**.</span><span class="sxs-lookup"><span data-stu-id="8233b-143">Click **Storage**, and then click **Storage account**.</span></span>

    ![Щелкните хранилище, а затем выберите Учетная запись хранилища.](media/FBCimage13.png)

4. <span data-ttu-id="8233b-145">На странице " **Создание учетной записи хранения** " в поле подписка выберите вариант **Оплата от имени** или **бесплатной пробной версии** в зависимости от того, какой тип подписки Azure вы используете.</span><span class="sxs-lookup"><span data-stu-id="8233b-145">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="8233b-146">Затем выберите или создайте группу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8233b-146">Then select or create a resource group.</span></span>

    ![Выберите вариант оплата от имени или бесплатной пробной версии](media/FBCimage14.png)

5. <span data-ttu-id="8233b-148">Введите имя учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="8233b-148">Type a name for the storage account.</span></span>

    ![Введите имя учетной записи хранения](media/FBCimage15.png)

6. <span data-ttu-id="8233b-150">Просмотрите, а затем нажмите кнопку **создать** , чтобы создать учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="8233b-150">Review and then click **Create** to create the storage account.</span></span>

    ![Создание учетной записи хранения](media/FBCimage16.png)

7. <span data-ttu-id="8233b-152">Через несколько секунд нажмите кнопку **Обновить** , а затем выберите **Перейти к ресурсу** , чтобы перейти к учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="8233b-152">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![Перейдите к учетной записи хранения](media/FBCimage17.png)

8. <span data-ttu-id="8233b-154">Нажмите **клавиши доступа** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="8233b-154">Click **Access keys** in the left navigation pane.</span></span>

    ![Нажмите клавиши доступа](media/FBCimage18.png)

9. <span data-ttu-id="8233b-156">Скопируйте **строку подключения** и сохраните ее в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8233b-156">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="8233b-157">Используется при создании ресурса веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="8233b-157">You use this when creating a web app resource.</span></span>

    ![Копирование строки подключения и ее сохранение](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="8233b-159">Шаг 4: создание нового ресурса веб-приложения в Azure</span><span class="sxs-lookup"><span data-stu-id="8233b-159">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="8233b-160">На **домашней** странице на портале Azure выберите **создать веб-приложение " \> все \> ресурсы**".</span><span class="sxs-lookup"><span data-stu-id="8233b-160">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="8233b-161">На странице **веб-приложение** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="8233b-161">On the **Web app** page, click **Create**.</span></span> 

   ![Создание нового ресурса веб-приложения](media/FBCimage20.png)

2. <span data-ttu-id="8233b-163">Заполните сведения (как показано ниже) и создайте веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="8233b-163">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="8233b-164">Обратите внимание, что имя, введенное в поле **имя приложения** , используется для создания URL-адреса службы приложений Azure; Например, fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="8233b-164">Note that the name that you enter in the **App name** box is used to create the Azure app service URL; for example, fbconnector.azurewebsites.net.</span></span>

   ![Заполните сведения и создайте веб-приложение.](media/FBCimage21.png)

3. <span data-ttu-id="8233b-166">Перейдите к только что созданному ресурсу веб-приложения, щелкните **Параметры приложения** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="8233b-166">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="8233b-167">В разделе Параметры приложения щелкните Добавить новый параметр и добавьте следующие три параметра: используйте значения (скопированные в текстовый файл из предыдущих шагов):</span><span class="sxs-lookup"><span data-stu-id="8233b-167">Under Application settings, click Add new setting and add the following three settings: Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="8233b-168">**Аписекреткэй** — в качестве секрета можно ввести любое значение.</span><span class="sxs-lookup"><span data-stu-id="8233b-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="8233b-169">Он используется для доступа к веб-приложению Connector на шаге 7.</span><span class="sxs-lookup"><span data-stu-id="8233b-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="8233b-170">**Сторажеаккаунтконнектионстринг** — универсальный код ресурса (URI) строки подключения, скопированный после создания учетной записи хранилища Azure на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="8233b-170">**StorageAccountConnectionString** — The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="8233b-171">**tenantId** — идентификатор клиента организации Office 365, который вы скопировали после создания приложения соединителя Facebook в Azure Active Directory в действии 2.</span><span class="sxs-lookup"><span data-stu-id="8233b-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![Введите параметры приложения](media/FBCimage22.png)

4. <span data-ttu-id="8233b-173">В разделе **Общие параметры**нажмите **кнопку рядом с** параметром **Always On (включено**).</span><span class="sxs-lookup"><span data-stu-id="8233b-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="8233b-174">В верхней части страницы нажмите кнопку **сохранить** , чтобы сохранить параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="8233b-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![Сохранение параметров приложения](media/FBCimage23.png)

5. <span data-ttu-id="8233b-176">Последним шагом является отправка исходного кода приложения соединителя в Azure, который был загружен в действии 1.</span><span class="sxs-lookup"><span data-stu-id="8233b-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="8233b-177">В веб-браузере перейдите по адресу<AzureAppResourceName>https://. SCM.azurewebsites.NET/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="8233b-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="8233b-178">Например, если имя ресурса приложения Azure (с именем, указанным в шаге 2 в этом разделе) — **фбконнектор**, перейдите на https://fbconnector.scm.azurewebsites.net/ZipDeployUiстраницу.</span><span class="sxs-lookup"><span data-stu-id="8233b-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="8233b-179">Перетащите Самплеконнектор. zip (, скачанный на шаге 1) на эту страницу.</span><span class="sxs-lookup"><span data-stu-id="8233b-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="8233b-180">После отправки файлов и успешного развертывания страница будет выглядеть аналогично следующему снимку экрана:</span><span class="sxs-lookup"><span data-stu-id="8233b-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Перетащите Самплеконнектор. zip на эту страницу](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="8233b-182">Шаг 5: регистрация приложения Facebook</span><span class="sxs-lookup"><span data-stu-id="8233b-182">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="8233b-183">Перейдите к <https://developers.facebook.com>, войдите в систему, используя учетные данные для учетной записи для бизнес-страниц Facebook вашей организации, а затем щелкните **Добавить новое приложение**.</span><span class="sxs-lookup"><span data-stu-id="8233b-183">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![Добавление новой веб-страницы приложения для Facebook](media/FBCimage25.png)

2. <span data-ttu-id="8233b-185">Создайте идентификатор нового приложения.</span><span class="sxs-lookup"><span data-stu-id="8233b-185">Create a new app ID.</span></span>

   ![Создание идентификатора нового приложения](media/FBCimage26.png)

3. <span data-ttu-id="8233b-187">В левой области навигации щелкните **Добавить продукты** , а затем — **Настройка** на плитке **входа Facebook** .</span><span class="sxs-lookup"><span data-stu-id="8233b-187">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Нажмите кнопку "добавить продукты"](media/FBCimage27.png)

4. <span data-ttu-id="8233b-189">На странице Интеграция входа в Facebook нажмите кнопку **веб**.</span><span class="sxs-lookup"><span data-stu-id="8233b-189">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Нажмите кнопку "веб-сайт" на странице интеграция Facebook login](media/FBCimage28.png)

5. <span data-ttu-id="8233b-191">Добавьте URL-адрес службы приложений Azure; например `https://fbconnector.azurewebsites.net`:.</span><span class="sxs-lookup"><span data-stu-id="8233b-191">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Добавление URL-адреса службы приложений Azure](media/FBCimage29.png)

6. <span data-ttu-id="8233b-193">Заполните раздел Краткое руководство по настройке входа в Facebook.</span><span class="sxs-lookup"><span data-stu-id="8233b-193">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Выполнение раздела "Быстрый запуск"](media/FBCimage30.png)

7. <span data-ttu-id="8233b-195">В левой области навигации в разделе **Login Facebook**щелкните **Параметры**, а затем добавьте URI перенаправления OAuth в поле **допустимые URI переадресации OAuth** .</span><span class="sxs-lookup"><span data-stu-id="8233b-195">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="8233b-196">Используйте формат \*\* \<коннекторсервицеури>/виевс/фацебукоаус\*\*, где значением коннекторсервицеури является URL-адрес службы приложений Azure для вашей организации; Пример: `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="8233b-196">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Добавление URI перенаправления OAuth в допустимое поле URI перенаправления OAuth](media/FBCimage31.png)

8. <span data-ttu-id="8233b-198">В левой области навигации щелкните **Добавить продукты** и выберите **веб-перехватчики.**</span><span class="sxs-lookup"><span data-stu-id="8233b-198">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="8233b-199">В раскрывающемся меню **Page (страница** ) выберите пункт **Page (страница**).</span><span class="sxs-lookup"><span data-stu-id="8233b-199">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![Щелкните Добавить продукты и выберите \* \* веб-перехватчики](media/FBCimage32.png)

9. <span data-ttu-id="8233b-201">Добавьте URL-адрес обратного вызова для веб-перехватчиков и добавьте маркер проверки.</span><span class="sxs-lookup"><span data-stu-id="8233b-201">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="8233b-202">Формат URL-адреса обратного вызова, используйте формат \*\* <connectorserviceuri>/АПИ/фбпажевебхук\*\*, где значение параметра коннекторсервицеури — это URL-адрес службы приложений Azure для вашей организации; например `https://fbconnector.azurewebsites.net`:.</span><span class="sxs-lookup"><span data-stu-id="8233b-202">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span> 

    <span data-ttu-id="8233b-203">Маркер проверки должен быть похож на надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="8233b-203">The verify token should similar to a strong password.</span></span> <span data-ttu-id="8233b-204">Скопируйте токен проверки в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8233b-204">Copy the verify token to a text file or other storage location.</span></span>

        ![Add the verify token](media/FBCimage33.png)

10. <span data-ttu-id="8233b-205">Протестируйте и подпишитесь на конечную точку для веб-канала.</span><span class="sxs-lookup"><span data-stu-id="8233b-205">Test and subscribe to the endpoint for feed.</span></span>

    ![Тестирование конечной точки и подписка на нее](media/FBCimage34.png)

11. <span data-ttu-id="8233b-207">Добавьте URL-адрес конфиденциальности, значок приложения и использование для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8233b-207">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="8233b-208">Кроме того, скопируйте идентификатор приложения и секрет приложения в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="8233b-208">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Добавление URL-адреса конфиденциальности, значка приложения и использования для бизнеса](media/FBCimage35.png)

12. <span data-ttu-id="8233b-210">Сделайте приложение общедоступным.</span><span class="sxs-lookup"><span data-stu-id="8233b-210">Make the app public.</span></span>

    ![Сделайте приложение общедоступным](media/FBCimage36.png)

13. <span data-ttu-id="8233b-212">Добавьте пользователя к роли администратора или тестера.</span><span class="sxs-lookup"><span data-stu-id="8233b-212">Add user to the admin or tester role.</span></span>

    ![Добавление пользователя к роли администратора или тестера](media/FBCimage37.png)

14. <span data-ttu-id="8233b-214">Добавьте разрешение на **доступ к общему содержимому страницы** .</span><span class="sxs-lookup"><span data-stu-id="8233b-214">Add the **Page Public Content Access** permission.</span></span>

    ![DD разрешение на доступ к общедоступному содержимому страницы](media/FBCimage38.png)

15. <span data-ttu-id="8233b-216">Разрешение "добавить Управление страницами".</span><span class="sxs-lookup"><span data-stu-id="8233b-216">Add Manage Pages permission.</span></span>

    ![Разрешение "Добавление страниц управления"](media/FBCimage39.png)

16. <span data-ttu-id="8233b-218">Получение приложения, проверенного Facebook.</span><span class="sxs-lookup"><span data-stu-id="8233b-218">Get the application reviewed by Facebook.</span></span>

    ![Получение приложения, проверенного с помощью Facebook](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="8233b-220">Шаг 6: Настройка соединительного веб-приложения</span><span class="sxs-lookup"><span data-stu-id="8233b-220">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="8233b-221">Перейдите в раздел\<https://азуреаппресаурценаме>. azurewebsites.NET (где азуреаппресаурценаме — имя ресурса приложения Azure, имя которого указано в шаге 4) например, если имя — **фбконнектор**, перейдите на `https://fbconnector.azurewebsites.net`страницу.</span><span class="sxs-lookup"><span data-stu-id="8233b-221">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="8233b-222">Домашняя страница приложения будет выглядеть, как на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="8233b-222">The home page of the app will look like the following screenshot:</span></span>

   ![Перейдите в веб-приложение Connector Connector.](media/FBCimage41.png)

2. <span data-ttu-id="8233b-224">Нажмите кнопку **настроить** , чтобы отобразить страницу входа.</span><span class="sxs-lookup"><span data-stu-id="8233b-224">Click **Configure** to display a sign in page.</span></span>
 
   ![Нажмите кнопку Настройка, чтобы отобразить страницу входа](media/FBCimage42.png)

3. <span data-ttu-id="8233b-226">В поле Идентификатор клиента введите или вставьте идентификатор клиента (полученный на шаге 2).</span><span class="sxs-lookup"><span data-stu-id="8233b-226">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="8233b-227">В поле Пароль введите или вставьте Аписекреткэй (полученное в действии 2), а затем нажмите кнопку **Настройка параметров конфигурации** , чтобы отобразить страницу **сведений о конфигурации** .</span><span class="sxs-lookup"><span data-stu-id="8233b-227">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![Вход с использованием идентификатора и пароля клиента и переход на страницу сведений о конфигурации](media/FBCimage43.png)

4. <span data-ttu-id="8233b-229">В разделе **сведения о конфигурации**введите следующие параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8233b-229">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="8233b-230">**Application ID Application ID** — идентификатор приложения для приложения Facebook, полученного в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="8233b-230">**Facebook application ID** – The app ID for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="8233b-231">**Секрет приложения Facebook** — секрет приложения для приложения Facebook, полученного в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="8233b-231">**Facebook application secret** – The app secret for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="8233b-232">**Веб-перехватчики Facebook проверьте токен** — маркер проверки, созданный на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="8233b-232">**Facebook webhooks verify token** – The verify token that you created in Step 5.</span></span>
   - <span data-ttu-id="8233b-233">**Идентификатор приложения AAD** — идентификатор приложения для приложения Azure Active Directory, созданного в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="8233b-233">**AAD application ID** – The application ID for the Azure Active Directory app that you created in Step 2.</span></span>
   - <span data-ttu-id="8233b-234">**Секрет приложения AAD** — значение для секрета аписекреткэй, созданного на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="8233b-234">**AAD application secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="8233b-235">**URI приложения AAD** — URI приложения AAD, полученный в шаге 2. Пример: `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span><span class="sxs-lookup"><span data-stu-id="8233b-235">**AAD application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="8233b-236">**Ключ инструментирования App Insights** — оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="8233b-236">**App insights instrumentation key** – Leave this box blank.</span></span>

5. <span data-ttu-id="8233b-237">Нажмите кнопку **сохранить** , чтобы сохранить параметры соединителя.</span><span class="sxs-lookup"><span data-stu-id="8233b-237">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="8233b-238">Шаг 7: Настройка настраиваемого соединителя в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="8233b-238">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="8233b-239">Перейдите в <https://protection.office.com> раздел **Управление \> данными и выберите пункт \> архивы импорта данных сторонних поставщиков**.</span><span class="sxs-lookup"><span data-stu-id="8233b-239">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

   ![Перейдите в центр безопасности и соответствия требованиям и выберите Управление данными > импорта > архивы сторонних данных](media/FBCimage44.png)

2.  <span data-ttu-id="8233b-241">Нажмите кнопку **Добавить соединитель** , а затем выберите **страницы Facebook**.</span><span class="sxs-lookup"><span data-stu-id="8233b-241">Click **Add a connector** and then click **Facebook pages**.</span></span>

    ![Добавление соединителя Facebook Настройка соединителя](media/FBCimage46.png)

3.  <span data-ttu-id="8233b-243">На странице **Добавление приложения соединителя** введите следующие сведения и нажмите кнопку **проверить соединитель**.</span><span class="sxs-lookup"><span data-stu-id="8233b-243">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="8233b-244">В первом поле введите имя соединителя, например **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="8233b-244">In the first box, type a name for the connector, such as **Facebook**.</span></span>
    - <span data-ttu-id="8233b-245">Во втором поле введите или вставьте значение Аписекреткэй, добавленное на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="8233b-245">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="8233b-246">В третьем поле введите или вставьте URL-адрес службы приложений Azure; например `https://fbconnector.azurewebsites.net`:.</span><span class="sxs-lookup"><span data-stu-id="8233b-246">In the third box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>
 
    <span data-ttu-id="8233b-247">После успешной проверки соединителя нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8233b-247">After the connector is successfully validated, click **Next**.</span></span>
    
    ![После успешной проверки соединителя нажмите кнопку Далее.](media/FBCimage47.png)

4.  <span data-ttu-id="8233b-249">Щелкните **имя входа с приложением Connector Connector**.</span><span class="sxs-lookup"><span data-stu-id="8233b-249">Click **Login with Connector App**.</span></span>

    ![Щелкните имя входа с приложением Connector](media/FBCimage45.png)

5. <span data-ttu-id="8233b-251">Введите или вставьте Аписекреткэй еще раз, а затем щелкните **Вход в службу соединителя**.</span><span class="sxs-lookup"><span data-stu-id="8233b-251">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![Введите или вставьте Аписекреткэй, а затем нажмите кнопку Вход](media/FBCimage48.png)

6. <span data-ttu-id="8233b-253">Выберите **Вход с помощью Facebook**.</span><span class="sxs-lookup"><span data-stu-id="8233b-253">Click **Login with Facebook**.</span></span>

   ![Щелкните \* \* Войти с помощью Facebook](media/FBCimage49.png)

7. <span data-ttu-id="8233b-255">На странице **Вход в Facebook** Войдите в систему, используя учетные данные для учетной записи для бизнес-страниц Facebook вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8233b-255">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="8233b-256">Убедитесь, что учетной записи Facebook, в которую вы выполнили вход, назначена роль администратора для бизнес-страниц Facebook Организации.</span><span class="sxs-lookup"><span data-stu-id="8233b-256">Make sure the Facebook account that you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![Вход в Facebook](media/FBCimage50.png)

8. <span data-ttu-id="8233b-258">Нажмите кнопку **Выбор страниц** , чтобы выбрать деловые страницы Организации, которые нужно архивировать в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8233b-258">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![Нажмите кнопку Выбор страниц, чтобы отобразить деловые страницы Организации](media/FBCimage51.png)

9. <span data-ttu-id="8233b-260">Отображается список бизнес-страниц, управляемых учетной записью Facebook, в которой выполнен вход.</span><span class="sxs-lookup"><span data-stu-id="8233b-260">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="8233b-261">Выберите страницу для архивации и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8233b-261">Select the page to archive and then click **Save**.</span></span>

    ![Выберите бизнес-страницу Организации, которую нужно архивировать](media/FBCimage52.png)

10. <span data-ttu-id="8233b-263">Нажмите кнопку **Готово** , чтобы выйти из программы установки приложения службы соединителя.</span><span class="sxs-lookup"><span data-stu-id="8233b-263">Click **Finish** to exit the setup of the connector service app.</span></span>

    ![Нажмите кнопку Готово, чтобы выйти из приложения службы соединителя](media/FBCimage53.png)

11. <span data-ttu-id="8233b-265">На странице " **Настройка фильтров** " можно применить фильтр для импорта (и архивирования) элементов с определенным сроком хранения.</span><span class="sxs-lookup"><span data-stu-id="8233b-265">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="8233b-266">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8233b-266">Click **Next**.</span></span>

    ![Применение фильтра для импорта элементов с определенным сроком хранения](media/FBCimage54.png)

12. <span data-ttu-id="8233b-268">На странице " **Настройка учетной записи хранения** " выберите почтовый ящик Office 365, в который будут импортированы элементы из ранее выбранных страниц Facebook бизнес-страниц.</span><span class="sxs-lookup"><span data-stu-id="8233b-268">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![Указание элементов архивов почтовых ящиков Office 365, импортированных из Facebook](media/FBCimage55.png)

13. <span data-ttu-id="8233b-270">Проверьте параметры и нажмите кнопку **Готово** , чтобы завершить настройку соединителя в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="8233b-270">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![Обзор параметров соединителя](media/FBCimage56.png)

14. <span data-ttu-id="8233b-272">Перейдите на страницу **архивации сторонних данных** , чтобы просмотреть ход процесса импорта.</span><span class="sxs-lookup"><span data-stu-id="8233b-272">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![Переход на страницу "Архивация сторонних данных" для отслеживания процесса импорта](media/FBCimage58.png)
