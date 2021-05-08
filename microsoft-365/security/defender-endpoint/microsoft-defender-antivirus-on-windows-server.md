---
title: Антивирусная программа в Microsoft Defender в Windows Server
description: Узнайте, как включить и настроить антивирус Microsoft Defender на Windows Server 2016 и Windows Server 2019.
keywords: защитник windows, сервер, scep, защита конечных точек центра системы, сервер 2016, текущая ветвь, сервер 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269496"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="01640-104">Антивирусная программа в Microsoft Defender в Windows Server</span><span class="sxs-lookup"><span data-stu-id="01640-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="01640-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="01640-105">**Applies to:**</span></span>

- [<span data-ttu-id="01640-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="01640-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="01640-107">Антивирус Microsoft Defender доступен в следующих выпусках и версиях Windows Server:</span><span class="sxs-lookup"><span data-stu-id="01640-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="01640-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="01640-108">Windows Server 2019</span></span>
- <span data-ttu-id="01640-109">Windows Server, версия 1803 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="01640-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="01640-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="01640-110">Windows Server 2016.</span></span> 

<span data-ttu-id="01640-111">В некоторых случаях антивирус Microsoft Defender называется *endpoint Protection;* однако механизм защиты один и тот же.</span><span class="sxs-lookup"><span data-stu-id="01640-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="01640-112">Несмотря на то, что функциональность, конфигурация и управление в основном одинаковы для антивируса [Microsoft Defender в Windows 10,](microsoft-defender-antivirus-in-windows-10.md)в Windows Server есть несколько ключевых отличий:</span><span class="sxs-lookup"><span data-stu-id="01640-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="01640-113">На Windows Server [автоматические исключения](configure-server-exclusions-microsoft-defender-antivirus.md) применяются в зависимости от определенной роли сервера.</span><span class="sxs-lookup"><span data-stu-id="01640-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="01640-114">На Windows Server, если вы работаете с антивирусным или антивирусным решением, которое не является microsoft, антивирус Microsoft Defender не будет автоматически переходить в пассивный или отключенный режим.</span><span class="sxs-lookup"><span data-stu-id="01640-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="01640-115">Однако антивирус Microsoft Defender можно настроить в пассивном или отключенном режиме вручную.</span><span class="sxs-lookup"><span data-stu-id="01640-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="01640-116">Настройка антивируса Microsoft Defender на Windows Server</span><span class="sxs-lookup"><span data-stu-id="01640-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="01640-117">Процесс настройки и запуска антивируса Microsoft Defender на серверной платформе включает в себя несколько действий:</span><span class="sxs-lookup"><span data-stu-id="01640-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="01640-118">[Включить интерфейс](#enable-the-user-interface-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="01640-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="01640-119">[Установка антивируса Microsoft Defender](#install-microsoft-defender-antivirus-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="01640-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="01640-120">[Проверка работы антивируса Microsoft Defender.](#verify-microsoft-defender-antivirus-is-running)</span><span class="sxs-lookup"><span data-stu-id="01640-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="01640-121">[Обновление сведений о безопасности антивирусных программ.](#update-antimalware-security-intelligence)</span><span class="sxs-lookup"><span data-stu-id="01640-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="01640-122">(По мере необходимости) [Отправка образцов](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="01640-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="01640-123">(По мере необходимости) [Настройка автоматических исключений.](#configure-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="01640-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="01640-124">(Только при необходимости) [Установите антивирус Microsoft Defender в пассивный режим.](#need-to-set-microsoft-defender-antivirus-to-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="01640-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="01640-125">Включить пользовательский интерфейс на Windows Server</span><span class="sxs-lookup"><span data-stu-id="01640-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="01640-126">По умолчанию антивирус Microsoft Defender устанавливается и функционирует на Windows Server.</span><span class="sxs-lookup"><span data-stu-id="01640-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="01640-127">Иногда пользовательский интерфейс (GUI) устанавливается по умолчанию, но GUI не требуется.</span><span class="sxs-lookup"><span data-stu-id="01640-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="01640-128">Для управления антивирусным вирусом Microsoft Defender можно использовать PowerShell, Group Policy или другие методы.</span><span class="sxs-lookup"><span data-stu-id="01640-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="01640-129">Если GUI не установлен на сервере, и вы хотите  установить его, мастер добавить роли и функции или powerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="01640-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="01640-130">Включив GUI с помощью мастера добавить роли и функции</span><span class="sxs-lookup"><span data-stu-id="01640-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="01640-131">См. в рублях Install [roles, role services and features by using the Add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the Add Roles and Features **Wizard.**</span><span class="sxs-lookup"><span data-stu-id="01640-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="01640-132">Когда вы доберетеся до шага **Features** мастера, в **Защитник Windows features** выберите **GUI** для Защитник Windows параметра.</span><span class="sxs-lookup"><span data-stu-id="01640-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="01640-133">В Windows Server 2016 мастер **добавления ролей** и функций выглядит так:</span><span class="sxs-lookup"><span data-stu-id="01640-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Добавление ролей и мастер функций, показывающих GUI для Защитник Windows параметра](images/server-add-gui.png)

   <span data-ttu-id="01640-135">В Windows Server 2019 мастер **добавления ролей** и функций похож.</span><span class="sxs-lookup"><span data-stu-id="01640-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="01640-136">Включив GUI с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="01640-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="01640-137">Следующий cmdlet PowerShell будет включить интерфейс:</span><span class="sxs-lookup"><span data-stu-id="01640-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="01640-138">Установка антивируса Microsoft Defender на Windows Server</span><span class="sxs-lookup"><span data-stu-id="01640-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="01640-139">Если вам необходимо установить или переустановить антивирус Microsoft Defender на  Windows Server, вы можете сделать это с помощью мастера добавить роли и функции или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01640-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="01640-140">Используйте мастер добавления ролей и функций для установки антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="01640-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="01640-141">Обратитесь [к этой статье](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)и используйте мастер добавить роли и **функции**.</span><span class="sxs-lookup"><span data-stu-id="01640-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="01640-142">Когда вы дойдете до шага **Features** мастера, выберите параметр Антивирус Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="01640-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="01640-143">Также выберите **GUI для Защитник Windows** параметра.</span><span class="sxs-lookup"><span data-stu-id="01640-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="01640-144">Использование PowerShell для установки антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="01640-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="01640-145">Чтобы использовать PowerShell для установки антивируса Microsoft Defender, запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="01640-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="01640-146">Сообщения о событиях для антивирусного двигателя, включенного в антивирус Microsoft Defender, можно найти в [событиях Microsoft Defender AV.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="01640-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="01640-147">Проверка запуска антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="01640-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="01640-148">После установки антивируса Microsoft Defender следующий шаг — проверка его работы.</span><span class="sxs-lookup"><span data-stu-id="01640-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="01640-149">В конечной точке Windows Server запустите следующий комдлет PowerShell:</span><span class="sxs-lookup"><span data-stu-id="01640-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="01640-150">Чтобы убедиться, что защита брандмауэра включена, запустите следующий кодлет PowerShell:</span><span class="sxs-lookup"><span data-stu-id="01640-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="01640-151">В качестве альтернативы PowerShell можно использовать командную подсказку для проверки работы антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="01640-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="01640-152">Для этого запустите следующую команду из командной подсказки:</span><span class="sxs-lookup"><span data-stu-id="01640-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="01640-153">Команда `sc query` возвращает сведения о антивирусной службе Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="01640-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="01640-154">При запуске антивируса Microsoft Defender отображается `STATE` значение `RUNNING` .</span><span class="sxs-lookup"><span data-stu-id="01640-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="01640-155">Обновление сведений о безопасности антивирусных программ</span><span class="sxs-lookup"><span data-stu-id="01640-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="01640-156">Чтобы получить обновленные сведения о безопасности антивирусных программ, необходимо иметь службу обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="01640-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="01640-157">Если вы используете службу управления обновлениями, например cлужбы Windows Server Update Services (WSUS), убедитесь, что обновления для антивирусной безопасности Microsoft Defender утверждены для управляемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="01640-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="01640-158">По умолчанию Обновление Windows не загружает и не устанавливает обновления автоматически на Windows Server 2019 или Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="01640-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="01640-159">Эту конфигурацию можно изменить с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="01640-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="01640-160">Метод</span><span class="sxs-lookup"><span data-stu-id="01640-160">Method</span></span>  |<span data-ttu-id="01640-161">Описание</span><span class="sxs-lookup"><span data-stu-id="01640-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="01640-162">**Обновление Windows в** панели управления</span><span class="sxs-lookup"><span data-stu-id="01640-162">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="01640-163">- **Установка обновлений автоматически** приводит к автоматической установке всех обновлений, включая обновления Защитник Windows безопасности.</span><span class="sxs-lookup"><span data-stu-id="01640-163">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="01640-164">- **Скачайте** обновления, но позвольте мне выбрать, следует ли их устанавливать, Защитник Windows автоматически загружать и устанавливать обновления разведки безопасности, но другие обновления не устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="01640-164">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="01640-165">**Групповая политика**</span><span class="sxs-lookup"><span data-stu-id="01640-165">**Group Policy**</span></span>     | <span data-ttu-id="01640-166">Настроить и управлять обновлением Windows можно с помощью параметров, доступных в групповой политике, по следующему пути: Административные **шаблоны\компоненты Windows\Windows Update\Configure Automatic Updates**</span><span class="sxs-lookup"><span data-stu-id="01640-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="01640-167">Ключ **реестра AUOptions**</span><span class="sxs-lookup"><span data-stu-id="01640-167">The **AUOptions** registry key</span></span>     |<span data-ttu-id="01640-168">Следующие два значения позволяют Windows Update автоматически загружать и устанавливать обновления разведки безопасности:</span><span class="sxs-lookup"><span data-stu-id="01640-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="01640-169">- **4**  -  **Установка обновлений автоматически.**</span><span class="sxs-lookup"><span data-stu-id="01640-169">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="01640-170">Это значение приводит к автоматической установке всех обновлений, включая обновления Защитник Windows безопасности.</span><span class="sxs-lookup"><span data-stu-id="01640-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="01640-171">- **3**  -  **Скачайте обновления, но позвольте мне выбрать, следует ли их устанавливать.**</span><span class="sxs-lookup"><span data-stu-id="01640-171">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="01640-172">Это значение позволяет Защитник Windows автоматически загружать и устанавливать обновления разведки безопасности, но другие обновления не устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="01640-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="01640-173">Чтобы обеспечить защиту от вредоносных программ, рекомендуется включить следующие службы:</span><span class="sxs-lookup"><span data-stu-id="01640-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="01640-174">Служба отчетности об ошибках Windows</span><span class="sxs-lookup"><span data-stu-id="01640-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="01640-175">Служба обновления Windows</span><span class="sxs-lookup"><span data-stu-id="01640-175">Windows Update service</span></span>

<span data-ttu-id="01640-176">В следующей таблице перечислены службы антивируса Microsoft Defender и зависимых служб.</span><span class="sxs-lookup"><span data-stu-id="01640-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="01640-177">Имя службы</span><span class="sxs-lookup"><span data-stu-id="01640-177">Service Name</span></span>|<span data-ttu-id="01640-178">Расположение файла</span><span class="sxs-lookup"><span data-stu-id="01640-178">File Location</span></span>|<span data-ttu-id="01640-179">Описание</span><span class="sxs-lookup"><span data-stu-id="01640-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="01640-180">Защитник Windows (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="01640-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="01640-181">Это основная антивирусная служба Microsoft Defender, которая должна быть запущена во все времена.</span><span class="sxs-lookup"><span data-stu-id="01640-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="01640-182">Служба отчетности об ошибках Windows (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="01640-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="01640-183">Эта служба отправляет отчеты об ошибках обратно в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="01640-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="01640-184">Защитник Windows брандмауэра (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="01640-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="01640-185">Рекомендуется оставить включенную Защитник Windows брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="01640-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="01640-186">Обновление Windows (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="01640-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="01640-187">Обновление Windows необходимо для получения обновлений аналитики безопасности и обновлений движка антивирусного программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="01640-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="01640-188">Отправка образцов</span><span class="sxs-lookup"><span data-stu-id="01640-188">Submit samples</span></span>

<span data-ttu-id="01640-189">Пример отправки позволяет Корпорации Майкрософт собирать образцы потенциально вредоносного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="01640-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="01640-190">Чтобы обеспечить постоянное и обновленное обеспечение защиты, исследователи Корпорации Майкрософт используют эти примеры для анализа подозрительных действий и создания обновленных сведений о безопасности антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="01640-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="01640-191">Мы собираем исполняемые файлы программы, такие как .exe и .dll файлы.</span><span class="sxs-lookup"><span data-stu-id="01640-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="01640-192">Мы не собираем файлы, содержащие персональные данные, такие как документы Microsoft Word и PDF-файлы.</span><span class="sxs-lookup"><span data-stu-id="01640-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="01640-193">Отправка файла</span><span class="sxs-lookup"><span data-stu-id="01640-193">Submit a file</span></span>

1. <span data-ttu-id="01640-194">Просмотрите [руководство по отправке.](/windows/security/threat-protection/intelligence/submission-guide)</span><span class="sxs-lookup"><span data-stu-id="01640-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="01640-195">Посетите пример [портала отправки](https://www.microsoft.com/wdsi/filesubmission)и отправьте файл.</span><span class="sxs-lookup"><span data-stu-id="01640-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="01640-196">Включить автоматическую отправку образца</span><span class="sxs-lookup"><span data-stu-id="01640-196">Enable automatic sample submission</span></span>

<span data-ttu-id="01640-197">Чтобы включить автоматическую отправку примера, запустите консоль Windows PowerShell в качестве администратора и установите данные значения **SubmitSamplesConsent** в соответствии с одним из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="01640-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="01640-198">Setting</span><span class="sxs-lookup"><span data-stu-id="01640-198">Setting</span></span>  |<span data-ttu-id="01640-199">Описание</span><span class="sxs-lookup"><span data-stu-id="01640-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="01640-200">**0**  -  **Всегда подсказка**</span><span class="sxs-lookup"><span data-stu-id="01640-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="01640-201">Антивирусная служба Microsoft Defender подсказает вам подтверждение отправки всех необходимых файлов.</span><span class="sxs-lookup"><span data-stu-id="01640-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="01640-202">Это параметр по умолчанию для антивируса Microsoft Defender, но не рекомендуется для установок на Windows Server 2016 или 2019 без GUI.</span><span class="sxs-lookup"><span data-stu-id="01640-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="01640-203">**1**   -  **Автоматически отправлять безопасные образцы**</span><span class="sxs-lookup"><span data-stu-id="01640-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="01640-204">Антивирусная служба Microsoft Defender отправляет все файлы, помеченные как "безопасные" и подсказок для остальных файлов.</span><span class="sxs-lookup"><span data-stu-id="01640-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="01640-205">**2**  -  **Никогда не отправлять**</span><span class="sxs-lookup"><span data-stu-id="01640-205">**2** - **Never send**</span></span>      |<span data-ttu-id="01640-206">Антивирусная служба Microsoft Defender не подсказывает и не отправляет файлы.</span><span class="sxs-lookup"><span data-stu-id="01640-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="01640-207">**3**  -  **Отправка всех образцов автоматически**</span><span class="sxs-lookup"><span data-stu-id="01640-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="01640-208">Антивирусная служба Microsoft Defender отправляет все файлы без запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="01640-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="01640-209">Настройка автоматических исключений</span><span class="sxs-lookup"><span data-stu-id="01640-209">Configure automatic exclusions</span></span>

<span data-ttu-id="01640-210">Чтобы обеспечить безопасность и производительность, автоматически добавляются определенные исключения в зависимости от ролей и функций, устанавливаемой при использовании антивируса Microsoft Defender на Windows Server 2016 или 2019.</span><span class="sxs-lookup"><span data-stu-id="01640-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="01640-211">См. [в рубке Настройка исключений в антивирусе Microsoft Defender на Windows Server.](configure-server-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="01640-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="01640-212">Необходимо настроить антивирус Microsoft Defender в пассивный режим?</span><span class="sxs-lookup"><span data-stu-id="01640-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="01640-213">Если в качестве основного антивирусного решения на Windows Server используется антивирусный продукт, не относячий к Майкрософт, необходимо настроить антивирус Microsoft Defender в пассивный или отключенный режим.</span><span class="sxs-lookup"><span data-stu-id="01640-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="01640-214">На Windows Server версии 1803 или более новой версии или Windows Server 2019 можно настроить антивирус Microsoft Defender в пассивный режим.</span><span class="sxs-lookup"><span data-stu-id="01640-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="01640-215">В Windows Server 2016 антивирус Microsoft Defender не поддерживается наряду с антивирусным и антивирусным продуктом, не относя к Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="01640-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="01640-216">В этих случаях необходимо настроить режим отключения антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="01640-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a><span data-ttu-id="01640-217">Установите антивирус Microsoft Defender в пассивный режим с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="01640-217">Set Microsoft Defender Antivirus to passive mode using PowerShell</span></span>

<span data-ttu-id="01640-218">Если вы используете Windows Server, версию 1803 или Windows Server 2019, можно настроить антивирус Microsoft Defender в пассивный режим с помощью следующего cmdlet PowerShell:</span><span class="sxs-lookup"><span data-stu-id="01640-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by using the following PowerShell cmdlet:</span></span>

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a><span data-ttu-id="01640-219">Установите антивирус Microsoft Defender в пассивный режим с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="01640-219">Set Microsoft Defender Antivirus to passive mode using Group Policy</span></span>

<span data-ttu-id="01640-220">НЕОБХОДИМЫЕ ПРОЦЕДУРЫ</span><span class="sxs-lookup"><span data-stu-id="01640-220">PROCEDURE NEEDED</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="01640-221">Установите антивирус Microsoft Defender в пассивный режим с помощью ключа реестра</span><span class="sxs-lookup"><span data-stu-id="01640-221">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="01640-222">Если вы используете Windows Server, версию 1803 или Windows Server 2019, можно настроить антивирус Microsoft Defender в пассивный режим, установив следующий ключ реестра:</span><span class="sxs-lookup"><span data-stu-id="01640-222">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="01640-223">Путь: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="01640-223">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="01640-224">Имя: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="01640-224">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="01640-225">Тип: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="01640-225">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="01640-226">Значение: `1`</span><span class="sxs-lookup"><span data-stu-id="01640-226">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="01640-227">Отключение антивируса Microsoft Defender с помощью мастера по удалению ролей и функций</span><span class="sxs-lookup"><span data-stu-id="01640-227">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="01640-228">См. в рублях Install или [Uninstall Roles, Role Services или Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)и use the **Remove Roles and Features Wizard**.</span><span class="sxs-lookup"><span data-stu-id="01640-228">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="01640-229">Когда вы доберется до шага **Features** мастера, уберем **Защитник Windows Features.**</span><span class="sxs-lookup"><span data-stu-id="01640-229">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="01640-230">Если вы **Защитник Windows** в разделе **Защитник Windows Features,** вам будет предложено удалить интерфейс **GUI** параметра для Защитник Windows .</span><span class="sxs-lookup"><span data-stu-id="01640-230">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="01640-231">Антивирус Microsoft Defender по-прежнему будет работать нормально без пользовательского интерфейса, но  пользовательский интерфейс не может быть включен, если отключить Защитник Windows функцию.</span><span class="sxs-lookup"><span data-stu-id="01640-231">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="01640-232">Отключение пользовательского интерфейса антивируса Microsoft Defender с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="01640-232">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="01640-233">Чтобы отключить интерфейс антивирусного интерфейса Microsoft Defender, используйте следующий комдлет PowerShell:</span><span class="sxs-lookup"><span data-stu-id="01640-233">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="01640-234">Используете ли вы Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="01640-234">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="01640-235">Если вы используете Windows Server 2016 и сторонний антивирусный продукт, который не предлагается или не разрабатывается Корпорацией Майкрософт, необходимо отключить или удалить антивирус Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="01640-235">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="01640-236">Вы не можете удалить приложение Безопасности Windows, но вы можете отключить интерфейс с этими инструкциями.</span><span class="sxs-lookup"><span data-stu-id="01640-236">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="01640-237">Следующий кодлет PowerShell отстрагирует антивирус Microsoft Defender на Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="01640-237">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="01640-238">Чтобы отключить антивирус Microsoft Defender на Windows Server 2016, используйте следующий cmdlet PowerShell:</span><span class="sxs-lookup"><span data-stu-id="01640-238">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="01640-239">См. также</span><span class="sxs-lookup"><span data-stu-id="01640-239">See also</span></span>

- [<span data-ttu-id="01640-240">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="01640-240">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="01640-241">Совместимость антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="01640-241">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
