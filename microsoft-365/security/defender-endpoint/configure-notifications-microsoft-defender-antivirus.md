---
title: Настройка антивирусная программа в Microsoft Defender уведомлений
description: Узнайте, как настроить и настроить стандартные и другие антивирусная программа в Microsoft Defender на конечных точках.
keywords: уведомления, защитник, антивирус, конечная точка, управление, администратор
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985412"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a><span data-ttu-id="21f88-104">Настройка антивирусная программа в Microsoft Defender уведомлений, которые отображаются в конечных точках</span><span class="sxs-lookup"><span data-stu-id="21f88-104">Configure Microsoft Defender Antivirus notifications that appear on endpoints</span></span>

<span data-ttu-id="21f88-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="21f88-105">**Applies to:**</span></span>

- [<span data-ttu-id="21f88-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="21f88-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="21f88-107">В Windows 10 приложения уведомления об обнаружении и исправлении вредоносных программ являются более надежными, последовательными и краткими.</span><span class="sxs-lookup"><span data-stu-id="21f88-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span> <span data-ttu-id="21f88-108">антивирусная программа в Microsoft Defender уведомления отображаются на конечных точках при завершении сканирования и обнаружении угроз.</span><span class="sxs-lookup"><span data-stu-id="21f88-108">Microsoft Defender Antivirus notifications appear on endpoints when scans are completed and threats are detected.</span></span> <span data-ttu-id="21f88-109">Уведомления следуют как запланированным, так и ручным сканам.</span><span class="sxs-lookup"><span data-stu-id="21f88-109">Notifications follow both scheduled and manually triggered scans.</span></span> <span data-ttu-id="21f88-110">Эти уведомления также отображаются в **Центре** уведомлений, а сводка о проверках и обнаружениях угроз появляется через регулярные промежутки времени.</span><span class="sxs-lookup"><span data-stu-id="21f88-110">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="21f88-111">Если вы входите в команду безопасности организации, вы можете настроить, как отображаются уведомления в конечных точках, например уведомления, которые подсказали перезагрузку системы или свидетельствуют об обнаружении и исправлении угрозы.</span><span class="sxs-lookup"><span data-stu-id="21f88-111">If you're part of your organization's security team, you can configure how notifications appear on endpoints, such as notifications that prompt for a system reboot or that indicate a threat has been detected and remediated.</span></span>

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a><span data-ttu-id="21f88-112">Настройка антивирусных уведомлений с помощью групповой политики или Безопасность Windows приложения</span><span class="sxs-lookup"><span data-stu-id="21f88-112">Configure antivirus notifications using Group Policy or the Windows Security app</span></span>

<span data-ttu-id="21f88-113">Вы можете настроить отображение дополнительных уведомлений, например недавних [](microsoft-defender-security-center-antivirus.md) сводок обнаружения угроз, в приложении Безопасность Windows и групповой политике.</span><span class="sxs-lookup"><span data-stu-id="21f88-113">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="21f88-114">В Windows 10 версии 1607 функция называлась  Расширенные уведомления и была настроена в соответствии с Windows Параметры  >  **update & безопасности**  >  **Защитник Windows**.</span><span class="sxs-lookup"><span data-stu-id="21f88-114">In Windows 10, version 1607 the feature was called **Enhanced notifications** and was configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="21f88-115">В параметрах групповой политики для всех версий Windows 10 функция уведомлений называется **Расширенные уведомления.**</span><span class="sxs-lookup"><span data-stu-id="21f88-115">In Group Policy settings for all versions of Windows 10, the notification feature is called **Enhanced notifications**.</span></span>

### <a name="use-group-policy-to-disable-additional-notifications"></a><span data-ttu-id="21f88-116">Использование групповой политики для отключения дополнительных уведомлений</span><span class="sxs-lookup"><span data-stu-id="21f88-116">Use Group Policy to disable additional notifications</span></span>

1. <span data-ttu-id="21f88-117">На компьютере управления групповыми политиками откройте [консоль управления групповыми политиками](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="21f88-117">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="21f88-118">Щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="21f88-118">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="21f88-119">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="21f88-119">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4. <span data-ttu-id="21f88-120">Выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="21f88-120">Select **Administrative templates**.</span></span>

5. <span data-ttu-id="21f88-121">Расширь **дерево и Windows компоненты антивирусная программа в Microsoft Defender**  >   > отчеты\*\*.</span><span class="sxs-lookup"><span data-stu-id="21f88-121">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > Reporting\*\*.</span></span>

6. <span data-ttu-id="21f88-122">Дважды **щелкните Кнопку Отключение расширенных уведомлений** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="21f88-122">Double-click **Turn off enhanced notifications**, and set the option to **Enabled**.</span></span> <span data-ttu-id="21f88-123">После этого нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="21f88-123">Then select **OK**.</span></span> <span data-ttu-id="21f88-124">Это позволит избежать появления дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="21f88-124">This will prevent additional notifications from appearing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21f88-125">Отключение дополнительных уведомлений не отключит важные уведомления, такие как обнаружение угрозы и оповещения о исправлении.</span><span class="sxs-lookup"><span data-stu-id="21f88-125">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a><span data-ttu-id="21f88-126">Использование приложения Безопасность Windows для отключения дополнительных уведомлений</span><span class="sxs-lookup"><span data-stu-id="21f88-126">Use the Windows Security app to disable additional notifications</span></span>

1. <span data-ttu-id="21f88-127">Откройте приложение Безопасность Windows, щелкнув значок щита в панели задач или нажав меню пусков для **безопасности.**</span><span class="sxs-lookup"><span data-stu-id="21f88-127">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="21f88-128">Выберите **плитку &** угрозы (или значок щита в левой панели меню) и выберите параметры защиты **& вирусов**</span><span class="sxs-lookup"><span data-stu-id="21f88-128">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="21f88-129">Прокрутите в раздел **Уведомления** и выберите **параметры уведомлений об изменении.**</span><span class="sxs-lookup"><span data-stu-id="21f88-129">Scroll to the **Notifications** section and select **Change notification settings**.</span></span>

4. <span data-ttu-id="21f88-130">Отключите **или**  включите дополнительные уведомления.</span><span class="sxs-lookup"><span data-stu-id="21f88-130">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21f88-131">Отключение дополнительных уведомлений не отключит важные уведомления, такие как обнаружение угрозы и оповещения о исправлении.</span><span class="sxs-lookup"><span data-stu-id="21f88-131">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a><span data-ttu-id="21f88-132">Настройка стандартных уведомлений в конечных точках с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="21f88-132">Configure standard notifications on endpoints using Group Policy</span></span>

<span data-ttu-id="21f88-133">Групповую политику можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="21f88-133">You can use Group Policy to:</span></span>

- <span data-ttu-id="21f88-134">Отображение дополнительного настраиваемного текста в конечных точках, когда пользователю необходимо выполнить действие</span><span class="sxs-lookup"><span data-stu-id="21f88-134">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="21f88-135">Скрыть все уведомления в конечных точках</span><span class="sxs-lookup"><span data-stu-id="21f88-135">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="21f88-136">Скрыть уведомления о перезагрузке в конечных точках</span><span class="sxs-lookup"><span data-stu-id="21f88-136">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="21f88-137">Сокрытие уведомлений может быть полезно в ситуациях, когда нельзя скрыть весь интерфейс антивирусная программа в Microsoft Defender интерфейса.</span><span class="sxs-lookup"><span data-stu-id="21f88-137">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="21f88-138">Дополнительные [сведения см. в](prevent-end-user-interaction-microsoft-defender-antivirus.md) см. в антивирусная программа в Microsoft Defender пользователей.</span><span class="sxs-lookup"><span data-stu-id="21f88-138">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> <span data-ttu-id="21f88-139">Сокрытие уведомлений будет происходить только в конечных точках, в которые была развернута политика.</span><span class="sxs-lookup"><span data-stu-id="21f88-139">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="21f88-140">Уведомления, связанные с действиями, которые должны быть приняты (например, перезагрузка), по-прежнему будут отображаться на панели мониторинга Microsoft Endpoint Manager Endpoint Protection мониторинга [и отчетов](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="21f88-140">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="21f88-141">Чтобы добавить пользовательские контактные данные в конечные уведомления, см. в Безопасность Windows [приложения для вашей организации.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="21f88-141">To add custom contact information to endpoint notifications, see [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).</span></span>

### <a name="use-group-policy-to-hide-notifications"></a><span data-ttu-id="21f88-142">Использование групповой политики для сокрытия уведомлений</span><span class="sxs-lookup"><span data-stu-id="21f88-142">Use Group Policy to hide notifications</span></span>

1. <span data-ttu-id="21f88-143">На компьютере управления групповыми политиками откройте [консоль управления групповыми политиками](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="21f88-143">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="21f88-144">Щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="21f88-144">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="21f88-145">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="21f88-145">In the **Group Policy Management Editor** go to **Computer configuration** and then select **Administrative templates**.</span></span>

4. <span data-ttu-id="21f88-146">Расширь **дерево, Windows компоненты антивирусная программа в Microsoft Defender**  >    >  **клиентского интерфейса.**</span><span class="sxs-lookup"><span data-stu-id="21f88-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span> 

5. <span data-ttu-id="21f88-147">Дважды нажмите **кнопку Подавления всех уведомлений** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="21f88-147">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="21f88-148">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="21f88-148">Select **OK**.</span></span> <span data-ttu-id="21f88-149">Это позволит избежать появления дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="21f88-149">This will prevent additional notifications from appearing.</span></span>

### <a name="use-group-policy-to-hide-reboot-notifications"></a><span data-ttu-id="21f88-150">Использование групповой политики для сокрытия уведомлений о перезагрузке</span><span class="sxs-lookup"><span data-stu-id="21f88-150">Use Group Policy to hide reboot notifications</span></span>

1. <span data-ttu-id="21f88-151">На компьютере управления групповыми политиками откройте [консоль управления групповыми политиками](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="21f88-151">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="21f88-152">Щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="21f88-152">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

2. <span data-ttu-id="21f88-153">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="21f88-153">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="21f88-154">Щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="21f88-154">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="21f88-155">Расширь **дерево, Windows компоненты антивирусная программа в Microsoft Defender**  >    >  **клиентского интерфейса.**</span><span class="sxs-lookup"><span data-stu-id="21f88-155">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span>

5. <span data-ttu-id="21f88-156">Дважды нажмите **кнопку Подавляет уведомления о** перезагрузке и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="21f88-156">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> 

5. <span data-ttu-id="21f88-157">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="21f88-157">Select **OK**.</span></span> <span data-ttu-id="21f88-158">Это позволит избежать появления дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="21f88-158">This will prevent additional notifications from appearing.</span></span>

