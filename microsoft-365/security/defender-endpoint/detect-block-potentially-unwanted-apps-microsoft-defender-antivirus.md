---
title: Блокировка потенциально нежелательных приложений с помощью антивируса Microsoft Defender
description: Включить антивирусную функцию потенциально нежелательного приложения (PUA) для блокировки нежелательного программного обеспечения, например adware.
keywords: pua, включить нежелательное программное обеспечение, нежелательные приложения, adware, панель инструментов браузера, обнаружить, заблокировать, Антивирус Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bee92dfa998596578c27bda579a86776bc77c07b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691482"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="d9e21-104">Обнаружение и блокировка потенциально нежелательных приложений</span><span class="sxs-lookup"><span data-stu-id="d9e21-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d9e21-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d9e21-105">**Applies to:**</span></span>

- [<span data-ttu-id="d9e21-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d9e21-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="d9e21-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d9e21-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> <span data-ttu-id="d9e21-108">Потенциально нежелательные приложения (PUA) — это категория программного обеспечения, которое может привести к медленному запуску компьютера, показу неожиданных объявлений или в худшем случае установке другого программного обеспечения, которое может быть неожиданным или нежелательным.</span><span class="sxs-lookup"><span data-stu-id="d9e21-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> <span data-ttu-id="d9e21-109">По умолчанию в Windows 10 (версия 2004 и более поздние версии) антивирус Microsoft Defender блокирует приложения, которые считаются PUA, для устройств Enterprise (E5).</span><span class="sxs-lookup"><span data-stu-id="d9e21-109">By default in Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA, for Enterprise (E5) devices.</span></span>

<span data-ttu-id="d9e21-110">Потенциально нежелательные приложения (PUA) не считаются вирусами, вредоносными программами или другими типами угроз, но могут выполнять действия в конечных точках, которые отрицательно влияют на производительность конечных точек или их использование.</span><span class="sxs-lookup"><span data-stu-id="d9e21-110">Potentially unwanted applications (PUA) are not considered viruses, malware, or other types of threats, but they might perform actions on endpoints which adversely affect endpoint performance or use.</span></span> <span data-ttu-id="d9e21-111">_PUA также_ может ссылаться на приложение, которое имеет плохую репутацию, как оценивает Microsoft Defender для конечной точки, из-за определенных видов нежелательного поведения.</span><span class="sxs-lookup"><span data-stu-id="d9e21-111">_PUA_ can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="d9e21-112">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="d9e21-112">Here are some examples:</span></span>

- <span data-ttu-id="d9e21-113">**Рекламное** программное обеспечение, которое отображает рекламу или рекламные акции, в том числе программное обеспечение, которое вставляет рекламу на веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="d9e21-113">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="d9e21-114">**Комплектирование программного** обеспечения, которое предлагает установить другое программное обеспечение, которое не подписано одной и той же сущностью в цифровом формате.</span><span class="sxs-lookup"><span data-stu-id="d9e21-114">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="d9e21-115">Кроме того, программное обеспечение, которое предлагает установить другое программное обеспечение, которое квалифицируется как PUA.</span><span class="sxs-lookup"><span data-stu-id="d9e21-115">Also, software that offers to install other software that qualify as PUA.</span></span>
- <span data-ttu-id="d9e21-116">**Программное обеспечение для уклонения,** которое активно пытается избежать обнаружения с помощью продуктов безопасности, в том числе программного обеспечения, которое ведет себя по-разному в присутствии продуктов безопасности.</span><span class="sxs-lookup"><span data-stu-id="d9e21-116">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="d9e21-117">Дополнительные примеры и обсуждение критериев, которые мы используем для обозначения приложений для особого внимания со стороны функций безопасности, см. в примере, как Корпорация Майкрософт определяет вредоносные программы и потенциально [нежелательные приложения.](/windows/security/threat-protection/intelligence/criteria)</span><span class="sxs-lookup"><span data-stu-id="d9e21-117">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="d9e21-118">Потенциально нежелательные приложения могут повысить риск заражения сети фактическими вредоносными программами, усложнять выявление вредоносных программ или тратить ИТ-ресурсы на их очистку.</span><span class="sxs-lookup"><span data-stu-id="d9e21-118">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="d9e21-119">Защита PUA поддерживается в Windows 10, Windows Server 2019 и Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="d9e21-119">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="d9e21-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d9e21-120">Microsoft Edge</span></span>

<span data-ttu-id="d9e21-121">Новый [Microsoft Edge,](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)основанный на хроме, блокирует потенциально нежелательные загрузки приложений и связанные URL-адреса ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d9e21-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="d9e21-122">Эта функция предоставляется с [помощью Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span><span class="sxs-lookup"><span data-stu-id="d9e21-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="d9e21-123">Включить защиту PUA в Microsoft Edge на основе хрома</span><span class="sxs-lookup"><span data-stu-id="d9e21-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="d9e21-124">Хотя потенциально нежелательная защита приложений в Microsoft Edge (на основе хрома, версия 80.0.361.50) отключена по умолчанию, ее можно легко включить из браузера.</span><span class="sxs-lookup"><span data-stu-id="d9e21-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="d9e21-125">Выберите эллипсы и выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="d9e21-125">Select the ellipses, and then choose **Settings**.</span></span>
2. <span data-ttu-id="d9e21-126">Выберите **конфиденциальность, поиск и службы.**</span><span class="sxs-lookup"><span data-stu-id="d9e21-126">Select **Privacy, search, and services**.</span></span>
3. <span data-ttu-id="d9e21-127">В разделе **Безопасность** включаем **блок потенциально нежелательных приложений.**</span><span class="sxs-lookup"><span data-stu-id="d9e21-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="d9e21-128">Если вы работаете в Microsoft Edge (на основе хрома), вы можете безопасно изучить функцию защиты PUA, блокирующую URL-адрес, опробуя ее на одной из демонстрационных страниц [Microsoft Defender SmartScreen.](https://demo.smartscreen.msft.net/)</span><span class="sxs-lookup"><span data-stu-id="d9e21-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="d9e21-129">Блокировка URL-адресов с помощью SmartScreen защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d9e21-129">Blocking URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="d9e21-130">В Chromium-edge с включенной защитой PUA Microsoft Defender SmartScreen защищает вас от URL-адресов, связанных с PUA.</span><span class="sxs-lookup"><span data-stu-id="d9e21-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="d9e21-131">Администраторы безопасности могут настроить [совместное](/DeployEdge/configure-microsoft-edge) работу Microsoft Edge и Microsoft Defender SmartScreen для защиты групп пользователей от URL-адресов, связанных с PUA.</span><span class="sxs-lookup"><span data-stu-id="d9e21-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="d9e21-132">Существует несколько [параметров групповой политики](/DeployEdge/microsoft-edge-policies#smartscreen-settings) для SmartScreen Microsoft Defender, в том числе для блокировки [PUA.](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)</span><span class="sxs-lookup"><span data-stu-id="d9e21-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="d9e21-133">Кроме того, администраторы могут настроить [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) в целом, используя параметры групповой политики, чтобы включить или отключить Microsoft Defender SmartScreen.</span><span class="sxs-lookup"><span data-stu-id="d9e21-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="d9e21-134">Несмотря на то, что Microsoft Defender для конечной точки имеет свой собственный список блоков на основе набора данных, управляемых Корпорацией Майкрософт, этот список можно настроить на основе собственных сведений об угрозах.</span><span class="sxs-lookup"><span data-stu-id="d9e21-134">Although Microsoft Defender for Endpoint has its own block list based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="d9e21-135">Если вы [создаете и управляете](/microsoft-365/security/defender-endpoint/manage-indicators) индикаторами на портале Microsoft Defender for Endpoint, Microsoft Defender SmartScreen уважает новые параметры.</span><span class="sxs-lookup"><span data-stu-id="d9e21-135">If you [create and manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus"></a><span data-ttu-id="d9e21-136">Антивирус Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d9e21-136">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="d9e21-137">Функция защиты потенциально нежелательного приложения (PUA) в антивирусе Microsoft Defender может обнаруживать и блокировать puAs в конечных точках сети.</span><span class="sxs-lookup"><span data-stu-id="d9e21-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUAs on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="d9e21-138">Эта функция доступна в Windows 10, Windows Server 2019 и Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="d9e21-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="d9e21-139">Антивирус Microsoft Defender блокирует обнаруженные файлы PUA и любые попытки скачивания, перемещения, запуска или установки.</span><span class="sxs-lookup"><span data-stu-id="d9e21-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="d9e21-140">Заблокированные файлы PUA затем перемещаются на карантин.</span><span class="sxs-lookup"><span data-stu-id="d9e21-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="d9e21-141">При обнаружении файла PUA на конечной точке антивирус Microsoft Defender отправляет пользователю уведомление[(если](configure-notifications-microsoft-defender-antivirus.md)уведомления не отключены) в том же формате, что и другие обнаружения угроз.</span><span class="sxs-lookup"><span data-stu-id="d9e21-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="d9e21-142">Уведомление предисловие, чтобы `PUA:` указать его содержимое.</span><span class="sxs-lookup"><span data-stu-id="d9e21-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="d9e21-143">Уведомление отображается в обычном списке [карантина в приложении Windows Security.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d9e21-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="d9e21-144">Настройка защиты PUA в антивирусе Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d9e21-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="d9e21-145">Вы можете включить защиту PUA с [помощью Microsoft Intune,](/mem/intune/protect/device-protect) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection)Групповой политики [или](/azure/active-directory-domain-services/manage-group-policy)с помощью [команды PowerShell.](/powershell/module/defender/?preserve-view=true&view=win10-ps)</span><span class="sxs-lookup"><span data-stu-id="d9e21-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="d9e21-146">Вы также можете использовать защиту PUA в режиме аудита для обнаружения потенциально нежелательных приложений, не блокируя их.</span><span class="sxs-lookup"><span data-stu-id="d9e21-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="d9e21-147">Обнаружения запечатлены в журнале событий Windows.</span><span class="sxs-lookup"><span data-stu-id="d9e21-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="d9e21-148">Посетите веб-сайт демонстрации Microsoft Defender для конечной точки [demo.wd.microsoft.com,](https://demo.wd.microsoft.com/Page/UrlRep) чтобы подтвердить, что функция работает, и увидеть ее в действии.</span><span class="sxs-lookup"><span data-stu-id="d9e21-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="d9e21-149">Защита PUA в режиме аудита полезна, если ваша компания проводит внутреннюю проверку соответствия требованиям безопасности программного обеспечения, и вы хотите избежать ложных срабатывай.</span><span class="sxs-lookup"><span data-stu-id="d9e21-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

#### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="d9e21-150">Использование Intune для настройки защиты PUA</span><span class="sxs-lookup"><span data-stu-id="d9e21-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="d9e21-151">Дополнительные сведения см. в настройках параметров ограничения устройств [в Microsoft Intune](/intune/device-restrictions-configure) и [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="d9e21-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

#### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="d9e21-152">Настройка защиты PUA с помощью диспетчера конфигурации</span><span class="sxs-lookup"><span data-stu-id="d9e21-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="d9e21-153">Защита PUA включена по умолчанию в Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="d9e21-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="d9e21-154">Сведения о настройке Microsoft Endpoint Manager (Current Branch) см. в материале "Создание и развертывание политик противомалярийных [программ".](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)</span><span class="sxs-lookup"><span data-stu-id="d9e21-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="d9e21-155">Дополнительные System Center 2012 настройки см. в приложении How [to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)</span><span class="sxs-lookup"><span data-stu-id="d9e21-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="d9e21-156">События PUA, заблокированные антивирусом Microsoft Defender, сообщаются в Windows Event Viewer, а не в Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d9e21-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

#### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="d9e21-157">Настройка защиты PUA с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="d9e21-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="d9e21-158">Загрузка и установка административных шаблонов [(.admx) для Обновления Windows 10 октября 2020 г. (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="d9e21-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="d9e21-159">На компьютере управления групповой политикой откройте консоль [управления групповой политикой.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="d9e21-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="d9e21-160">Выберите объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d9e21-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="d9e21-161">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="d9e21-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="d9e21-162">Расширь дерево до **антивируса**  >  **Microsoft Defender компоненты Windows.**</span><span class="sxs-lookup"><span data-stu-id="d9e21-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="d9e21-163">Дважды **щелкните Настройка обнаружения для потенциально нежелательных приложений.**</span><span class="sxs-lookup"><span data-stu-id="d9e21-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="d9e21-164">Выберите **Включено,** чтобы включить защиту PUA.</span><span class="sxs-lookup"><span data-stu-id="d9e21-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="d9e21-165">В **Параметры** выберите **Блок** для блокировки потенциально  нежелательных приложений или выберите режим аудита, чтобы проверить, как работает параметр в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="d9e21-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="d9e21-166">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d9e21-166">Select **OK**.</span></span>

9. <span data-ttu-id="d9e21-167">Развертывание объекта групповой политики, как обычно.</span><span class="sxs-lookup"><span data-stu-id="d9e21-167">Deploy your Group Policy object as you usually do.</span></span>

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="d9e21-168">Чтобы настроить защиту PUA, используйте cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9e21-168">Use PowerShell cmdlets to configure PUA protection</span></span>

##### <a name="to-enable-pua-protection"></a><span data-ttu-id="d9e21-169">Чтобы включить защиту PUA</span><span class="sxs-lookup"><span data-stu-id="d9e21-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="d9e21-170">Настройка значения для этого cmdlet включает `Enabled` функцию, если она отключена.</span><span class="sxs-lookup"><span data-stu-id="d9e21-170">Setting the value for this cmdlet to `Enabled` turns the feature on if it has been disabled.</span></span>

##### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="d9e21-171">Настройка режима аудита защиты PUA</span><span class="sxs-lookup"><span data-stu-id="d9e21-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="d9e21-172">Параметр `AuditMode` обнаруживает PUAs, не блокируя их.</span><span class="sxs-lookup"><span data-stu-id="d9e21-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

##### <a name="to-disable-pua-protection"></a><span data-ttu-id="d9e21-173">Отключение защиты PUA</span><span class="sxs-lookup"><span data-stu-id="d9e21-173">To disable PUA protection</span></span>

<span data-ttu-id="d9e21-174">Рекомендуется поддерживать включенную защиту PUA.</span><span class="sxs-lookup"><span data-stu-id="d9e21-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="d9e21-175">Однако вы можете отключить его с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d9e21-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="d9e21-176">Настройка значения для этого комлета, чтобы `Disabled` отключить функцию, если она включена.</span><span class="sxs-lookup"><span data-stu-id="d9e21-176">Setting the value for this cmdlet to `Disabled` turns the feature off if it has been enabled.</span></span>

<span data-ttu-id="d9e21-177">Дополнительные сведения о том, как использовать [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) с антивирусным вирусом Microsoft Defender и [Defender,](/powershell/module/defender/index) см. в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="d9e21-177">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="view-pua-events"></a><span data-ttu-id="d9e21-178">Просмотр событий PUA</span><span class="sxs-lookup"><span data-stu-id="d9e21-178">View PUA events</span></span>

<span data-ttu-id="d9e21-179">События PUA сообщаются в Windows Event Viewer, но не в Microsoft Endpoint Manager или Intune.</span><span class="sxs-lookup"><span data-stu-id="d9e21-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="d9e21-180">Кроме того, можно использовать `Get-MpThreat` этот кодлет для просмотра угроз, с помощью антивирусных программ Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d9e21-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="d9e21-181">Пример:</span><span class="sxs-lookup"><span data-stu-id="d9e21-181">Here's an example:</span></span>

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

<span data-ttu-id="d9e21-182">Вы можете включить уведомления электронной почты для получения почты об обнаружении PUA.</span><span class="sxs-lookup"><span data-stu-id="d9e21-182">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="d9e21-183">Сведения [о просмотре антивирусных](troubleshoot-microsoft-defender-antivirus.md) событий Microsoft Defender см. в материале "Устранение неполадок".</span><span class="sxs-lookup"><span data-stu-id="d9e21-183">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="d9e21-184">События PUA записывают в соответствии с ИД события **1160**.</span><span class="sxs-lookup"><span data-stu-id="d9e21-184">PUA events are recorded under event ID **1160**.</span></span>

## <a name="excluding-files"></a><span data-ttu-id="d9e21-185">Исключение файлов</span><span class="sxs-lookup"><span data-stu-id="d9e21-185">Excluding files</span></span>

<span data-ttu-id="d9e21-186">Иногда файл ошибочно блокируется защитой PUA или для выполнения задачи требуется функция PUA.</span><span class="sxs-lookup"><span data-stu-id="d9e21-186">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="d9e21-187">В этих случаях файл можно добавить в список исключений.</span><span class="sxs-lookup"><span data-stu-id="d9e21-187">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="d9e21-188">Дополнительные сведения см. в [материалах Configure and validate exclusions based on file extension and folder location.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d9e21-188">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9e21-189">См. также</span><span class="sxs-lookup"><span data-stu-id="d9e21-189">See also</span></span>

- [<span data-ttu-id="d9e21-190">Защита нового поколения</span><span class="sxs-lookup"><span data-stu-id="d9e21-190">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d9e21-191">Настройка поведенческой, севристической и защиты в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="d9e21-191">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)