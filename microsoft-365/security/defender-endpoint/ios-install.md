---
title: Развертывание на основе приложений для Microsoft Defender для конечной точки на iOS
ms.reviewer: ''
description: Описывает развертывание Microsoft Defender для конечной точки на iOS с помощью приложения
keywords: Microsoft, defender, Microsoft Defender for Endpoint, ios, app, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 371208433cbb0f65ab5a2808318c03dae6bb6d8b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842309"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="47474-104">Развертывание Microsoft Defender для конечной точки на iOS</span><span class="sxs-lookup"><span data-stu-id="47474-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="47474-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="47474-105">**Applies to:**</span></span>
- [<span data-ttu-id="47474-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="47474-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="47474-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47474-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="47474-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="47474-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="47474-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="47474-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="47474-110">В этом разделе описывается развертывание Defender для конечной точки на iOS на Корпоративный портал Intune зарегистрированных устройствах.</span><span class="sxs-lookup"><span data-stu-id="47474-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="47474-111">Дополнительные сведения о регистрации устройств Intune см. в записи [устройств iOS/iPadOS в Intune.](/mem/intune/enrollment/ios-enroll)</span><span class="sxs-lookup"><span data-stu-id="47474-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="47474-112">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="47474-112">Before you begin</span></span>

- <span data-ttu-id="47474-113">Убедитесь, что у вас есть доступ к центру администрирования [менеджеров конечных точек Майкрософт.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="47474-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="47474-114">Убедитесь, что регистрация на iOS будет сделана для пользователей.</span><span class="sxs-lookup"><span data-stu-id="47474-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="47474-115">Для использования Defender для конечной точки в iOS пользователям должна быть назначена лицензия Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="47474-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="47474-116">Обратитесь [к назначению лицензий пользователям](/azure/active-directory/users-groups-roles/licensing-groups-assign) для получения инструкций по назначению лицензий.</span><span class="sxs-lookup"><span data-stu-id="47474-116">Refer to [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="47474-117">Microsoft Defender для конечной точки на iOS доступен в [Магазине приложений Apple.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="47474-117">Microsoft Defender for Endpoint on iOS is available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="47474-118">Действия по развертыванию</span><span class="sxs-lookup"><span data-stu-id="47474-118">Deployment steps</span></span>

<span data-ttu-id="47474-119">Развертывание Defender для конечной точки на iOS через Корпоративный портал Intune.</span><span class="sxs-lookup"><span data-stu-id="47474-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="47474-120">Добавление приложения магазина iOS</span><span class="sxs-lookup"><span data-stu-id="47474-120">Add iOS store app</span></span>

1. <span data-ttu-id="47474-121">В [центре администрирования менеджеров](https://go.microsoft.com/fwlink/?linkid=2109431)конечных точек Майкрософт перейдите в **приложение Apps**  ->  **iOS/iPadOS**  ->  **Add**  ->  **iOS Store app** и нажмите **кнопку Выберите**.</span><span class="sxs-lookup"><span data-stu-id="47474-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="47474-122">![Изображение центра администрирования Microsoft Endpoint Manager 1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="47474-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="47474-123">На странице Добавление приложения нажмите кнопку Поиск в **Магазине приложений** и введите конечную точку **Microsoft Defender** в панели поиска.</span><span class="sxs-lookup"><span data-stu-id="47474-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="47474-124">В разделе Результаты поиска щелкните конечную точку *Microsoft Defender и* выберите **Выберите**.</span><span class="sxs-lookup"><span data-stu-id="47474-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="47474-125">Выберите **iOS 11.0 в** качестве минимальной операционной системы.</span><span class="sxs-lookup"><span data-stu-id="47474-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="47474-126">Просмотрите остальные сведения о приложении и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="47474-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="47474-127">В разделе *Назначения* перейдите в раздел **"Необходимые"** и выберите **группу Добавить.**</span><span class="sxs-lookup"><span data-stu-id="47474-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="47474-128">Затем можно выбрать группу пользователей, которую вы хотите нацелить на Defender для конечной точки в приложении iOS.</span><span class="sxs-lookup"><span data-stu-id="47474-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="47474-129">Нажмите **кнопку Выберите** и **затем далее**.</span><span class="sxs-lookup"><span data-stu-id="47474-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="47474-130">Выбранная группа пользователей должна состоять из зарегистрированных пользователей Intune.</span><span class="sxs-lookup"><span data-stu-id="47474-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="47474-131">![Изображение центра администрирования Microsoft Endpoint Manager 2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="47474-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="47474-132">В разделе *Обзор + Создание* убедитесь, что вся введенная информация является правильной, а затем выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="47474-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="47474-133">Через несколько минут приложение Defender для конечной точки должно быть создано успешно, а уведомление должно показываться в правом верхнем углу страницы.</span><span class="sxs-lookup"><span data-stu-id="47474-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="47474-134">На странице информации о приложении, отображаемой  в разделе **Monitor,** выберите состояние установки устройства, чтобы убедиться, что установка устройства успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="47474-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="47474-135">![Изображение центра администрирования Microsoft Endpoint Manager 3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="47474-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="47474-136">Автоматическая встраивка vpn-профиля (упрощенная встраивка)</span><span class="sxs-lookup"><span data-stu-id="47474-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

<span data-ttu-id="47474-137">Администраторы могут настроить автоматическую настройку ПРОФИЛЯ VPN.</span><span class="sxs-lookup"><span data-stu-id="47474-137">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="47474-138">Это автоматически установит VPN-профиль Defender для конечной точки без необходимости этого пользователя во время его работы.</span><span class="sxs-lookup"><span data-stu-id="47474-138">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="47474-139">Обратите внимание, что VPN используется для предоставления функции веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="47474-139">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="47474-140">Это не обычный VPN и локальный или самоциклинг VPN, который не принимает трафик за пределами устройства.</span><span class="sxs-lookup"><span data-stu-id="47474-140">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="47474-141">В [центре администрирования менеджеров конечных точек](https://go.microsoft.com/fwlink/?linkid=2109431)Майкрософт перейдите к **профилям** конфигурации устройств  ->    ->  **Create Profile**.</span><span class="sxs-lookup"><span data-stu-id="47474-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create Profile**.</span></span>
1. <span data-ttu-id="47474-142">Выберите **платформу** в **виде iOS/iPadOS** и **типа профиля** в **качестве VPN.**</span><span class="sxs-lookup"><span data-stu-id="47474-142">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="47474-143">Щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="47474-143">Click **Create**.</span></span>
1. <span data-ttu-id="47474-144">Введите имя профиля и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="47474-144">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="47474-145">Выберите **настраиваемый VPN** для типа подключения и в разделе **Базовый VPN** введите следующее:</span><span class="sxs-lookup"><span data-stu-id="47474-145">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="47474-146">Имя подключения = Защитник Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="47474-146">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="47474-147">Адрес VPN-сервера = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="47474-147">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="47474-148">Метод Auth = "Имя пользователя и пароль"</span><span class="sxs-lookup"><span data-stu-id="47474-148">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="47474-149">Разделение туннелей = Отключение</span><span class="sxs-lookup"><span data-stu-id="47474-149">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="47474-150">ИДЕНТИФИКАТОР VPN = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="47474-150">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="47474-151">В парах значения ключа введите клавишу **AutoOnboard** и установите значение **True**.</span><span class="sxs-lookup"><span data-stu-id="47474-151">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="47474-152">Тип автоматического VPN = VPN по требованию</span><span class="sxs-lookup"><span data-stu-id="47474-152">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="47474-153">Нажмите **кнопку** Добавить для **правил** по требованию и выберите я хочу сделать следующее = **Установить VPN**, я хочу ограничить = Все **домены**.</span><span class="sxs-lookup"><span data-stu-id="47474-153">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![Снимок экрана конфигурации профиля VPN](images/ios-deploy-8.png)

1. <span data-ttu-id="47474-155">Нажмите кнопку Далее и назначьте профиль целевым пользователям.</span><span class="sxs-lookup"><span data-stu-id="47474-155">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="47474-156">В разделе *Обзор + Создание* убедитесь, что вся введенная информация является правильной, а затем выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="47474-156">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="47474-157">Полное состояние onboarding и проверки</span><span class="sxs-lookup"><span data-stu-id="47474-157">Complete onboarding and check status</span></span>

1. <span data-ttu-id="47474-158">После установки Защитника для конечной точки на iOS на устройстве вы увидите значок приложения.</span><span class="sxs-lookup"><span data-stu-id="47474-158">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Снимок экрана с автоматически созданным описанием смартфона](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="47474-160">Нажмите значок приложения Defender для конечной точки (MSDefender) и выполните инструкции на экране для выполнения действий на борту.</span><span class="sxs-lookup"><span data-stu-id="47474-160">Tap the Defender for Endpoint app icon (MSDefender) and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="47474-161">Эти сведения включают принятие конечным пользователем разрешений на iOS, необходимых Defender для конечной точки на iOS.</span><span class="sxs-lookup"><span data-stu-id="47474-161">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="47474-162">После успешной работы над устройством устройство начнет появляться в списке Устройств в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="47474-162">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="47474-163">![Снимок экрана с автоматически созданным описанием мобильного телефона](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="47474-163">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="47474-164">Настройка Microsoft Defender для конечной точки для режима с контролем</span><span class="sxs-lookup"><span data-stu-id="47474-164">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="47474-165">Microsoft Defender для конечной точки на iOS-приложении имеет специальные возможности на контролируемых устройствах iOS/iPadOS, учитывая повышенные возможности управления, предоставляемые платформой на этих типах устройств.</span><span class="sxs-lookup"><span data-stu-id="47474-165">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="47474-166">Чтобы воспользоваться этими возможностями, приложению Defender for Endpoint необходимо знать, находится ли устройство в режиме "Контролируемый".</span><span class="sxs-lookup"><span data-stu-id="47474-166">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="47474-167">Настройка режима "Контролируемый" с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="47474-167">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="47474-168">Intune позволяет настроить приложение Defender для iOS с помощью политики конфигурации приложений.</span><span class="sxs-lookup"><span data-stu-id="47474-168">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="47474-169">Эта политика конфигурации приложений для контролируемых устройств применима только к управляемым устройствам и должна быть ориентирована на все управляемые устройства iOS в качестве наилучшей практики.</span><span class="sxs-lookup"><span data-stu-id="47474-169">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="47474-170">Войдите в центр [администрирования Microsoft Endpoint Manager и](https://go.microsoft.com/fwlink/?linkid=2109431) перейдите к политикам конфигурации **приложений**  >    >  **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="47474-170">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="47474-171">Щелкните **управляемые устройства.**</span><span class="sxs-lookup"><span data-stu-id="47474-171">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="47474-172">![Изображение центра администрирования Microsoft Endpoint Manager 4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="47474-172">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="47474-173">На странице *Политика конфигурации приложений* создайте следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="47474-173">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="47474-174">Имя политики</span><span class="sxs-lookup"><span data-stu-id="47474-174">Policy Name</span></span>
    - <span data-ttu-id="47474-175">Платформа: Выберите iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="47474-175">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="47474-176">Целевое приложение: Выберите **конечную точку Защитника Майкрософт** из списка</span><span class="sxs-lookup"><span data-stu-id="47474-176">Targeted app: Select **Microsoft Defender Endpoint** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="47474-177">![Изображение центра Microsoft Endpoint Manager администрирования5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="47474-177">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="47474-178">На следующем экране в качестве формата выберите **конструктор конфигурации** Use.</span><span class="sxs-lookup"><span data-stu-id="47474-178">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="47474-179">Укажите следующее свойство:</span><span class="sxs-lookup"><span data-stu-id="47474-179">Specify the following property:</span></span>
    - <span data-ttu-id="47474-180">Ключ конфигурации: issupervised</span><span class="sxs-lookup"><span data-stu-id="47474-180">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="47474-181">Тип значения: String</span><span class="sxs-lookup"><span data-stu-id="47474-181">Value type: String</span></span>
    - <span data-ttu-id="47474-182">Значение конфигурации: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="47474-182">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="47474-183">![Изображение Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="47474-183">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="47474-184">Нажмите **кнопку Далее,** чтобы **открыть страницу Теги области.**</span><span class="sxs-lookup"><span data-stu-id="47474-184">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="47474-185">Теги области необязательны.</span><span class="sxs-lookup"><span data-stu-id="47474-185">Scope tags are optional.</span></span> <span data-ttu-id="47474-186">Для продолжения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="47474-186">Click **Next** to continue.</span></span>

1. <span data-ttu-id="47474-187">На странице **Назначения выберите** группы, которые получат этот профиль.</span><span class="sxs-lookup"><span data-stu-id="47474-187">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="47474-188">В этом сценарии лучше всего нацелить все **устройства.**</span><span class="sxs-lookup"><span data-stu-id="47474-188">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="47474-189">Дополнительные сведения о назначении профилей см. в странице [Назначение профилей пользователей и устройств.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="47474-189">For more information on assigning profiles, see [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="47474-190">При развертывании в группах пользователей пользователь должен войти на устройство до того, как применяется политика.</span><span class="sxs-lookup"><span data-stu-id="47474-190">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="47474-191">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="47474-191">Click **Next**.</span></span>

1. <span data-ttu-id="47474-192">На странице **Обзор + создание,** когда вы сделали, выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="47474-192">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="47474-193">Новый профиль отображается в списке профилей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="47474-193">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="47474-194">Далее для расширения возможностей защиты от фишинга можно развернуть настраиваемый профиль на контролируемых устройствах iOS.</span><span class="sxs-lookup"><span data-stu-id="47474-194">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="47474-195">Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="47474-195">Follow the steps below:</span></span>
    - <span data-ttu-id="47474-196">Скачайте профиль config из [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="47474-196">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="47474-197">Перейдите **к**  ->  **профилям конфигурации устройств iOS/iPadOS**  ->    ->  **Create Profile**</span><span class="sxs-lookup"><span data-stu-id="47474-197">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="47474-198">![Изображение Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="47474-198">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="47474-199">Укай имя профиля.</span><span class="sxs-lookup"><span data-stu-id="47474-199">Provide a name of the profile.</span></span> <span data-ttu-id="47474-200">Если вам будет предложено импортировать файл профилей конфигурации, выберите скачаный выше файл.</span><span class="sxs-lookup"><span data-stu-id="47474-200">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="47474-201">В разделе **Назначение** выберите группу устройств, к которой необходимо применить этот профиль.</span><span class="sxs-lookup"><span data-stu-id="47474-201">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="47474-202">В качестве наилучшей практики это следует применять ко всем управляемым устройствам iOS.</span><span class="sxs-lookup"><span data-stu-id="47474-202">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="47474-203">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="47474-203">Click **Next**.</span></span>
    - <span data-ttu-id="47474-204">На странице **Обзор + создание,** когда вы сделали, выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="47474-204">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="47474-205">Новый профиль отображается в списке профилей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="47474-205">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="47474-206">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="47474-206">Next Steps</span></span>

[<span data-ttu-id="47474-207">Настройка Защитника для конечной точки на функции iOS</span><span class="sxs-lookup"><span data-stu-id="47474-207">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
