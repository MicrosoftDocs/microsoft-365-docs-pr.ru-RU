---
title: Начало работы с расширением соответствия требованиям Майкрософт (предварительная версия)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Подготовьтесь к использованию расширения соответствия требованиям Майкрософт и разверните его.
ms.openlocfilehash: c6f56c65de6428374d912545db38337d34720c94
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838352"
---
# <a name="get-started-with-microsoft-compliance-extension-preview"></a><span data-ttu-id="27e09-103">Начало работы с расширением соответствия требованиям Майкрософт (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="27e09-103">Get started with Microsoft Compliance Extension (preview)</span></span>

<span data-ttu-id="27e09-104">Используйте эти процедуры для развертывания расширения соответствия требованиям Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="27e09-104">Use these procedures to roll out the Microsoft Compliance Extension.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="27e09-105">Подготовка</span><span class="sxs-lookup"><span data-stu-id="27e09-105">Before you begin</span></span>

<span data-ttu-id="27e09-106">Чтобы использовать расширение соответствия требованиям Майкрософт, устройство должно быть подключено к защите от потери данных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="27e09-106">To use Microsoft Compliance Extension, the device must be onboarded into endpoint DLP.</span></span> <span data-ttu-id="27e09-107">Просмотрите эти статьи, если вы незнакомы с защитой от потери данных (DLP) или DLP в конечной точке</span><span class="sxs-lookup"><span data-stu-id="27e09-107">Review these articles if you are new to DLP or endpoint DLP</span></span>

- [<span data-ttu-id="27e09-108">Сведения о расширении соответствия требованиям Майкрософт</span><span class="sxs-lookup"><span data-stu-id="27e09-108">Learn about Microsoft Compliance Extension</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="27e09-109">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="27e09-109">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="27e09-110">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="27e09-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="27e09-111">Создание политики защиты от потери данных на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="27e09-111">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="27e09-112">Сведения о защите от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="27e09-112">Learn about endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="27e09-113">Начало работы с функцией защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="27e09-113">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="27e09-114">Средства и методы подключения для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="27e09-114">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
- [<span data-ttu-id="27e09-115">Настройка параметров прокси-сервера устройства и подключения к Интернету для защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="27e09-115">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)
- [<span data-ttu-id="27e09-116">Использование защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="27e09-116">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="27e09-117">Лицензирование SKU и подписок</span><span class="sxs-lookup"><span data-stu-id="27e09-117">SKU/subscriptions licensing</span></span>

<span data-ttu-id="27e09-118">Перед началом работы подтвердите [подписку Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) и любые дополнительные надстройки.</span><span class="sxs-lookup"><span data-stu-id="27e09-118">Before you get started, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="27e09-119">Чтобы использовать функции защиты от потери данных в конечной точке, необходимо иметь одну из этих подписок или надстроек.</span><span class="sxs-lookup"><span data-stu-id="27e09-119">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="27e09-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="27e09-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="27e09-121">Microsoft 365 A5 (для учебных заведений)</span><span class="sxs-lookup"><span data-stu-id="27e09-121">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="27e09-122">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="27e09-122">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="27e09-123">Соответствие требованиям Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="27e09-123">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="27e09-124">Защита информации и управление данными в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="27e09-124">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="27e09-125">Защита информации и управление данными в Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="27e09-125">Microsoft 365 A5 information protection and governance</span></span>

<span data-ttu-id="27e09-126">Подробные инструкции по лицензированию см. в статье [Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="27e09-126">For detailed licensing guidance, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

- <span data-ttu-id="27e09-127">У вашей организации должна быть лицензия на защиту от потери данных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="27e09-127">Your org must be licensed for Endpoint DLP</span></span>
- <span data-ttu-id="27e09-128">Ваши устройства должны работать под управлением 64-разрядной версии Windows 10 сборки 1809 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="27e09-128">Your devices must be running Windows 10 x64 build 1809 or later.</span></span>
- <span data-ttu-id="27e09-129">На устройстве должен быть установлен клиент защиты от вредоносных программ версии 4.18.2101.9 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="27e09-129">The device must have Antimalware Client Version is 4.18.2101.9 or later.</span></span> <span data-ttu-id="27e09-130">Проверьте свою текущую версию, открыв приложение **Безопасность Windows**, щелкнув значок **Параметры** и выбрав **О программе**.</span><span class="sxs-lookup"><span data-stu-id="27e09-130">Check your current version by opening **Windows Security** app, select the **Settings** icon, and then select **About**.</span></span>


### <a name="permissions"></a><span data-ttu-id="27e09-131">Разрешения</span><span class="sxs-lookup"><span data-stu-id="27e09-131">Permissions</span></span>

<span data-ttu-id="27e09-132">Данные из службы защиты от потери данных в конечной точке доступны в [Обозревателе действий](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="27e09-132">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="27e09-133">Существует семь ролей, которые предоставляют разрешения обозревателю действий. Учетная запись, которую вы используете для доступа к данным, должна входить в любую из этих ролей.</span><span class="sxs-lookup"><span data-stu-id="27e09-133">There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="27e09-134">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="27e09-134">Global admin</span></span>
- <span data-ttu-id="27e09-135">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="27e09-135">Compliance admin</span></span>
- <span data-ttu-id="27e09-136">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="27e09-136">Security admin</span></span>
- <span data-ttu-id="27e09-137">Администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="27e09-137">Compliance data admin</span></span>
- <span data-ttu-id="27e09-138">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="27e09-138">Global reader</span></span>
- <span data-ttu-id="27e09-139">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="27e09-139">Security reader</span></span>
- <span data-ttu-id="27e09-140">Читатель отчетов</span><span class="sxs-lookup"><span data-stu-id="27e09-140">Reports reader</span></span>

### <a name="overall-installation-workflow"></a><span data-ttu-id="27e09-141">Общий рабочий процесс установки</span><span class="sxs-lookup"><span data-stu-id="27e09-141">Overall installation workflow</span></span>

<span data-ttu-id="27e09-142">Развертывание расширения соответствия требованиям Майкрософт — это многоэтапный процесс.</span><span class="sxs-lookup"><span data-stu-id="27e09-142">Deploying Microsoft Compliance Extension is a multi-phase process.</span></span> <span data-ttu-id="27e09-143">Вы можете выбрать установку на одном компьютере одновременно или использовать Microsoft Endpoint Manager или групповую политику для развертывания в пределах организации.</span><span class="sxs-lookup"><span data-stu-id="27e09-143">You can choose to install on one machine at a time, or use Microsoft Endpoint Manager or Group Policy for organization-wide deployments.</span></span>

1. <span data-ttu-id="27e09-144">[Подготовка устройств](#prepare-your-devices).</span><span class="sxs-lookup"><span data-stu-id="27e09-144">[Prepare your devices](#prepare-your-devices).</span></span>
2. [<span data-ttu-id="27e09-145">Базовая настройка Selfhost на одном компьютере</span><span class="sxs-lookup"><span data-stu-id="27e09-145">Basic Setup Single Machine Selfhost</span></span>](#basic-setup-single-machine-selfhost)
3. [<span data-ttu-id="27e09-146">Развертывание с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="27e09-146">Deploy using Microsoft Endpoint Manager</span></span>](#deploy-using-microsoft-endpoint-manager)
4. [<span data-ttu-id="27e09-147">Развертывание с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="27e09-147">Deploy using Group Policy</span></span>](#deploy-using-group-policy)
5. [<span data-ttu-id="27e09-148">Тестирование расширения</span><span class="sxs-lookup"><span data-stu-id="27e09-148">Test the Extension</span></span>](#test-the-extension)
6. [<span data-ttu-id="27e09-149">Просмотр оповещений защиты от потери данных Chrome с помощью панели управления оповещениями</span><span class="sxs-lookup"><span data-stu-id="27e09-149">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [<span data-ttu-id="27e09-150">Просмотр данных защиты от потери данных Chrome с помощью обозревателя действий</span><span class="sxs-lookup"><span data-stu-id="27e09-150">Viewing Chrome DLP data in activity explorer</span></span>](#viewing-chrome-dlp-data-in-activity-explorer) 

### <a name="prepare-infrastructure"></a><span data-ttu-id="27e09-151">Подготовка инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="27e09-151">Prepare infrastructure</span></span>

<span data-ttu-id="27e09-152">Если вы разворачиваете расширение соответствия требованиям Майкрософт на всех отслеживаемых устройствах с Windows 10, удалите Google Chrome из списка запрещенных приложений или запрещенных браузеров.</span><span class="sxs-lookup"><span data-stu-id="27e09-152">If you are rolling out the Microsoft Compliance Extension to all your monitored Windows 10 devices, you should remove Google Chrome from the unallowed app and unallowed browser lists.</span></span> <span data-ttu-id="27e09-153">Дополнительные сведения см. в разделе [Запрещенные браузеры](endpoint-dlp-using.md#unallowed-browsers).</span><span class="sxs-lookup"><span data-stu-id="27e09-153">For more information, see [Unallowed browsers](endpoint-dlp-using.md#unallowed-browsers).</span></span> <span data-ttu-id="27e09-154">Если вы разворачиваете его только на нескольких устройствах, вы можете оставить Chrome в списке запрещенных браузеров или запрещенных приложений.</span><span class="sxs-lookup"><span data-stu-id="27e09-154">If you are only rolling it out to a few devices, you can leave Chrome on the unallowed browser or unallowed app lists.</span></span> <span data-ttu-id="27e09-155">Расширение соответствия требованиям Майкрософт обойдет ограничения обоих списков для компьютеров, на которых оно устанавливается.</span><span class="sxs-lookup"><span data-stu-id="27e09-155">The Microsoft Compliance Extension will bypass the restrictions of both lists for those computers where it is installed.</span></span>  

### <a name="prepare-your-devices"></a><span data-ttu-id="27e09-156">Подготовка устройств</span><span class="sxs-lookup"><span data-stu-id="27e09-156">Prepare your devices</span></span>

1. <span data-ttu-id="27e09-157">Используйте процедуры из следующих статей, чтобы подключить свои устройства.</span><span class="sxs-lookup"><span data-stu-id="27e09-157">Use the procedures in these topics to onboard your devices:</span></span>
    1. [<span data-ttu-id="27e09-158">Начало работы с функцией защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="27e09-158">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
    1. [<span data-ttu-id="27e09-159">Средства и методы подключения для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="27e09-159">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
    1. [<span data-ttu-id="27e09-160">Настройка параметров прокси-сервера устройства и подключения к Интернету для защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="27e09-160">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a><span data-ttu-id="27e09-161">Базовая настройка Selfhost на одном компьютере</span><span class="sxs-lookup"><span data-stu-id="27e09-161">Basic Setup Single Machine Selfhost</span></span>

<span data-ttu-id="27e09-162">Это рекомендуемый метод.</span><span class="sxs-lookup"><span data-stu-id="27e09-162">This is the recommended method.</span></span> 

1. <span data-ttu-id="27e09-163">Войдите на компьютер с Windows 10, где нужно установить расширение соответствия требованиям Майкрософт, и запустите этот сценарий PowerShell в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="27e09-163">Sign in to the Windows 10 computer on which you want to install the Microsoft Compliance Extension on, and run this PowerShell script as an administrator.</span></span> 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  <span data-ttu-id="27e09-164">Перейдите на страницу [Расширение соответствия требованиям Майкрософт — интернет-магазин Chrome (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span><span class="sxs-lookup"><span data-stu-id="27e09-164">Navigate to [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span></span>

3.  <span data-ttu-id="27e09-165">Установите расширение с помощью инструкций на странице интернет-магазина Chrome.</span><span class="sxs-lookup"><span data-stu-id="27e09-165">Install the extension using the instructions on the Chrome Web Store page.</span></span>

### <a name="deploy-using-microsoft-endpoint-manager"></a><span data-ttu-id="27e09-166">Развертывание с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="27e09-166">Deploy using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="27e09-167">Используйте этот метод установки для развертывания в пределах организации</span><span class="sxs-lookup"><span data-stu-id="27e09-167">Use this setup method for organization-wide deployments.</span></span>


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a><span data-ttu-id="27e09-168">Включение обязательного ключа реестра с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="27e09-168">Enabling Required Registry Key via Microsoft Endpoint Manager</span></span>

1.  <span data-ttu-id="27e09-169">Создайте сценарий PowerShell со следующим содержимым:</span><span class="sxs-lookup"><span data-stu-id="27e09-169">Create a PowerShell script with the following contents:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  <span data-ttu-id="27e09-170">Войдите в [Центр администрирования Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="27e09-170">Sign in to the [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com).</span></span>

3.  <span data-ttu-id="27e09-171">Выберите **Устройства** > **Сценарии** и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="27e09-171">Navigate to **Devices** > **Scripts** and select **Add**.</span></span>

4.  <span data-ttu-id="27e09-172">Перейдите к расположению сценария, созданного при запросе.</span><span class="sxs-lookup"><span data-stu-id="27e09-172">Browse to the location of the script created when prompted.</span></span>

5.  <span data-ttu-id="27e09-173">Выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="27e09-173">Select the following settings:</span></span>
    1. <span data-ttu-id="27e09-174">Запускать сценарий по учетным данным входа: ДА</span><span class="sxs-lookup"><span data-stu-id="27e09-174">Run this script using the logged-on credentials: YES</span></span>
    1. <span data-ttu-id="27e09-175">Принудительно проверить подпись сценария: НЕТ</span><span class="sxs-lookup"><span data-stu-id="27e09-175">Enforce script signature check: NO</span></span>
    1. <span data-ttu-id="27e09-176">Запуск сценария в 64-разрядном узле PowerShell: ДА</span><span class="sxs-lookup"><span data-stu-id="27e09-176">Run script in 64-bit PowerShell Host: YES</span></span>

6.  <span data-ttu-id="27e09-177">Выберите подходящие группы устройств и примените политику.</span><span class="sxs-lookup"><span data-stu-id="27e09-177">Select the proper device groups and apply the policy.</span></span>

#### <a name="microsoft-endpoint-manager-force-install-steps"></a><span data-ttu-id="27e09-178">Этапы принудительной установки Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="27e09-178">Microsoft Endpoint Manager Force Install Steps</span></span>

<span data-ttu-id="27e09-179">Перед добавлением расширения соответствия требованиям Майкрософт в список принудительно устанавливаемых расширений важно внедрить ADMX Chrome.</span><span class="sxs-lookup"><span data-stu-id="27e09-179">Before adding the Microsoft Compliance Extension to the list of force-installed extensions, it is important to ingest the Chrome ADMX.</span></span> <span data-ttu-id="27e09-180">Этапы этого процесса в Microsoft Endpoint Manager описаны корпорацией Google: [Как управлять браузером Chrome с помощью Microsoft Intune — корпоративная справка Google Chrome](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span><span class="sxs-lookup"><span data-stu-id="27e09-180">Steps for this process in Microsoft Endpoint Manager are documented by Google: [Manage Chrome Browser with Microsoft Intune - Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span></span>

 <span data-ttu-id="27e09-181">После внедрения ADMX можно с помощью инструкций ниже создать профиль конфигурации для этого расширения.</span><span class="sxs-lookup"><span data-stu-id="27e09-181">After ingesting the ADMX, the steps below can be followed to create a configuration profile for this extension.</span></span>

1.  <span data-ttu-id="27e09-182">Войдите в Центр администрирования Microsoft Endpoint Manager (https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="27e09-182">Sign in to the Microsoft Endpoint Manager Admin Center (https://endpoint.microsoft.com).</span></span>

2.  <span data-ttu-id="27e09-183">Перейдите к профилям конфигурации.</span><span class="sxs-lookup"><span data-stu-id="27e09-183">Navigate to Configuration Profiles.</span></span>

3.  <span data-ttu-id="27e09-184">Нажмите **Создать профиль**.</span><span class="sxs-lookup"><span data-stu-id="27e09-184">Select **Create Profile**.</span></span>

4.  <span data-ttu-id="27e09-185">Выберите **Windows 10** в качестве платформы.</span><span class="sxs-lookup"><span data-stu-id="27e09-185">Select **Windows 10** as the platform.</span></span>

5.  <span data-ttu-id="27e09-186">Выберите **Пользовательский** в качестве типа профиля.</span><span class="sxs-lookup"><span data-stu-id="27e09-186">Select **Custom** as profile type.</span></span>

6.  <span data-ttu-id="27e09-187">Выберите вкладку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="27e09-187">Select the **Settings** tab.</span></span>

7.  <span data-ttu-id="27e09-188">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="27e09-188">Select **Add**.</span></span>

8.  <span data-ttu-id="27e09-189">Введите следующие сведения о политике.</span><span class="sxs-lookup"><span data-stu-id="27e09-189">Enter the following policy information.</span></span>
    
    <span data-ttu-id="27e09-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span><span class="sxs-lookup"><span data-stu-id="27e09-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span></span><br/>
    <span data-ttu-id="27e09-191">Тип данных: `String`</span><span class="sxs-lookup"><span data-stu-id="27e09-191">Data type: `String`</span></span><br/>
    <span data-ttu-id="27e09-192">Значение: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span><span class="sxs-lookup"><span data-stu-id="27e09-192">Value: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span></span>

9.  <span data-ttu-id="27e09-193">Нажмите "Создать".</span><span class="sxs-lookup"><span data-stu-id="27e09-193">Click create.</span></span>

### <a name="deploy-using-group-policy"></a><span data-ttu-id="27e09-194">Развертывание с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="27e09-194">Deploy using Group Policy</span></span>

<span data-ttu-id="27e09-195">Если вы не хотите использовать Microsoft Endpoint Manager, можно применить групповые политики для развертывания расширения соответствия требованиям Майкрософт в организации</span><span class="sxs-lookup"><span data-stu-id="27e09-195">If you don't want to use Microsoft Endpoint Manager, you can use group policies to deploy the Microsoft Compliance Extension across your organization</span></span>

1. <span data-ttu-id="27e09-196">Ваши устройства должны быть управляемыми с помощью групповой политики, и необходимо импортировать все ADMX Chrome в центральное хранилище групповой политики.</span><span class="sxs-lookup"><span data-stu-id="27e09-196">Your devices must be manageable via Group Policy, and you need to import all Chrome ADMXs into the Group Policy Central Store.</span></span> <span data-ttu-id="27e09-197">Дополнительные сведения см. в статье [Как создать центральное хранилище для административных шаблонов групповой политики в Windows и управлять им](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span><span class="sxs-lookup"><span data-stu-id="27e09-197">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span></span>

2.  <span data-ttu-id="27e09-198">Создайте сценарий PowerShell с помощью команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="27e09-198">Create a PowerShell script using this PowerShell command:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  <span data-ttu-id="27e09-199">Откройте **консоль управления групповой политикой** и перейдите в свое подразделение.</span><span class="sxs-lookup"><span data-stu-id="27e09-199">Open the **Group Policy Management Console** and navigate to your organizational unit (OU).</span></span>

4.  <span data-ttu-id="27e09-200">Щелкните правой кнопкой мыши и выберите **Создать GPO в этом домене и связать его**.</span><span class="sxs-lookup"><span data-stu-id="27e09-200">Right-click and select **Create a GPO in this domain and Link it here**.</span></span> <span data-ttu-id="27e09-201">При запросе назначьте понятное имя этому объекту групповой политики (GPO) и завершите его создание.</span><span class="sxs-lookup"><span data-stu-id="27e09-201">When prompted, assign a descriptive name to this group policy object (GPO) and finish creating it.</span></span>

5.  <span data-ttu-id="27e09-202">Щелкните правой кнопкой мыши GPO и нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="27e09-202">Right-click the GPO and select **Edit**.</span></span>

6.  <span data-ttu-id="27e09-203">Перейдите в раздел **Конфигурация компьютера** > **Настройки** > **Настройки панели управления** > **Запланированные задачи**.</span><span class="sxs-lookup"><span data-stu-id="27e09-203">Go to **Computer Configuration** > **Preferences** > **Control Panel Settings** > **Scheduled Tasks**.</span></span>

7.  <span data-ttu-id="27e09-204">Создайте новую задачу для немедленного запуска, щелкнув правой кнопкой мыши и выбрав **Создать** > **Немедленная задача (Windows 7 и выше)**.</span><span class="sxs-lookup"><span data-stu-id="27e09-204">Create a new immediate task by selecting right-clicking and selecting **New** > **Immediate Task (At least Windows 7)**.</span></span>

8.  <span data-ttu-id="27e09-205">Добавьте имя и описание задачи.</span><span class="sxs-lookup"><span data-stu-id="27e09-205">Give the task a name & description.</span></span>

9.  <span data-ttu-id="27e09-206">Выберите соответствующую учетную запись для запуска немедленной задачи, например NT Authority.</span><span class="sxs-lookup"><span data-stu-id="27e09-206">Choose the corresponding account to run the immediate task, for example NT Authority</span></span>

10. <span data-ttu-id="27e09-207">Выберите **Выполнить с наивысшими правами**.</span><span class="sxs-lookup"><span data-stu-id="27e09-207">Select **Run with highest privileges**.</span></span>

11. <span data-ttu-id="27e09-208">Настройте политику для Windows 10.</span><span class="sxs-lookup"><span data-stu-id="27e09-208">Configure the policy for Windows 10.</span></span>

12. <span data-ttu-id="27e09-209">На вкладке **Действия** выберите действие **Запуск программы**.</span><span class="sxs-lookup"><span data-stu-id="27e09-209">In the **Actions** tab, select the action **Start a program**.</span></span>

13. <span data-ttu-id="27e09-210">Введите путь к программе или сценарию, созданному на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="27e09-210">Enter the path to the Program/Script created in Step 1.</span></span>

14. <span data-ttu-id="27e09-211">Нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="27e09-211">Select **Apply**.</span></span>

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a><span data-ttu-id="27e09-212">Добавление расширения Chrome в список ForceInstall</span><span class="sxs-lookup"><span data-stu-id="27e09-212">Adding the Chrome Extension to the ForceInstall List</span></span>

1.  <span data-ttu-id="27e09-213">В редакторе управления групповыми политиками перейдите к своему подразделению.</span><span class="sxs-lookup"><span data-stu-id="27e09-213">In the Group Policy Management Editor, navigate to your OU.</span></span>

2.  <span data-ttu-id="27e09-214">Разверните следующий путь: **Конфигурация компьютера или пользователя** > **Политики** > **Административные шаблоны** > **Классические административные шаблоны** > **Google** > **Google Chrome** > **Расширения**.</span><span class="sxs-lookup"><span data-stu-id="27e09-214">Expand the following path **Computer/User configuration** > **Policies** > **Administrative templates** > **Classic administrative templates** > **Google** > **Google Chrome** > **Extensions**.</span></span> <span data-ttu-id="27e09-215">Этот путь может отличаться в зависимости от вашей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="27e09-215">This path may vary depending on your configuration.</span></span>

3.  <span data-ttu-id="27e09-216">Выберите **Настроить список принудительно устанавливаемых расширений**.</span><span class="sxs-lookup"><span data-stu-id="27e09-216">Select **Configure the list of force-installed extensions**.</span></span>

4.  <span data-ttu-id="27e09-217">Щелкните правой кнопкой мыши и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="27e09-217">Right click and select **Edit**.</span></span>

5.  <span data-ttu-id="27e09-218">Щелкните **Включено**.</span><span class="sxs-lookup"><span data-stu-id="27e09-218">Select **Enabled**.</span></span>

6.  <span data-ttu-id="27e09-219">Выберите **Показать**.</span><span class="sxs-lookup"><span data-stu-id="27e09-219">Select **Show**.</span></span>

7.  <span data-ttu-id="27e09-220">В разделе **Значение** добавьте следующую запись: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span><span class="sxs-lookup"><span data-stu-id="27e09-220">Under **Value**, add the following entry: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span></span>

8.  <span data-ttu-id="27e09-221">Нажмите **ОК** и **Применить**.</span><span class="sxs-lookup"><span data-stu-id="27e09-221">Select **OK** and then **Apply**.</span></span>

### <a name="test-the-extension"></a><span data-ttu-id="27e09-222">Тестирование расширения</span><span class="sxs-lookup"><span data-stu-id="27e09-222">Test the Extension</span></span>

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a><span data-ttu-id="27e09-223">Отправка в облачную службу или доступ путем выхода в облако запрещенными браузерами</span><span class="sxs-lookup"><span data-stu-id="27e09-223">Upload to cloud service, or access by unallowed browsers Cloud Egress</span></span>  

1. <span data-ttu-id="27e09-224">Создайте или получите конфиденциальный элемент и попробуйте отправить файл в один из запрещенных доменов службы вашей организации.</span><span class="sxs-lookup"><span data-stu-id="27e09-224">Create or get a sensitive item and, try to upload a file to one of your organization’s restricted service domains.</span></span> <span data-ttu-id="27e09-225">Конфиденциальные данные должны соответствовать одному из наших встроенных [типов конфиденциальной информации](sensitive-information-type-entity-definitions.md) или одному из типов конфиденциальной информации вашей организации.</span><span class="sxs-lookup"><span data-stu-id="27e09-225">The sensitive data must match one of our built-in [Sensitive Info Types](sensitive-information-type-entity-definitions.md), or one of your organization’s sensitive information types.</span></span> <span data-ttu-id="27e09-226">На тестируемом устройстве должно появиться всплывающее уведомление защиты от потери данных о том, что это действие запрещено при открытом файле.</span><span class="sxs-lookup"><span data-stu-id="27e09-226">You should get a DLP toast notification on the device you are testing from that shows that this action is not allowed when the file is open.</span></span>

#### <a name="testing-other-dlp-scenarios-in-chrome"></a><span data-ttu-id="27e09-227">Тестирование других сценариев защиты от потери данных в Chrome</span><span class="sxs-lookup"><span data-stu-id="27e09-227">Testing other DLP scenarios in Chrome</span></span> 

<span data-ttu-id="27e09-228">Теперь, когда вы удалили Chrome из списка запрещенных браузеров или приложений, вы можете протестировать сценарии, указанные ниже, чтобы подтвердить, что действие соответствует требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="27e09-228">Now that you’ve removed Chrome from the disallowed browsers/apps list, you can test the scenarios below to confirm the behavior meets your organization’s requirements:</span></span>

- <span data-ttu-id="27e09-229">Копирование данных из конфиденциального элемента в другой документ с помощью буфера обмена</span><span class="sxs-lookup"><span data-stu-id="27e09-229">Copy data from a sensitive item to another document using the Clipboard</span></span>
    - <span data-ttu-id="27e09-230">Для проверки откройте в браузере Chrome файл, защищенный от копирования в буфер обмена, и попытайтесь скопировать данные из файла.</span><span class="sxs-lookup"><span data-stu-id="27e09-230">To test, open a file that is protected against copy to clipboard actions in the Chrome browser and attempt to copy data from the file.</span></span>
    - <span data-ttu-id="27e09-231">Ожидаемый результат: всплывающее уведомление защиты от потери данных о том, что это действие запрещено при открытом файле.</span><span class="sxs-lookup"><span data-stu-id="27e09-231">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="27e09-232">Печать документа</span><span class="sxs-lookup"><span data-stu-id="27e09-232">Print a document</span></span>
    - <span data-ttu-id="27e09-233">Для проверки откройте в браузере Chrome файл, защищенный от печати, и попытайтесь распечатать файл.</span><span class="sxs-lookup"><span data-stu-id="27e09-233">To test, open a file that is protected against print actions in the Chrome browser and attempt to print the file.</span></span>
    - <span data-ttu-id="27e09-234">Ожидаемый результат: всплывающее уведомление защиты от потери данных о том, что это действие запрещено при открытом файле.</span><span class="sxs-lookup"><span data-stu-id="27e09-234">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="27e09-235">Копирование на съемный USB-носитель</span><span class="sxs-lookup"><span data-stu-id="27e09-235">Copy to USB Removeable Media</span></span>
    - <span data-ttu-id="27e09-236">Для проверки попробуйте сохранить файл на съемном носителе.</span><span class="sxs-lookup"><span data-stu-id="27e09-236">To test, try to save the file to a removeable media storage.</span></span>
    - <span data-ttu-id="27e09-237">Ожидаемый результат: всплывающее уведомление защиты от потери данных о том, что это действие запрещено при открытом файле.</span><span class="sxs-lookup"><span data-stu-id="27e09-237">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="27e09-238">Копирование в сетевую папку</span><span class="sxs-lookup"><span data-stu-id="27e09-238">Copy to Network Share</span></span>
    - <span data-ttu-id="27e09-239">Для проверки попробуйте сохранить файл в сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="27e09-239">To test, try to save the file to a network share.</span></span>
    - <span data-ttu-id="27e09-240">Ожидаемый результат: всплывающее уведомление защиты от потери данных о том, что это действие запрещено при открытом файле.</span><span class="sxs-lookup"><span data-stu-id="27e09-240">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a><span data-ttu-id="27e09-241">Просмотр оповещений защиты от потери данных Chrome с помощью панели управления оповещениями</span><span class="sxs-lookup"><span data-stu-id="27e09-241">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>

1. <span data-ttu-id="27e09-242">Откройте страницу **Защита от потери данных** в [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com) и выберите **Оповещения**.</span><span class="sxs-lookup"><span data-stu-id="27e09-242">Open the **Data loss prevention** page in the [Microsoft 365 Compliance center](https://compliance.microsoft.com) and select **Alerts**.</span></span>

2. <span data-ttu-id="27e09-243">Используйте процедуры из статьи [Настройка и просмотр оповещений для политик защиты от потери данных](dlp-configure-view-alerts-policies.md), чтобы просмотреть оповещения для своих политик защиты от потери данных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="27e09-243">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a><span data-ttu-id="27e09-244">Просмотр данных защиты от потери данных Chrome с помощью обозревателя действий</span><span class="sxs-lookup"><span data-stu-id="27e09-244">Viewing Chrome DLP data in activity explorer</span></span>

1. <span data-ttu-id="27e09-245">Откройте страницу [Классификация данных](https://compliance.microsoft.com/dataclassification?viewid=overview) для своего домена в Центре соответствия требованиям Microsoft 365 и выберите **Обозреватель действий**.</span><span class="sxs-lookup"><span data-stu-id="27e09-245">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose **Activity explorer**.</span></span>

2. <span data-ttu-id="27e09-246">Выполните действия, описанные в статье [Начало работы с обозревателем действий](data-classification-activity-explorer.md), чтобы получить доступ к данным и отфильтровать их на своих устройствах конечной точки.</span><span class="sxs-lookup"><span data-stu-id="27e09-246">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="27e09-247">![фильтр обозревателя действий для устройств конечных точек](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="27e09-247">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

### <a name="known-issues-and-limitations"></a><span data-ttu-id="27e09-248">Известные проблемы и ограничения</span><span class="sxs-lookup"><span data-stu-id="27e09-248">Known Issues and Limitations</span></span>

1. <span data-ttu-id="27e09-249">Не поддерживается перетаскивание для отправки папок.</span><span class="sxs-lookup"><span data-stu-id="27e09-249">Drag & Drop enforcement for folder upload is not supported.</span></span>
2. <span data-ttu-id="27e09-250">Не поддерживается блокировка переопределения для выхода в облако.</span><span class="sxs-lookup"><span data-stu-id="27e09-250">Block Override enforcement for cloud egress is not supported.</span></span>
3. <span data-ttu-id="27e09-251">Режим инкогнито не поддерживается и должен быть отключен.</span><span class="sxs-lookup"><span data-stu-id="27e09-251">Incognito mode is not supported and must be disabled.</span></span>

## <a name="next-steps"></a><span data-ttu-id="27e09-252">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="27e09-252">Next steps</span></span>
<span data-ttu-id="27e09-253">После того, как вы подключили устройства, вы можете просмотреть данные об активности в обозревателе действий и перейти к этапу создания политик защиты от потери данных для конфиденциальных элементов.</span><span class="sxs-lookup"><span data-stu-id="27e09-253">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="27e09-254">Использование Защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="27e09-254">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="27e09-255">См. также</span><span class="sxs-lookup"><span data-stu-id="27e09-255">See also</span></span>

- [<span data-ttu-id="27e09-256">Сведения о защите от потери данных в конечной точке </span><span class="sxs-lookup"><span data-stu-id="27e09-256">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="27e09-257">Использование защиты от потери данных в конечной точке </span><span class="sxs-lookup"><span data-stu-id="27e09-257">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="27e09-258">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="27e09-258">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="27e09-259">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="27e09-259">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="27e09-260">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="27e09-260">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="27e09-261">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="27e09-261">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="27e09-262">Средства и методы подключения для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="27e09-262">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="27e09-263">Подписка на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="27e09-263">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="27e09-264">Устройства, подключенные к Azure AD</span><span class="sxs-lookup"><span data-stu-id="27e09-264">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="27e09-265">Загрузка нового браузера Microsoft Edge на основе Chromium</span><span class="sxs-lookup"><span data-stu-id="27e09-265">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
