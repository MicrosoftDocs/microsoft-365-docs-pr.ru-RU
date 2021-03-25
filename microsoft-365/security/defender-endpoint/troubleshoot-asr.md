---
title: Устранение проблем с правилами уменьшения поверхности атаки
description: Ресурсы и пример кода для устранения неполадок с правилами уменьшения поверхности атаки в Microsoft Defender для конечной точки.
keywords: устранение неполадок, ошибка, исправление, защитник Windows, например, asr, правила, бедра, устранение неполадок, аудит, исключение, ложное срабатывательство, нарушение, блокировка, защитник Майкрософт для конечной точки, защита от угроз microsoft defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: d090c82e8c76da8f2e19dc9189006fdea3d6990d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074846"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a><span data-ttu-id="45270-104">Правила устранения неполадок в области уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="45270-104">Troubleshoot attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="45270-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="45270-105">**Applies to:**</span></span>
- [<span data-ttu-id="45270-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="45270-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="45270-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45270-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="45270-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="45270-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="45270-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="45270-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="45270-110">При использовании [правил уменьшения поверхности](attack-surface-reduction.md) атаки могут возникнуть проблемы, такие как:</span><span class="sxs-lookup"><span data-stu-id="45270-110">When you use [attack surface reduction rules](attack-surface-reduction.md) you may run into issues, such as:</span></span>

- <span data-ttu-id="45270-111">Правило блокирует файл, обработку или выполняет другие действия, которые не должны выполняться (ложное срабатыва-</span><span class="sxs-lookup"><span data-stu-id="45270-111">A rule blocks a file, process, or performs some other action that it shouldn't (false positive)</span></span>

- <span data-ttu-id="45270-112">Правило не работает так, как описано, или не блокирует файл или процесс, который он должен (ложный отрицательный)</span><span class="sxs-lookup"><span data-stu-id="45270-112">A rule doesn't work as described, or doesn't block a file or process that it should (false negative)</span></span>

<span data-ttu-id="45270-113">Для устранения этих проблем необходимо четыре шага:</span><span class="sxs-lookup"><span data-stu-id="45270-113">There are four steps to troubleshooting these problems:</span></span>

1. [<span data-ttu-id="45270-114">Подтверждение необходимых условий</span><span class="sxs-lookup"><span data-stu-id="45270-114">Confirm prerequisites</span></span>](#confirm-prerequisites)

2. [<span data-ttu-id="45270-115">Чтобы проверить правило, используйте режим аудита</span><span class="sxs-lookup"><span data-stu-id="45270-115">Use audit mode to test the rule</span></span>](#use-audit-mode-to-test-the-rule)

3. <span data-ttu-id="45270-116">[Добавление исключений для указанного правила](#add-exclusions-for-a-false-positive) (для ложных срабатыва-</span><span class="sxs-lookup"><span data-stu-id="45270-116">[Add exclusions for the specified rule](#add-exclusions-for-a-false-positive) (for false positives)</span></span>

4. [<span data-ttu-id="45270-117">Отправка журналов поддержки</span><span class="sxs-lookup"><span data-stu-id="45270-117">Submit support logs</span></span>](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a><span data-ttu-id="45270-118">Подтверждение необходимых условий</span><span class="sxs-lookup"><span data-stu-id="45270-118">Confirm prerequisites</span></span>

<span data-ttu-id="45270-119">Правила уменьшения поверхности атаки будут работать только на устройствах со следующими условиями:</span><span class="sxs-lookup"><span data-stu-id="45270-119">Attack surface reduction rules will only work on devices with the following conditions:</span></span>

- <span data-ttu-id="45270-120">Конечные точки работают в Windows 10 Enterprise версии 1709 (также известной как Fall Creators Update).</span><span class="sxs-lookup"><span data-stu-id="45270-120">Endpoints are running Windows 10 Enterprise, version 1709 (also known as the Fall Creators Update).</span></span>

- <span data-ttu-id="45270-121">Конечные точки используют антивирус Microsoft Defender в качестве единственного приложения для защиты от антивирусов.</span><span class="sxs-lookup"><span data-stu-id="45270-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="45270-122">[Использование любого другого антивирусного приложения приведет к](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)отключению microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="45270-122">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

- <span data-ttu-id="45270-123">[Включена защита в](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="45270-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>

- <span data-ttu-id="45270-124">Режим аудита не включен.</span><span class="sxs-lookup"><span data-stu-id="45270-124">Audit mode isn't enabled.</span></span> <span data-ttu-id="45270-125">Используйте групповую политику, чтобы установить правило **Отключено** (значение: **0),** как описано в правилах уменьшения поверхности [атаки.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="45270-125">Use Group Policy to set the rule to **Disabled** (value: **0**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

<span data-ttu-id="45270-126">Если все эти необходимые условия выполнены, переступим к следующему шагу, чтобы проверить правило в режиме аудита.</span><span class="sxs-lookup"><span data-stu-id="45270-126">If these prerequisites have all been met, proceed to the next step to test the rule in audit mode.</span></span>

## <a name="use-audit-mode-to-test-the-rule"></a><span data-ttu-id="45270-127">Чтобы проверить правило, используйте режим аудита</span><span class="sxs-lookup"><span data-stu-id="45270-127">Use audit mode to test the rule</span></span>

<span data-ttu-id="45270-128">Вы можете посетить веб-сайт Защитник Windows test ground в [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) чтобы подтвердить, что правила уменьшения поверхности атаки обычно работают для предварительно настроенных сценариев и процессов на устройстве, или вы можете использовать режим аудита, который включает правила только для отчетности.</span><span class="sxs-lookup"><span data-stu-id="45270-128">You can visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm attack surface reduction rules are generally working for pre-configured scenarios and processes on a device, or you can use audit mode, which enables rules for reporting only.</span></span>

<span data-ttu-id="45270-129">Следуйте этим инструкциям в с помощью средства [демонстрации,](evaluate-attack-surface-reduction.md) чтобы узнать, как работают правила уменьшения поверхности атаки для проверки конкретного правила, с которым вы столкнулись.</span><span class="sxs-lookup"><span data-stu-id="45270-129">Follow these instructions in [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.</span></span>

1. <span data-ttu-id="45270-130">Включить режим аудита для определенного правила, которое необходимо протестировать.</span><span class="sxs-lookup"><span data-stu-id="45270-130">Enable audit mode for the specific rule you want to test.</span></span> <span data-ttu-id="45270-131">Используйте групповую политику, чтобы установить правило в **режиме аудита** (значение: **2),** как описано в правилах уменьшения поверхности [атаки.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="45270-131">Use Group Policy to set the rule to **Audit mode** (value: **2**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span> <span data-ttu-id="45270-132">Режим аудита позволяет правилу сообщать о файле или процессе, но все равно позволяет ему работать.</span><span class="sxs-lookup"><span data-stu-id="45270-132">Audit mode allows the rule to report the file or process, but will still allow it to run.</span></span>

2. <span data-ttu-id="45270-133">Выполните действия, которые вызывают проблему (например, откройте или выполните файл или процесс, который должен быть заблокирован, но разрешен).</span><span class="sxs-lookup"><span data-stu-id="45270-133">Perform the activity that is causing an issue (for example, open or execute the file or process that should be blocked but is being allowed).</span></span>

3. <span data-ttu-id="45270-134">[Просмотрите журналы](attack-surface-reduction.md) событий событий правила уменьшения поверхности атаки, чтобы узнать, заблокировало ли правило файл или процесс, если бы правило было за установлено для **включения.**</span><span class="sxs-lookup"><span data-stu-id="45270-134">[Review the attack surface reduction rule event logs](attack-surface-reduction.md) to see if the rule would have blocked the file or process if the rule had been set to **Enabled**.</span></span>

<span data-ttu-id="45270-135">Если правило не блокирует файл или процесс, который следует заблокировать, сначала проверьте, включен ли режим аудита.</span><span class="sxs-lookup"><span data-stu-id="45270-135">If a rule isn't blocking a file or process that you're expecting it should block, first check if audit mode is enabled.</span></span>

<span data-ttu-id="45270-136">Режим аудита мог быть включен для тестирования другой функции или с помощью автоматического сценария PowerShell и не был отключен после завершения тестов.</span><span class="sxs-lookup"><span data-stu-id="45270-136">Audit mode may have been enabled for testing another feature, or by an automated PowerShell script, and may not have been disabled after the tests were completed.</span></span>

<span data-ttu-id="45270-137">Если вы протестировали правило с помощью средства демонстрации и в режиме аудита, а правила уменьшения поверхности атаки работают над заранее настроенными сценариями, но это правило не работает, переехав в любой из следующих разделов в зависимости от ситуации:</span><span class="sxs-lookup"><span data-stu-id="45270-137">If you've tested the rule with the demo tool and with audit mode, and attack surface reduction rules are working on pre-configured scenarios, but the rule isn't working as expected, proceed to either of the following sections based on your situation:</span></span>

1. <span data-ttu-id="45270-138">Если правило уменьшения поверхности атаки блокирует то, что не должно блокировать (также известное как ложное срабатыважение), сначала можно добавить исключение правила уменьшения поверхности [атаки.](#add-exclusions-for-a-false-positive)</span><span class="sxs-lookup"><span data-stu-id="45270-138">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can [first add an attack surface reduction rule exclusion](#add-exclusions-for-a-false-positive).</span></span>

2. <span data-ttu-id="45270-139">Если правило уменьшения поверхности атаки не блокирует то, что оно должно блокировать (также известное как ложный отрицательный), вы можете немедленно перейти к последнему шагу, собирая диагностические данные и сообщая нам о [проблеме.](#collect-diagnostic-data-for-file-submissions)</span><span class="sxs-lookup"><span data-stu-id="45270-139">If the attack surface reduction rule isn't blocking something that it should block (also known as a false negative), you can proceed immediately to the last step, [collecting diagnostic data and submitting the issue to us](#collect-diagnostic-data-for-file-submissions).</span></span>

## <a name="add-exclusions-for-a-false-positive"></a><span data-ttu-id="45270-140">Добавление исключений для ложного срабатыва</span><span class="sxs-lookup"><span data-stu-id="45270-140">Add exclusions for a false positive</span></span>

<span data-ttu-id="45270-141">Если правило уменьшения поверхности атаки блокирует то, что не должно блокировать (также известное как ложное срабатывание), можно добавить исключения, чтобы предотвратить оценку исключенных файлов или папок правилами уменьшения поверхности атаки.</span><span class="sxs-lookup"><span data-stu-id="45270-141">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can add exclusions to prevent attack surface reduction rules from evaluating the excluded files or folders.</span></span>

<span data-ttu-id="45270-142">Чтобы добавить исключение, см. [в статью Настройка уменьшения поверхности attack.](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="45270-142">To add an exclusion, see [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="45270-143">Можно указать отдельные файлы и папки, которые следует исключить, но нельзя указать отдельные правила.</span><span class="sxs-lookup"><span data-stu-id="45270-143">You can specify individual files and folders to be excluded, but you cannot specify individual rules.</span></span>
><span data-ttu-id="45270-144">Это означает, что все файлы или папки, которые исключены, будут исключены из всех правил ASR.</span><span class="sxs-lookup"><span data-stu-id="45270-144">This means any files or folders that are excluded will be excluded from all ASR rules.</span></span>

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="45270-145">Сообщение о ложном срабатыве или ложном отрицательном</span><span class="sxs-lookup"><span data-stu-id="45270-145">Report a false positive or false negative</span></span>

<span data-ttu-id="45270-146">Чтобы [сообщить о ложном отрицательном](https://www.microsoft.com/wdsi/filesubmission) или ложном срабатывии для защиты сети, используйте веб-форму отправки Защитник Windows Security Intelligence.</span><span class="sxs-lookup"><span data-stu-id="45270-146">Use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="45270-147">С подпиской на Windows E5 вы также можете предоставить ссылку на любое [связанное оповещение.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="45270-147">With a Windows E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="45270-148">Сбор диагностических данных для отправки файлов</span><span class="sxs-lookup"><span data-stu-id="45270-148">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="45270-149">Когда вы сообщаете о проблеме с правилами уменьшения поверхности атаки, вам будет предложено собирать и отправлять диагностические данные, которые могут использоваться группами поддержки Майкрософт и инженерными группами для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="45270-149">When you report a problem with attack surface reduction rules, you're asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="45270-150">Откройте повышенную командную подсказку и измените каталог Защитник Windows:</span><span class="sxs-lookup"><span data-stu-id="45270-150">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd "c:\program files\windows defender"
   ```

2. <span data-ttu-id="45270-151">Запустите эту команду для создания диагностических журналов:</span><span class="sxs-lookup"><span data-stu-id="45270-151">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="45270-152">По умолчанию они сохраняются до `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="45270-152">By default, they're saved to `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> <span data-ttu-id="45270-153">Прикрепить файл к форме отправки.</span><span class="sxs-lookup"><span data-stu-id="45270-153">Attach the file to the submission form.</span></span>

## <a name="related-articles"></a><span data-ttu-id="45270-154">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="45270-154">Related articles</span></span>

- [<span data-ttu-id="45270-155">Правила сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="45270-155">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="45270-156">Включить правила уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="45270-156">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)

- [<span data-ttu-id="45270-157">Оценка правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="45270-157">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
