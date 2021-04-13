---
title: Развертывание на основе приложений для ATP Защитника Microsoft для iOS
ms.reviewer: ''
description: Описание развертывания ATP Защитника Майкрософт для iOS с помощью приложения
keywords: Microsoft, defender, atp, ios, app, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6cfd2953e752ed9c96f7f16a3ec7ea1fd8862ab2
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689741"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="5f6ec-104">Развертывание Microsoft Defender для конечной точки на iOS</span><span class="sxs-lookup"><span data-stu-id="5f6ec-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5f6ec-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5f6ec-105">**Applies to:**</span></span>
- [<span data-ttu-id="5f6ec-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5f6ec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5f6ec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f6ec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5f6ec-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5f6ec-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5f6ec-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="5f6ec-110">В этом разделе описывается развертывание устройств Defender для конечной точки для iOS на зарегистрированных устройствах портала компаний Intune.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-110">This topic describes deploying Defender for Endpoint for iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="5f6ec-111">Дополнительные сведения о регистрации устройств Intune см. в записи [устройств iOS/iPadOS в Intune.](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5f6ec-112">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="5f6ec-112">Before you begin</span></span>

- <span data-ttu-id="5f6ec-113">Убедитесь, что у вас есть доступ к центру администрирования [менеджеров конечных точек Майкрософт.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="5f6ec-114">Убедитесь, что регистрация на iOS будет сделана для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="5f6ec-115">Пользователям необходимо иметь лицензию Defender для конечной точки, чтобы использовать Defender для конечной точки для iOS.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint for iOS.</span></span> <span data-ttu-id="5f6ec-116">Обратитесь [к назначению лицензий пользователям](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) для получения инструкций по назначению лицензий.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="5f6ec-117">AtP защитника Microsoft (Microsoft Defender для конечной точки) для iOS теперь доступен в [Магазине приложений Apple.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-117">Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="5f6ec-118">Действия по развертыванию</span><span class="sxs-lookup"><span data-stu-id="5f6ec-118">Deployment steps</span></span>

<span data-ttu-id="5f6ec-119">Развертывание Defender для конечной точки для iOS через портал компании Intune.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-119">Deploy Defender for Endpoint for iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="5f6ec-120">Добавление приложения магазина iOS</span><span class="sxs-lookup"><span data-stu-id="5f6ec-120">Add iOS store app</span></span>

1. <span data-ttu-id="5f6ec-121">В [центре администрирования менеджеров](https://go.microsoft.com/fwlink/?linkid=2109431)конечных точек Майкрософт перейдите в **приложение Apps**  ->  **iOS/iPadOS**  ->  **Add**  ->  **iOS Store app** и нажмите **кнопку Выберите**.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f6ec-122">![Изображение Центра администрирования конечных точек Microsoft Endpoint Manager1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="5f6ec-123">На странице Добавление приложения нажмите кнопку Поиск в **Магазине приложений** и введите конечную точку **Microsoft Defender** в панели поиска.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="5f6ec-124">В разделе Результаты поиска щелкните конечную точку *Microsoft Defender и* выберите **Выберите**.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="5f6ec-125">Выберите **iOS 11.0 в** качестве минимальной операционной системы.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="5f6ec-126">Просмотрите остальные сведения о приложении и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="5f6ec-127">В разделе *Назначения* перейдите в раздел **"Необходимые"** и выберите **группу Добавить.**</span><span class="sxs-lookup"><span data-stu-id="5f6ec-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="5f6ec-128">Затем можно выбрать группу пользователей, которую вы хотите нацелить на Defender для конечной точки для приложения iOS.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-128">You can then choose the user group(s) that you would like to target Defender for Endpoint for iOS app.</span></span> <span data-ttu-id="5f6ec-129">Нажмите **кнопку Выберите** и **затем далее**.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5f6ec-130">Выбранная группа пользователей должна состоять из зарегистрированных пользователей Intune.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f6ec-131">![Изображение Центра администрирования конечных точек Microsoft Endpoint Manager2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="5f6ec-132">В разделе *Обзор + Создание* убедитесь, что вся введенная информация является правильной, а затем выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="5f6ec-133">Через несколько минут приложение Defender для конечной точки должно быть создано успешно, а уведомление должно показываться в правом верхнем углу страницы.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="5f6ec-134">На странице информации о приложении, отображаемой  в разделе **Monitor,** выберите состояние установки устройства, чтобы убедиться, что установка устройства успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f6ec-135">![Изображение Центра администрирования конечной точки Майкрософт](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="5f6ec-136">Полное состояние onboarding и проверки</span><span class="sxs-lookup"><span data-stu-id="5f6ec-136">Complete onboarding and check status</span></span>

1. <span data-ttu-id="5f6ec-137">После установки защитника для конечной точки для iOS на устройстве вы увидите значок приложения.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-137">Once Defender for Endpoint for iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Снимок экрана с автоматически созданным описанием смартфона](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="5f6ec-139">Нажмите значок приложения Defender для конечной точки и выполните инструкции на экране для выполнения действий на борту.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-139">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="5f6ec-140">Сведения включают принятие конечным пользователем разрешений на iOS, необходимых Defender для конечной точки для iOS.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-140">The details include end-user acceptance of iOS permissions required by Defender for Endpoint for iOS.</span></span>

3. <span data-ttu-id="5f6ec-141">После успешного взбора устройство начнет появляться в списке Устройств в Центре безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-141">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f6ec-142">![Снимок экрана с автоматически созданным описанием мобильного телефона](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-142">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="5f6ec-143">Настройка Microsoft Defender для конечной точки для режима с контролем</span><span class="sxs-lookup"><span data-stu-id="5f6ec-143">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="5f6ec-144">Microsoft Defender для конечной точки на iOS-приложении имеет специальные возможности на контролируемых устройствах iOS/iPadOS, учитывая повышенные возможности управления, предоставляемые платформой на этих типах устройств.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-144">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="5f6ec-145">Чтобы воспользоваться этими возможностями, приложению Defender for Endpoint необходимо знать, находится ли устройство в режиме "Контролируемый".</span><span class="sxs-lookup"><span data-stu-id="5f6ec-145">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="5f6ec-146">Настройка режима "Контролируемый" с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="5f6ec-146">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="5f6ec-147">Intune позволяет настроить приложение Defender для iOS с помощью политики конфигурации приложений.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-147">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5f6ec-148">Эта политика конфигурации приложений для контролируемых устройств применима только к управляемым устройствам и должна быть ориентирована на все управляемые устройства iOS в качестве наилучшей практики.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-148">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="5f6ec-149">Войдите в центр администрирования [microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) и перейдите к политикам конфигурации **приложений**  >    >  **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-149">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="5f6ec-150">Щелкните **управляемые устройства.**</span><span class="sxs-lookup"><span data-stu-id="5f6ec-150">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f6ec-151">![Изображение Центра администрирования конечных точек Microsoft Endpoint Manager4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-151">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="5f6ec-152">На странице *Политика конфигурации приложений* создайте следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="5f6ec-152">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="5f6ec-153">Имя политики</span><span class="sxs-lookup"><span data-stu-id="5f6ec-153">Policy Name</span></span>
    - <span data-ttu-id="5f6ec-154">Платформа: Выберите iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="5f6ec-154">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="5f6ec-155">Целевое приложение: Выберите **ATP защитника Майкрософт** из списка</span><span class="sxs-lookup"><span data-stu-id="5f6ec-155">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f6ec-156">![Изображение Центра администрирования конечных точек Майкрософт](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-156">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="5f6ec-157">На следующем экране в качестве формата выберите **конструктор конфигурации** Use.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-157">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="5f6ec-158">Укажите следующее свойство:</span><span class="sxs-lookup"><span data-stu-id="5f6ec-158">Specify the following property:</span></span>
    - <span data-ttu-id="5f6ec-159">Ключ конфигурации: issupervised</span><span class="sxs-lookup"><span data-stu-id="5f6ec-159">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="5f6ec-160">Тип значения: String</span><span class="sxs-lookup"><span data-stu-id="5f6ec-160">Value type: String</span></span>
    - <span data-ttu-id="5f6ec-161">Значение конфигурации: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="5f6ec-161">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f6ec-162">![Изображение Центра администрирования конечных точек Майкрософт](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-162">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="5f6ec-163">Нажмите **кнопку Далее,** чтобы **открыть страницу Теги области.**</span><span class="sxs-lookup"><span data-stu-id="5f6ec-163">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="5f6ec-164">Теги области необязательны.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-164">Scope tags are optional.</span></span> <span data-ttu-id="5f6ec-165">Для продолжения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-165">Click **Next** to continue.</span></span>

1. <span data-ttu-id="5f6ec-166">На странице **Назначения выберите** группы, которые получат этот профиль.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-166">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="5f6ec-167">В этом сценарии лучше всего нацелить все **устройства.**</span><span class="sxs-lookup"><span data-stu-id="5f6ec-167">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="5f6ec-168">Дополнительные сведения о назначении профилей см. в странице [Назначение профилей пользователей и устройств.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-168">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="5f6ec-169">При развертывании в группах пользователей пользователь должен войти на устройство до того, как применяется политика.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-169">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="5f6ec-170">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-170">Click **Next**.</span></span>

1. <span data-ttu-id="5f6ec-171">На странице **Обзор + создание,** когда вы сделали, выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-171">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="5f6ec-172">Новый профиль отображается в списке профилей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-172">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="5f6ec-173">Далее для расширения возможностей защиты от фишинга можно развернуть настраиваемый профиль на контролируемых устройствах iOS.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-173">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="5f6ec-174">Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5f6ec-174">Follow the steps below:</span></span>
    - <span data-ttu-id="5f6ec-175">Скачайте профиль config из [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-175">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="5f6ec-176">Перейдите **к**  ->  **профилям конфигурации устройств iOS/iPadOS**  ->    ->  **Create Profile**</span><span class="sxs-lookup"><span data-stu-id="5f6ec-176">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f6ec-177">![Изображение Центра администрирования конечных точек Майкрософт](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-177">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="5f6ec-178">Укай имя профиля.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-178">Provide a name of the profile.</span></span> <span data-ttu-id="5f6ec-179">Если вам будет предложено импортировать файл профилей конфигурации, выберите скачаный выше файл.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-179">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="5f6ec-180">В разделе **Назначение** выберите группу устройств, к которой необходимо применить этот профиль.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-180">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="5f6ec-181">В качестве наилучшей практики это следует применять ко всем управляемым устройствам iOS.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-181">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="5f6ec-182">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-182">Click **Next**.</span></span>
    - <span data-ttu-id="5f6ec-183">На странице **Обзор + создание,** когда вы сделали, выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-183">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="5f6ec-184">Новый профиль отображается в списке профилей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-184">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5f6ec-185">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5f6ec-185">Next Steps</span></span>

[<span data-ttu-id="5f6ec-186">Настройка Защитника для конечной точки для функций iOS</span><span class="sxs-lookup"><span data-stu-id="5f6ec-186">Configure Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
