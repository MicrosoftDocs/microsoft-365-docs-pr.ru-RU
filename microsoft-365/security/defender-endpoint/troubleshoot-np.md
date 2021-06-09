---
title: Устранение проблем с защитой сети
description: Ресурсы и пример кода для устранения неполадок с защитой сети в Microsoft Defender для конечной точки.
keywords: устранение неполадок, ошибка, исправление, защита windows, например, asr, правила, бедра, устранение неполадок, аудит, исключение, ложное срабатыважение, нарушение, блокировка, Microsoft Defender для Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 481a8f15d6a41bda8dc866ce40d98c4f3717223d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844062"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="94920-104">Защита сети от неполадок</span><span class="sxs-lookup"><span data-stu-id="94920-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="94920-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="94920-105">**Applies to:**</span></span>
- [<span data-ttu-id="94920-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="94920-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="94920-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94920-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="94920-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="94920-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="94920-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="94920-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="94920-110">При использовании [сетевой защиты](network-protection.md) могут возникнуть проблемы, такие как:</span><span class="sxs-lookup"><span data-stu-id="94920-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="94920-111">Защита сети блокирует безопасный веб-сайт (ложное срабатывательство)</span><span class="sxs-lookup"><span data-stu-id="94920-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="94920-112">Защита сети не блокирует подозрительный или известный вредоносный веб-сайт (ложный отрицательный)</span><span class="sxs-lookup"><span data-stu-id="94920-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="94920-113">Для устранения этих проблем необходимо четыре шага:</span><span class="sxs-lookup"><span data-stu-id="94920-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="94920-114">Подтверждение необходимых условий</span><span class="sxs-lookup"><span data-stu-id="94920-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="94920-115">Чтобы проверить правило, используйте режим аудита</span><span class="sxs-lookup"><span data-stu-id="94920-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="94920-116">Добавление исключений для указанного правила (для ложных срабатыва-</span><span class="sxs-lookup"><span data-stu-id="94920-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="94920-117">Отправка журналов поддержки</span><span class="sxs-lookup"><span data-stu-id="94920-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="94920-118">Подтверждение необходимых условий</span><span class="sxs-lookup"><span data-stu-id="94920-118">Confirm prerequisites</span></span>

<span data-ttu-id="94920-119">Защита сети будет работать только на устройствах со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="94920-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="94920-120">Конечные точки запускаются Windows 10 Pro или Enterprise версии 1709 или выше.</span><span class="sxs-lookup"><span data-stu-id="94920-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="94920-121">Конечные точки используют антивирусная программа в Microsoft Defender в качестве единственного приложения для защиты от антивирусов.</span><span class="sxs-lookup"><span data-stu-id="94920-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="94920-122">[Узнайте, что происходит при использовании антивирусного решения, не используемого Корпорацией Майкрософт.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="94920-122">[See what happens when you are using a non-Microsoft antivirus solution](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="94920-123">[Включена защита в](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="94920-123">[Real-time protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="94920-124">[Включена облачная](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) защита.</span><span class="sxs-lookup"><span data-stu-id="94920-124">[Cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="94920-125">Режим аудита не включен.</span><span class="sxs-lookup"><span data-stu-id="94920-125">Audit mode is not enabled.</span></span> <span data-ttu-id="94920-126">Используйте [групповую](enable-network-protection.md#group-policy) политику, чтобы установить правило **отключено** (значение: **0).**</span><span class="sxs-lookup"><span data-stu-id="94920-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="94920-127">Использовать режим аудита</span><span class="sxs-lookup"><span data-stu-id="94920-127">Use audit mode</span></span>

<span data-ttu-id="94920-128">Вы можете включить защиту сети в режиме аудита, а затем посетить веб-сайт, созданный для демонстрации этой функции.</span><span class="sxs-lookup"><span data-stu-id="94920-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="94920-129">Все подключения к веб-сайту будут разрешены с помощью сетевой защиты, но событие будет включено в журнал, чтобы указать любое подключение, которое было бы заблокировано, если бы была включена защита сети.</span><span class="sxs-lookup"><span data-stu-id="94920-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="94920-130">Настройка сетевой защиты в **режиме аудита.**</span><span class="sxs-lookup"><span data-stu-id="94920-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="94920-131">Выполните действия подключения, которые вызывают проблему (например, попытка посетить сайт или подключиться к IP-адресу, который вы делаете или не хотите блокировать).</span><span class="sxs-lookup"><span data-stu-id="94920-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="94920-132">[Просмотрите журналы событий защиты](network-protection.md#review-network-protection-events-in-windows-event-viewer) сети, чтобы узнать, заблокировала ли бы эта функция подключение, если бы оно было установлено для **включения.**</span><span class="sxs-lookup"><span data-stu-id="94920-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="94920-133">Если защита сети не блокирует подключение, которое, как вы ожидаете, должно блокироваться, в включить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="94920-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="94920-134">Сообщение о ложном срабатыве или ложном отрицательном</span><span class="sxs-lookup"><span data-stu-id="94920-134">Report a false positive or false negative</span></span>

<span data-ttu-id="94920-135">Если вы протестировали эту функцию на демо-сайте и в режиме аудита, а защита сети работает в предварительно настроенных сценариях, но работает не так, как ожидалось, для определенного подключения используйте [веб-форму](https://www.microsoft.com/wdsi/filesubmission) отправки Защитник Windows Security Intelligence, чтобы сообщить о ложном отрицательном или ложном срабатывке для защиты сети.</span><span class="sxs-lookup"><span data-stu-id="94920-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="94920-136">С подпиской на E5 вы также можете предоставить ссылку на любое [связанное оповещение.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="94920-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="94920-137">См. [адрес ложных срабатыва-срабатыва-минусов в Microsoft Defender для конечной точки.](defender-endpoint-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="94920-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="94920-138">Исключение веб-сайта из области защиты сети</span><span class="sxs-lookup"><span data-stu-id="94920-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="94920-139">Чтобы разрешить заблокированный веб-сайт (ложное срабатываний), добавьте ЕГО URL-адрес в [список доверенных сайтов.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)</span><span class="sxs-lookup"><span data-stu-id="94920-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="94920-140">Веб-ресурсы из этого списка обходят проверку защиты сети.</span><span class="sxs-lookup"><span data-stu-id="94920-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="94920-141">Сбор диагностических данных для отправки файлов</span><span class="sxs-lookup"><span data-stu-id="94920-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="94920-142">Когда вы сообщаете о проблеме с сетевой защитой, вам будет предложено собирать и отправлять диагностические данные, которые могут использоваться группами поддержки Майкрософт и инженерными группами для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="94920-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="94920-143">Откройте повышенную командную подсказку и измените каталог Защитник Windows:</span><span class="sxs-lookup"><span data-stu-id="94920-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="94920-144">Запустите эту команду для создания диагностических журналов:</span><span class="sxs-lookup"><span data-stu-id="94920-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="94920-145">Прикрепить файл к форме отправки.</span><span class="sxs-lookup"><span data-stu-id="94920-145">Attach the file to the submission form.</span></span> <span data-ttu-id="94920-146">По умолчанию диагностические журналы сохраняются на `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` уровне .</span><span class="sxs-lookup"><span data-stu-id="94920-146">By default, diagnostic logs are saved at `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a><span data-ttu-id="94920-147">Устранение проблем с подключением с помощью защиты сети (для клиентов E5)</span><span class="sxs-lookup"><span data-stu-id="94920-147">Resolve connectivity issues with network protection (for E5 customers)</span></span>

<span data-ttu-id="94920-148">Из-за среды, в которой выполняется защита сети, Корпорация Майкрософт не может видеть параметры прокси-сервера операционной системы.</span><span class="sxs-lookup"><span data-stu-id="94920-148">Due to the environment where network protection runs, Microsoft is unable to see your operating system proxy settings.</span></span> <span data-ttu-id="94920-149">В некоторых случаях клиенты сетевой защиты не могут добраться до облачной службы.</span><span class="sxs-lookup"><span data-stu-id="94920-149">In some cases, network protection clients are unable to reach the cloud service.</span></span> <span data-ttu-id="94920-150">Чтобы устранить проблемы с подключением с помощью сетевой защиты, настройте один из следующих ключей реестра, чтобы защита сети знала о конфигурации прокси:</span><span class="sxs-lookup"><span data-stu-id="94920-150">To resolve connectivity issues with network protection, configure one of the following registry keys so that network protection becomes aware of the proxy configuration:</span></span>

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

<span data-ttu-id="94920-151">---OR---</span><span class="sxs-lookup"><span data-stu-id="94920-151">---OR---</span></span>


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

<span data-ttu-id="94920-152">Ключ реестра можно настроить с помощью PowerShell, Microsoft Endpoint Manager или групповой политики.</span><span class="sxs-lookup"><span data-stu-id="94920-152">You can configure the registry key by using PowerShell, Microsoft Endpoint Manager, or Group Policy.</span></span> <span data-ttu-id="94920-153">Вот некоторые ресурсы, которые помогут:</span><span class="sxs-lookup"><span data-stu-id="94920-153">Here are some resources to help:</span></span>
- [<span data-ttu-id="94920-154">Работа с ключами реестра</span><span class="sxs-lookup"><span data-stu-id="94920-154">Working with Registry Keys</span></span>](/powershell/scripting/samples/working-with-registry-keys)
- [<span data-ttu-id="94920-155">Настройка настраиваемых параметров клиента для Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="94920-155">Configure custom client settings for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [<span data-ttu-id="94920-156">Используйте параметры групповой политики для управления Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="94920-156">Use Group Policy settings to manage Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a><span data-ttu-id="94920-157">См. также</span><span class="sxs-lookup"><span data-stu-id="94920-157">See also</span></span>

- [<span data-ttu-id="94920-158">Защита сети</span><span class="sxs-lookup"><span data-stu-id="94920-158">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="94920-159">Оценка защиты сети</span><span class="sxs-lookup"><span data-stu-id="94920-159">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="94920-160">Включить защиту сети</span><span class="sxs-lookup"><span data-stu-id="94920-160">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="94920-161">Адрес ложных срабатыва-срабатыва-</span><span class="sxs-lookup"><span data-stu-id="94920-161">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
