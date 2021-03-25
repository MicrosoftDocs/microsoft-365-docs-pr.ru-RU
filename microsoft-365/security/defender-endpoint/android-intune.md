---
title: Развертывание ATP защитника Майкрософт для Android с помощью Microsoft Intune
description: Описание развертывания ATP Microsoft Defender для Android с помощью Microsoft Intune
keywords: Microsoft, defender, atp, android, installation, deploy, uninstallation,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e557f60346b2f68354df621b6e4812eac775d812
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165673"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-android-with-microsoft-intune"></a><span data-ttu-id="06207-104">Развертывание Microsoft Defender для конечной точки для Android с помощью Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="06207-104">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="06207-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="06207-105">**Applies to:**</span></span>
- [<span data-ttu-id="06207-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="06207-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="06207-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06207-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="06207-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="06207-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="06207-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="06207-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="06207-110">Узнайте, как развернуть устройства Для Конечной точки Defender для Android на зарегистрированных устройствах портала компаний Intune.</span><span class="sxs-lookup"><span data-stu-id="06207-110">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="06207-111">Дополнительные сведения о регистрации устройств Intune см. в [записи устройства.](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)</span><span class="sxs-lookup"><span data-stu-id="06207-111">For more information about Intune device enrollment, see  [Enroll your device](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="06207-112">**Защитник для конечной точки для Android теперь доступен в [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="06207-112">**Defender for Endpoint for Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="06207-113">Вы можете подключиться к Google Play из Intune, чтобы развернуть приложение Defender for Endpoint в режимах entrollment администратора устройств и Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="06207-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="06207-114">Обновления приложения автоматически обновляются с помощью Google Play.</span><span class="sxs-lookup"><span data-stu-id="06207-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="06207-115">Развертывание на зарегистрированных устройствах администратора устройств</span><span class="sxs-lookup"><span data-stu-id="06207-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="06207-116">**Развертывание Defender для конечной точки для Android на портале компании Intune — устройства администратора устройств**</span><span class="sxs-lookup"><span data-stu-id="06207-116">**Deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="06207-117">Узнайте, как развернуть устройства Defender для конечной точки для Android на портале компании Intune — устройства администратора устройств.</span><span class="sxs-lookup"><span data-stu-id="06207-117">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="06207-118">Добавление приложения в магазине Android</span><span class="sxs-lookup"><span data-stu-id="06207-118">Add as Android store app</span></span>

1. <span data-ttu-id="06207-119">В [центре администрирования Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) перейдите в приложения **Android** \> **Apps** Add Android Store \> **\> app** и выберите **Выберите .**</span><span class="sxs-lookup"><span data-stu-id="06207-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Изображение Центра администрирования конечной точки Microsoft Endpoint Manager добавить приложение магазина Android](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="06207-121">На странице **Добавление приложения** и в разделе Сведения *о приложении* введите:</span><span class="sxs-lookup"><span data-stu-id="06207-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="06207-122">**Название**</span><span class="sxs-lookup"><span data-stu-id="06207-122">**Name**</span></span> 
   - <span data-ttu-id="06207-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="06207-123">**Description**</span></span>
   - <span data-ttu-id="06207-124">**Издатель** в качестве Microsoft.</span><span class="sxs-lookup"><span data-stu-id="06207-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="06207-125">**URL-адрес магазина приложений** как (URL-адрес магазина https://play.google.com/store/apps/details?id=com.microsoft.scmx Приложений Для конечной точки в Google Play Store)</span><span class="sxs-lookup"><span data-stu-id="06207-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="06207-126">Другие поля необязательны.</span><span class="sxs-lookup"><span data-stu-id="06207-126">Other fields are optional.</span></span> <span data-ttu-id="06207-127">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="06207-127">Select **Next**.</span></span>

   ![Изображение Центра администрирования конечных точек Microsoft Endpoint Manager добавить сведения о приложениях](images/mda-addappinfo.png)

3. <span data-ttu-id="06207-129">В разделе *Назначения* перейдите в **необходимый** раздел и выберите **группу Добавить.**</span><span class="sxs-lookup"><span data-stu-id="06207-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="06207-130">Затем вы можете выбрать группу пользователей, которую вы хотите использовать для приложения Defender для конечной точки для Android.</span><span class="sxs-lookup"><span data-stu-id="06207-130">You can then choose the user group(s) that you would like to target Defender for Endpoint for Android app.</span></span> <span data-ttu-id="06207-131">Выберите **Выберите и** затем **далее**.</span><span class="sxs-lookup"><span data-stu-id="06207-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="06207-132">Выбранная группа пользователей должна состоять из зарегистрированных пользователей Intune.</span><span class="sxs-lookup"><span data-stu-id="06207-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![Изображение центра администрирования конечной точки Майкрософт для администратора конечных точек выбранных групп пользователей](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="06207-134">В разделе **Обзор+Создание** убедитесь, что вся введенная информация является правильной, а затем выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="06207-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="06207-135">Через несколько минут приложение Defender for Endpoint будет создано успешно, и уведомление будет показываться в правом верхнем углу страницы.</span><span class="sxs-lookup"><span data-stu-id="06207-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Изображение уведомления центра администрирования конечной точки Microsoft Endpoint Manager о приложении конечной точки защитника](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="06207-137">На странице информации о приложении, отображаемой  в разделе **Monitor,** выберите состояние установки устройства, чтобы убедиться, что установка устройства успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="06207-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06207-138">![Изображение установки устройства Центра администрирования конечных точек Microsoft Endpoint Manager](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="06207-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="06207-139">Полное состояние onboarding и проверки</span><span class="sxs-lookup"><span data-stu-id="06207-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="06207-140">После установки защитника для конечной точки для Android на устройстве вы увидите значок приложения.</span><span class="sxs-lookup"><span data-stu-id="06207-140">Once Defender for Endpoint for Android has been installed on the device, you'll see the app icon.</span></span>

    ![Значок на мобильном устройстве](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="06207-142">Нажмите значок приложения ATP Защитника Майкрософт и выполните инструкции на экране для завершения работы над приложением.</span><span class="sxs-lookup"><span data-stu-id="06207-142">Tap the Microsoft Defender ATP app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="06207-143">Подробные сведения включают принятие конечным пользователем разрешений на Android, необходимых Defender для конечной точки для Android.</span><span class="sxs-lookup"><span data-stu-id="06207-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint for Android.</span></span>

3. <span data-ttu-id="06207-144">После успешного взбора устройство начнет появляться в списке Устройств в Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="06207-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Изображение устройства на портале Defender for Endpoint](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="06207-146">Развертывание на устройствах, зарегистрированных на Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="06207-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="06207-147">Defender for Endpoint для Android поддерживает зарегистрированные устройства Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="06207-147">Defender for Endpoint for Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="06207-148">Дополнительные сведения о вариантах регистрации, поддерживаемых Intune, см. в дополнительных [сведениях о параметрах регистрации.](https://docs.microsoft.com/mem/intune/enrollment/android-enroll)</span><span class="sxs-lookup"><span data-stu-id="06207-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="06207-149">**В настоящее время для развертывания поддерживаются лично управляемые устройства с профилем работы и полностью управляемыми пользовательскими устройствами.**</span><span class="sxs-lookup"><span data-stu-id="06207-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-for-android-as-a-managed-google-play-app"></a><span data-ttu-id="06207-150">Добавление Microsoft Defender для конечной точки для Android в качестве управляемого приложения Google Play</span><span class="sxs-lookup"><span data-stu-id="06207-150">Add Microsoft Defender for Endpoint for Android as a Managed Google Play app</span></span>

<span data-ttu-id="06207-151">Выполните ниже шаги, чтобы добавить приложение Microsoft Defender для конечной точки в управляемое приложение Google Play.</span><span class="sxs-lookup"><span data-stu-id="06207-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="06207-152">В [центре администрирования Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) перейдите в приложения **Android** \> **Apps** \> **Add** и выберите **управляемое приложение Google Play.**</span><span class="sxs-lookup"><span data-stu-id="06207-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06207-153">![Изображение центра администрирования microsoft Endpoint Manager управляемый Google play](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="06207-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="06207-154">На управляемой странице Google Play, загружаемой впоследствии, перейдите в поле поиска и посмотрите **microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="06207-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="06207-155">В вашем поиске должно отображаться приложение Microsoft Defender для конечной точки в управляемом Google Play.</span><span class="sxs-lookup"><span data-stu-id="06207-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="06207-156">Щелкните приложение Microsoft Defender для конечной точки из результата поиска Приложений.</span><span class="sxs-lookup"><span data-stu-id="06207-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Изображение поиска приложений центра администрирования microsoft Endpoint Manager](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="06207-158">На следующей странице описания приложения можно увидеть сведения о приложении в Защитнике для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="06207-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="06207-159">Просмотрите сведения на странице и выберите **Утверждение**.</span><span class="sxs-lookup"><span data-stu-id="06207-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06207-160">![Снимок экрана управляемой игры в Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="06207-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="06207-161">Вам будут представлены разрешения, которые защитник для конечной точки получает для работы.</span><span class="sxs-lookup"><span data-stu-id="06207-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="06207-162">Просмотрите их и выберите **Утверждение**.</span><span class="sxs-lookup"><span data-stu-id="06207-162">Review them and then select **Approve**.</span></span>

    ![Снимок экрана утверждения приложения предварительного просмотра Defender для конечной точки](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="06207-164">Вам будет представлена страница Параметры утверждения.</span><span class="sxs-lookup"><span data-stu-id="06207-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="06207-165">Страница подтверждает ваше предпочтение обработки разрешений на новые приложения, которые может спросить Defender for Endpoint для Android.</span><span class="sxs-lookup"><span data-stu-id="06207-165">The page confirms your preference to handle new app permissions that Defender for Endpoint for Android might ask.</span></span> <span data-ttu-id="06207-166">Просмотрите выбор и выберите предпочтительный вариант.</span><span class="sxs-lookup"><span data-stu-id="06207-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="06207-167">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="06207-167">Select **Done**.</span></span>

    <span data-ttu-id="06207-168">По умолчанию управляемый Google Play выбирает *Keep approved, когда приложение запрашивает новые разрешения.*</span><span class="sxs-lookup"><span data-stu-id="06207-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06207-169">![Изображение вкладки уведомлений](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="06207-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="06207-170">После выбора обработки разрешений выберите **Синхронизация,** чтобы синхронизировать Microsoft Defender для конечной точки в списке приложений.</span><span class="sxs-lookup"><span data-stu-id="06207-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06207-171">![Изображение страницы синхронизации](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="06207-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="06207-172">Синхронизация завершится через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="06207-172">The sync will complete in a few minutes.</span></span>

    ![Изображение приложения Android](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="06207-174">Выберите **кнопку Обновить** на экране приложений Android, а в списке приложений должна быть видна atP Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="06207-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender ATP should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06207-175">![Изображение списка приложений для Android](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="06207-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="06207-176">Defender for Endpoint поддерживает политики конфигурации приложений для управляемых устройств с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="06207-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="06207-177">Эту возможность можно использовать для автоматического использования применимых разрешений на Android(ы), поэтому конечный пользователь не должен принимать эти разрешения(ы).</span><span class="sxs-lookup"><span data-stu-id="06207-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="06207-178">На странице **Apps** перейдите к политикам > политики конфигурации приложений > **добавить > управляемые устройства.**</span><span class="sxs-lookup"><span data-stu-id="06207-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Изображение управляемых android-устройств центра администрирования Microsoft Endpoint Manager](images/android-mem.png)

    1. <span data-ttu-id="06207-180">На странице **Создание политики конфигурации приложений** введите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="06207-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="06207-181">Имя: ATP Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="06207-181">Name: Microsoft Defender ATP.</span></span>
        - <span data-ttu-id="06207-182">Выберите **Android Enterprise в** качестве платформы.</span><span class="sxs-lookup"><span data-stu-id="06207-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="06207-183">Выберите **профиль работы только** в виде типа профиля.</span><span class="sxs-lookup"><span data-stu-id="06207-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="06207-184">Щелкните **Выберите приложение,** выберите **ATP Защитника Microsoft,** выберите **ОК** и **далее**.</span><span class="sxs-lookup"><span data-stu-id="06207-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="06207-185">![Изображение страницы политики конфигурации приложений](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="06207-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="06207-186">На странице **Параметры** перейдите в раздел Разрешения нажмите кнопку Добавить, чтобы просмотреть список поддерживаемых разрешений.</span><span class="sxs-lookup"><span data-stu-id="06207-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="06207-187">В разделе Добавить разрешения выберите следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="06207-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="06207-188">Внешнее хранилище (чтение)</span><span class="sxs-lookup"><span data-stu-id="06207-188">External storage (read)</span></span>
       - <span data-ttu-id="06207-189">Внешнее хранилище (записи)</span><span class="sxs-lookup"><span data-stu-id="06207-189">External storage (write)</span></span>

       <span data-ttu-id="06207-190">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="06207-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="06207-191">![Image of Android create app configuration policy](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="06207-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="06207-192">Теперь вы должны видеть как перечисленные разрешения, так и теперь вы можете  автоматически отобрать автозаявку в выпадаемом состоянии разрешения, а затем выбрать **Далее**.</span><span class="sxs-lookup"><span data-stu-id="06207-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="06207-193">![Изображение автоматического гранта android создать политику конфигурации приложений](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="06207-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="06207-194">На странице **Назначения** выберите группу пользователей, которой будет назначена эта политика конфигурировать приложения.</span><span class="sxs-lookup"><span data-stu-id="06207-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="06207-195">Щелкните **Выберите группы, чтобы включить** и выбрать применимую группу, а затем выбрать **Далее.**</span><span class="sxs-lookup"><span data-stu-id="06207-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="06207-196">Выбранная здесь группа обычно является той же группой, к которой можно назначить Microsoft Defender для android-приложения Endpoint.</span><span class="sxs-lookup"><span data-stu-id="06207-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="06207-197">![Изображение политики конфигурации приложения](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="06207-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="06207-198">На странице **Обзор + Создание** следующей страницы просмотрите всю информацию и выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="06207-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="06207-199">Политика конфигурации приложения для автозадания разрешения на хранение Defender для конечной точки теперь назначена выбранной группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="06207-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="06207-200">![Image of Android review create app config policy](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="06207-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="06207-201">Выберите **приложение ATP Защитника Майкрософт** в списке Назначения \>  \> **свойств** \> **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="06207-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![Изображение списка приложений](images/mda-properties.png)


11. <span data-ttu-id="06207-203">Назначьте приложение в качестве *обязательного* приложения группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="06207-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="06207-204">Он автоматически устанавливается в профиле *работы* во время следующей синхронизации устройства с помощью приложения портала компании.</span><span class="sxs-lookup"><span data-stu-id="06207-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="06207-205">Это назначение можно сделать, перейдите в группу "Требуется добавить", выбрав группу пользователей и нажмите  \>  **кнопку Выберите**.</span><span class="sxs-lookup"><span data-stu-id="06207-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06207-206">![Изображение страницы редактирования приложения](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="06207-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="06207-207">На странице **Редактирование приложения** просмотрите все сведения, которые были введены выше.</span><span class="sxs-lookup"><span data-stu-id="06207-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="06207-208">Затем выберите **Обзор + Сохранить,** а затем **сохранить** снова, чтобы приступить к назначению.</span><span class="sxs-lookup"><span data-stu-id="06207-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="06207-209">Автоматическая настройка VPN с помощью always-on</span><span class="sxs-lookup"><span data-stu-id="06207-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="06207-210">Defender for Endpoint поддерживает политики конфигурации устройств для управляемых устройств с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="06207-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="06207-211">Эту возможность можно использовать для автоматической установки VPN на зарегистрированных устройствах Android Enterprise, поэтому конечному пользователю не нужно настроить **VPN-службу** во время работы на борту.</span><span class="sxs-lookup"><span data-stu-id="06207-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="06207-212">На **устройствах** выберите **профили** конфигурации Создание ограничений для корпоративного устройства платформы Android в соответствии с одним из следующих ограничений, основанных на типе  >    >    >   регистрации устройства. </span><span class="sxs-lookup"><span data-stu-id="06207-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="06207-213">**Полностью управляемый, выделенный и Corporate-Owned профиль**</span><span class="sxs-lookup"><span data-stu-id="06207-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="06207-214">**Личный профиль работы**</span><span class="sxs-lookup"><span data-stu-id="06207-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="06207-215">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="06207-215">Select **Create**.</span></span>
 
   > ![Изображение профиля конфигурации устройств Create](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="06207-217">**Параметры конфигурации** Предоставление **имени** и **описания для** уникальной идентификации профиля конфигурации.</span><span class="sxs-lookup"><span data-stu-id="06207-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![Изображение профиля конфигурации устройств Имя и описание](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="06207-219">Выберите **подключение и** настройте VPN:</span><span class="sxs-lookup"><span data-stu-id="06207-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="06207-220">Включай установку **VPN-клиента always-on** в профиле работы для автоматического подключения и подключения к VPN по мере возможности.</span><span class="sxs-lookup"><span data-stu-id="06207-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="06207-221">Только один VPN-клиент может быть настроен для всегда на VPN на заданных устройствах, поэтому не забудьте иметь не более одной политики VPN, развернутой на одном устройстве.</span><span class="sxs-lookup"><span data-stu-id="06207-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="06207-222">Выберите **Настраиваемый** в списке выпаданий vpn-клиентов Настраиваемый VPN, в данном случае это VPN Defender for Endpoint, который используется для предоставления функции веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="06207-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="06207-223">Приложение ATP Защитника Майкрософт должно быть установлено на устройстве пользователя для функционирования автоматической установки этого VPN.</span><span class="sxs-lookup"><span data-stu-id="06207-223">Microsoft Defender ATP app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="06207-224">Введите **ID пакета** приложения ATP Microsoft Defender в магазине Google Play.</span><span class="sxs-lookup"><span data-stu-id="06207-224">Enter **Package ID** of the Microsoft Defender ATP app in Google Play store.</span></span> <span data-ttu-id="06207-225">Для URL-адреса приложения Defender ID пакета https://play.google.com/store/apps/details?id=com.microsoft.scmx **— com.microsoft.scmx**</span><span class="sxs-lookup"><span data-stu-id="06207-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="06207-226">**Режим блокировки** Не настроен (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06207-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![Изображение профиля конфигурации устройств позволяет всегда на VPN](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="06207-228">**Назначение** На странице  **Назначения** выберите группу пользователей, которой будет назначена эта политика конфигурировать   приложения.</span><span class="sxs-lookup"><span data-stu-id="06207-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="06207-229">Щелкните **Выберите группы,** чтобы включить и выбрать применимую группу, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="06207-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="06207-230">Выбранная здесь группа обычно является той же группой, к которой можно назначить Microsoft Defender для android-приложения Endpoint.</span><span class="sxs-lookup"><span data-stu-id="06207-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![Изображение профиля конфигурации устройств Назначение](images/4autosetupofvpn.png)

5. <span data-ttu-id="06207-232">На странице **Обзор + Создание** следующей страницы просмотрите всю информацию и выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="06207-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="06207-233">Теперь профиль конфигурации устройства назначен выбранной группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="06207-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![Изображение профиля конфигурации устройств Обзор и создание](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="06207-235">Полное состояние onboarding и проверки</span><span class="sxs-lookup"><span data-stu-id="06207-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="06207-236">Подтвердить состояние установки Microsoft Defender для конечной точки для Android, нажав на состояние **установки устройства.**</span><span class="sxs-lookup"><span data-stu-id="06207-236">Confirm the installation status of Microsoft Defender for Endpoint for Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="06207-237">Убедитесь, что устройство отображается здесь.</span><span class="sxs-lookup"><span data-stu-id="06207-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06207-238">![Изображение состояния установки устройства](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="06207-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="06207-239">На устройстве можно проверить состояние бортового устройства, переехав в рабочий **профиль.**</span><span class="sxs-lookup"><span data-stu-id="06207-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="06207-240">Подтверди, что Defender для конечной точки доступен и вы зарегистрированы на устройствах, которые принадлежат лично, **с профилем работы.**</span><span class="sxs-lookup"><span data-stu-id="06207-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="06207-241">Если вы зарегистрированы на корпоративном устройстве **с** полностью управляемым пользователем, у вас будет один профиль на устройстве, где вы можете подтвердить, что Defender для конечной точки доступен.</span><span class="sxs-lookup"><span data-stu-id="06207-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![Изображение приложения на мобильном устройстве](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="06207-243">Когда приложение установлено, откройте приложение и примите разрешения, после чего ваша вечная система должна быть успешной.</span><span class="sxs-lookup"><span data-stu-id="06207-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![Изображение мобильного устройства с приложением Microsoft Defender для конечной точки](images/mda-devicesafe.png)

4. <span data-ttu-id="06207-245">На данном этапе устройство успешно вошел в Defender для конечной точки для Android.</span><span class="sxs-lookup"><span data-stu-id="06207-245">At this stage the device is successfully onboarded onto Defender for Endpoint for Android.</span></span> <span data-ttu-id="06207-246">Это можно проверить в [Центре безопасности Защитника Майкрософт,](https://securitycenter.microsoft.com) перенаходив на страницу **Устройства.**</span><span class="sxs-lookup"><span data-stu-id="06207-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![Изображение портала Microsoft Defender для конечных точек](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="06207-248">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="06207-248">Related topics</span></span>
- [<span data-ttu-id="06207-249">Обзор Microsoft Defender для конечной точки для Android</span><span class="sxs-lookup"><span data-stu-id="06207-249">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="06207-250">Настройка Функций Microsoft Defender для конечной точки для Android</span><span class="sxs-lookup"><span data-stu-id="06207-250">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)
