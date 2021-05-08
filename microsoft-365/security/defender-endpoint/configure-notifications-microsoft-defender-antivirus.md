---
title: Настройка уведомлений о антивирусных программах Microsoft Defender
description: Узнайте, как настроить и настроить стандартные и дополнительные антивирусные уведомления Microsoft Defender на конечных точках.
keywords: уведомления, защитник, антивирус, конечная точка, управление, администратор
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6e11c9394f250a6f3882183224f53954b1390a23
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274632"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="e50af-104">Настройка уведомлений, которые отображаются в конечных точках</span><span class="sxs-lookup"><span data-stu-id="e50af-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e50af-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e50af-105">**Applies to:**</span></span>

- [<span data-ttu-id="e50af-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e50af-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e50af-107">В Windows 10 уведомления приложений об обнаружении и исправлении вредоносных программ являются более надежными, последовательными и краткими.</span><span class="sxs-lookup"><span data-stu-id="e50af-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="e50af-108">Уведомления отображаются на конечных точках при завершении ручного и запланированного сканирования и обнаружении угроз.</span><span class="sxs-lookup"><span data-stu-id="e50af-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="e50af-109">Эти уведомления также отображаются в **Центре** уведомлений, а сводка о проверках и обнаружениях угроз появляется через регулярные промежутки времени.</span><span class="sxs-lookup"><span data-stu-id="e50af-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="e50af-110">Можно также настроить, как стандартные уведомления отображаются на конечных точках, например уведомления о перезагрузке или при обнаружении и устранении угрозы.</span><span class="sxs-lookup"><span data-stu-id="e50af-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="e50af-111">Настройка дополнительных уведомлений, которые отображаются на конечных точках</span><span class="sxs-lookup"><span data-stu-id="e50af-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="e50af-112">Вы можете настроить отображение дополнительных уведомлений, например недавних сводок обнаружения угроз, в приложении [Windows Security](microsoft-defender-security-center-antivirus.md) и групповой политике.</span><span class="sxs-lookup"><span data-stu-id="e50af-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="e50af-113">В Windows 10, версии 1607  функция называлась Расширенные уведомления и может быть настроена в windows **Settings**  >  **Update &** безопасности  >  **Защитник Windows**.</span><span class="sxs-lookup"><span data-stu-id="e50af-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="e50af-114">В параметрах групповой политики во всех версиях Windows 10 он называется **Расширенные уведомления.**</span><span class="sxs-lookup"><span data-stu-id="e50af-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e50af-115">Отключение дополнительных уведомлений не отключит важные уведомления, такие как обнаружение угрозы и оповещения о исправлении.</span><span class="sxs-lookup"><span data-stu-id="e50af-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="e50af-116">**Чтобы отключить дополнительные уведомления, используйте приложение Windows Security.**</span><span class="sxs-lookup"><span data-stu-id="e50af-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="e50af-117">Откройте приложение Безопасности Windows, щелкнув значок щита в панели задач или нажав меню пусков для **Defender.**</span><span class="sxs-lookup"><span data-stu-id="e50af-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="e50af-118">Щелкните **плитку** защиты & вирусов (или значок щита в левой панели меню), а затем **метку** параметров защиты & вирусов:</span><span class="sxs-lookup"><span data-stu-id="e50af-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Снимок экрана метки & защиты от угроз в приложении Windows Security](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="e50af-120">Прокрутите в раздел **Уведомления** и нажмите **кнопку Изменить параметры уведомлений.**</span><span class="sxs-lookup"><span data-stu-id="e50af-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="e50af-121">Отключите **или**  включите дополнительные уведомления.</span><span class="sxs-lookup"><span data-stu-id="e50af-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="e50af-122">**Использование групповой политики для отключения дополнительных уведомлений:**</span><span class="sxs-lookup"><span data-stu-id="e50af-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="e50af-123">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e50af-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="e50af-124">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="e50af-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="e50af-125">Щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="e50af-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="e50af-126">Расширь дерево до **компонентов Windows и > Microsoft Defender > Отчеты**.</span><span class="sxs-lookup"><span data-stu-id="e50af-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="e50af-127">Дважды **щелкните Кнопку Отключение расширенных уведомлений** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="e50af-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="e50af-128">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e50af-128">Click **OK**.</span></span> <span data-ttu-id="e50af-129">Это позволит избежать появления дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="e50af-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="e50af-130">Настройка стандартных уведомлений на конечных точках</span><span class="sxs-lookup"><span data-stu-id="e50af-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="e50af-131">Групповую политику можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="e50af-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="e50af-132">Отображение дополнительного настраиваемного текста в конечных точках, когда пользователю необходимо выполнить действие</span><span class="sxs-lookup"><span data-stu-id="e50af-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="e50af-133">Скрыть все уведомления в конечных точках</span><span class="sxs-lookup"><span data-stu-id="e50af-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="e50af-134">Скрыть уведомления о перезагрузке в конечных точках</span><span class="sxs-lookup"><span data-stu-id="e50af-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="e50af-135">Сокрытие уведомлений может быть полезно в ситуациях, когда нельзя скрыть весь антивирусный интерфейс Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e50af-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="e50af-136">Дополнительные сведения см. в дополнительных сведениях о том, как запретить пользователям видеть и взаимодействовать с пользовательским интерфейсом [антивируса Microsoft Defender.](prevent-end-user-interaction-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e50af-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="e50af-137">Сокрытие уведомлений будет происходить только в конечных точках, в которые была развернута политика.</span><span class="sxs-lookup"><span data-stu-id="e50af-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="e50af-138">Уведомления, связанные с действиями, которые необходимо принять (например, перезагрузка), по-прежнему будут отображаться на панели мониторинга мониторинга конечной точки и отчетах [Microsoft Endpoint Manager Endpoint Protection.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="e50af-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="e50af-139">Инструкции по добавлению пользовательских контактных данных в уведомления, которые пользователи видят на компьютерах, см. в приложении [Customize the Windows Security](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) для организации.</span><span class="sxs-lookup"><span data-stu-id="e50af-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="e50af-140">**Используйте групповую политику для сокрытия уведомлений:**</span><span class="sxs-lookup"><span data-stu-id="e50af-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="e50af-141">На компьютере управления групповой [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))политикой откройте консоль управления групповой политикой, щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e50af-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="e50af-142">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="e50af-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="e50af-143">Расширь дерево до **компонентов Windows и > антивируса Microsoft Defender > клиентского интерфейса.**</span><span class="sxs-lookup"><span data-stu-id="e50af-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="e50af-144">Дважды нажмите **кнопку Подавления всех уведомлений** и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="e50af-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="e50af-145">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e50af-145">Click **OK**.</span></span> <span data-ttu-id="e50af-146">Это позволит избежать появления дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="e50af-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="e50af-147">**Используйте групповую политику для сокрытия уведомлений о перезагрузке:**</span><span class="sxs-lookup"><span data-stu-id="e50af-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="e50af-148">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, и нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e50af-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="e50af-149">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="e50af-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="e50af-150">Щелкните **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="e50af-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="e50af-151">Расширь дерево до **компонентов Windows и > антивируса Microsoft Defender > клиентского интерфейса.**</span><span class="sxs-lookup"><span data-stu-id="e50af-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="e50af-152">Дважды нажмите **кнопку Подавляет уведомления о** перезагрузке и установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="e50af-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="e50af-153">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e50af-153">Click **OK**.</span></span> <span data-ttu-id="e50af-154">Это позволит избежать появления дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="e50af-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e50af-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e50af-155">Related topics</span></span>

- [<span data-ttu-id="e50af-156">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="e50af-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="e50af-157">Настройка взаимодействия между конечными пользователями с антивирусом Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e50af-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)