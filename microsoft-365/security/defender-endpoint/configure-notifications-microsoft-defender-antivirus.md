---
title: Настройка антивирусная программа в Microsoft Defender уведомлений
description: Узнайте, как настроить и настроить как стандартные, так и дополнительные антивирусная программа в Microsoft Defender уведомления на конечных точках.
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
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572349"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="4e073-104">Настройка уведомлений, которые отображаются в конечных точках</span><span class="sxs-lookup"><span data-stu-id="4e073-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="4e073-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4e073-105">**Applies to:**</span></span>

- [<span data-ttu-id="4e073-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4e073-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4e073-107">В Windows 10 время уведомления приложений об обнаружении и исправлении вредоносных программ являются более надежными, последовательными и краткими.</span><span class="sxs-lookup"><span data-stu-id="4e073-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="4e073-108">Уведомления отображаются в конечных точках при ручном срабатывании и завершении планового сканирования и обнаружении угроз.</span><span class="sxs-lookup"><span data-stu-id="4e073-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="4e073-109">Эти уведомления также отображаются в Центре **уведомлений,** и сводка сканирований и обнаружения угроз появляется через регулярные промежутки времени.</span><span class="sxs-lookup"><span data-stu-id="4e073-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="4e073-110">Можно также настроить, как стандартные уведомления отображаются в конечных точках, например уведомления для перезагрузки или когда угроза была обнаружена и исправлена.</span><span class="sxs-lookup"><span data-stu-id="4e073-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="4e073-111">Настройка дополнительных уведомлений, которые отображаются в конечных точках</span><span class="sxs-lookup"><span data-stu-id="4e073-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="4e073-112">Вы можете настроить отображение дополнительных уведомлений, таких как последние сводки обнаружения угроз, [в приложении Безопасность Windows и](microsoft-defender-security-center-antivirus.md) с групповой политикой.</span><span class="sxs-lookup"><span data-stu-id="4e073-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="4e073-113">В Windows 10 версия 1607 эта функция называлась **Расширенные уведомления** и может быть настроена **под Windows Параметры** обновление &  >    >  **безопасности Защитник Windows**.</span><span class="sxs-lookup"><span data-stu-id="4e073-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="4e073-114">В настройках групповой политики во всех Windows 10, она называется **Расширенные уведомления**.</span><span class="sxs-lookup"><span data-stu-id="4e073-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e073-115">Отключение дополнительных уведомлений не отключает критические уведомления, такие как оповещения об обнаружении угроз и исправлении.</span><span class="sxs-lookup"><span data-stu-id="4e073-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="4e073-116">**Используйте приложение Безопасность Windows для отключения дополнительных уведомлений:**</span><span class="sxs-lookup"><span data-stu-id="4e073-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="4e073-117">Откройте приложение Безопасность Windows, нажав значок щита в баре задач или поиск меню старта для **безопасности.**</span><span class="sxs-lookup"><span data-stu-id="4e073-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="4e073-118">Выберите **& защиты** от угроз (или значок щита в левой меню), а затем **выберите настройки & защиты от угроз**</span><span class="sxs-lookup"><span data-stu-id="4e073-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="4e073-119">Прокрутите раздел Уведомления **и нажмите** **Настройки уведомления Изменения**.</span><span class="sxs-lookup"><span data-stu-id="4e073-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="4e073-120">Сдвиньте переключатель **на Выключение** **или Включить,** чтобы отключить или включить дополнительные уведомления.</span><span class="sxs-lookup"><span data-stu-id="4e073-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="4e073-121">**Используйте групповую политику для отключения дополнительных уведомлений:**</span><span class="sxs-lookup"><span data-stu-id="4e073-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="4e073-122">На компьютере управления групповой политикой откройте консоль [управления групповой политикой, нажмите](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопку «Групповой объект политики», которую вы хотите настроить, и нажмите **на Редактировать.**</span><span class="sxs-lookup"><span data-stu-id="4e073-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="4e073-123">В редакторе **управления групповой политикой перейдите** на **компьютерную конфигурацию.**</span><span class="sxs-lookup"><span data-stu-id="4e073-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="4e073-124">Нажмите **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="4e073-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="4e073-125">Расширьте дерево до **Windows компонентов > антивирусная программа в Microsoft Defender > отчетности.**</span><span class="sxs-lookup"><span data-stu-id="4e073-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="4e073-126">Дважды **нажмите Выключите расширенные уведомления** и установите опцию **enabled**.</span><span class="sxs-lookup"><span data-stu-id="4e073-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="4e073-127">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4e073-127">Click **OK**.</span></span> <span data-ttu-id="4e073-128">Это предотвратит появление дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="4e073-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="4e073-129">Настройка стандартных уведомлений в конечных точках</span><span class="sxs-lookup"><span data-stu-id="4e073-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="4e073-130">Вы можете использовать групповую политику для:</span><span class="sxs-lookup"><span data-stu-id="4e073-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="4e073-131">Отображение дополнительного, настроенного текста в конечных точках, когда пользователю необходимо выполнить действие</span><span class="sxs-lookup"><span data-stu-id="4e073-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="4e073-132">Скрыть все уведомления в конечных точках</span><span class="sxs-lookup"><span data-stu-id="4e073-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="4e073-133">Скрыть уведомления о перезагрузке конечных точек</span><span class="sxs-lookup"><span data-stu-id="4e073-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="4e073-134">Скрытие уведомлений может быть полезно в ситуациях, когда вы не можете скрыть весь антивирусная программа в Microsoft Defender интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4e073-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="4e073-135">[Подробнее о пользователе не можно увидеть или взаимодействовать антивирусная программа в Microsoft Defender интерфейсом пользователя.](prevent-end-user-interaction-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4e073-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="4e073-136">Сокрытие уведомлений будет происходить только в конечных точках, к которым была развернута политика.</span><span class="sxs-lookup"><span data-stu-id="4e073-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="4e073-137">Уведомления, связанные с действиями, которые должны быть приняты (например, перезагрузка), по-прежнему [будут отображаться на панели мониторинга Microsoft Endpoint Manager Endpoint Protection мониторинга и отчетов.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="4e073-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="4e073-138">Смотрите [настройную Безопасность Windows для организации инструкций по](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) добавление пользовательской контактной информации в уведомления, которые пользователи видят на своих машинах.</span><span class="sxs-lookup"><span data-stu-id="4e073-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="4e073-139">**Используйте групповую политику для сокрытия уведомлений:**</span><span class="sxs-lookup"><span data-stu-id="4e073-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="4e073-140">На компьютере управления групповой политикой откройте консоль [управления групповой политикой, нажмите](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопку «Групповой объект политики», которую вы хотите настроить, и нажмите **«Изменить».**</span><span class="sxs-lookup"><span data-stu-id="4e073-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="4e073-141">В редакторе **управления групповой политикой перейдите** на **конфигурацию компьютера и** нажмите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="4e073-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="4e073-142">Расширьте дерево до **Windows компонентов > антивирусная программа в Microsoft Defender > интерфейса клиента.**</span><span class="sxs-lookup"><span data-stu-id="4e073-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="4e073-143">Дважды **щелкните Подавите все** уведомления и установите опцию **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="4e073-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="4e073-144">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4e073-144">Click **OK**.</span></span> <span data-ttu-id="4e073-145">Это предотвратит появление дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="4e073-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="4e073-146">**Используйте групповую политику, чтобы скрыть уведомления о перезагрузке:**</span><span class="sxs-lookup"><span data-stu-id="4e073-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="4e073-147">На компьютере управления групповой политикой откройте консоль [управления групповой политикой, нажмите](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопку «Групповой объект политики», которую вы хотите настроить, и нажмите **на Редактировать.**</span><span class="sxs-lookup"><span data-stu-id="4e073-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="4e073-148">В редакторе **управления групповой политикой перейдите** на **компьютерную конфигурацию.**</span><span class="sxs-lookup"><span data-stu-id="4e073-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="4e073-149">Нажмите **административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="4e073-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="4e073-150">Расширьте дерево до **Windows компонентов > антивирусная программа в Microsoft Defender > интерфейса клиента.**</span><span class="sxs-lookup"><span data-stu-id="4e073-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="4e073-151">Двойной клик **подавляет перезагрузку уведомлений** и устанавливает опцию **включенной**.</span><span class="sxs-lookup"><span data-stu-id="4e073-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="4e073-152">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4e073-152">Click **OK**.</span></span> <span data-ttu-id="4e073-153">Это предотвратит появление дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="4e073-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4e073-154">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="4e073-154">Related topics</span></span>

- [<span data-ttu-id="4e073-155">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="4e073-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="4e073-156">Настройка взаимодействия конечных пользователей с антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4e073-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
