---
title: Настройка антивирусная программа в Microsoft Defender уведомлений
description: Узнайте, как настроить и настроить стандартные и дополнительные уведомления антивирусная программа в Microsoft Defender конечных точек.
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
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 1e9f733b20b62af7e73a923932057920ff1dc155
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926242"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="92842-104">Настройка уведомлений, отображающихся в конечных точках</span><span class="sxs-lookup"><span data-stu-id="92842-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="92842-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="92842-105">**Applies to:**</span></span>

- [<span data-ttu-id="92842-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="92842-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="92842-107">В Windows 10 приложения уведомления об обнаружении и исправлении вредоносных программ являются более надежными, последовательными и краткими.</span><span class="sxs-lookup"><span data-stu-id="92842-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="92842-108">Уведомления отображаются на конечных точках при завершении ручного и запланированного сканирования и обнаружении угроз.</span><span class="sxs-lookup"><span data-stu-id="92842-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="92842-109">Эти уведомления также отображаются в **Центре** уведомлений, а сводка о проверках и обнаружениях угроз появляется через регулярные промежутки времени.</span><span class="sxs-lookup"><span data-stu-id="92842-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="92842-110">Можно также настроить, как стандартные уведомления отображаются на конечных точках, например уведомления о перезагрузке или при обнаружении и устранении угрозы.</span><span class="sxs-lookup"><span data-stu-id="92842-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="92842-111">Настройка дополнительных уведомлений, которые отображаются на конечных точках</span><span class="sxs-lookup"><span data-stu-id="92842-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="92842-112">Вы можете настроить отображение дополнительных уведомлений, например недавних [](microsoft-defender-security-center-antivirus.md) сводок обнаружения угроз, в приложении Безопасность Windows и групповой политике.</span><span class="sxs-lookup"><span data-stu-id="92842-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="92842-113">В Windows 10 версии 1607 функция называлась  Расширенные уведомления и могла быть настроена в соответствии с Windows Параметры  >  **update & безопасности**  >  **Защитник Windows**.</span><span class="sxs-lookup"><span data-stu-id="92842-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="92842-114">В параметрах групповой политики во всех версиях Windows 10 это называется **Расширенные уведомления.**</span><span class="sxs-lookup"><span data-stu-id="92842-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92842-115">Отключение дополнительных уведомлений не отключит важные уведомления, такие как обнаружение угрозы и оповещения о исправлении.</span><span class="sxs-lookup"><span data-stu-id="92842-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="92842-116">**Используйте приложение Безопасность Windows для отключения дополнительных уведомлений:**</span><span class="sxs-lookup"><span data-stu-id="92842-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="92842-117">Откройте приложение Безопасность Windows, щелкнув значок щита в панели задач или нажав меню пусков для **безопасности.**</span><span class="sxs-lookup"><span data-stu-id="92842-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="92842-118">Выберите **плитку &** угрозы (или значок щита в левой панели меню) и выберите параметры защиты **& вирусов**</span><span class="sxs-lookup"><span data-stu-id="92842-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="92842-119">Прокрутите в раздел **Уведомления** и нажмите **кнопку Изменить параметры уведомлений.**</span><span class="sxs-lookup"><span data-stu-id="92842-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="92842-120">Отключите **или**  включите дополнительные уведомления.</span><span class="sxs-lookup"><span data-stu-id="92842-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="92842-121">**Использование групповой политики для отключения дополнительных уведомлений:**</span><span class="sxs-lookup"><span data-stu-id="92842-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="92842-122">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="92842-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="92842-123">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="92842-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="92842-124">Щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="92842-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="92842-125">Расширь **дерево до Windows компонентов > антивирусная программа в Microsoft Defender > отчетов.**</span><span class="sxs-lookup"><span data-stu-id="92842-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="92842-126">Дважды **щелкните Кнопку Отключение расширенных уведомлений** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="92842-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="92842-127">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="92842-127">Click **OK**.</span></span> <span data-ttu-id="92842-128">Это позволит избежать появления дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="92842-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="92842-129">Настройка стандартных уведомлений на конечных точках</span><span class="sxs-lookup"><span data-stu-id="92842-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="92842-130">Групповую политику можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="92842-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="92842-131">Отображение дополнительного настраиваемного текста в конечных точках, когда пользователю необходимо выполнить действие</span><span class="sxs-lookup"><span data-stu-id="92842-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="92842-132">Скрыть все уведомления в конечных точках</span><span class="sxs-lookup"><span data-stu-id="92842-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="92842-133">Скрыть уведомления о перезагрузке в конечных точках</span><span class="sxs-lookup"><span data-stu-id="92842-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="92842-134">Сокрытие уведомлений может быть полезно в ситуациях, когда нельзя скрыть весь интерфейс антивирусная программа в Microsoft Defender интерфейса.</span><span class="sxs-lookup"><span data-stu-id="92842-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="92842-135">Дополнительные [сведения см. в](prevent-end-user-interaction-microsoft-defender-antivirus.md) см. в антивирусная программа в Microsoft Defender пользователей.</span><span class="sxs-lookup"><span data-stu-id="92842-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="92842-136">Сокрытие уведомлений будет происходить только в конечных точках, в которые была развернута политика.</span><span class="sxs-lookup"><span data-stu-id="92842-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="92842-137">Уведомления, связанные с действиями, которые должны быть приняты (например, перезагрузка), по-прежнему будут отображаться на панели мониторинга Microsoft Endpoint Manager Endpoint Protection мониторинга [и отчетов](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="92842-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="92842-138">См. [в Безопасность Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) для организации инструкции по добавлению пользовательских контактных данных в уведомления, которые пользователи видят на своих компьютерах.</span><span class="sxs-lookup"><span data-stu-id="92842-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="92842-139">**Используйте групповую политику для сокрытия уведомлений:**</span><span class="sxs-lookup"><span data-stu-id="92842-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="92842-140">На компьютере управления групповой [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))политикой откройте консоль управления групповой политикой, щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="92842-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="92842-141">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="92842-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="92842-142">Расширь **дерево, Windows компоненты > антивирусная программа в Microsoft Defender > клиентского интерфейса.**</span><span class="sxs-lookup"><span data-stu-id="92842-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="92842-143">Дважды нажмите **кнопку Подавления всех уведомлений** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="92842-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="92842-144">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="92842-144">Click **OK**.</span></span> <span data-ttu-id="92842-145">Это позволит избежать появления дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="92842-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="92842-146">**Используйте групповую политику для сокрытия уведомлений о перезагрузке:**</span><span class="sxs-lookup"><span data-stu-id="92842-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="92842-147">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="92842-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="92842-148">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="92842-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="92842-149">Щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="92842-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="92842-150">Расширь **дерево, Windows компоненты > антивирусная программа в Microsoft Defender > клиентского интерфейса.**</span><span class="sxs-lookup"><span data-stu-id="92842-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="92842-151">Дважды нажмите **кнопку Подавляет уведомления о** перезагрузке и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="92842-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="92842-152">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="92842-152">Click **OK**.</span></span> <span data-ttu-id="92842-153">Это позволит избежать появления дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="92842-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="92842-154">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="92842-154">Related topics</span></span>

- [<span data-ttu-id="92842-155">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="92842-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="92842-156">Настройка взаимодействия конечных пользователей с антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="92842-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
