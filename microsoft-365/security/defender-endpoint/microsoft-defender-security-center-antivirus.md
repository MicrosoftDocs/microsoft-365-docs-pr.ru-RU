---
title: Антивирус Microsoft Defender в приложении Безопасности Windows
description: С помощью антивируса Microsoft Defender, включенного в приложение Безопасности Windows, вы можете просмотреть, сравнить и выполнить общие задачи.
keywords: wdav, антивирус, брандмауэр, безопасность, окна
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 042bb67c223631ae1759b62a32c2f5713b4d62e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690924"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="bd57d-104">Антивирус Microsoft Defender в приложении Безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="bd57d-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bd57d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="bd57d-105">**Applies to:**</span></span>

- [<span data-ttu-id="bd57d-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="bd57d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bd57d-107">В Windows 10 версии 1703 и более поздней версии Защитник Windows является частью windows Security.</span><span class="sxs-lookup"><span data-stu-id="bd57d-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="bd57d-108">Параметры, которые ранее были частью Защитник Windows и основных параметров Windows, были объединены и перенесены в новое приложение, которое по умолчанию устанавливается в составе Windows 10 версии 1703.</span><span class="sxs-lookup"><span data-stu-id="bd57d-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd57d-109">Отключение службы Центра безопасности Windows не отключит антивирус Microsoft Defender [или Защитник Windows брандмауэра.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="bd57d-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="bd57d-110">Они автоматически отключаются при установке сторонних антивирусных или брандмауэрных продуктов.</span><span class="sxs-lookup"><span data-stu-id="bd57d-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="bd57d-111">Если вы отключаете службу Центра безопасности Windows или настраивайте связанные с ней параметры групповой политики, чтобы предотвратить ее запуск или запуск, приложение Windows Security может отображать устаревшие или неточные сведения о любых антивирусных или брандмауэрных продуктах, установленных на устройстве.</span><span class="sxs-lookup"><span data-stu-id="bd57d-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="bd57d-112">Это также может помешать антивирусу Microsoft Defender включить себя, если у вас есть старый или устаревший сторонний антивирус, или если вы отключаете все сторонние антивирусные продукты, которые вы могли установить ранее.</span><span class="sxs-lookup"><span data-stu-id="bd57d-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="bd57d-113">Это значительно снижает защиту устройства и может привести к заражению вредоносными программами.</span><span class="sxs-lookup"><span data-stu-id="bd57d-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="bd57d-114">Дополнительные [сведения](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) о других функций безопасности Windows, которые можно отслеживать в приложении, см. в статье Windows Security.</span><span class="sxs-lookup"><span data-stu-id="bd57d-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="bd57d-115">Приложение Windows Security — это клиентский интерфейс в Windows 10 версии 1703 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="bd57d-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="bd57d-116">Это не веб-портал Центра безопасности Microsoft Defender, который используется для проверки и управления [Microsoft Defender для конечной точки.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="bd57d-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="bd57d-117">Просмотр параметров защиты от вирусов и угроз в приложении Безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="bd57d-117">Review virus and threat protection settings in the Windows Security app</span></span>

![Снимок экрана метки & защиты от угроз в приложении Windows Security](images/defender/wdav-protection-settings-wdsc.png)

1. <span data-ttu-id="bd57d-119">Откройте приложение Безопасности Windows, щелкнув значок щита в панели задач или нажав меню пусков для **Defender.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="bd57d-120">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="bd57d-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="bd57d-121">В следующих разделах описывается выполнение некоторых наиболее распространенных задач при просмотре или взаимодействии с защитой от угроз, предоставляемой антивирусом Microsoft Defender в приложении Windows Security.</span><span class="sxs-lookup"><span data-stu-id="bd57d-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="bd57d-122">Если эти параметры настроены и развернуты с помощью групповой политики, описанные в этом разделе параметры будут серыми и недоступны для использования в отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="bd57d-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="bd57d-123">Изменения, внесенные с помощью объекта групповой политики, сначала должны быть развернуты в отдельных конечных точках, прежде чем параметр будет обновлен в параметрах Windows.</span><span class="sxs-lookup"><span data-stu-id="bd57d-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="bd57d-124">В разделе Настройка взаимодействия конечных пользователей с [антивирусной программой Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md) описывается настройка параметров переопределения локальной политики.</span><span class="sxs-lookup"><span data-stu-id="bd57d-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="bd57d-125">Выполнить сканирование с помощью приложения Безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="bd57d-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="bd57d-126">Откройте приложение Безопасности Windows, ищем меню пуск для **безопасности,** а затем выберите **Службу безопасности Windows.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd57d-127">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="bd57d-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd57d-128">Выберите **быстрое сканирование.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-128">Select **Quick scan**.</span></span> <span data-ttu-id="bd57d-129">Или, чтобы выполнить полное сканирование, выберите **параметры сканирования,** а затем выберите параметр, например **полное сканирование.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="bd57d-130">Просмотрите версию обновления аналитики безопасности и скачайте последние обновления в приложении Безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="bd57d-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

![Сведения о номере версии версии безопасности](images/defender/wdav-wdsc-defs.png)

1. <span data-ttu-id="bd57d-132">Откройте приложение Безопасности Windows, ищем меню пуск для *безопасности,* а затем выберите **Службу безопасности Windows.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd57d-133">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="bd57d-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd57d-134">Выберите **обновления & защиты от угроз.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="bd57d-135">Установленная в настоящее время версия отображается вместе с некоторыми сведениями о том, когда она была загружена.</span><span class="sxs-lookup"><span data-stu-id="bd57d-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="bd57d-136">Вы можете проверить текущий с последней версией, доступной для ручной загрузки, или просмотреть журнал изменений для этой версии.</span><span class="sxs-lookup"><span data-stu-id="bd57d-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="bd57d-137">Сведения [о безопасности см. в обновлениях для антивируса Microsoft Defender и других антивирусных программ Майкрософт.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="bd57d-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="bd57d-138">Выберите **Проверьте обновления для** загрузки новых обновлений защиты (если они имеются).</span><span class="sxs-lookup"><span data-stu-id="bd57d-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="bd57d-139">Убедитесь, что антивирус Microsoft Defender включен в приложении Безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="bd57d-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="bd57d-140">Откройте приложение Безопасности Windows, ищем меню пуск для *безопасности,* а затем выберите **Службу безопасности Windows.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd57d-141">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="bd57d-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd57d-142">Выберите **параметры & защиты от угроз.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="bd57d-143">Переключатель защиты **в режиме реального времени** на **включение**.</span><span class="sxs-lookup"><span data-stu-id="bd57d-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd57d-144">Если отключить защиту в режиме **реального** времени, она автоматически включается после короткой задержки.</span><span class="sxs-lookup"><span data-stu-id="bd57d-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="bd57d-145">Это необходимо для защиты от вредоносных программ и угроз.</span><span class="sxs-lookup"><span data-stu-id="bd57d-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="bd57d-146">Если вы устанавливаете другой антивирусный продукт, антивирус Microsoft Defender автоматически отключает себя и указывается как таковой в приложении Windows Security.</span><span class="sxs-lookup"><span data-stu-id="bd57d-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="bd57d-147">Появится параметр, который позволит включить [ограниченное периодическое сканирование.](limited-periodic-scanning-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="bd57d-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="bd57d-148">Добавление исключений для антивируса Microsoft Defender в приложении Безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="bd57d-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="bd57d-149">Откройте приложение Безопасности Windows, ищем меню пуск для *безопасности,* а затем выберите **Службу безопасности Windows.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd57d-150">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="bd57d-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd57d-151">В статье **Управление настройками** выберите **параметры защиты & вирусов.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="bd57d-152">В **параметре Исключения** выберите **Добавить или удалить исключения.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="bd57d-153">Выберите значок плюс () для выбора типа и **+** настройки параметров для каждого исключения.</span><span class="sxs-lookup"><span data-stu-id="bd57d-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="bd57d-154">В следующей таблице обобщены типы исключений и то, что происходит:</span><span class="sxs-lookup"><span data-stu-id="bd57d-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="bd57d-155">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="bd57d-155">Exclusion type</span></span>  |<span data-ttu-id="bd57d-156">Определенный</span><span class="sxs-lookup"><span data-stu-id="bd57d-156">Defined by</span></span>  |<span data-ttu-id="bd57d-157">Что происходит</span><span class="sxs-lookup"><span data-stu-id="bd57d-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bd57d-158">**File**</span><span class="sxs-lookup"><span data-stu-id="bd57d-158">**File**</span></span> |<span data-ttu-id="bd57d-159">Расположение</span><span class="sxs-lookup"><span data-stu-id="bd57d-159">Location</span></span> <br/><span data-ttu-id="bd57d-160">Пример: `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="bd57d-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="bd57d-161">Определенный файл пропускается антивирусом Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bd57d-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="bd57d-162">**Folder**</span><span class="sxs-lookup"><span data-stu-id="bd57d-162">**Folder**</span></span>    |<span data-ttu-id="bd57d-163">Расположение</span><span class="sxs-lookup"><span data-stu-id="bd57d-163">Location</span></span> <br/><span data-ttu-id="bd57d-164">Пример: `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="bd57d-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="bd57d-165">Все элементы в указанной папке пропускаются антивирусом Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bd57d-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="bd57d-166">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="bd57d-166">**File type**</span></span>   |<span data-ttu-id="bd57d-167">Расширение файла</span><span class="sxs-lookup"><span data-stu-id="bd57d-167">File extension</span></span> <br/><span data-ttu-id="bd57d-168">Пример: `.test`</span><span class="sxs-lookup"><span data-stu-id="bd57d-168">Example: `.test`</span></span> |<span data-ttu-id="bd57d-169">Все файлы с `.test` расширением в любом месте устройства пропускаются антивирусом Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bd57d-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="bd57d-170">**Процесс**</span><span class="sxs-lookup"><span data-stu-id="bd57d-170">**Process**</span></span>     |<span data-ttu-id="bd57d-171">Путь к исполняемым файлам</span><span class="sxs-lookup"><span data-stu-id="bd57d-171">Executable file path</span></span> <br><span data-ttu-id="bd57d-172">Пример: `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="bd57d-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="bd57d-173">Определенный процесс и все файлы, открытые этим процессом, пропускаются антивирусом Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bd57d-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="bd57d-174">Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.</span><span class="sxs-lookup"><span data-stu-id="bd57d-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="bd57d-175">Настройка и проверка исключений в зависимости от расположения расширения файлов и папок</span><span class="sxs-lookup"><span data-stu-id="bd57d-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="bd57d-176">Настройка исключений для файлов, открытых процессами</span><span class="sxs-lookup"><span data-stu-id="bd57d-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="bd57d-177">Просмотр истории обнаружения угроз в приложении Защитник Windows Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="bd57d-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="bd57d-178">Откройте приложение Безопасности Windows, ищем меню пуск для *безопасности,* а затем выберите **Службу безопасности Windows.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd57d-179">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="bd57d-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd57d-180">Выберите **историю защиты.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-180">Select **Protection history**.</span></span> <span data-ttu-id="bd57d-181">Все последние элементы перечислены.</span><span class="sxs-lookup"><span data-stu-id="bd57d-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="bd57d-182">Настройка параметров защиты и восстановления программ-вымогателей</span><span class="sxs-lookup"><span data-stu-id="bd57d-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="bd57d-183">Откройте приложение Безопасности Windows, ищем меню пуск для *безопасности,* а затем выберите **Службу безопасности Windows.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd57d-184">Выберите **плитку защиты & вирусов** (или значок щита в левой панели меню).</span><span class="sxs-lookup"><span data-stu-id="bd57d-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd57d-185">Под **защитой вымогателей** выберите **Управление защитой вымогателей.**</span><span class="sxs-lookup"><span data-stu-id="bd57d-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="bd57d-186">Чтобы изменить **параметры доступа к** управляемым папкам, см. в руб. Защита важных [папок с управляемым доступом к папкам.](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="bd57d-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="bd57d-187">Чтобы настроить параметры восстановления  программ-вымогателей, выберите Настройка в рамках восстановления данных вымогателей и следуйте инструкциям по увязке или настройке учетной записи OneDrive, чтобы вы могли легко восстановиться после атаки вымогателей. </span><span class="sxs-lookup"><span data-stu-id="bd57d-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd57d-188">См. также</span><span class="sxs-lookup"><span data-stu-id="bd57d-188">See also</span></span>
- [<span data-ttu-id="bd57d-189">Антивирус Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bd57d-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)