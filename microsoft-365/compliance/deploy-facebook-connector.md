---
title: Развертывание соединителя для архивации данных бизнес-страниц Facebook
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
description: Администраторы могут настроить собственный соединитель для импорта и архивации бизнес-страниц Facebook в Microsoft 365. После импорта этих данных в Microsoft 365 вы можете использовать такие функции обеспечения соответствия, как судебное удержание, поиск контента и политики хранения, для управления управлением данными Facebook Организации.
ms.openlocfilehash: 065a5c6a1276c1ce37aa48137caf6627e76c8db0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200864"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="a30d5-104">Развертывание соединителя для архивации данных бизнес-страниц Facebook</span><span class="sxs-lookup"><span data-stu-id="a30d5-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="a30d5-105">В этой статье представлено пошаговое руководство по развертыванию соединителя, использующего службу импорта Office 365 для импорта данных из бизнес-страниц Facebook в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a30d5-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="a30d5-106">Общий обзор этого процесса и список необходимых компонентов, необходимых для развертывания соединителя Facebook, приведены в разделе [Настройка соединителя для архивации данных Facebook](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a30d5-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="a30d5-107">Шаг 1: создание приложения в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a30d5-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="a30d5-108">Перейдите на страницу <https://portal.azure.com> и войдите, используя учетные данные глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="a30d5-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![Создание приложения в AAD](../media/FBCimage1.png)

2. <span data-ttu-id="a30d5-110">В области навигации слева выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Выберите Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="a30d5-112">В левой области навигации щелкните **Регистрация приложений (Предварительная версия)** , а затем нажмите кнопку **создать регистрацию**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Выберите \* \* регистрации приложений (Предварительная версия) \* \* и нажмите \* \* Новая регистрация \* \*](../media/FBCimage3.png)

4. <span data-ttu-id="a30d5-114">Зарегистрируйте приложение.</span><span class="sxs-lookup"><span data-stu-id="a30d5-114">Register the application.</span></span> <span data-ttu-id="a30d5-115">В разделе URI перенаправления выберите пункт веб-сайт в раскрывающемся списке Тип приложения, а затем введите <https://portal.azure.com> в поле для URI.</span><span class="sxs-lookup"><span data-stu-id="a30d5-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Регистрация приложения](../media/FBCimage4.png)

5. <span data-ttu-id="a30d5-117">Скопируйте идентификатор **приложения (идентификатор клиента)** и **идентификатор каталога (клиента)** и сохраните их в текстовый файл или другое надежное расположение.</span><span class="sxs-lookup"><span data-stu-id="a30d5-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="a30d5-118">Эти идентификаторы используются на последующих этапах.</span><span class="sxs-lookup"><span data-stu-id="a30d5-118">You use these IDs in later steps.</span></span>

   ![Скопируйте идентификатор приложения и идентификатор каталога и сохраните их](../media/FBCimage5.png)

6. <span data-ttu-id="a30d5-120">Перейдите к разделу **сертификаты & секреты для нового приложения.**</span><span class="sxs-lookup"><span data-stu-id="a30d5-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Перейти к сертификатам & секреты для нового приложения](../media/FBCimage6.png)

7. <span data-ttu-id="a30d5-122">Щелкните **новый секрет клиента**</span><span class="sxs-lookup"><span data-stu-id="a30d5-122">Click **New client secret**</span></span>

   ![Щелкните новый секрет клиента](../media/FBCimage7.png)

8. <span data-ttu-id="a30d5-124">Создайте новый секрет.</span><span class="sxs-lookup"><span data-stu-id="a30d5-124">Create a new secret.</span></span> <span data-ttu-id="a30d5-125">В поле Описание введите секрет, а затем выберите срок действия.</span><span class="sxs-lookup"><span data-stu-id="a30d5-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![Введите секрет, а затем выберите срок действия](../media/FBCimage8.png)

9. <span data-ttu-id="a30d5-127">Скопируйте значение секрета и сохраните его в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="a30d5-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="a30d5-128">Это секрет приложения AAD, который вы используете в дальнейших действиях.</span><span class="sxs-lookup"><span data-stu-id="a30d5-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Скопируйте значение секрета и сохраните его](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="a30d5-130">Шаг 2: разверните веб-службу соединителя из GitHub в учетную запись Azure.</span><span class="sxs-lookup"><span data-stu-id="a30d5-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="a30d5-131">Перейдите на [этот сайт GitHub](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) и нажмите кнопку **развернуть в Azure**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Нажмите кнопку развернуть в Azure.](../media/FBCGithubApp.png)

2. <span data-ttu-id="a30d5-133">После нажатия кнопки **развернуть в Azure**вы будете перенаправлены на портал Azure с настраиваемой страницей шаблона.</span><span class="sxs-lookup"><span data-stu-id="a30d5-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="a30d5-134">Заполните сведения о **основных** **параметрах и параметрах** , а затем щелкните **купить**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="a30d5-135">**Подписка:** Выберите свою подписку на Azure, в которую вы хотите развернуть веб-службу соединителя для бизнес-страниц Facebook.</span><span class="sxs-lookup"><span data-stu-id="a30d5-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="a30d5-136">**Группа ресурсов:** Выберите или создайте новую группу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a30d5-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="a30d5-137">Группа ресурсов — это контейнер, в котором хранятся связанные ресурсы для решения Azure.</span><span class="sxs-lookup"><span data-stu-id="a30d5-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="a30d5-138">**Расположение:** Выберите расположение.</span><span class="sxs-lookup"><span data-stu-id="a30d5-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="a30d5-139">**Имя веб-приложения:** Укажите уникальное имя для веб-приложения соединителя.</span><span class="sxs-lookup"><span data-stu-id="a30d5-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="a30d5-140">Длина имени должна составлять от 3 до 18 символов.</span><span class="sxs-lookup"><span data-stu-id="a30d5-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="a30d5-141">Это имя используется для создания URL-адреса службы приложений Azure; Например, если указать имя веб-приложения **фбконнектор** , URL-адрес службы приложений Azure будет **fbconnector.azurewebsites.NET**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="a30d5-142">**tenantId:** Идентификатор клиента вашей организации Microsoft 365, который вы скопировали после создания приложения соединителя Facebook в Azure Active Directory на этапе 1.</span><span class="sxs-lookup"><span data-stu-id="a30d5-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="a30d5-143">**Аписекреткэй:** В качестве секрета можно ввести любое значение.</span><span class="sxs-lookup"><span data-stu-id="a30d5-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="a30d5-144">Он используется для доступа к веб-приложению Connector в действии 5.</span><span class="sxs-lookup"><span data-stu-id="a30d5-144">This is used to access the connector web app in Step 5.</span></span>

     ![Нажмите кнопку Создать ресурс и введите учетную запись хранения.](../media/FBCimage12.png)

3. <span data-ttu-id="a30d5-146">После успешного развертывания страница будет выглядеть примерно так, как показано на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="a30d5-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Щелкните хранилище, а затем выберите Учетная запись хранилища.](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="a30d5-148">Шаг 3: регистрация приложения Facebook</span><span class="sxs-lookup"><span data-stu-id="a30d5-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="a30d5-149">Перейдите к <https://developers.facebook.com> , войдите в систему, используя учетные данные для учетной записи для бизнес-страниц Facebook вашей организации, а затем щелкните **Добавить новое приложение**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Добавление новой веб-страницы приложения для Facebook](../media/FBCimage25.png)

2. <span data-ttu-id="a30d5-151">Создайте идентификатор нового приложения.</span><span class="sxs-lookup"><span data-stu-id="a30d5-151">Create a new app ID.</span></span>

   ![Создание идентификатора нового приложения](../media/FBCimage26.png)

3. <span data-ttu-id="a30d5-153">В левой области навигации щелкните **Добавить продукты** , а затем — **Настройка** на плитке **входа Facebook** .</span><span class="sxs-lookup"><span data-stu-id="a30d5-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Нажмите кнопку "добавить продукты"](../media/FBCimage27.png)

4. <span data-ttu-id="a30d5-155">На странице Интеграция входа в Facebook нажмите кнопку **веб**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Нажмите кнопку "веб-сайт" на странице интеграция Facebook login](../media/FBCimage28.png)

5. <span data-ttu-id="a30d5-157">Добавьте URL-адрес службы приложений Azure; например `https://fbconnector.azurewebsites.net` :.</span><span class="sxs-lookup"><span data-stu-id="a30d5-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Добавление URL-адреса службы приложений Azure](../media/FBCimage29.png)

6. <span data-ttu-id="a30d5-159">Заполните раздел Краткое руководство по настройке входа в Facebook.</span><span class="sxs-lookup"><span data-stu-id="a30d5-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Выполнение раздела "Быстрый запуск"](../media/FBCimage30.png)

7. <span data-ttu-id="a30d5-161">В левой области навигации в разделе **Login Facebook**щелкните **Параметры**, а затем добавьте URI перенаправления OAuth в поле **допустимые URI переадресации OAuth** .</span><span class="sxs-lookup"><span data-stu-id="a30d5-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="a30d5-162">Используйте формат \*\* \<connectorserviceuri> /виевс/фацебукоаус\*\*, где значение параметра коннекторсервицеури — это URL-адрес службы приложений Azure для вашей организации; например, `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="a30d5-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Добавление URI перенаправления OAuth в допустимое поле URI перенаправления OAuth](../media/FBCimage31.png)

8. <span data-ttu-id="a30d5-164">В левой области навигации щелкните **Добавить продукты** и выберите **веб-перехватчики.**</span><span class="sxs-lookup"><span data-stu-id="a30d5-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="a30d5-165">В раскрывающемся меню **Page (страница** ) выберите пункт **Page (страница**).</span><span class="sxs-lookup"><span data-stu-id="a30d5-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![Щелкните Добавить продукты и выберите \* \* веб-перехватчики](../media/FBCimage32.png)

9. <span data-ttu-id="a30d5-167">Добавьте URL-адрес обратного вызова для веб-перехватчиков и добавьте маркер проверки.</span><span class="sxs-lookup"><span data-stu-id="a30d5-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="a30d5-168">Формат URL-адреса обратного вызова, используйте формат \*\* <connectorserviceuri> /АПИ/фбпажевебхук\*\*, где значение параметра коннекторсервицеури — это URL-адрес службы приложений Azure для вашей организации; например `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="a30d5-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="a30d5-169">Маркер проверки должен быть похож на надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="a30d5-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="a30d5-170">Скопируйте токен проверки в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="a30d5-170">Copy the verify token to a text file or other storage location.</span></span>

   ![Добавление токена проверки](../media/FBCimage33.png)

10. <span data-ttu-id="a30d5-172">Протестируйте и подпишитесь на конечную точку для веб-канала.</span><span class="sxs-lookup"><span data-stu-id="a30d5-172">Test and subscribe to the endpoint for feed.</span></span>

    ![Тестирование конечной точки и подписка на нее](../media/FBCimage34.png)

11. <span data-ttu-id="a30d5-174">Добавьте URL-адрес конфиденциальности, значок приложения и использование для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a30d5-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="a30d5-175">Кроме того, скопируйте идентификатор приложения и секрет приложения в текстовый файл или другое место хранения.</span><span class="sxs-lookup"><span data-stu-id="a30d5-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Добавление URL-адреса конфиденциальности, значка приложения и использования для бизнеса](../media/FBCimage35.png)

12. <span data-ttu-id="a30d5-177">Сделайте приложение общедоступным.</span><span class="sxs-lookup"><span data-stu-id="a30d5-177">Make the app public.</span></span>

    ![Сделайте приложение общедоступным](../media/FBCimage36.png)

13. <span data-ttu-id="a30d5-179">Добавьте пользователя к роли администратора или тестера.</span><span class="sxs-lookup"><span data-stu-id="a30d5-179">Add user to the admin or tester role.</span></span>

    ![Добавление пользователя к роли администратора или тестера](../media/FBCimage37.png)

14. <span data-ttu-id="a30d5-181">Добавьте разрешение на **доступ к общему содержимому страницы** .</span><span class="sxs-lookup"><span data-stu-id="a30d5-181">Add the **Page Public Content Access** permission.</span></span>

    ![DD разрешение на доступ к общедоступному содержимому страницы](../media/FBCimage38.png)

15. <span data-ttu-id="a30d5-183">Разрешение "добавить Управление страницами".</span><span class="sxs-lookup"><span data-stu-id="a30d5-183">Add Manage Pages permission.</span></span>

    ![Разрешение "Добавление страниц управления"](../media/FBCimage39.png)

16. <span data-ttu-id="a30d5-185">Получение приложения, проверенного Facebook.</span><span class="sxs-lookup"><span data-stu-id="a30d5-185">Get the application reviewed by Facebook.</span></span>

    ![Получение приложения, проверенного с помощью Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="a30d5-187">Шаг 4: Настройка веб-приложения соединителя</span><span class="sxs-lookup"><span data-stu-id="a30d5-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="a30d5-188">Перейдите к разделу `https://<AzureAppResourceName>.azurewebsites.net` (где азуреаппресаурценаме — имя ресурса приложения Azure, имя которого указано в шаге 4).</span><span class="sxs-lookup"><span data-stu-id="a30d5-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="a30d5-189">Например, если имя — **фбконнектор**, перейдите на страницу `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="a30d5-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="a30d5-190">Домашняя страница приложения будет выглядеть, как на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="a30d5-190">The home page of the app will look like the following screenshot:</span></span>

   ![Перейдите в веб-приложение Connector Connector.](../media/FBCimage41.png)

2. <span data-ttu-id="a30d5-192">Нажмите кнопку **настроить** , чтобы отобразить страницу входа.</span><span class="sxs-lookup"><span data-stu-id="a30d5-192">Click **Configure** to display a sign in page.</span></span>

   ![Нажмите кнопку Настройка, чтобы отобразить страницу входа](../media/FBCimage42.png)

3. <span data-ttu-id="a30d5-194">В поле Идентификатор клиента введите или вставьте идентификатор клиента (полученный на шаге 2).</span><span class="sxs-lookup"><span data-stu-id="a30d5-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="a30d5-195">В поле Пароль введите или вставьте Аписекреткэй (полученное в действии 2), а затем нажмите кнопку **Настройка параметров конфигурации** , чтобы отобразить страницу сведений о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a30d5-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Вход с использованием идентификатора и пароля клиента и переход на страницу сведений о конфигурации](../media/FBCimage43.png)

4. <span data-ttu-id="a30d5-197">Введите следующие параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="a30d5-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="a30d5-198">**Идентификатор приложения Facebook:** Идентификатор приложения для приложения Facebook, полученного на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="a30d5-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="a30d5-199">**Секрет приложения Facebook:** Секрет приложения для приложения Facebook, полученного на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="a30d5-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="a30d5-200">**Веб-перехватчики Facebook проверьте маркер:** Токен проверки, созданный на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="a30d5-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="a30d5-201">**Идентификатор приложения AAD:** Идентификатор приложения для приложения Azure Active Directory, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="a30d5-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="a30d5-202">**Секрет приложения AAD:** Значение секрета Аписекреткэй, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="a30d5-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="a30d5-203">Нажмите кнопку **сохранить** , чтобы сохранить параметры соединителя.</span><span class="sxs-lookup"><span data-stu-id="a30d5-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="a30d5-204">Шаг 5: Настройка соединителя Facebook в центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a30d5-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="a30d5-205">[https://compliance.microsoft.com](https://compliance.microsoft.com)В левой панели навигации выберите элемент **соединители данных и нажмите кнопку соединители данных** .</span><span class="sxs-lookup"><span data-stu-id="a30d5-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="a30d5-206">На странице " **соединители данных** " в разделе **Facebook Business Pages**нажмите кнопку **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="a30d5-207">На странице **Facebook Business Pages** (добавить соединитель) нажмите кнопку **Добавить соединитель**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="a30d5-208">На странице **условия обслуживания** нажмите кнопку **принять**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="a30d5-209">На странице " **Добавление учетных данных для приложения соединителя** " введите следующие сведения и нажмите кнопку **проверить подключение**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Введите учетные данные приложения соединителя](../media/TCimage38.png)

   - <span data-ttu-id="a30d5-211">В поле **имя** введите имя соединителя, например **Страница новостей Facebook**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="a30d5-212">В поле **URL-адрес подключения** введите или вставьте URL-адрес службы приложений Azure; например `https://fbconnector.azurewebsites.net` :.</span><span class="sxs-lookup"><span data-stu-id="a30d5-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="a30d5-213">В поле **пароль** введите или вставьте значение аписекреткэй, добавленное на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="a30d5-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="a30d5-214">В поле **идентификатор приложения Azure** введите или вставьте значение идентификатора приложения (клиента), который также называется идентификатором приложения AAD, созданным на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="a30d5-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="a30d5-215">После успешной проверки подключения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="a30d5-216">На странице **авторизовать Microsoft 365 to Import Data (разрешить Microsoft** ) введите или вставьте аписекреткэй еще раз, а затем нажмите кнопку **Login Web App**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="a30d5-217">На странице " **Настройка приложения соединителя Facebook Connector** " щелкните **Вход с Facebook** и войдите в систему, используя учетные данные для учетной записи для бизнес-страниц Facebook Организации.</span><span class="sxs-lookup"><span data-stu-id="a30d5-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="a30d5-218">Убедитесь, что учетной записи Facebook, в которую вы вошли в систему, назначена роль администратора для бизнес-страниц Facebook вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a30d5-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Вход с помощью Facebook](../media/FBCimage50.png)

9. <span data-ttu-id="a30d5-220">Отображается список бизнес-страниц, управляемых учетной записью Facebook, в которой выполнен вход.</span><span class="sxs-lookup"><span data-stu-id="a30d5-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="a30d5-221">Выберите страницу для архивации и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-221">Select the page to archive and then click **Next**.</span></span>

   ![Выберите бизнес-страницу Организации, которую нужно архивировать](../media/FBCimage52.png)

10. <span data-ttu-id="a30d5-223">Нажмите кнопку **продолжить** , чтобы выйти из программы установки приложения службы соединителя.</span><span class="sxs-lookup"><span data-stu-id="a30d5-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="a30d5-224">На странице " **Настройка фильтров** " можно применить фильтр для начального импорта элементов с определенным сроком хранения.</span><span class="sxs-lookup"><span data-stu-id="a30d5-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="a30d5-225">Выберите возраст, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="a30d5-226">На странице **Выбор места хранения** введите адрес электронной почты почтового ящика Microsoft 365, в который будут импортированы элементы Facebook, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a30d5-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="a30d5-227">На странице **предоставление разрешений администратора**щелкните **предоставить согласие** и следуйте инструкциям.</span><span class="sxs-lookup"><span data-stu-id="a30d5-227">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="a30d5-228">Вы должны быть глобальным администратором, чтобы предоставить разрешение службе импорта Office 365 для доступа к данным в Организации.</span><span class="sxs-lookup"><span data-stu-id="a30d5-228">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="a30d5-229">Нажмите кнопку **Далее** , чтобы проверить параметры соединителя, а затем нажмите кнопку **Готово** , чтобы завершить настройку соединителя.</span><span class="sxs-lookup"><span data-stu-id="a30d5-229">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="a30d5-230">В центре соответствия требованиям откройте страницу " **соединители данных** " и перейдите на вкладку **соединители** , чтобы просмотреть ход процесса импорта.</span><span class="sxs-lookup"><span data-stu-id="a30d5-230">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
