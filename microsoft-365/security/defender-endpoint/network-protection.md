---
title: Использование сетевой защиты для предотвращения подключения к плохим сайтам
description: Защита сети путем предотвращения доступа пользователей к известным вредоносным и подозрительным сетевым адресам
keywords: Защита сети, эксплойтов, вредоносный веб-сайт, IP, домен, домены
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b6b664d471e238e2feb1e1aedd100c1299fc5bbe
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844266"
---
# <a name="protect-your-network"></a><span data-ttu-id="24900-104">Защита сети</span><span class="sxs-lookup"><span data-stu-id="24900-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="24900-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="24900-105">**Applies to:**</span></span>
- [<span data-ttu-id="24900-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="24900-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24900-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24900-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="24900-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="24900-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="24900-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="24900-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="24900-110">Защита сети помогает уменьшить поверхность атаки устройств от событий, происходящих в Интернете.</span><span class="sxs-lookup"><span data-stu-id="24900-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="24900-111">Это не позволяет сотрудникам использовать любое приложение для доступа к опасным доменам, в которые могут быть организованы фишинговые атаки, эксплойты и другой вредоносный контент в Интернете.</span><span class="sxs-lookup"><span data-stu-id="24900-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="24900-112">Защита сети расширяет область фильтр SmartScreen в Microsoft Defender для блокировки всего исходящего трафика [HTTP(ы),](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) который пытается подключиться к источникам с низкой репутацией (на основе домена или имени хост-сайта).</span><span class="sxs-lookup"><span data-stu-id="24900-112">Network protection expands the scope of [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="24900-113">Защита сети поддерживается на Windows, начиная с Windows 10 версии 1709.</span><span class="sxs-lookup"><span data-stu-id="24900-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="24900-114">Защита сети еще не поддерживается в других операционных системах, но веб-защита поддерживается с помощью нового Microsoft Edge на основе Chromium.</span><span class="sxs-lookup"><span data-stu-id="24900-114">Network protection is not yet supported on other operating systems, but web protection is supported using the new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="24900-115">Дополнительные информации см. в [веб-защите.](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="24900-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="24900-116">Защита сети расширяет защиту в [веб-защите](web-protection-overview.md) до уровня операционной системы.</span><span class="sxs-lookup"><span data-stu-id="24900-116">Network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="24900-117">Он предоставляет функции веб-защиты в Edge для других поддерживаемых браузеров и не браузерных приложений.</span><span class="sxs-lookup"><span data-stu-id="24900-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="24900-118">Кроме того, защита сети обеспечивает видимость и блокировку индикаторов компрометации (IOCs) при их обнаружении и реагировании на [конечные точки.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="24900-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="24900-119">Например, защита сети работает с [настраиваемой индикаторами.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="24900-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="24900-120">Дополнительные сведения о том, как включить защиту сети, см. в дополнительных [сведениях о том, как включить защиту сети.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="24900-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="24900-121">Используйте групповой политики, PowerShell или MDM CSPs для обеспечения и управления сетевой защитой в сети.</span><span class="sxs-lookup"><span data-stu-id="24900-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="24900-122">Узнайте, как работает защита сети, на demo.wd.microsoft.com сайте microsoft Defender [for](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Endpoint.</span><span class="sxs-lookup"><span data-stu-id="24900-122">See the Microsoft Defender for Endpoint testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="24900-123">Защита сети лучше всего работает с [Microsoft Defender для конечной](microsoft-defender-endpoint.md)точки , которая предоставляет подробные отчеты о событиях и блоках защиты от эксплуатации в рамках сценариев расследования [оповещения.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="24900-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="24900-124">Когда защита сети блокирует подключение, из Центра действий отображается уведомление.</span><span class="sxs-lookup"><span data-stu-id="24900-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="24900-125">Группа операций безопасности может [настроить уведомление](customize-attack-surface-reduction.md#customize-the-notification) с помощью сведений и контактных данных организации.</span><span class="sxs-lookup"><span data-stu-id="24900-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="24900-126">Кроме того, отдельные правила уменьшения поверхности атаки можно включить и настроить в соответствии с определенными методами мониторинга.</span><span class="sxs-lookup"><span data-stu-id="24900-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="24900-127">Вы также можете использовать [режим аудита](audit-windows-defender.md) для оценки влияния сетевой защиты на организацию, если она включена.</span><span class="sxs-lookup"><span data-stu-id="24900-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="24900-128">Требования</span><span class="sxs-lookup"><span data-stu-id="24900-128">Requirements</span></span>

<span data-ttu-id="24900-129">Защита сети требует Windows 10 Pro или Enterprise и антивирусная программа в Microsoft Defender защиты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="24900-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="24900-130">Версия Windows</span><span class="sxs-lookup"><span data-stu-id="24900-130">Windows version</span></span> | <span data-ttu-id="24900-131">Антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="24900-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="24900-132">Windows 10 версии 1709 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="24900-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="24900-133">Windows Сервер 1803 или более поздний</span><span class="sxs-lookup"><span data-stu-id="24900-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="24900-134">[антивирусная программа в Microsoft Defender должна](configure-real-time-protection-microsoft-defender-antivirus.md) быть включена защита в режиме реального времени и [облачная](enable-cloud-protection-microsoft-defender-antivirus.md) защита</span><span class="sxs-lookup"><span data-stu-id="24900-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="24900-135">После включения служб может потребоваться настроить сеть или брандмауэр, чтобы разрешить подключения между службами и устройствами (также именуемые конечными точками).</span><span class="sxs-lookup"><span data-stu-id="24900-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="24900-136">Просмотр событий защиты сети в Центре безопасности конечных точек Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="24900-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="24900-137">Microsoft Defender for Endpoint предоставляет подробные отчеты о событиях и блоках в рамках сценариев расследования [оповещений.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="24900-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="24900-138">Вы можете запрашивать данные Microsoft Defender для конечных точек с помощью [расширенных методов охоты.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="24900-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="24900-139">Если вы используете [](audit-windows-defender.md)режим аудита, вы можете использовать расширенный режим охоты, чтобы узнать, как параметры сетевой защиты влияют на среду, если они включены.</span><span class="sxs-lookup"><span data-stu-id="24900-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="24900-140">Вот пример запроса</span><span class="sxs-lookup"><span data-stu-id="24900-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="24900-141">Просмотр событий защиты сети в Windows просмотра событий</span><span class="sxs-lookup"><span data-stu-id="24900-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="24900-142">Вы можете просмотреть журнал Windows событий, чтобы просмотреть события, созданные при блоке сетевой защиты (или аудите) доступа к вредоносному IP или домену:</span><span class="sxs-lookup"><span data-stu-id="24900-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="24900-143">[Скопируйте XML напрямую.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="24900-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="24900-144">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="24900-144">Select **OK**.</span></span>

<span data-ttu-id="24900-145">Эта процедура создает настраиваемую точку зрения, которая фильтрует только следующие события, связанные с защитой сети:</span><span class="sxs-lookup"><span data-stu-id="24900-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="24900-146">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="24900-146">Event ID</span></span> | <span data-ttu-id="24900-147">Описание</span><span class="sxs-lookup"><span data-stu-id="24900-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="24900-148">5007</span><span class="sxs-lookup"><span data-stu-id="24900-148">5007</span></span> | <span data-ttu-id="24900-149">Событие при смене параметров</span><span class="sxs-lookup"><span data-stu-id="24900-149">Event when settings are changed</span></span> |
| <span data-ttu-id="24900-150">1125</span><span class="sxs-lookup"><span data-stu-id="24900-150">1125</span></span> | <span data-ttu-id="24900-151">Событие, когда защита сети загорелась в режиме аудита</span><span class="sxs-lookup"><span data-stu-id="24900-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="24900-152">1126</span><span class="sxs-lookup"><span data-stu-id="24900-152">1126</span></span> | <span data-ttu-id="24900-153">Событие, когда защита сети загорелась в режиме блокировки</span><span class="sxs-lookup"><span data-stu-id="24900-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="24900-154">Соображения для Windows рабочего стола с Windows 10 Корпоративная multi-Session</span><span class="sxs-lookup"><span data-stu-id="24900-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="24900-155">Учитывая многоцелевую природу Windows 10 Корпоративная, следует помнить о следующих моментах:</span><span class="sxs-lookup"><span data-stu-id="24900-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="24900-156">Защита от сети — это функция для всего устройства и не может быть ориентирована на определенные сеансы пользователей.</span><span class="sxs-lookup"><span data-stu-id="24900-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="24900-157">Политики фильтрации веб-контента также являются широкими устройствами.</span><span class="sxs-lookup"><span data-stu-id="24900-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="24900-158">Если необходимо различать группы пользователей, рассмотрите возможность создания отдельных пулов Windows виртуальных настольных компьютеров и назначений.</span><span class="sxs-lookup"><span data-stu-id="24900-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="24900-159">Проверьте защиту сети в режиме аудита, чтобы оценить ее поведение перед развертыванием.</span><span class="sxs-lookup"><span data-stu-id="24900-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="24900-160">Рассмотрите возможность повторного развертывания, если у вас большое количество пользователей или большое количество сеансов с несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="24900-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="24900-161">Альтернативный вариант защиты сети</span><span class="sxs-lookup"><span data-stu-id="24900-161">Alternative option for network protection</span></span>

<span data-ttu-id="24900-162">Для Windows 10 Корпоративная 1909 и более, используемых в Windows Virtual Desktop в Azure, защита сети для Microsoft Edge может быть включена с помощью следующего метода:</span><span class="sxs-lookup"><span data-stu-id="24900-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="24900-163">[Включите защиту сети](enable-network-protection.md) и следуйте инструкциям, чтобы применить политику.</span><span class="sxs-lookup"><span data-stu-id="24900-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="24900-164">Выполните следующую команду PowerShell: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="24900-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="24900-165">Устранение неполадок в сетевой защите</span><span class="sxs-lookup"><span data-stu-id="24900-165">Network protection troubleshooting</span></span>

<span data-ttu-id="24900-166">Из-за среды, в которой выполняется защита сети, Microsoft может не обнаруживать параметры прокси-сервера операционной системы.</span><span class="sxs-lookup"><span data-stu-id="24900-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="24900-167">В некоторых случаях клиенты сетевой защиты не могут добраться до облачной службы.</span><span class="sxs-lookup"><span data-stu-id="24900-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="24900-168">Чтобы устранить проблему подключения, клиенты с лицензиями E5 должны настроить один из следующих ключей реестра Defender:</span><span class="sxs-lookup"><span data-stu-id="24900-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="24900-169">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="24900-169">Related articles</span></span>

- <span data-ttu-id="24900-170">[Оценка защиты](evaluate-network-protection.md) сети | Создай быстрый сценарий, в который показано, как работает функция и какие события обычно создаются.</span><span class="sxs-lookup"><span data-stu-id="24900-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="24900-171">[Включить защиту](enable-network-protection.md) сети | Используйте групповой политики, PowerShell или MDM CSPs для обеспечения и управления сетевой защитой в сети.</span><span class="sxs-lookup"><span data-stu-id="24900-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
