---
title: Устранение проблем с защитой сети
description: Ресурсы и пример кода для устранения неполадок с защитой сети в Microsoft Defender для конечной точки.
keywords: устранение неполадок, ошибка, исправление, защитник Windows, например, asr, правила, бедра, устранение неполадок, аудит, исключение, ложное срабатывательство, нарушение, блокировка, защитник Майкрософт для конечной точки, защита от угроз microsoft defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.date: 01/26/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 34bebddcf052a643529f1d2b8a8a869a0ffe4a91
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183827"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="67418-104">Защита сети от неполадок</span><span class="sxs-lookup"><span data-stu-id="67418-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="67418-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="67418-105">**Applies to:**</span></span>
- [<span data-ttu-id="67418-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="67418-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="67418-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67418-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="67418-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="67418-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="67418-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="67418-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="67418-110">При использовании [сетевой защиты](network-protection.md) могут возникнуть проблемы, такие как:</span><span class="sxs-lookup"><span data-stu-id="67418-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="67418-111">Защита сети блокирует безопасный веб-сайт (ложное срабатывательство)</span><span class="sxs-lookup"><span data-stu-id="67418-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="67418-112">Защита сети не блокирует подозрительный или известный вредоносный веб-сайт (ложный отрицательный)</span><span class="sxs-lookup"><span data-stu-id="67418-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="67418-113">Для устранения этих проблем необходимо четыре шага:</span><span class="sxs-lookup"><span data-stu-id="67418-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="67418-114">Подтверждение необходимых условий</span><span class="sxs-lookup"><span data-stu-id="67418-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="67418-115">Чтобы проверить правило, используйте режим аудита</span><span class="sxs-lookup"><span data-stu-id="67418-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="67418-116">Добавление исключений для указанного правила (для ложных срабатыва-</span><span class="sxs-lookup"><span data-stu-id="67418-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="67418-117">Отправка журналов поддержки</span><span class="sxs-lookup"><span data-stu-id="67418-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="67418-118">Подтверждение необходимых условий</span><span class="sxs-lookup"><span data-stu-id="67418-118">Confirm prerequisites</span></span>

<span data-ttu-id="67418-119">Защита сети будет работать только на устройствах со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="67418-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="67418-120">Конечные точки работают в выпуске Windows 10 Pro или Enterprise версии 1709 или выше.</span><span class="sxs-lookup"><span data-stu-id="67418-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="67418-121">Конечные точки используют антивирус Microsoft Defender в качестве единственного приложения для защиты от антивирусов.</span><span class="sxs-lookup"><span data-stu-id="67418-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="67418-122">[Узнайте, что происходит при использовании антивирусного решения, не используемого Корпорацией Майкрософт.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="67418-122">[See what happens when you are using a non-Microsoft antivirus solution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="67418-123">[Включена защита в](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="67418-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="67418-124">[Включена облачная](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) защита.</span><span class="sxs-lookup"><span data-stu-id="67418-124">[Cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="67418-125">Режим аудита не включен.</span><span class="sxs-lookup"><span data-stu-id="67418-125">Audit mode is not enabled.</span></span> <span data-ttu-id="67418-126">Используйте [групповую](enable-network-protection.md#group-policy) политику, чтобы установить правило **отключено** (значение: **0).**</span><span class="sxs-lookup"><span data-stu-id="67418-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="67418-127">Использование режима аудита</span><span class="sxs-lookup"><span data-stu-id="67418-127">Use audit mode</span></span>

<span data-ttu-id="67418-128">Вы можете включить защиту сети в режиме аудита, а затем посетить веб-сайт, созданный для демонстрации этой функции.</span><span class="sxs-lookup"><span data-stu-id="67418-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="67418-129">Все подключения к веб-сайту будут разрешены с помощью сетевой защиты, но событие будет включено в журнал, чтобы указать любое подключение, которое было бы заблокировано, если бы была включена защита сети.</span><span class="sxs-lookup"><span data-stu-id="67418-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="67418-130">Настройка сетевой защиты в **режиме аудита.**</span><span class="sxs-lookup"><span data-stu-id="67418-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="67418-131">Выполните действия подключения, которые вызывают проблему (например, попытка посетить сайт или подключиться к IP-адресу, который вы делаете или не хотите блокировать).</span><span class="sxs-lookup"><span data-stu-id="67418-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="67418-132">[Просмотрите журналы событий защиты](network-protection.md#review-network-protection-events-in-windows-event-viewer) сети, чтобы узнать, заблокировала ли бы эта функция подключение, если бы оно было установлено для **включения.**</span><span class="sxs-lookup"><span data-stu-id="67418-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="67418-133">Если защита сети не блокирует подключение, которое, как вы ожидаете, должно блокироваться, в включить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="67418-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="67418-134">Сообщение о ложном срабатыве или ложном отрицательном</span><span class="sxs-lookup"><span data-stu-id="67418-134">Report a false positive or false negative</span></span>

<span data-ttu-id="67418-135">Если вы протестировали эту функцию на демо-сайте и в режиме аудита, а защита сети работает в предварительно настроенных сценариях, но работает не так, как ожидалось для определенного подключения, используйте [веб-форму](https://www.microsoft.com/wdsi/filesubmission) отправки Защитник Windows Security Intelligence, чтобы сообщить о ложном отрицательном или ложном срабатывке для защиты сети.</span><span class="sxs-lookup"><span data-stu-id="67418-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="67418-136">С подпиской на E5 вы также можете предоставить ссылку на любое [связанное оповещение.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="67418-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="67418-137">См. [адрес ложных срабатыва-срабатыва-минусов в Microsoft Defender для конечной точки.](defender-endpoint-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="67418-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="67418-138">Исключение веб-сайта из области защиты сети</span><span class="sxs-lookup"><span data-stu-id="67418-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="67418-139">Чтобы разрешить заблокированный веб-сайт (ложное срабатываний), добавьте ЕГО URL-адрес в [список доверенных сайтов.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)</span><span class="sxs-lookup"><span data-stu-id="67418-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="67418-140">Веб-ресурсы из этого списка обходят проверку защиты сети.</span><span class="sxs-lookup"><span data-stu-id="67418-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="67418-141">Сбор диагностических данных для отправки файлов</span><span class="sxs-lookup"><span data-stu-id="67418-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="67418-142">Когда вы сообщаете о проблеме с сетевой защитой, вам будет предложено собирать и отправлять диагностические данные, которые могут использоваться группами поддержки Майкрософт и инженерными группами для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="67418-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="67418-143">Откройте повышенную командную подсказку и измените каталог Защитник Windows:</span><span class="sxs-lookup"><span data-stu-id="67418-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="67418-144">Запустите эту команду для создания диагностических журналов:</span><span class="sxs-lookup"><span data-stu-id="67418-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="67418-145">По умолчанию они сохраняются в C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab.</span><span class="sxs-lookup"><span data-stu-id="67418-145">By default, they are saved to C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab.</span></span> <span data-ttu-id="67418-146">Прикрепить файл к форме отправки.</span><span class="sxs-lookup"><span data-stu-id="67418-146">Attach the file to the submission form.</span></span>

## <a name="related-topics"></a><span data-ttu-id="67418-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="67418-147">Related topics</span></span>

- [<span data-ttu-id="67418-148">Защита сети</span><span class="sxs-lookup"><span data-stu-id="67418-148">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="67418-149">Оценка защиты сети</span><span class="sxs-lookup"><span data-stu-id="67418-149">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="67418-150">Включить защиту сети</span><span class="sxs-lookup"><span data-stu-id="67418-150">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="67418-151">Адрес ложных срабатыва-срабатыва-</span><span class="sxs-lookup"><span data-stu-id="67418-151">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
