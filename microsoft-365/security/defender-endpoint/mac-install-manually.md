---
title: Ручное развертывание для ATP Защитника Майкрософт для macOS
description: Установите ATP Microsoft Defender для macOS вручную из командной строки.
keywords: Microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b2629eb3d13e6eb908644dfcade46a7ac2768637
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187449"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="729db-104">Ручное развертывание для Microsoft Defender для конечной точки для macOS</span><span class="sxs-lookup"><span data-stu-id="729db-104">Manual deployment for Microsoft Defender for Endpoint for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="729db-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="729db-105">**Applies to:**</span></span>
- [<span data-ttu-id="729db-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="729db-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="729db-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="729db-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="729db-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="729db-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="729db-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="729db-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="729db-110">В этом разделе описывается, как развернуть Microsoft Defender для конечной точки для macOS вручную.</span><span class="sxs-lookup"><span data-stu-id="729db-110">This topic describes how to deploy Microsoft Defender for Endpoint for macOS manually.</span></span> <span data-ttu-id="729db-111">Успешное развертывание требует выполнения всех следующих действий:</span><span class="sxs-lookup"><span data-stu-id="729db-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="729db-112">Загрузка пакетов установки и загрузки</span><span class="sxs-lookup"><span data-stu-id="729db-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="729db-113">Установка приложения (macOS 10.15 и более старые версии)</span><span class="sxs-lookup"><span data-stu-id="729db-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="729db-114">Установка приложения (macOS 11 и более новые версии)</span><span class="sxs-lookup"><span data-stu-id="729db-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="729db-115">Конфигурация клиента</span><span class="sxs-lookup"><span data-stu-id="729db-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="729db-116">Необходимые условия и требования к системе</span><span class="sxs-lookup"><span data-stu-id="729db-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="729db-117">Перед началом работы см. на главной странице [Microsoft Defender for Endpoint для macOS](microsoft-defender-endpoint-mac.md) описание необходимых условий и системных требований для текущей версии программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="729db-117">Before you get started, see [the main Microsoft Defender for Endpoint for macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="729db-118">Загрузка пакетов установки и загрузки</span><span class="sxs-lookup"><span data-stu-id="729db-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="729db-119">Скачайте пакеты установки и загрузки из Центра безопасности Защитника Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="729db-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="729db-120">В Центре безопасности Защитника Майкрософт перейдите в **параметры > управления устройствами > onboarding.**</span><span class="sxs-lookup"><span data-stu-id="729db-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="729db-121">В разделе 1 страницы установите операционную систему для **macOS** и метода развертывания к **локальному сценарию.**</span><span class="sxs-lookup"><span data-stu-id="729db-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="729db-122">В разделе 2 страницы выберите **пакет установки Загрузка**.</span><span class="sxs-lookup"><span data-stu-id="729db-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="729db-123">Сохраните его как wdav.pkg в локальном каталоге.</span><span class="sxs-lookup"><span data-stu-id="729db-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="729db-124">В разделе 2 страницы выберите **пакет Загрузка onboarding**.</span><span class="sxs-lookup"><span data-stu-id="729db-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="729db-125">Сохраните его WindowsDefenderATPOnboardingPackage.zip в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="729db-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Снимок экрана Центра безопасности Защитника Майкрософт](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="729db-127">В командной подсказке убедитесь, что у вас есть два файла.</span><span class="sxs-lookup"><span data-stu-id="729db-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="729db-128">Установка приложения (macOS 10.15 и более старые версии)</span><span class="sxs-lookup"><span data-stu-id="729db-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="729db-129">Чтобы завершить этот процесс, на устройстве должны быть привилегии администратора.</span><span class="sxs-lookup"><span data-stu-id="729db-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="729db-130">Перейдите к скачаемой wdav.pkg в Finder и откройте его.</span><span class="sxs-lookup"><span data-stu-id="729db-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Снимок экрана установки приложения1](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-28-appinstall)

2. <span data-ttu-id="729db-132">Выберите **Продолжить,** согласитесь с условиями лицензии и введите пароль при запросе.</span><span class="sxs-lookup"><span data-stu-id="729db-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![Скриншот установки приложения2](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-29-appinstalllogin)

   > [!IMPORTANT]
   > <span data-ttu-id="729db-134">Вам будет предложено разрешить установку драйвера из Microsoft (либо "Расширение системы заблокировано", либо "Установка заблокирована" или оба.</span><span class="sxs-lookup"><span data-stu-id="729db-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="729db-135">Необходимо разрешить установку драйвера.</span><span class="sxs-lookup"><span data-stu-id="729db-135">The driver must be allowed to be installed.</span></span>

   ![Снимок экрана установки приложения3](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-30-systemextension)

3. <span data-ttu-id="729db-137">Выберите **параметры Open Security Preferences** или **Open System Preferences > безопасности & конфиденциальности.**</span><span class="sxs-lookup"><span data-stu-id="729db-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="729db-138">Выберите **Разрешить:**</span><span class="sxs-lookup"><span data-stu-id="729db-138">Select **Allow**:</span></span>

    ![Снимок экрана окна безопасности и конфиденциальности](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-31-securityprivacysettings)

   <span data-ttu-id="729db-140">Продолжается установка.</span><span class="sxs-lookup"><span data-stu-id="729db-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="729db-141">Если вы не выберите **Разрешить,** установка будет продолжаться через 5 минут.</span><span class="sxs-lookup"><span data-stu-id="729db-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="729db-142">Microsoft Defender для конечной точки будет загружен, но некоторые функции, например защита в режиме реального времени, будут отключены.</span><span class="sxs-lookup"><span data-stu-id="729db-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="729db-143">Сведения [о том,](mac-support-kext.md) как устранить неполадки в расширении ядра, см. в выпуске "Устранение неполадок".</span><span class="sxs-lookup"><span data-stu-id="729db-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="729db-144">MacOS может потребовать перезагрузить устройство при первой установке Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="729db-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="729db-145">Защита в режиме реального времени не будет доступна до перезагрузки устройства.</span><span class="sxs-lookup"><span data-stu-id="729db-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="729db-146">Установка приложения (macOS 11 и более новые версии)</span><span class="sxs-lookup"><span data-stu-id="729db-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="729db-147">Чтобы завершить этот процесс, на устройстве должны быть привилегии администратора.</span><span class="sxs-lookup"><span data-stu-id="729db-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="729db-148">Перейдите к скачаемой wdav.pkg в Finder и откройте его.</span><span class="sxs-lookup"><span data-stu-id="729db-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Скриншот установки приложения4](images/big-sur-install-1.png)

2. <span data-ttu-id="729db-150">Выберите **Продолжить,** согласитесь с условиями лицензии и введите пароль при запросе.</span><span class="sxs-lookup"><span data-stu-id="729db-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="729db-151">По завершении процесса установки вам будет назначено утверждение системных расширений, используемых продуктом.</span><span class="sxs-lookup"><span data-stu-id="729db-151">At the end of the installation process, you will be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="729db-152">Выберите **параметры открытой безопасности.**</span><span class="sxs-lookup"><span data-stu-id="729db-152">Select **Open Security Preferences**.</span></span>

    ![Утверждение расширения системы](images/big-sur-install-2.png)

4. <span data-ttu-id="729db-154">Из окна **конфиденциальности & безопасности** выберите **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="729db-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![Параметры безопасности расширения системы1](images/big-sur-install-3.png)

5. <span data-ttu-id="729db-156">Повторите действия 3 & 4 для всех расширений системы, распространяемых с помощью Microsoft Defender для конечной точки для Mac.</span><span class="sxs-lookup"><span data-stu-id="729db-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint for Mac.</span></span>

6. <span data-ttu-id="729db-157">В рамках возможностей обнаружения конечных точек и ответов Microsoft Defender for Endpoint для Mac проверяет трафик розетки и передает эти сведения на портал Центра безопасности Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="729db-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="729db-158">Если вам предложено предоставить разрешения Microsoft Defender для конечной точки для фильтрации сетевого трафика, выберите **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="729db-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![Параметры безопасности расширения системы2](images/big-sur-install-4.png)

7. <span data-ttu-id="729db-160">Откройте **систему настройки** безопасности & конфиденциальности и перейдите на вкладку Конфиденциальность. Предоставление полного доступа к диску в ПТП Microsoft Defender и Расширение безопасности конечной точки  >     **ATP Защитника Майкрософт.** </span><span class="sxs-lookup"><span data-stu-id="729db-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![Полный доступ к диску](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="729db-162">Конфигурация клиента</span><span class="sxs-lookup"><span data-stu-id="729db-162">Client configuration</span></span>

1. <span data-ttu-id="729db-163">Скопируйте wdav.pkg и MicrosoftDefenderATPOnboardingMacOs.py на устройство, на котором развернут Microsoft Defender для конечной точки для macOS.</span><span class="sxs-lookup"><span data-stu-id="729db-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint for macOS.</span></span>

    <span data-ttu-id="729db-164">Устройство клиента не связано с orgId.</span><span class="sxs-lookup"><span data-stu-id="729db-164">The client device is not associated with orgId.</span></span> <span data-ttu-id="729db-165">Обратите внимание, что *атрибут orgId* пустой.</span><span class="sxs-lookup"><span data-stu-id="729db-165">Note that the *orgId* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="729db-166">Запустите скрипт Python для установки файла конфигурации:</span><span class="sxs-lookup"><span data-stu-id="729db-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="729db-167">Убедитесь, что устройство теперь связано с организацией и сообщает о допустимой *orgId:*</span><span class="sxs-lookup"><span data-stu-id="729db-167">Verify that the device is now associated with your organization and reports a valid *orgId*:</span></span>

    ```bash
    mdatp health --field org_id
    ```

<span data-ttu-id="729db-168">После установки вы увидите значок Microsoft Defender в панели состояния macOS в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="729db-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>

   ![Значок Microsoft Defender в скриншоте панели состояния](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)
   

## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="729db-170">Как разрешить полный доступ к диску</span><span class="sxs-lookup"><span data-stu-id="729db-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="729db-171">MacOS 10.15 (Catalina) содержит новые улучшения безопасности и конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="729db-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="729db-172">Начиная с этой версии, по умолчанию приложения не могут получить доступ к определенным расположениям на диске (например, документы, скачивания, настольные компьютеры и т.д.) без явного согласия.</span><span class="sxs-lookup"><span data-stu-id="729db-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="729db-173">При отсутствии такого согласия Microsoft Defender для конечной точки не может полностью защитить ваше устройство.</span><span class="sxs-lookup"><span data-stu-id="729db-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

<span data-ttu-id="729db-174">Чтобы предоставить согласие, откройте параметры system Preferences -> безопасности & конфиденциальности -> конфиденциальности -> полный доступ к диску.</span><span class="sxs-lookup"><span data-stu-id="729db-174">To grant consent, open System Preferences -> Security & Privacy -> Privacy -> Full Disk Access.</span></span> <span data-ttu-id="729db-175">Щелкните значок блокировки, чтобы внести изменения (в нижней части диалогового окна).</span><span class="sxs-lookup"><span data-stu-id="729db-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="729db-176">Выберите Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="729db-176">Select Microsoft Defender for Endpoint.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="729db-177">Проблемы с установкой журнала</span><span class="sxs-lookup"><span data-stu-id="729db-177">Logging installation issues</span></span>

<span data-ttu-id="729db-178">Дополнительные [сведения](mac-resources.md#logging-installation-issues) о том, как найти автоматически созданный журнал, созданный установщиком при ошибке, см. в дополнительных сведениях.</span><span class="sxs-lookup"><span data-stu-id="729db-178">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="729db-179">Uninstallation</span><span class="sxs-lookup"><span data-stu-id="729db-179">Uninstallation</span></span>

<span data-ttu-id="729db-180">Сведения о том, как удалить Microsoft Defender для конечной точки для macOS с клиентских устройств, см. в материале [Uninstalling.](mac-resources.md#uninstalling)</span><span class="sxs-lookup"><span data-stu-id="729db-180">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for macOS from client devices.</span></span>