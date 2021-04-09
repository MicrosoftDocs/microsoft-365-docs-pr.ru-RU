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
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: 2ef3fbeec65be512dfe07f1d533df4d8e9b31532
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644504"
---
# <a name="protect-your-network"></a><span data-ttu-id="dbe1a-104">Защита сети</span><span class="sxs-lookup"><span data-stu-id="dbe1a-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dbe1a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="dbe1a-105">**Applies to:**</span></span>
- [<span data-ttu-id="dbe1a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="dbe1a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dbe1a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbe1a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dbe1a-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="dbe1a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dbe1a-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="dbe1a-110">Защита сети помогает уменьшить поверхность атаки устройств от событий, происходящих в Интернете.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="dbe1a-111">Это не позволяет сотрудникам использовать любое приложение для доступа к опасным доменам, в которые могут быть организованы фишинговые атаки, эксплойты и другой вредоносный контент в Интернете.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="dbe1a-112">Защита от сети расширяет область [SmartScreen Microsoft Defender,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) чтобы заблокировать весь исходящий трафик HTTP(s), который пытается подключиться к источникам с низкой репутацией (на основе домена или имени хост-сайта).</span><span class="sxs-lookup"><span data-stu-id="dbe1a-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="dbe1a-113">Защита сети поддерживается в Windows, начиная с Windows 10 версии 1709.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> 

<span data-ttu-id="dbe1a-114">Дополнительные сведения о том, как включить защиту сети, см. в дополнительных [сведениях о том, как включить защиту сети.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="dbe1a-114">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="dbe1a-115">Используйте групповой политики, PowerShell или MDM CSPs для обеспечения и управления сетевой защитой в сети.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-115">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="dbe1a-116">Узнайте, как работает защита сети, demo.wd.microsoft.com на [сайте тестового поля ATP](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-116">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="dbe1a-117">Защита сети лучше всего работает с [Microsoft Defender для конечной](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)точки , которая предоставляет подробные отчеты о событиях и блоках защиты от эксплуатации в рамках сценариев расследования [оповещения.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="dbe1a-117">Network protection works best with [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="dbe1a-118">Когда защита сети блокирует подключение, из Центра действий отображается уведомление.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-118">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="dbe1a-119">Группа операций безопасности может [настроить уведомление](customize-attack-surface-reduction.md#customize-the-notification) с помощью сведений и контактных данных организации.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-119">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="dbe1a-120">Кроме того, отдельные правила уменьшения поверхности атаки можно включить и настроить в соответствии с определенными методами мониторинга.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-120">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="dbe1a-121">Вы также можете использовать [режим аудита](audit-windows-defender.md) для оценки влияния сетевой защиты на организацию, если она включена.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-121">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="dbe1a-122">Требования</span><span class="sxs-lookup"><span data-stu-id="dbe1a-122">Requirements</span></span>

<span data-ttu-id="dbe1a-123">Защита сети требует защиты Windows 10 Pro или Enterprise и антивируса Microsoft Defender в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-123">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="dbe1a-124">Версия Windows</span><span class="sxs-lookup"><span data-stu-id="dbe1a-124">Windows version</span></span> | <span data-ttu-id="dbe1a-125">Антивирус Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dbe1a-125">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="dbe1a-126">Windows 10 версии 1709 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="dbe1a-126">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="dbe1a-127">Windows Server 1803 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="dbe1a-127">Windows Server 1803 or later</span></span> | <span data-ttu-id="dbe1a-128">[Антивирус Microsoft Defender в режиме реального времени и](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) [облачная](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) защита должны быть включены</span><span class="sxs-lookup"><span data-stu-id="dbe1a-128">[Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="dbe1a-129">После включения служб может потребоваться настроить сеть или брандмауэр, чтобы разрешить подключения между службами и устройствами (также именуемые конечными точками).</span><span class="sxs-lookup"><span data-stu-id="dbe1a-129">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- <span data-ttu-id="dbe1a-130">.smartscreen.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dbe1a-130">.smartscreen.microsoft.com</span></span>
- <span data-ttu-id="dbe1a-131">.smartscreen-prod.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dbe1a-131">.smartscreen-prod.microsoft.com</span></span>

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="dbe1a-132">Просмотр событий защиты сети в Центре безопасности конечных точек Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="dbe1a-132">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="dbe1a-133">Microsoft Defender for Endpoint предоставляет подробные отчеты о событиях и блоках в рамках сценариев расследования [оповещений.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="dbe1a-133">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="dbe1a-134">Вы можете запрашивать данные Microsoft Defender для конечных точек с помощью [расширенных методов охоты.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="dbe1a-134">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="dbe1a-135">Если вы используете [](audit-windows-defender.md)режим аудита, вы можете использовать расширенный режим охоты, чтобы узнать, как параметры сетевой защиты влияют на среду, если они включены.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-135">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="dbe1a-136">Вот пример запроса</span><span class="sxs-lookup"><span data-stu-id="dbe1a-136">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="dbe1a-137">Просмотр событий защиты сети в Windows Event Viewer</span><span class="sxs-lookup"><span data-stu-id="dbe1a-137">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="dbe1a-138">Вы можете просмотреть журнал событий Windows, чтобы просмотреть события, созданные при блоке сетевой защиты (или аудите) доступа к вредоносному IP или домену:</span><span class="sxs-lookup"><span data-stu-id="dbe1a-138">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="dbe1a-139">[Скопируйте XML напрямую.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="dbe1a-139">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="dbe1a-140">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-140">Select **OK**.</span></span>

<span data-ttu-id="dbe1a-141">Эта процедура создает настраиваемую точку зрения, которая фильтрует только следующие события, связанные с защитой сети:</span><span class="sxs-lookup"><span data-stu-id="dbe1a-141">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="dbe1a-142">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="dbe1a-142">Event ID</span></span> | <span data-ttu-id="dbe1a-143">Описание</span><span class="sxs-lookup"><span data-stu-id="dbe1a-143">Description</span></span> |
|:---|:---|
| <span data-ttu-id="dbe1a-144">5007</span><span class="sxs-lookup"><span data-stu-id="dbe1a-144">5007</span></span> | <span data-ttu-id="dbe1a-145">Событие при смене параметров</span><span class="sxs-lookup"><span data-stu-id="dbe1a-145">Event when settings are changed</span></span> |
| <span data-ttu-id="dbe1a-146">1125</span><span class="sxs-lookup"><span data-stu-id="dbe1a-146">1125</span></span> | <span data-ttu-id="dbe1a-147">Событие, когда защита сети загорелась в режиме аудита</span><span class="sxs-lookup"><span data-stu-id="dbe1a-147">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="dbe1a-148">1126</span><span class="sxs-lookup"><span data-stu-id="dbe1a-148">1126</span></span> | <span data-ttu-id="dbe1a-149">Событие, когда защита сети загорелась в режиме блокировки</span><span class="sxs-lookup"><span data-stu-id="dbe1a-149">Event when network protection fires in block mode</span></span> |

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="dbe1a-150">Устранение неполадок в сетевой защите</span><span class="sxs-lookup"><span data-stu-id="dbe1a-150">Network protection troubleshooting</span></span>

<span data-ttu-id="dbe1a-151">Из-за среды, в которой выполняется защита сети, Microsoft может не обнаруживать параметры прокси-сервера операционной системы.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-151">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="dbe1a-152">В некоторых случаях клиенты Network Protection не могут добраться до облачной службы.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-152">In some cases, Network Protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="dbe1a-153">Чтобы устранить проблему подключения, клиенты с лицензиями E5 должны настроить один из следующих ключей реестра Defender:</span><span class="sxs-lookup"><span data-stu-id="dbe1a-153">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="dbe1a-154">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="dbe1a-154">Related articles</span></span>

- <span data-ttu-id="dbe1a-155">[Оценка защиты](evaluate-network-protection.md) сети | Создай быстрый сценарий, в который показано, как работает функция и какие события обычно создаются.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-155">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="dbe1a-156">[Включить защиту](enable-network-protection.md) сети | Используйте групповой политики, PowerShell или MDM CSPs для обеспечения и управления сетевой защитой в сети.</span><span class="sxs-lookup"><span data-stu-id="dbe1a-156">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
