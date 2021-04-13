---
title: Антивирус Microsoft Defender на Windows Server
description: Узнайте, как включить и настроить антивирус Microsoft Defender на Windows Server 2016 и Windows Server 2019.
keywords: защитник windows, сервер, scep, защита конечных точек центра системы, сервер 2016, текущая ветвь, сервер 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3415d0caf0192b202cc4f471d5a9bf9051c3878d
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690989"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="00a76-104">Антивирус Microsoft Defender на Windows Server</span><span class="sxs-lookup"><span data-stu-id="00a76-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="00a76-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="00a76-105">**Applies to:**</span></span>

- [<span data-ttu-id="00a76-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="00a76-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="00a76-107">Антивирус Microsoft Defender доступен в следующих выпусках и версиях Windows Server:</span><span class="sxs-lookup"><span data-stu-id="00a76-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="00a76-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="00a76-108">Windows Server 2019</span></span>
- <span data-ttu-id="00a76-109">Windows Server, версия 1803 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="00a76-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="00a76-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="00a76-110">Windows Server 2016.</span></span> 

<span data-ttu-id="00a76-111">В некоторых случаях антивирус Microsoft Defender называется *endpoint Protection;* однако механизм защиты один и тот же.</span><span class="sxs-lookup"><span data-stu-id="00a76-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="00a76-112">Несмотря на то, что функциональность, конфигурация и управление в основном одинаковы для антивируса [Microsoft Defender в Windows 10,](microsoft-defender-antivirus-in-windows-10.md)в Windows Server есть несколько ключевых отличий:</span><span class="sxs-lookup"><span data-stu-id="00a76-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="00a76-113">В Windows Server [автоматические исключения](configure-server-exclusions-microsoft-defender-antivirus.md) применяются в зависимости от определенной роли сервера.</span><span class="sxs-lookup"><span data-stu-id="00a76-113">In Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
- <span data-ttu-id="00a76-114">В Windows Server антивирус Microsoft Defender автоматически не отключится при запуске другого антивирусного продукта.</span><span class="sxs-lookup"><span data-stu-id="00a76-114">In Windows Server, Microsoft Defender Antivirus does not automatically disable itself if you are running another antivirus product.</span></span>

## <a name="the-process-at-a-glance"></a><span data-ttu-id="00a76-115">Краткий обзор процесса</span><span class="sxs-lookup"><span data-stu-id="00a76-115">The process at a glance</span></span>

<span data-ttu-id="00a76-116">Процесс настройки и запуска антивируса Microsoft Defender на серверной платформе включает в себя несколько действий:</span><span class="sxs-lookup"><span data-stu-id="00a76-116">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="00a76-117">[Включить интерфейс](#enable-the-user-interface-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="00a76-117">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="00a76-118">[Установка антивируса Microsoft Defender](#install-microsoft-defender-antivirus-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="00a76-118">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="00a76-119">[Проверка работы антивируса Microsoft Defender.](#verify-microsoft-defender-antivirus-is-running)</span><span class="sxs-lookup"><span data-stu-id="00a76-119">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="00a76-120">[Обновление сведений о безопасности антивирусных программ.](#update-antimalware-security-intelligence)</span><span class="sxs-lookup"><span data-stu-id="00a76-120">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="00a76-121">(По мере необходимости) [Отправка образцов](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="00a76-121">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="00a76-122">(По мере необходимости) [Настройка автоматических исключений.](#configure-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="00a76-122">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="00a76-123">(Только при необходимости) [Установите антивирус Microsoft Defender в пассивный режим.](#need-to-set-microsoft-defender-antivirus-to-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="00a76-123">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="00a76-124">Включить пользовательский интерфейс на Windows Server</span><span class="sxs-lookup"><span data-stu-id="00a76-124">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="00a76-125">По умолчанию антивирус Microsoft Defender устанавливается и функционирует на Windows Server.</span><span class="sxs-lookup"><span data-stu-id="00a76-125">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="00a76-126">Пользовательский интерфейс (GUI) устанавливается по умолчанию в некоторых skUs, но не требуется, так как для управления антивирусом Microsoft Defender можно использовать PowerShell или другие методы.</span><span class="sxs-lookup"><span data-stu-id="00a76-126">The user interface (GUI) is installed by default on some SKUs, but is not required because you can use PowerShell or other methods to manage Microsoft Defender Antivirus.</span></span> <span data-ttu-id="00a76-127">Если GUI не установлен на сервере, его можно  добавить с помощью мастера добавить роли и функции или с помощью cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00a76-127">If the GUI is not installed on your server, you can add it by using the **Add Roles and Features** wizard, or by using PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="00a76-128">Включив GUI с помощью мастера добавить роли и функции</span><span class="sxs-lookup"><span data-stu-id="00a76-128">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="00a76-129">См. в рублях Install [roles, role services and features by using the Add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the Add Roles and Features **Wizard.**</span><span class="sxs-lookup"><span data-stu-id="00a76-129">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="00a76-130">Когда вы доберетеся до шага **Features** мастера, в **Защитник Windows features** выберите **GUI** для Защитник Windows параметра.</span><span class="sxs-lookup"><span data-stu-id="00a76-130">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="00a76-131">В Windows Server 2016 мастер **добавления ролей** и функций выглядит так:</span><span class="sxs-lookup"><span data-stu-id="00a76-131">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Добавление ролей и мастер функций, показывающих GUI для Защитник Windows параметра](images/server-add-gui.png)

   <span data-ttu-id="00a76-133">В Windows Server 2019 мастер **добавления ролей** и функций похож.</span><span class="sxs-lookup"><span data-stu-id="00a76-133">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="00a76-134">Включив GUI с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="00a76-134">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="00a76-135">Следующий cmdlet PowerShell будет включить интерфейс:</span><span class="sxs-lookup"><span data-stu-id="00a76-135">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="00a76-136">Установка антивируса Microsoft Defender на Windows Server</span><span class="sxs-lookup"><span data-stu-id="00a76-136">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="00a76-137">Для установки антивируса Microsoft Defender можно использовать мастер по добавлению ролей и функций или PowerShell. </span><span class="sxs-lookup"><span data-stu-id="00a76-137">You can use either the **Add Roles and Features Wizard** or PowerShell to install Microsoft Defender Antivirus.</span></span>

### <a name="use-the-add-roles-and-features-wizard"></a><span data-ttu-id="00a76-138">Используйте мастер добавления ролей и функций</span><span class="sxs-lookup"><span data-stu-id="00a76-138">Use the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="00a76-139">Обратитесь [к этой статье](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)и используйте мастер добавить роли и **функции**.</span><span class="sxs-lookup"><span data-stu-id="00a76-139">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="00a76-140">Когда вы дойдете до шага **Features** мастера, выберите параметр Антивирус Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="00a76-140">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="00a76-141">Также выберите **GUI для Защитник Windows** параметра.</span><span class="sxs-lookup"><span data-stu-id="00a76-141">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="00a76-142">Воспользуйтесь PowerShell</span><span class="sxs-lookup"><span data-stu-id="00a76-142">Use PowerShell</span></span>

<span data-ttu-id="00a76-143">Чтобы использовать PowerShell для установки антивируса Microsoft Defender, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="00a76-143">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="00a76-144">Сообщения о событиях для антивирусного двигателя, включенного в антивирус Microsoft Defender, можно найти в [событиях Microsoft Defender AV.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="00a76-144">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="00a76-145">Проверка запуска антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="00a76-145">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="00a76-146">Чтобы убедиться, что антивирус Microsoft Defender запущен на сервере, запустите следующий комдлет PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a76-146">To verify that Microsoft Defender Antivirus is running on your server, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="00a76-147">Чтобы убедиться, что защита брандмауэра включена, запустите следующий кодлет PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a76-147">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="00a76-148">В качестве альтернативы PowerShell можно использовать командную подсказку для проверки работы антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="00a76-148">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="00a76-149">Для этого запустите следующую команду из командной подсказки:</span><span class="sxs-lookup"><span data-stu-id="00a76-149">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="00a76-150">Команда `sc query` возвращает сведения о антивирусной службе Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="00a76-150">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="00a76-151">При запуске антивируса Microsoft Defender отображается `STATE` значение `RUNNING` .</span><span class="sxs-lookup"><span data-stu-id="00a76-151">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="00a76-152">Обновление сведений о безопасности антивирусных программ</span><span class="sxs-lookup"><span data-stu-id="00a76-152">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="00a76-153">Чтобы получить обновленные сведения о безопасности антивирусных программ, необходимо иметь службу обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="00a76-153">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="00a76-154">Если вы используете службу управления обновлениями, например cлужбы Windows Server Update Services (WSUS), убедитесь, что обновления для антивирусной безопасности Microsoft Defender утверждены для управляемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="00a76-154">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="00a76-155">По умолчанию Обновление Windows не загружает и не устанавливает обновления автоматически на Windows Server 2019 или Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="00a76-155">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="00a76-156">Эту конфигурацию можно изменить с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="00a76-156">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="00a76-157">Метод</span><span class="sxs-lookup"><span data-stu-id="00a76-157">Method</span></span>  |<span data-ttu-id="00a76-158">Описание</span><span class="sxs-lookup"><span data-stu-id="00a76-158">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="00a76-159">**Обновление Windows в** панели управления</span><span class="sxs-lookup"><span data-stu-id="00a76-159">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="00a76-160">- **Установка обновлений автоматически** приводит к автоматической установке всех обновлений, включая обновления Защитник Windows безопасности.</span><span class="sxs-lookup"><span data-stu-id="00a76-160">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="00a76-161">- **Скачайте** обновления, но позвольте мне выбрать, следует ли их устанавливать, Защитник Windows автоматически загружать и устанавливать обновления разведки безопасности, но другие обновления не устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="00a76-161">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="00a76-162">**Групповая политика**</span><span class="sxs-lookup"><span data-stu-id="00a76-162">**Group Policy**</span></span>     | <span data-ttu-id="00a76-163">Настроить и управлять обновлением Windows можно с помощью параметров, доступных в групповой политике, по следующему пути: Административные **шаблоны\компоненты Windows\Windows Update\Configure Automatic Updates**</span><span class="sxs-lookup"><span data-stu-id="00a76-163">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="00a76-164">Ключ **реестра AUOptions**</span><span class="sxs-lookup"><span data-stu-id="00a76-164">The **AUOptions** registry key</span></span>     |<span data-ttu-id="00a76-165">Следующие два значения позволяют Windows Update автоматически загружать и устанавливать обновления разведки безопасности:</span><span class="sxs-lookup"><span data-stu-id="00a76-165">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="00a76-166">- **4**  -  **Установка обновлений автоматически.**</span><span class="sxs-lookup"><span data-stu-id="00a76-166">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="00a76-167">Это значение приводит к автоматической установке всех обновлений, включая обновления Защитник Windows безопасности.</span><span class="sxs-lookup"><span data-stu-id="00a76-167">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="00a76-168">- **3**  -  **Скачайте обновления, но позвольте мне выбрать, следует ли их устанавливать.**</span><span class="sxs-lookup"><span data-stu-id="00a76-168">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="00a76-169">Это значение позволяет Защитник Windows автоматически загружать и устанавливать обновления разведки безопасности, но другие обновления не устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="00a76-169">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="00a76-170">Чтобы обеспечить защиту от вредоносных программ, рекомендуется включить следующие службы:</span><span class="sxs-lookup"><span data-stu-id="00a76-170">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="00a76-171">Служба отчетности об ошибках Windows</span><span class="sxs-lookup"><span data-stu-id="00a76-171">Windows Error Reporting service</span></span>

- <span data-ttu-id="00a76-172">Служба обновления Windows</span><span class="sxs-lookup"><span data-stu-id="00a76-172">Windows Update service</span></span>

<span data-ttu-id="00a76-173">В следующей таблице перечислены службы антивируса Microsoft Defender и зависимых служб.</span><span class="sxs-lookup"><span data-stu-id="00a76-173">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="00a76-174">Имя службы</span><span class="sxs-lookup"><span data-stu-id="00a76-174">Service Name</span></span>|<span data-ttu-id="00a76-175">Расположение файла</span><span class="sxs-lookup"><span data-stu-id="00a76-175">File Location</span></span>|<span data-ttu-id="00a76-176">Описание</span><span class="sxs-lookup"><span data-stu-id="00a76-176">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="00a76-177">Защитник Windows (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="00a76-177">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="00a76-178">Это основная антивирусная служба Microsoft Defender, которая должна быть запущена во все времена.</span><span class="sxs-lookup"><span data-stu-id="00a76-178">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="00a76-179">Служба отчетности об ошибках Windows (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="00a76-179">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="00a76-180">Эта служба отправляет отчеты об ошибках обратно в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="00a76-180">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="00a76-181">Защитник Windows брандмауэра (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="00a76-181">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="00a76-182">Рекомендуется оставить включенную Защитник Windows брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="00a76-182">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="00a76-183">Обновление Windows (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="00a76-183">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="00a76-184">Обновление Windows необходимо для получения обновлений аналитики безопасности и обновлений движка антивирусного программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="00a76-184">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="00a76-185">Отправка образцов</span><span class="sxs-lookup"><span data-stu-id="00a76-185">Submit samples</span></span>

<span data-ttu-id="00a76-186">Пример отправки позволяет Корпорации Майкрософт собирать образцы потенциально вредоносного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="00a76-186">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="00a76-187">Чтобы обеспечить постоянное и обновленное обеспечение защиты, исследователи Корпорации Майкрософт используют эти примеры для анализа подозрительных действий и создания обновленных сведений о безопасности антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="00a76-187">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="00a76-188">Мы собираем файлы, исполняемые программой, такие как файлы .exe и файлы dll.</span><span class="sxs-lookup"><span data-stu-id="00a76-188">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="00a76-189">Мы не собираем файлы, содержащие персональные данные, такие как документы Microsoft Word и PDF-файлы.</span><span class="sxs-lookup"><span data-stu-id="00a76-189">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="00a76-190">Отправка файла</span><span class="sxs-lookup"><span data-stu-id="00a76-190">Submit a file</span></span>

1. <span data-ttu-id="00a76-191">Просмотрите [руководство по отправке.](/windows/security/threat-protection/intelligence/submission-guide)</span><span class="sxs-lookup"><span data-stu-id="00a76-191">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="00a76-192">Посетите пример [портала отправки](https://www.microsoft.com/wdsi/filesubmission)и отправьте файл.</span><span class="sxs-lookup"><span data-stu-id="00a76-192">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="00a76-193">Включить автоматическую отправку образца</span><span class="sxs-lookup"><span data-stu-id="00a76-193">Enable automatic sample submission</span></span>

<span data-ttu-id="00a76-194">Чтобы включить автоматическую отправку примера, запустите консоль Windows PowerShell в качестве администратора и установите данные значения **SubmitSamplesConsent** в соответствии с одним из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="00a76-194">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="00a76-195">Setting</span><span class="sxs-lookup"><span data-stu-id="00a76-195">Setting</span></span>  |<span data-ttu-id="00a76-196">Описание</span><span class="sxs-lookup"><span data-stu-id="00a76-196">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="00a76-197">**0**  -  **Всегда подсказка**</span><span class="sxs-lookup"><span data-stu-id="00a76-197">**0** - **Always prompt**</span></span>     |<span data-ttu-id="00a76-198">Антивирусная служба Microsoft Defender подсказает вам подтверждение отправки всех необходимых файлов.</span><span class="sxs-lookup"><span data-stu-id="00a76-198">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="00a76-199">Это параметр по умолчанию для антивируса Microsoft Defender, но не рекомендуется для установок на Windows Server 2016 или 2019 без GUI.</span><span class="sxs-lookup"><span data-stu-id="00a76-199">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="00a76-200">**1**   -  **Автоматически отправлять безопасные образцы**</span><span class="sxs-lookup"><span data-stu-id="00a76-200">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="00a76-201">Антивирусная служба Microsoft Defender отправляет все файлы, помеченные как "безопасные" и подсказок для остальных файлов.</span><span class="sxs-lookup"><span data-stu-id="00a76-201">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="00a76-202">**2**  -  **Никогда не отправлять**</span><span class="sxs-lookup"><span data-stu-id="00a76-202">**2** - **Never send**</span></span>      |<span data-ttu-id="00a76-203">Антивирусная служба Microsoft Defender не подсказывает и не отправляет файлы.</span><span class="sxs-lookup"><span data-stu-id="00a76-203">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="00a76-204">**3**  -  **Отправка всех образцов автоматически**</span><span class="sxs-lookup"><span data-stu-id="00a76-204">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="00a76-205">Антивирусная служба Microsoft Defender отправляет все файлы без запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="00a76-205">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="00a76-206">Настройка автоматических исключений</span><span class="sxs-lookup"><span data-stu-id="00a76-206">Configure automatic exclusions</span></span>

<span data-ttu-id="00a76-207">Чтобы обеспечить безопасность и производительность, автоматически добавляются определенные исключения в зависимости от ролей и функций, устанавливаемой при использовании антивируса Microsoft Defender на Windows Server 2016 или 2019.</span><span class="sxs-lookup"><span data-stu-id="00a76-207">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="00a76-208">См. [в рубке Настройка исключений в антивирусе Microsoft Defender на Windows Server.](configure-server-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="00a76-208">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="00a76-209">Необходимо настроить антивирус Microsoft Defender в пассивный режим?</span><span class="sxs-lookup"><span data-stu-id="00a76-209">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="00a76-210">Если в качестве основного антивирусного решения используется антивирусный продукт, не в microsoft, установите антивирус Microsoft Defender в пассивный режим.</span><span class="sxs-lookup"><span data-stu-id="00a76-210">If you are using a non-Microsoft antivirus product as your primary antivirus solution, set Microsoft Defender Antivirus to passive mode.</span></span>  

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="00a76-211">Установите антивирус Microsoft Defender в пассивный режим с помощью ключа реестра</span><span class="sxs-lookup"><span data-stu-id="00a76-211">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="00a76-212">Если вы используете Windows Server, версию 1803 или Windows Server 2019, можно настроить антивирус Microsoft Defender в пассивный режим, установив следующий ключ реестра:</span><span class="sxs-lookup"><span data-stu-id="00a76-212">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="00a76-213">Путь: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="00a76-213">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="00a76-214">Имя: `ForcePassiveMode`</span><span class="sxs-lookup"><span data-stu-id="00a76-214">Name: `ForcePassiveMode`</span></span>
- <span data-ttu-id="00a76-215">Тип: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="00a76-215">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="00a76-216">Значение: `1`</span><span class="sxs-lookup"><span data-stu-id="00a76-216">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="00a76-217">Отключение антивируса Microsoft Defender с помощью мастера по удалению ролей и функций</span><span class="sxs-lookup"><span data-stu-id="00a76-217">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="00a76-218">См. в рублях Install или [Uninstall Roles, Role Services или Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)и use the **Remove Roles and Features Wizard**.</span><span class="sxs-lookup"><span data-stu-id="00a76-218">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="00a76-219">Когда вы доберется до шага **Features** мастера, уберем **Защитник Windows Features.**</span><span class="sxs-lookup"><span data-stu-id="00a76-219">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="00a76-220">Если вы **Защитник Windows** в разделе **Защитник Windows Features,** вам будет предложено удалить интерфейс **GUI** параметра для Защитник Windows .</span><span class="sxs-lookup"><span data-stu-id="00a76-220">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="00a76-221">Антивирус Microsoft Defender по-прежнему будет работать нормально без пользовательского интерфейса, но  пользовательский интерфейс не может быть включен, если отключить Защитник Windows функцию.</span><span class="sxs-lookup"><span data-stu-id="00a76-221">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="00a76-222">Отключение пользовательского интерфейса антивируса Microsoft Defender с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="00a76-222">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="00a76-223">Чтобы отключить интерфейс антивирусного интерфейса Microsoft Defender, используйте следующий комдлет PowerShell:</span><span class="sxs-lookup"><span data-stu-id="00a76-223">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="00a76-224">Используете ли вы Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="00a76-224">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="00a76-225">Если вы используете Windows Server 2016 и сторонний антивирусный продукт, который не предлагается или не разрабатывается Корпорацией Майкрософт, необходимо отключить или удалить антивирус Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="00a76-225">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="00a76-226">Вы не можете удалить приложение Безопасности Windows, но вы можете отключить интерфейс с этими инструкциями.</span><span class="sxs-lookup"><span data-stu-id="00a76-226">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="00a76-227">Следующий кодлет PowerShell отстрагирует антивирус Microsoft Defender на Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="00a76-227">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

## <a name="see-also"></a><span data-ttu-id="00a76-228">См. также</span><span class="sxs-lookup"><span data-stu-id="00a76-228">See also</span></span>

- [<span data-ttu-id="00a76-229">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="00a76-229">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="00a76-230">Совместимость антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="00a76-230">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)