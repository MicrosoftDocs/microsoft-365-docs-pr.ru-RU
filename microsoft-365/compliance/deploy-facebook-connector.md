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
ms.openlocfilehash: 1f5b0f241616cc95e79e80d054a8782f97c5887b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071189"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a><span data-ttu-id="a4626-104">Развертывание соединителя для архивации данных Facebook в Office 365</span><span class="sxs-lookup"><span data-stu-id="a4626-104">Deploy a connector to archive Facebook data in Office 365</span></span>

<span data-ttu-id="a4626-105">В этой статье представлено пошаговое руководство по развертыванию соединителя, использующего службу импорта Office 365 для импорта данных из бизнес-страниц Facebook в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4626-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="a4626-106">Общий обзор этого процесса и список необходимых компонентов, необходимых для развертывания соединителя Facebook, приведены в статье [Использование примера соединителя для архивации данных Facebook в Office 365 (Предварительная версия)](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a4626-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use a sample connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="a4626-107">Шаг 1: Загрузка пакета</span><span class="sxs-lookup"><span data-stu-id="a4626-107">Step 1: Download the package</span></span>

<span data-ttu-id="a4626-108">Скачайте готовый пакет из раздела Release репозитория GitHub по адресу <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span><span class="sxs-lookup"><span data-stu-id="a4626-108">Download the prebuilt package from the Release section in the GitHub repository at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="a4626-109">В последнем выпуске Скачайте ZIP-файл с именем **самплеконнектор. zip**.</span><span class="sxs-lookup"><span data-stu-id="a4626-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="a4626-110">Вы отправляете этот ZIP-файл в Azure на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="a4626-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="a4626-111">Шаг 2: создание приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a4626-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="a4626-112">Перейдите на <https://portal.azure.com> страницу и войдите, используя учетные данные глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4626-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![Создание приложения в AAD](media/FBCimage1.png)

2. <span data-ttu-id="a4626-114">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a4626-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![](media/FBCimage2.png)

3. <span data-ttu-id="a4626-115">В левой области навигации щелкните **Регистрация приложений (Предварительная версия)** , а затем нажмите кнопку **создать регистрацию**.</span><span class="sxs-lookup"><span data-stu-id="a4626-115">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![](media/FBCimage3.png)

4. <span data-ttu-id="a4626-116">Зарегистрируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="a4626-116">Register the application.</span></span> <span data-ttu-id="a4626-117">В разделе URI перенаправления выберите пункт веб-сайт в раскрывающемся списке Тип <https://portal.azure.com> приложения, а затем введите в поле для URI.</span><span class="sxs-lookup"><span data-stu-id="a4626-117">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/FBCimage4.png)

5. <span data-ttu-id="a4626-118">Скопируйте идентификатор **приложения (идентификатор клиента)** и **идентификатор каталога (клиента)** и сохраните их в текстовый файл или другое надежное расположение.</span><span class="sxs-lookup"><span data-stu-id="a4626-118">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="a4626-119">Эти идентификаторы используются на последующих этапах.</span><span class="sxs-lookup"><span data-stu-id="a4626-119">You use these IDs in later steps.</span></span>

   ![](media/FBCimage5.png)

6. <span data-ttu-id="a4626-120">Перейдите к разделу **сертификаты & секреты для нового приложения.**</span><span class="sxs-lookup"><span data-stu-id="a4626-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![](media/FBCimage6.png)

7. <span data-ttu-id="a4626-121">Щелкните **новый секрет клиента**</span><span class="sxs-lookup"><span data-stu-id="a4626-121">Click **New client secret**</span></span>

   ![](media/FBCimage7.png)

8. <span data-ttu-id="a4626-122">Создайте новый секрет.</span><span class="sxs-lookup"><span data-stu-id="a4626-122">Create a new secret.</span></span> <span data-ttu-id="a4626-123">В поле Описание введите секрет, а затем выберите срок действия.</span><span class="sxs-lookup"><span data-stu-id="a4626-123">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![](media/FBCimage8.png)

9. <span data-ttu-id="a4626-124">Скопируйте значение секрета и сохраните его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="a4626-124">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="a4626-125">Это секрет приложения AAD, который вы используете в дальнейших действиях.</span><span class="sxs-lookup"><span data-stu-id="a4626-125">This is the AAD application secret that you use in later steps.</span></span>

   ![](media/FBCimage9.png)

10. <span data-ttu-id="a4626-126">Перейдите к **манифесту** и скопируйте с identifieruris (который также называется URI приложения AAD), выделенный на следующем снимке экрана.</span><span class="sxs-lookup"><span data-stu-id="a4626-126">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="a4626-127">Скопируйте универсальный код ресурса (URI) приложения AAD в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="a4626-127">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="a4626-128">Его можно использовать на шаге 6.</span><span class="sxs-lookup"><span data-stu-id="a4626-128">You use it in Step 6.</span></span>

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="a4626-129">Шаг 3: создание учетной записи хранения Azure</span><span class="sxs-lookup"><span data-stu-id="a4626-129">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="a4626-130">Перейдите на домашнюю страницу Azure для своей организации.</span><span class="sxs-lookup"><span data-stu-id="a4626-130">Go to the Azure home page for your organization.</span></span>

    ![](media/FBCimage11.png)

2. <span data-ttu-id="a4626-131">Выберите **создать ресурс** и введите **учетную запись хранения** в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="a4626-131">Click **Create a resource** and they type **storage account** in the search box.</span></span>

    ![](media/FBCimage12.png)

3. <span data-ttu-id="a4626-132">Щелкните **хранилище**, а затем выберите **учетная запись хранилища**.</span><span class="sxs-lookup"><span data-stu-id="a4626-132">Click **Storage**, and then click **Storage account**.</span></span>

    ![](media/FBCimage13.png)

4. <span data-ttu-id="a4626-133">На странице " **Создание учетной записи хранения** " в поле подписка выберите вариант **Оплата от имени** или **бесплатной пробной версии** в зависимости от того, какой тип подписки Azure вы используете.</span><span class="sxs-lookup"><span data-stu-id="a4626-133">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="a4626-134">Затем выберите или создайте группу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a4626-134">Then select or create a resource group.</span></span>

    ![](media/FBCimage14.png)

5. <span data-ttu-id="a4626-135">Введите имя учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="a4626-135">Type a name for the storage account.</span></span>

    ![](media/FBCimage15.png)

6. <span data-ttu-id="a4626-136">Просмотрите, а затем нажмите кнопку **создать** , чтобы создать учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="a4626-136">Review and then click **Create** to create the storage account.</span></span>

    ![](media/FBCimage16.png)

7. <span data-ttu-id="a4626-137">Через несколько секунд нажмите кнопку **Обновить** , а затем выберите **Перейти к ресурсу** , чтобы перейти к учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="a4626-137">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![](media/FBCimage17.png)

8. <span data-ttu-id="a4626-138">Нажмите **клавиши доступа** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="a4626-138">Click **Access keys** in the left navigation pane.</span></span>

    ![](media/FBCimage18.png)

9. <span data-ttu-id="a4626-139">Скопируйте **строку подключения** и сохраните ее в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="a4626-139">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="a4626-140">Используется при создании ресурса веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="a4626-140">You use this when creating a web app resource.</span></span>

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="a4626-141">Шаг 4: создание нового ресурса веб-приложения в Azure</span><span class="sxs-lookup"><span data-stu-id="a4626-141">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="a4626-142">На **домашней** странице на портале Azure выберите **создать веб-приложение " \> все \> ресурсы**".</span><span class="sxs-lookup"><span data-stu-id="a4626-142">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="a4626-143">На странице **веб-приложение** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="a4626-143">On the **Web app** page, click **Create**.</span></span> 

   ![](media/FBCimage20.png)

2. <span data-ttu-id="a4626-144">Заполните сведения (как показано ниже) и создайте веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="a4626-144">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="a4626-145">Обратите внимание, что имя, введенное в поле **имя приложения** , используется для создания URL-адреса службы приложений Azure; Например, fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="a4626-145">Note that the name that you enter in the **App name** box is used to create the Azure app service URL; for example, fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage21.png)

3. <span data-ttu-id="a4626-146">Перейдите к только что созданному ресурсу веб-приложения, щелкните **Параметры приложения** в левой области навигации.</span><span class="sxs-lookup"><span data-stu-id="a4626-146">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="a4626-147">В разделе Параметры приложения щелкните Добавить новый параметр и добавьте следующие три параметра: используйте значения (скопированные в текстовый файл из предыдущих шагов):</span><span class="sxs-lookup"><span data-stu-id="a4626-147">Under Application settings, click Add new setting and add the following three settings: Use the values (that you copied to the text file from the previous steps):</span></span> 

    <span data-ttu-id="a4626-148">– **Аписекреткэй** — в качестве секрета можно ввести любое значение.</span><span class="sxs-lookup"><span data-stu-id="a4626-148">– **APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="a4626-149">Он используется для доступа к веб-приложению Connector на шаге 7.</span><span class="sxs-lookup"><span data-stu-id="a4626-149">This is used to access the connector web app in Step 7.</span></span>

    <span data-ttu-id="a4626-150">– \* \* Сторажеаккаунтконнектионстринг — универсальный код ресурса (URI) строки подключения, скопированный после создания учетной записи хранилища Azure на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="a4626-150">– \*\*StorageAccountConnectionString — The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    <span data-ttu-id="a4626-151">– **tenantId** — идентификатор клиента организации Office 365, скопированный после создания приложения соединителя Facebook в Azure Active Directory в действии 2.</span><span class="sxs-lookup"><span data-stu-id="a4626-151">– **tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/FBCimage22.png)

4. <span data-ttu-id="a4626-152">В разделе **Общие параметры**нажмите **кнопку рядом с** параметром **Always On (включено**).</span><span class="sxs-lookup"><span data-stu-id="a4626-152">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="a4626-153">В верхней части страницы нажмите кнопку **сохранить** , чтобы сохранить параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="a4626-153">Click **Save** at the top of the page to save application settings.</span></span>

   ![](media/FBCimage23.png)

5. <span data-ttu-id="a4626-154">Последним шагом является отправка исходного кода приложения соединителя в Azure, который был загружен в действии 1.</span><span class="sxs-lookup"><span data-stu-id="a4626-154">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="a4626-155">В веб-браузере перейдите по адресу<AzureAppResourceName>https://. SCM.azurewebsites.NET/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="a4626-155">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="a4626-156">Например, если имя ресурса приложения Azure (с именем, указанным в шаге 2 в этом разделе) — **фбконнектор**, перейдите на https://fbconnector.scm.azurewebsites.net/ZipDeployUiстраницу.</span><span class="sxs-lookup"><span data-stu-id="a4626-156">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="a4626-157">Перетащите Самплеконнектор. zip (, скачанный на шаге 1) на эту страницу.</span><span class="sxs-lookup"><span data-stu-id="a4626-157">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="a4626-158">После отправки файлов и успешного развертывания страница будет выглядеть аналогично следующему снимку экрана:</span><span class="sxs-lookup"><span data-stu-id="a4626-158">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="a4626-159">Шаг 5: регистрация приложения Facebook</span><span class="sxs-lookup"><span data-stu-id="a4626-159">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="a4626-160">Перейдите к <https://developers.facebook.com>, войдите в систему, используя учетные данные для учетной записи для бизнес-страниц Facebook вашей организации, а затем щелкните **Добавить новое приложение**.</span><span class="sxs-lookup"><span data-stu-id="a4626-160">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![](media/FBCimage25.png)

2. <span data-ttu-id="a4626-161">Создайте идентификатор нового приложения.</span><span class="sxs-lookup"><span data-stu-id="a4626-161">Create a new app ID.</span></span>

   ![](media/FBCimage26.png)

3. <span data-ttu-id="a4626-162">В левой области навигации щелкните **Добавить продукты** , а затем — **Настройка** на плитке **входа Facebook** .</span><span class="sxs-lookup"><span data-stu-id="a4626-162">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![](media/FBCimage27.png)

4. <span data-ttu-id="a4626-163">На странице Интеграция входа в Facebook нажмите кнопку **веб**.</span><span class="sxs-lookup"><span data-stu-id="a4626-163">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![](media/FBCimage28.png)

5. <span data-ttu-id="a4626-164">Добавьте URL-адрес службы приложений Azure; например https://fbconnector.azurewebsites.net:.</span><span class="sxs-lookup"><span data-stu-id="a4626-164">Add the Azure app service URL; for example https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage29.png)

6. <span data-ttu-id="a4626-165">Заполните раздел Краткое руководство по настройке входа в Facebook.</span><span class="sxs-lookup"><span data-stu-id="a4626-165">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![](media/FBCimage30.png)

7. <span data-ttu-id="a4626-166">В левой области навигации в разделе **Login Facebook**щелкните **Параметры**, а затем добавьте URI перенаправления OAuth в поле **допустимые URI переадресации OAuth** .</span><span class="sxs-lookup"><span data-stu-id="a4626-166">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="a4626-167">Используйте формат \*\* \<коннекторсервицеури>/виевс/фацебукоаус\*\*, где значением коннекторсервицеури является URL-адрес службы приложений Azure для вашей организации; Пример: https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="a4626-167">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage31.png)

8. <span data-ttu-id="a4626-168">В левой области навигации щелкните **Добавить продукты** и выберите **веб-перехватчики.**</span><span class="sxs-lookup"><span data-stu-id="a4626-168">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="a4626-169">В раскрывающемся меню **Page (страница** ) выберите пункт **Page (страница**).</span><span class="sxs-lookup"><span data-stu-id="a4626-169">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![](media/FBCimage32.png)

9. <span data-ttu-id="a4626-170">Добавьте URL-адрес обратного вызова для веб-перехватчиков и добавьте маркер проверки.</span><span class="sxs-lookup"><span data-stu-id="a4626-170">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="a4626-171">Формат URL-адреса обратного вызова, используйте формат \*\* <connectorserviceuri>/АПИ/фбпажевебхук\*\*, где значение параметра коннекторсервицеури — это URL-адрес службы приложений Azure для вашей организации; например https://fbconnector.azurewebsites.net:.</span><span class="sxs-lookup"><span data-stu-id="a4626-171">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example https://fbconnector.azurewebsites.net.</span></span> 

    <span data-ttu-id="a4626-172">Маркер проверки должен быть похож на надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="a4626-172">The verify token should similar to a strong password.</span></span> <span data-ttu-id="a4626-173">Скопируйте токен проверки в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="a4626-173">Copy the verify token to a text file or other storage location.</span></span>

     ![](media/FBCimage33.png)

10. <span data-ttu-id="a4626-174">Протестируйте и подпишитесь на конечную точку для веб-канала.</span><span class="sxs-lookup"><span data-stu-id="a4626-174">Test and subscribe to the endpoint for feed.</span></span>

    ![](media/FBCimage34.png)

11. <span data-ttu-id="a4626-175">Добавьте URL-адрес конфиденциальности, значок приложения и использование для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a4626-175">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="a4626-176">Кроме того, скопируйте идентификатор приложения и секрет приложения в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="a4626-176">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![](media/FBCimage35.png)

12. <span data-ttu-id="a4626-177">Сделайте приложение общедоступным.</span><span class="sxs-lookup"><span data-stu-id="a4626-177">Make the app public.</span></span>

    ![](media/FBCimage36.png)

13. <span data-ttu-id="a4626-178">Добавьте пользователя к роли администратора или тестера.</span><span class="sxs-lookup"><span data-stu-id="a4626-178">Add user to the admin or tester role.</span></span>

    ![](media/FBCimage37.png)

14. <span data-ttu-id="a4626-179">Добавьте разрешение на **доступ к общему содержимому страницы** .</span><span class="sxs-lookup"><span data-stu-id="a4626-179">Add the **Page Public Content Access** permission.</span></span>

    ![](media/FBCimage38.png)

15. <span data-ttu-id="a4626-180">Разрешение "добавить Управление страницами".</span><span class="sxs-lookup"><span data-stu-id="a4626-180">Add Manage Pages permission.</span></span>

    ![](media/FBCimage39.png)

16. <span data-ttu-id="a4626-181">Получение приложения, проверенного Facebook.</span><span class="sxs-lookup"><span data-stu-id="a4626-181">Get the application reviewed by Facebook.</span></span>

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="a4626-182">Шаг 6: Настройка соединительного веб-приложения</span><span class="sxs-lookup"><span data-stu-id="a4626-182">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="a4626-183">Перейдите в раздел\<https://азуреаппресаурценаме>. azurewebsites.NET (где азуреаппресаурценаме — имя ресурса приложения Azure, имя которого указано в шаге 4) например, если имя — **фбконнектор**, перейдите на https://fbconnector.azurewebsites.netстраницу.</span><span class="sxs-lookup"><span data-stu-id="a4626-183">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to https://fbconnector.azurewebsites.net.</span></span> <span data-ttu-id="a4626-184">Домашняя страница приложения будет выглядеть, как на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="a4626-184">The home page of the app will look like the following screenshot:</span></span>


   ![](media/FBCimage41.png)

2. <span data-ttu-id="a4626-185">Нажмите кнопку **настроить** , чтобы отобразить страницу входа.</span><span class="sxs-lookup"><span data-stu-id="a4626-185">Click **Configure** to display a sign in page.</span></span>
 
   ![](media/FBCimage42.png)

3. <span data-ttu-id="a4626-186">В поле Идентификатор клиента введите или вставьте идентификатор клиента (полученный на шаге 2).</span><span class="sxs-lookup"><span data-stu-id="a4626-186">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="a4626-187">В поле Пароль введите или вставьте Аписекреткэй (полученное в действии 2), а затем нажмите кнопку **Настройка параметров конфигурации** , чтобы отобразить страницу **сведений о конфигурации** .</span><span class="sxs-lookup"><span data-stu-id="a4626-187">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![](media/FBCimage43.png)


4. <span data-ttu-id="a4626-188">В разделе **сведения о конфигурации**введите следующие параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a4626-188">Under **Configuration Details**, enter the following configuration settings</span></span> 

   <span data-ttu-id="a4626-189">– **Application ID Application ID** — идентификатор приложения для приложения Facebook, полученного в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="a4626-189">– **Facebook application ID** – The app ID for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="a4626-190">— **Секрет приложения Facebook** — секрет приложения для приложения Facebook, полученного в шаге 5.</span><span class="sxs-lookup"><span data-stu-id="a4626-190">– **Facebook application secret** – The app secret for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="a4626-191">— **Веб-перехватчики Facebook проверка маркера** — маркер проверки, созданный на шаге 5.</span><span class="sxs-lookup"><span data-stu-id="a4626-191">– **Facebook webhooks verify token** – The verify token that you created in Step 5.</span></span>
   <span data-ttu-id="a4626-192">— **Идентификатор приложения AAD** — идентификатор приложения для приложения Azure Active Directory, созданного в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="a4626-192">– **AAD application ID** – The application ID for the Azure Active Directory app that you created in Step 2.</span></span>
   <span data-ttu-id="a4626-193">— **Секрет приложения AAD** — значение для секрета аписекреткэй, созданного на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="a4626-193">– **AAD application secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   <span data-ttu-id="a4626-194">— **URI приложения AAD** — URI приложения AAD, полученный в шаге 2; Пример: https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span><span class="sxs-lookup"><span data-stu-id="a4626-194">– **AAD application Uri** – The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   <span data-ttu-id="a4626-195">— **Ключ инструментирования Application Insights** — оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="a4626-195">– **App insights instrumentation key** – Leave this box blank.</span></span>

5. <span data-ttu-id="a4626-196">Нажмите кнопку **сохранить** , чтобы сохранить параметры соединителя.</span><span class="sxs-lookup"><span data-stu-id="a4626-196">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="a4626-197">Шаг 7: Настройка настраиваемого соединителя в центре безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a4626-197">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="a4626-198">Перейдите в <https://protection.office.com> раздел **Управление \> данными и выберите пункт \> архивы импорта данных сторонних поставщиков**.</span><span class="sxs-lookup"><span data-stu-id="a4626-198">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

   ![](media/FBCimage44.png)

2.  <span data-ttu-id="a4626-199">Нажмите кнопку **Добавить соединитель** , а затем выберите **страницы Facebook**.</span><span class="sxs-lookup"><span data-stu-id="a4626-199">Click **Add a connector** and then click **Facebook pages**.</span></span>

    ![](media/FBCimage46.png)

3.  <span data-ttu-id="a4626-200">На странице **Добавление приложения соединителя** введите следующие сведения и нажмите кнопку **проверить соединитель**.</span><span class="sxs-lookup"><span data-stu-id="a4626-200">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    <span data-ttu-id="a4626-201">— В первом поле введите имя соединителя, например **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="a4626-201">– In the first box, type a name for the connector, such as **Facebook**.</span></span>
    <span data-ttu-id="a4626-202">— Во втором поле введите или вставьте значение Аписекреткэй, добавленное на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="a4626-202">– In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    <span data-ttu-id="a4626-203">— В третьем поле введите или вставьте URL-адрес службы приложений Azure; например **https://fbconnector.azurewebsites.net**:.</span><span class="sxs-lookup"><span data-stu-id="a4626-203">– In the third box, type or paste the Azure app service URL; for example **https://fbconnector.azurewebsites.net**.</span></span>
 
    <span data-ttu-id="a4626-204">После успешной проверки соединителя нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4626-204">After the connector is successfully validated, click **Next**.</span></span>
    
    ![](media/FBCimage47.png)

4.  <span data-ttu-id="a4626-205">Щелкните **имя входа с приложением Connector Connector**.</span><span class="sxs-lookup"><span data-stu-id="a4626-205">Click **Login with Connector App**.</span></span>

    ![](media/FBCimage45.png)

5. <span data-ttu-id="a4626-206">Введите или вставьте Аписекреткэй еще раз, а затем щелкните **Вход в службу соединителя**.</span><span class="sxs-lookup"><span data-stu-id="a4626-206">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/FBCimage48.png)


6. <span data-ttu-id="a4626-207">Выберите **Вход с помощью Facebook.**</span><span class="sxs-lookup"><span data-stu-id="a4626-207">Click **Login with Facebook.**</span></span>

   ![](media/FBCimage49.png)

7. <span data-ttu-id="a4626-208">На странице **Вход в Facebook** Войдите в систему, используя учетные данные для учетной записи для бизнес-страниц Facebook вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a4626-208">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="a4626-209">Убедитесь, что учетной записи Facebook, в которую вы выполнили вход, назначена роль администратора для бизнес-страниц Facebook Организации.</span><span class="sxs-lookup"><span data-stu-id="a4626-209">Make sure the Facebook account that you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![](media/FBCimage50.png)

8. <span data-ttu-id="a4626-210">Нажмите кнопку **Выбор страниц** , чтобы выбрать деловые страницы Организации, которые нужно архивировать в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4626-210">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![](media/FBCimage51.png)

9. <span data-ttu-id="a4626-211">Отображается список бизнес-страниц, управляемых учетной записью Facebook, в которой выполнен вход.</span><span class="sxs-lookup"><span data-stu-id="a4626-211">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="a4626-212">Выберите страницу для архивации и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a4626-212">Select the page to archive and then click **Save**.</span></span>

    ![](media/FBCimage52.png)

10. <span data-ttu-id="a4626-213">Нажмите кнопку **подготовить** , чтобы выйти из программы установки приложения службы соединителя.</span><span class="sxs-lookup"><span data-stu-id="a4626-213">Click **prepare** to exit the setup of the connector service app.</span></span>

    ![](media/FBCimage53.png)

11. <span data-ttu-id="a4626-214">На странице " **Настройка фильтров** " можно применить фильтр для импорта (и архивирования) элементов с определенным сроком хранения.</span><span class="sxs-lookup"><span data-stu-id="a4626-214">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="a4626-215">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a4626-215">Click **Next**.</span></span>

    ![](media/FBCimage54.png)

12. <span data-ttu-id="a4626-216">На странице " **Настройка учетной записи хранения** " выберите почтовый ящик Office 365, в который будут импортированы элементы из ранее выбранных страниц Facebook бизнес-страниц.</span><span class="sxs-lookup"><span data-stu-id="a4626-216">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![](media/FBCimage55.png)

13. <span data-ttu-id="a4626-217">Проверьте параметры и нажмите кнопку **Готово** , чтобы завершить настройку соединителя в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a4626-217">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/FBCimage56.png)

14. <span data-ttu-id="a4626-218">Перейдите на страницу **архивации сторонних данных** , чтобы просмотреть ход процесса импорта.</span><span class="sxs-lookup"><span data-stu-id="a4626-218">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/FBCimage58.png)
