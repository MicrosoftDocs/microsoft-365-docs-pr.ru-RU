---
title: Блокировка потенциально нежелательных приложений с помощью антивирусной программы в Microsoft Defender
description: Включите функцию антивируса потенциально нежелательных приложений (PUA), чтобы блокировать нежелательное программное обеспечение, такое как программа для показа рекламы.
keywords: pua, включить, нежелательное программное обеспечение, нежелательные приложения, программа для показа рекламы, панель инструментов браузера, обнаружение, блокировка, антивирусная программа в Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8350db473580fd4d1728c3473742da5b63196c52
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893581"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="1d78c-104">Обнаружение и блокировка потенциально нежелательных приложений</span><span class="sxs-lookup"><span data-stu-id="1d78c-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d78c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1d78c-105">**Applies to:**</span></span>

- [<span data-ttu-id="1d78c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1d78c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="1d78c-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1d78c-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="1d78c-108">Потенциально нежелательные приложения (PUA) — это категория программного обеспечения, которое может привести к медленному запуску компьютера, показу неожиданных объявлений или, в худшем случае, установке другого программного обеспечения, которое может быть неожиданным или нежелательным.</span><span class="sxs-lookup"><span data-stu-id="1d78c-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="1d78c-109">PUA не считается вирусом, вредоносным программным обеспечением или другим типом угрозы, но может выполнять действия в конечных точках, которые отрицательно влияют на производительность конечных точек или использование.</span><span class="sxs-lookup"><span data-stu-id="1d78c-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="1d78c-110">Термин *PUA также* может относиться к приложению с плохой репутацией, как оценивает Microsoft Defender для конечной точки, из-за определенных видов нежелательного поведения.</span><span class="sxs-lookup"><span data-stu-id="1d78c-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="1d78c-111">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="1d78c-111">Here are some examples:</span></span>

- <span data-ttu-id="1d78c-112">**Рекламные программное обеспечение**, которые отображают рекламу или рекламные акции, в том числе программное обеспечение, которое вставляет рекламные объявления на веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="1d78c-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="1d78c-113">**Организация программного обеспечения**, которое предлагает установить другое программное обеспечение, не имеющее цифровой подписи той же организации.</span><span class="sxs-lookup"><span data-stu-id="1d78c-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="1d78c-114">Кроме того, программное обеспечение, которое предлагает установить другое программное обеспечение, которое квалифицируется как PUA.</span><span class="sxs-lookup"><span data-stu-id="1d78c-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="1d78c-115">**Уклонение программного обеспечения**, которое активно пытается уклониться от обнаружения продуктами безопасности, включая программное обеспечение, которое ведет себя иначе в присутствии продуктов безопасности.</span><span class="sxs-lookup"><span data-stu-id="1d78c-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="1d78c-116">Дополнительные примеры и обсуждение критериев, которые используются для пометки приложений, требующих особого внимания со стороны функций безопасности, см. разделе [Как Майкрософт определяет вредоносные и потенциально нежелательные приложения](/windows/security/threat-protection/intelligence/criteria).</span><span class="sxs-lookup"><span data-stu-id="1d78c-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="1d78c-117">Потенциально нежелательные приложения могут повысить риск заражения вашей сети фактическими вредоносными программами, затруднить выявление заражений вредоносными программами или тратить ИТ-ресурсы на их очистку.</span><span class="sxs-lookup"><span data-stu-id="1d78c-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="1d78c-118">Защита от потенциально нежелательных приложений поддерживается в Windows 10, Windows Server 2019 и Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="1d78c-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="1d78c-119">В Windows 10 (версии 2004 и более поздней версии) антивирус Microsoft Defender блокирует приложения, которые по умолчанию считаются устройствами PUA для предприятия (E5).</span><span class="sxs-lookup"><span data-stu-id="1d78c-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="1d78c-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1d78c-120">Microsoft Edge</span></span>

<span data-ttu-id="1d78c-121">[Новый Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), основанный на Chromium, блокирует загрузки потенциально нежелательных приложений и связанные URL-адреса ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1d78c-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="1d78c-122">Эта функция предоставляется через [фильтр SmartScreen в Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span><span class="sxs-lookup"><span data-stu-id="1d78c-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="1d78c-123">Включить защиту от потенциально нежелательных приложений в Microsoft Edge на основе Chromium</span><span class="sxs-lookup"><span data-stu-id="1d78c-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="1d78c-124">Хотя защита от потенциально нежелательных приложений в Microsoft Edge (на основе Chromium, версия 80.0.361.50) отключена по умолчанию, ее можно легко отключить в браузере.</span><span class="sxs-lookup"><span data-stu-id="1d78c-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="1d78c-125">В браузере Edge выберите эллипсы и выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="1d78c-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="1d78c-126">Выберите **Конфиденциальность, поиск и службы**.</span><span class="sxs-lookup"><span data-stu-id="1d78c-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="1d78c-127">В разделе **Безопасность** включите **Блокировка потенциально нежелательных приложений**.</span><span class="sxs-lookup"><span data-stu-id="1d78c-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="1d78c-128">Если вы работаете в Microsoft Edge (на основе Chromium), вы можете безопасно изучить функцию блокировки URL-адресов защиты от потенциально нежелательных приложений, протестировав ее на одной из наших [демонстрационных страниц фильтра SmartScreen в Microsoft Defender](https://demo.smartscreen.msft.net/).</span><span class="sxs-lookup"><span data-stu-id="1d78c-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="1d78c-129">Блокировка URL-адресов с помощью фильтра SmartScreen в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1d78c-129">Blocking URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="1d78c-130">В Edge на основе Chromium с включенной защитой от потенциально нежелательных приложений фильтр SmartScreen в Microsoft Defender защищает вас от URL-адресов, связанных с потенциально нежелательными приложениями.</span><span class="sxs-lookup"><span data-stu-id="1d78c-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="1d78c-131">Администраторы безопасности могут [настраивать](/DeployEdge/configure-microsoft-edge) совместную работу Microsoft Edge и фильтр SmartScreen в Microsoft Defender для защиты групп пользователей от URL-адресов, связанных с потенциально нежелательными приложениями.</span><span class="sxs-lookup"><span data-stu-id="1d78c-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="1d78c-132">Существует несколько [параметров групповой политики](/DeployEdge/microsoft-edge-policies#smartscreen-settings) исключительно для фильтра SmartScreen в Microsoft Defender, в том числе [один для блокировки потенциально нежелательных приложений](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span><span class="sxs-lookup"><span data-stu-id="1d78c-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="1d78c-133">Кроме того, администраторы могут [настраивать фильтр SmartScreen в Microsoft Defender](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) в целом, используя параметры групповой политики, чтобы включить или отключить фильтр SmartScreen в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1d78c-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="1d78c-134">Несмотря на то, что Microsoft Defender для конечной точки имеет собственный блоклист на основе набора данных, управляемых Корпорацией Майкрософт, этот список можно настроить на основе собственных сведений об угрозах.</span><span class="sxs-lookup"><span data-stu-id="1d78c-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="1d78c-135">При [создании и управлении индикаторами](manage-indicators.md) на портале Microsoft Defender для конечной точки, SmartScreen в Microsoft Defender учитывает новые параметры.</span><span class="sxs-lookup"><span data-stu-id="1d78c-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus"></a><span data-ttu-id="1d78c-136">Антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1d78c-136">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="1d78c-137">Функция защиты от потенциально нежелательных приложений (PUA) в антивирусной программе в Microsoft Defender может обнаруживать и блокировать потенциально нежелательные приложения на конечных точках в вашей сети.</span><span class="sxs-lookup"><span data-stu-id="1d78c-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUAs on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="1d78c-138">Эта функция доступна в Windows 10, Windows Server 2019 и Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="1d78c-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="1d78c-139">Антивирусная программа в Microsoft Defender блокирует обнаруженные PUA-файлы и все попытки их скачивания, перемещения, запуска или установки.</span><span class="sxs-lookup"><span data-stu-id="1d78c-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="1d78c-140">После этого заблокированные PUA-файлы перемещаются в карантин.</span><span class="sxs-lookup"><span data-stu-id="1d78c-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="1d78c-141">При обнаружении PUA-файла в конечной точке антивирусная программа в Microsoft Defender отправляет пользователю уведомление ([если уведомления не отключены](configure-notifications-microsoft-defender-antivirus.md)) в том же формате, что и другие обнаруженные угрозы.</span><span class="sxs-lookup"><span data-stu-id="1d78c-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="1d78c-142">Перед уведомлением указывается `PUA:` для указания его содержимого.</span><span class="sxs-lookup"><span data-stu-id="1d78c-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="1d78c-143">Уведомление отображается в обычном [списке карантина в приложении "Безопасность Windows"](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="1d78c-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="1d78c-144">Настройка защиты от потенциально нежелательных приложений в антивирусной программе в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1d78c-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="1d78c-145">Защиту от потенциально нежелательных приложений можно включить с помощью [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [групповой политики](/azure/active-directory-domain-services/manage-group-policy) или с помощью [командлетов PowerShell](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span><span class="sxs-lookup"><span data-stu-id="1d78c-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="1d78c-146">Вы также можете использовать защиту от потенциально нежелательных приложений в режиме аудита для обнаружения потенциально нежелательных приложений, не блокируя их.</span><span class="sxs-lookup"><span data-stu-id="1d78c-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="1d78c-147">Обнаружения записываются в журнале событий Windows.</span><span class="sxs-lookup"><span data-stu-id="1d78c-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="1d78c-148">Посетите демонстрационный веб-сайт Microsoft Defender для конечной точки по ссылке [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep), чтобы проверить, работает ли функция, и увидеть, как она работает.</span><span class="sxs-lookup"><span data-stu-id="1d78c-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="1d78c-149">Защита от потенциально нежелательных приложений в режиме аудита полезна, если ваша организация проводит внутреннюю проверку соответствия требованиям безопасности программного обеспечения, и вы хотите избежать ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="1d78c-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

#### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="1d78c-150">Настройка защиты от потенциально нежелательных приложений с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="1d78c-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="1d78c-151">Дополнительные сведения см. в статьях [Настройка параметров ограничения устройств в Microsoft Intune](/intune/device-restrictions-configure) и [Параметры ограничений устройств антивирусной программы в Microsoft Defender для Windows 10 в Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="1d78c-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

#### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="1d78c-152">Настройка защиты от потенциально нежелательных приложений с помощью Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1d78c-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="1d78c-153">Защита от потенциально нежелательных приложений по умолчанию включена в Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="1d78c-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="1d78c-154">Дополнительные сведения о настройке Microsoft Endpoint Manager (Current Branch) см. в статье [Создание и развертывание политик защиты от вредоносных программ: параметры запланированных проверок](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings).</span><span class="sxs-lookup"><span data-stu-id="1d78c-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="1d78c-155">Сведения о диспетчере конфигураций System Center 2012 см. в статье [Развертывание политики защиты от потенциально нежелательных приложений для Endpoint Protection в Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span><span class="sxs-lookup"><span data-stu-id="1d78c-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="1d78c-156">События PUA, заблокированные антивирусной программой в Microsoft Defender, отображаются в средстве просмотра событий Windows, а не в Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="1d78c-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

#### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="1d78c-157">Настройка защиты от потенциально нежелательных приложений с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="1d78c-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="1d78c-158">Скачивание и установка [административных шаблонов (.ADMX) для обновления Windows 10 за октябрь 2020 г. (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="1d78c-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="1d78c-159">На компьютере управления групповыми политиками откройте [консоль управления групповыми политиками](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="1d78c-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="1d78c-160">Выберите объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1d78c-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="1d78c-161">В **редакторе управления групповыми политиками** перейдите к **конфигурации компьютера** и выберите **Административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="1d78c-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="1d78c-162">Разверните дерево до **Компонентов Windows** > **антивирусной программы в Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="1d78c-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="1d78c-163">Дважды щелкните на пункт **Настройка обнаружения потенциально нежелательных приложений**.</span><span class="sxs-lookup"><span data-stu-id="1d78c-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="1d78c-164">Выберите **Включено**, чтобы включить защиту от потенциально нежелательных приложений.</span><span class="sxs-lookup"><span data-stu-id="1d78c-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="1d78c-165">В разделе **Параметры** выберите **Заблокировать**, чтобы заблокировать потенциально нежелательные приложения, или выберите **Режим аудита**, чтобы проверить, как этот параметр работает в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="1d78c-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="1d78c-166">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1d78c-166">Select **OK**.</span></span>

9. <span data-ttu-id="1d78c-167">Разверните объект групповой политики, как обычно.</span><span class="sxs-lookup"><span data-stu-id="1d78c-167">Deploy your Group Policy object as you usually do.</span></span>

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="1d78c-168">Настройка защиты от потенциально нежелательных приложений с помощью командлетов PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d78c-168">Use PowerShell cmdlets to configure PUA protection</span></span>

##### <a name="to-enable-pua-protection"></a><span data-ttu-id="1d78c-169">Чтобы включить защиту от потенциально нежелательных приложений:</span><span class="sxs-lookup"><span data-stu-id="1d78c-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="1d78c-170">Настройка значения для этого комлета включает `Enabled` функцию, если она отключена.</span><span class="sxs-lookup"><span data-stu-id="1d78c-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

##### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="1d78c-171">Чтобы настроить защиту от потенциально нежелательных приложений в режиме аудита:</span><span class="sxs-lookup"><span data-stu-id="1d78c-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="1d78c-172">Установите `AuditMode` для обнаружения потенциально нежелательных приложений, не блокируя их.</span><span class="sxs-lookup"><span data-stu-id="1d78c-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

##### <a name="to-disable-pua-protection"></a><span data-ttu-id="1d78c-173">Чтобы отключить защиту от потенциально нежелательных приложений:</span><span class="sxs-lookup"><span data-stu-id="1d78c-173">To disable PUA protection</span></span>

<span data-ttu-id="1d78c-174">Рекомендуем не отключать защиту от потенциально нежелательных приложений.</span><span class="sxs-lookup"><span data-stu-id="1d78c-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="1d78c-175">Однако её можно отключить с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="1d78c-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="1d78c-176">Настройка значения для этого комлета, чтобы `Disabled` отключить функцию, если она включена.</span><span class="sxs-lookup"><span data-stu-id="1d78c-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="1d78c-177">Дополнительные сведения об использовании PowerShell с антивирусной программой в Microsoft Defender см. в разделах [Использование командлетов PowerShell для настройки и запуска антивирусной программы в Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) и [Командлеты Defender](/powershell/module/defender/index).</span><span class="sxs-lookup"><span data-stu-id="1d78c-177">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="view-pua-events"></a><span data-ttu-id="1d78c-178">Просмотр событий PUA</span><span class="sxs-lookup"><span data-stu-id="1d78c-178">View PUA events</span></span>

<span data-ttu-id="1d78c-179">О событиях PUA сообщается в средстве просмотра событий Windows, но не в Microsoft Endpoint Manager или в Intune.</span><span class="sxs-lookup"><span data-stu-id="1d78c-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="1d78c-180">Вы также можете использовать командлет `Get-MpThreat` для просмотра угроз, обработанных антивирусной программой в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1d78c-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="1d78c-181">Пример:</span><span class="sxs-lookup"><span data-stu-id="1d78c-181">Here's an example:</span></span>

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

<span data-ttu-id="1d78c-182">Вы можете включить уведомления по электронной почте, чтобы получать сообщения об обнаружении потенциально нежелательных приложений.</span><span class="sxs-lookup"><span data-stu-id="1d78c-182">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="1d78c-183">Дополнительные сведения о просмотре событий Microsoft Defender Antivirus см. в разделе [Устранение неполадок с событиями идентификаторов](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="1d78c-183">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="1d78c-184">События PUA записываются в соответствии с идентификатором события **1160**.</span><span class="sxs-lookup"><span data-stu-id="1d78c-184">PUA events are recorded under event ID **1160**.</span></span>

<span data-ttu-id="1d78c-185">Если вы используете Microsoft Defender для конечной точки, для просмотра событий PUA можно использовать расширенный запрос на охоту.</span><span class="sxs-lookup"><span data-stu-id="1d78c-185">If you're using Microsoft Defender for Endpoint, you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="1d78c-186">Вот пример запроса:</span><span class="sxs-lookup"><span data-stu-id="1d78c-186">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

## <a name="excluding-files"></a><span data-ttu-id="1d78c-187">Исключение файлов</span><span class="sxs-lookup"><span data-stu-id="1d78c-187">Excluding files</span></span>

<span data-ttu-id="1d78c-188">Иногда файл ошибочно блокируется защитой от потенциально нежелательных приложений или для выполнения задачи требуется функция PUA.</span><span class="sxs-lookup"><span data-stu-id="1d78c-188">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="1d78c-189">В таких случаях файл можно добавить в список исключений.</span><span class="sxs-lookup"><span data-stu-id="1d78c-189">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="1d78c-190">Дополнительные сведения см. в статье [Настройка и проверка исключений с учетом расширения файла и расположения папки](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="1d78c-190">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d78c-191">См. также</span><span class="sxs-lookup"><span data-stu-id="1d78c-191">See also</span></span>

- [<span data-ttu-id="1d78c-192">Защита нового поколения</span><span class="sxs-lookup"><span data-stu-id="1d78c-192">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="1d78c-193">Настройка поведенческой, эвристической защиты и защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="1d78c-193">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)