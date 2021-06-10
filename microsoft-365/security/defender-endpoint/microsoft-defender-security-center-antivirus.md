---
title: антивирусная программа в Microsoft Defender в приложении Безопасность Windows
description: Если антивирусная программа в Microsoft Defender теперь включено в Безопасность Windows, вы можете просмотреть, сравнить и выполнить общие задачи.
keywords: wdav, антивирус, брандмауэр, безопасность, окна
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ccb0d4cf168bbb4d3c1575c1e6611829909d0817
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275412"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="db46a-104">антивирусная программа в Microsoft Defender в приложении Безопасность Windows</span><span class="sxs-lookup"><span data-stu-id="db46a-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="db46a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="db46a-105">**Applies to:**</span></span>

- [<span data-ttu-id="db46a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="db46a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="db46a-107">В Windows 10 версии 1703 и более поздней версии Защитник Windows приложение является частью Безопасность Windows.</span><span class="sxs-lookup"><span data-stu-id="db46a-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="db46a-108">Параметры, которые ранее были частью Защитник Windows и основного Windows Параметры, были объединены и перемещены в новое приложение, установленное по умолчанию в Windows 10 версии 1703.</span><span class="sxs-lookup"><span data-stu-id="db46a-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db46a-109">Отключение Безопасность Windows центра не отключит антивирусная программа в Microsoft Defender [или брандмауэр Защитника Windows.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="db46a-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="db46a-110">Они автоматически отключаются при установке сторонних антивирусных или брандмауэрных продуктов.</span><span class="sxs-lookup"><span data-stu-id="db46a-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="db46a-111">Если отключить службу центра Безопасность Windows или настроить связанные с ней параметры групповой политики, чтобы предотвратить ее запуск или запуск, приложение Безопасность Windows может отображать устаревшие или неточные сведения о любых антивирусных или брандмауэрных продуктах, установленных на устройстве.</span><span class="sxs-lookup"><span data-stu-id="db46a-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="db46a-112">Это также может антивирусная программа в Microsoft Defender, если у вас есть старый или устаревший сторонний антивирус или если вы отключаете все сторонние антивирусные продукты, которые вы могли установить ранее.</span><span class="sxs-lookup"><span data-stu-id="db46a-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="db46a-113">Это значительно снижает защиту устройства и может привести к заражению вредоносными программами.</span><span class="sxs-lookup"><span data-stu-id="db46a-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="db46a-114">Дополнительные [сведения о](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) других Windows, которые можно отслеживать в приложении, см. в Безопасность Windows статье.</span><span class="sxs-lookup"><span data-stu-id="db46a-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="db46a-115">Приложение Безопасность Windows — это клиентский интерфейс Windows 10 версии 1703 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="db46a-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="db46a-116">Это не веб Центр безопасности в Microsoft Defender портал, который используется для просмотра и управления [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span><span class="sxs-lookup"><span data-stu-id="db46a-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="db46a-117">Просмотр параметров защиты от вирусов и угроз в приложении Безопасность Windows</span><span class="sxs-lookup"><span data-stu-id="db46a-117">Review virus and threat protection settings in the Windows Security app</span></span>

![Снимок экрана: метка параметров защиты от вирусов и угроз в приложении "Безопасность Windows"](images/defender/wdav-protection-settings-wdsc.png)

1. <span data-ttu-id="db46a-119">Откройте приложение Безопасность Windows, щелкнув значок щита в панели задач или нажав меню пусков для **Defender.**</span><span class="sxs-lookup"><span data-stu-id="db46a-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="db46a-120">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="db46a-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="db46a-121">В следующих разделах описывается выполнение некоторых наиболее распространенных задач при просмотре или взаимодействии с защитой от угроз, предоставляемой антивирусная программа в Microsoft Defender в Безопасность Windows приложении.</span><span class="sxs-lookup"><span data-stu-id="db46a-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="db46a-122">Если эти параметры настроены и развернуты с помощью групповой политики, описанные в этом разделе параметры будут серыми и недоступны для использования в отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="db46a-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="db46a-123">Изменения, внесенные с помощью объекта групповой политики, необходимо сначала развернуть на отдельных конечных точках, прежде чем параметр будет обновлен в настройках Windows.</span><span class="sxs-lookup"><span data-stu-id="db46a-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="db46a-124">В [разделе Configure end-user interaction with антивирусная программа в Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md) описывается настройка параметров переопределения локальной политики.</span><span class="sxs-lookup"><span data-stu-id="db46a-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="db46a-125">Запуск сканирования с помощью Безопасность Windows приложения</span><span class="sxs-lookup"><span data-stu-id="db46a-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="db46a-126">Откройте приложение Безопасность Windows, ища меню пуск для **безопасности,** а затем **выберите Безопасность Windows**.</span><span class="sxs-lookup"><span data-stu-id="db46a-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="db46a-127">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="db46a-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="db46a-128">Выберите **быстрое сканирование.**</span><span class="sxs-lookup"><span data-stu-id="db46a-128">Select **Quick scan**.</span></span> <span data-ttu-id="db46a-129">Или, чтобы выполнить полное сканирование, выберите **параметры сканирования,** а затем выберите параметр, например **полное сканирование.**</span><span class="sxs-lookup"><span data-stu-id="db46a-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="db46a-130">Просмотрите версию обновления сведении безопасности и скачайте последние обновления в Безопасность Windows приложении</span><span class="sxs-lookup"><span data-stu-id="db46a-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

![Сведения о номере версии версии безопасности](images/defender/wdav-wdsc-defs.png)

1. <span data-ttu-id="db46a-132">Откройте приложение Безопасность Windows, ища меню пуск для *безопасности,* а затем **выберите Безопасность Windows**.</span><span class="sxs-lookup"><span data-stu-id="db46a-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="db46a-133">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="db46a-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="db46a-134">Выберите **обновления & защиты от угроз.**</span><span class="sxs-lookup"><span data-stu-id="db46a-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="db46a-135">Установленная в настоящее время версия отображается вместе с некоторыми сведениями о том, когда она была загружена.</span><span class="sxs-lookup"><span data-stu-id="db46a-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="db46a-136">Вы можете проверить текущий с последней версией, доступной для ручной загрузки, или просмотреть журнал изменений для этой версии.</span><span class="sxs-lookup"><span data-stu-id="db46a-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="db46a-137">Сведения [о безопасности см. в антивирусная программа в Microsoft Defender и других антивирусных программах Майкрософт.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="db46a-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="db46a-138">Выберите **Проверьте обновления для** загрузки новых обновлений защиты (если они имеются).</span><span class="sxs-lookup"><span data-stu-id="db46a-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="db46a-139">Убедитесь антивирусная программа в Microsoft Defender включено в приложении Безопасность Windows</span><span class="sxs-lookup"><span data-stu-id="db46a-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="db46a-140">Откройте приложение Безопасность Windows, ища меню пуск для *безопасности,* а затем **выберите Безопасность Windows**.</span><span class="sxs-lookup"><span data-stu-id="db46a-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="db46a-141">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="db46a-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="db46a-142">Выберите **параметры & защиты от угроз.**</span><span class="sxs-lookup"><span data-stu-id="db46a-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="db46a-143">Переключатель защиты **в режиме реального времени** на **включение**.</span><span class="sxs-lookup"><span data-stu-id="db46a-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="db46a-144">Если отключить защиту в режиме **реального** времени, она автоматически включается после короткой задержки.</span><span class="sxs-lookup"><span data-stu-id="db46a-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="db46a-145">Это необходимо для защиты от вредоносных программ и угроз.</span><span class="sxs-lookup"><span data-stu-id="db46a-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="db46a-146">При установке другого антивирусного продукта антивирусная программа в Microsoft Defender автоматически отключает себя и указывается как таковой в Безопасность Windows приложении.</span><span class="sxs-lookup"><span data-stu-id="db46a-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="db46a-147">Появится параметр, который позволит включить [ограниченное периодическое сканирование.](limited-periodic-scanning-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="db46a-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="db46a-148">Добавление исключений для антивирусная программа в Microsoft Defender в приложении Безопасность Windows</span><span class="sxs-lookup"><span data-stu-id="db46a-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="db46a-149">Откройте приложение Безопасность Windows, ища меню пуск для *безопасности,* а затем **выберите Безопасность Windows**.</span><span class="sxs-lookup"><span data-stu-id="db46a-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="db46a-150">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="db46a-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="db46a-151">В статье **Управление настройками** выберите **параметры защиты & вирусов.**</span><span class="sxs-lookup"><span data-stu-id="db46a-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="db46a-152">В **параметре Исключения** выберите **Добавить или удалить исключения.**</span><span class="sxs-lookup"><span data-stu-id="db46a-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="db46a-153">Выберите значок плюс () для выбора типа и **+** настройки параметров для каждого исключения.</span><span class="sxs-lookup"><span data-stu-id="db46a-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="db46a-154">В следующей таблице обобщены типы исключений и то, что происходит:</span><span class="sxs-lookup"><span data-stu-id="db46a-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="db46a-155">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="db46a-155">Exclusion type</span></span>  |<span data-ttu-id="db46a-156">Определенный</span><span class="sxs-lookup"><span data-stu-id="db46a-156">Defined by</span></span>  |<span data-ttu-id="db46a-157">Что происходит</span><span class="sxs-lookup"><span data-stu-id="db46a-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="db46a-158">**Файл**</span><span class="sxs-lookup"><span data-stu-id="db46a-158">**File**</span></span> |<span data-ttu-id="db46a-159">Расположение</span><span class="sxs-lookup"><span data-stu-id="db46a-159">Location</span></span> <br/><span data-ttu-id="db46a-160">Пример: `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="db46a-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="db46a-161">Определенный файл пропускается антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="db46a-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="db46a-162">**Folder**</span><span class="sxs-lookup"><span data-stu-id="db46a-162">**Folder**</span></span>    |<span data-ttu-id="db46a-163">Расположение</span><span class="sxs-lookup"><span data-stu-id="db46a-163">Location</span></span> <br/><span data-ttu-id="db46a-164">Пример: `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="db46a-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="db46a-165">Все элементы в указанной папке пропускаются антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="db46a-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="db46a-166">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="db46a-166">**File type**</span></span>   |<span data-ttu-id="db46a-167">Расширение файла</span><span class="sxs-lookup"><span data-stu-id="db46a-167">File extension</span></span> <br/><span data-ttu-id="db46a-168">Пример: `.test`</span><span class="sxs-lookup"><span data-stu-id="db46a-168">Example: `.test`</span></span> |<span data-ttu-id="db46a-169">Все файлы с `.test` расширением в любом месте устройства пропускаются антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="db46a-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="db46a-170">**Процесс**</span><span class="sxs-lookup"><span data-stu-id="db46a-170">**Process**</span></span>     |<span data-ttu-id="db46a-171">Путь к исполняемым файлам</span><span class="sxs-lookup"><span data-stu-id="db46a-171">Executable file path</span></span> <br><span data-ttu-id="db46a-172">Пример: `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="db46a-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="db46a-173">Определенный процесс и все файлы, открытые этим процессом, пропускаются антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="db46a-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="db46a-174">Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.</span><span class="sxs-lookup"><span data-stu-id="db46a-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="db46a-175">Настройка и проверка исключений в зависимости от расположения расширения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="db46a-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="db46a-176">Настройка исключений для файлов, открытых процессами</span><span class="sxs-lookup"><span data-stu-id="db46a-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="db46a-177">Просмотрите историю обнаружения угроз в приложении Защитник Windows Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="db46a-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="db46a-178">Откройте приложение Безопасность Windows, ища меню пуск для *безопасности,* а затем **выберите Безопасность Windows**.</span><span class="sxs-lookup"><span data-stu-id="db46a-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="db46a-179">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="db46a-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="db46a-180">Выберите **историю защиты.**</span><span class="sxs-lookup"><span data-stu-id="db46a-180">Select **Protection history**.</span></span> <span data-ttu-id="db46a-181">Все последние элементы перечислены.</span><span class="sxs-lookup"><span data-stu-id="db46a-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="db46a-182">Настройка параметров защиты и восстановления программ-вымогателей</span><span class="sxs-lookup"><span data-stu-id="db46a-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="db46a-183">Откройте приложение Безопасность Windows, ища меню пуск для *безопасности,* а затем **выберите Безопасность Windows**.</span><span class="sxs-lookup"><span data-stu-id="db46a-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="db46a-184">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="db46a-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="db46a-185">Под **защитой вымогателей** выберите **Управление защитой вымогателей.**</span><span class="sxs-lookup"><span data-stu-id="db46a-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="db46a-186">Чтобы изменить **параметры доступа к** управляемым папкам, см. в руб. Защита важных [папок с управляемым доступом к папкам.](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="db46a-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="db46a-187">Чтобы настроить параметры восстановления  программ-вымогателей, выберите Настройка в рамках восстановления данных вымогателей и следуйте инструкциям по увязке или настройке учетной записи OneDrive, чтобы вы могли легко восстановиться после атаки вымогателей. </span><span class="sxs-lookup"><span data-stu-id="db46a-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="db46a-188">См. также</span><span class="sxs-lookup"><span data-stu-id="db46a-188">See also</span></span>
- [<span data-ttu-id="db46a-189">Антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="db46a-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)