---
title: Новые возможности в Microsoft Defender для конечной точки для Mac
description: Узнайте о главных изменениях для предыдущих версий Microsoft Defender для конечной точки для Mac.
keywords: Microsoft, defender, atp, mac, installation, macos, Whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f1cd2221ab07caeab341447ebd19824d7476fb52
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187379"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="9e101-104">Новые возможности в Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="9e101-104">What's new in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9e101-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9e101-105">**Applies to:**</span></span>
- [<span data-ttu-id="9e101-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9e101-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9e101-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e101-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9e101-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="9e101-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9e101-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="9e101-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="9e101-110">В macOS 11 (Big Sur) Microsoft Defender для конечной точки требует дополнительных профилей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9e101-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="9e101-111">Если вы существующий клиент, обновляющийся из более ранних версий macOS, не забудьте развернуть дополнительные профили конфигурации, перечисленные [на этой странице.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9e101-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e101-112">Поддержка macOS 10.13 (High Sierra) будет прекращена 15 февраля 2021 г.</span><span class="sxs-lookup"><span data-stu-id="9e101-112">Support for macOS 10.13 (High Sierra) will be discontinued on February 15th, 2021.</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="9e101-113">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="9e101-113">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="9e101-114">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-114">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="9e101-115">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="9e101-115">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="9e101-116">Старый синтаксис средства командной строки был обесценит с помощью этого выпуска.</span><span class="sxs-lookup"><span data-stu-id="9e101-116">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="9e101-117">Сведения о новом синтаксисе см. в [сайте Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="9e101-117">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="9e101-118">Добавлен новый переключатель командной строки, чтобы отключить расширение сети: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="9e101-118">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="9e101-119">Эта команда может быть полезна для устранения проблем с сетью, которые могут быть связаны с Microsoft Defender для конечной точки для Mac</span><span class="sxs-lookup"><span data-stu-id="9e101-119">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="9e101-120">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-120">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="9e101-121">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="9e101-121">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="9e101-122">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-122">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="9e101-123">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="9e101-123">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="9e101-124">Улучшена надежность агента при работе на macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="9e101-124">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="9e101-125">Добавлен новый переключатель командной строки () для игнорирования исключений `--ignore-exclusions` av во время пользовательских сканирований ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="9e101-125">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="9e101-126">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-126">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="9e101-127">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="9e101-127">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="9e101-128">Устранены условия, когда Microsoft Defender для конечной точки запускала ошибку macOS 11 (Big Sur), которая проявляется в панике ядра</span><span class="sxs-lookup"><span data-stu-id="9e101-128">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="9e101-129">Исправлена утечка памяти в расширении системы безопасности конечных точек при работе на mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="9e101-129">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="9e101-130">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-130">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="9e101-131">101.10.72</span><span class="sxs-lookup"><span data-stu-id="9e101-131">101.10.72</span></span>

- <span data-ttu-id="9e101-132">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-132">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="9e101-133">101.09.61</span><span class="sxs-lookup"><span data-stu-id="9e101-133">101.09.61</span></span>

- <span data-ttu-id="9e101-134">Добавлено новое управляемое предпочтение для [отключения параметра отправки отзывов](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="9e101-134">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="9e101-135">Значок меню состояния теперь показывает здоровое состояние при настройке параметров продукта.</span><span class="sxs-lookup"><span data-stu-id="9e101-135">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="9e101-136">Ранее значок меню состояния отображал состояние предупреждения или ошибки, даже если параметры продукта управлялись администратором.</span><span class="sxs-lookup"><span data-stu-id="9e101-136">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="9e101-137">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-137">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="9e101-138">101.09.50</span><span class="sxs-lookup"><span data-stu-id="9e101-138">101.09.50</span></span>

- <span data-ttu-id="9e101-139">Эта версия продукта была проверена на macOS Big Sur 11 бета-версии 9</span><span class="sxs-lookup"><span data-stu-id="9e101-139">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="9e101-140">Новый синтаксис для средства `mdatp` командной строки теперь является по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9e101-140">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="9e101-141">Дополнительные сведения о новом синтаксисе см. в сайте [Resources for Microsoft Defender for Endpoint for Mac.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="9e101-141">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="9e101-142">Старый синтаксис средства командной строки будет удален из продукта 1 января **2021 г.**</span><span class="sxs-lookup"><span data-stu-id="9e101-142">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="9e101-143">Расширенный `mdatp diagnostic create` с помощью нового параметра (), который позволяет сохранить журналы диагностики в другом `--path [directory]` каталоге</span><span class="sxs-lookup"><span data-stu-id="9e101-143">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="9e101-144">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-144">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="9e101-145">101.09.49</span><span class="sxs-lookup"><span data-stu-id="9e101-145">101.09.49</span></span>

- <span data-ttu-id="9e101-146">Улучшения пользовательского интерфейса для различия исключений, управляемых ИТ-администратором, и исключений, определенных локальным пользователем</span><span class="sxs-lookup"><span data-stu-id="9e101-146">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="9e101-147">Улучшение использования ЦП во время проверки по запросу</span><span class="sxs-lookup"><span data-stu-id="9e101-147">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="9e101-148">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-148">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="9e101-149">101.07.23</span><span class="sxs-lookup"><span data-stu-id="9e101-149">101.07.23</span></span>

- <span data-ttu-id="9e101-150">Добавлены новые поля для проверки состояния пассивного режима и ID группы `mdatp --health` EDR</span><span class="sxs-lookup"><span data-stu-id="9e101-150">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="9e101-151">`mdatp --health` будет заменено `mdatp health` в будущем обновлении продукта.</span><span class="sxs-lookup"><span data-stu-id="9e101-151">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="9e101-152">Исправлена ошибка, при которой автоматическая отправка образца не была помечена как управляемой в пользовательском интерфейсе</span><span class="sxs-lookup"><span data-stu-id="9e101-152">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="9e101-153">Добавлены новые параметры для управления хранением элементов в истории антивирусного сканирования.</span><span class="sxs-lookup"><span data-stu-id="9e101-153">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="9e101-154">Теперь можно [указать количество](mac-preferences.md#antivirus-scan-history-retention-in-days) дней для сохранения элементов в истории сканирования и указать максимальное число элементов [в истории сканирования.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="9e101-154">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="9e101-155">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-155">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="9e101-156">101.06.63</span><span class="sxs-lookup"><span data-stu-id="9e101-156">101.06.63</span></span>

- <span data-ttu-id="9e101-157">Устранена регрессия производительности, представленная в версии `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="9e101-157">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="9e101-158">Регрессия была введена с исправлением для устранения паники ядра, наблюдаемой некоторыми клиентами при доступе к акциям SMB.</span><span class="sxs-lookup"><span data-stu-id="9e101-158">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="9e101-159">Мы вернули это изменение кода и исследуем альтернативные способы устранения паники ядра.</span><span class="sxs-lookup"><span data-stu-id="9e101-159">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="9e101-160">101.05.17</span><span class="sxs-lookup"><span data-stu-id="9e101-160">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e101-161">Мы работаем над новым и расширенным синтаксисом для средства `mdatp` командной строки.</span><span class="sxs-lookup"><span data-stu-id="9e101-161">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="9e101-162">Новый синтаксис в настоящее время является по умолчанию в каналах обновления Insider Fast и Insider Slow.</span><span class="sxs-lookup"><span data-stu-id="9e101-162">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="9e101-163">Мы рекомендуем вам famliliarize себя с помощью этого нового синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="9e101-163">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="9e101-164">Мы продолжим поддерживать старый синтаксис параллельно с новым синтаксисом и в предстоящие месяцы будем предоставлять дополнительные возможности связи по плану амортизации для старого синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="9e101-164">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="9e101-165">Устранена паника ядра, которая иногда возникла при доступе к акциям SMB-файла</span><span class="sxs-lookup"><span data-stu-id="9e101-165">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="9e101-166">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-166">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="9e101-167">101.05.16</span><span class="sxs-lookup"><span data-stu-id="9e101-167">101.05.16</span></span>

- <span data-ttu-id="9e101-168">Улучшение логики быстрого сканирования, чтобы значительно сократить число отсканированных файлов</span><span class="sxs-lookup"><span data-stu-id="9e101-168">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="9e101-169">Добавлена [поддержка автозаполнения](mac-resources.md#how-to-enable-autocompletion) для средства командной строки</span><span class="sxs-lookup"><span data-stu-id="9e101-169">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="9e101-170">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-170">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="9e101-171">101.03.12</span><span class="sxs-lookup"><span data-stu-id="9e101-171">101.03.12</span></span>

- <span data-ttu-id="9e101-172">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-172">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="9e101-173">101.01.54</span><span class="sxs-lookup"><span data-stu-id="9e101-173">101.01.54</span></span>

- <span data-ttu-id="9e101-174">Улучшения совместимости с машиной времени</span><span class="sxs-lookup"><span data-stu-id="9e101-174">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="9e101-175">Улучшения доступности</span><span class="sxs-lookup"><span data-stu-id="9e101-175">Accessibility improvements</span></span>
- <span data-ttu-id="9e101-176">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-176">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="9e101-177">101.00.31</span><span class="sxs-lookup"><span data-stu-id="9e101-177">101.00.31</span></span>

- <span data-ttu-id="9e101-178">Улучшенный опыт работы [с onboarding продуктов для пользователей Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="9e101-178">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="9e101-179">Исключения [антивирусов теперь поддерживают подкарды](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="9e101-179">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="9e101-180">Добавлена возможность запуска антивирусных сканов из контекстного меню macOS.</span><span class="sxs-lookup"><span data-stu-id="9e101-180">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="9e101-181">Теперь вы можете щелкнуть правой кнопкой мыши файл или папку в Finder и выбрать сканирование с **помощью Microsoft Defender для конечной точки**</span><span class="sxs-lookup"><span data-stu-id="9e101-181">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="9e101-182">В настоящее время установщик явно запрещает понижение продуктов на месте.</span><span class="sxs-lookup"><span data-stu-id="9e101-182">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="9e101-183">Если требуется понизить рейтинг, сначала отсоедините существующую версию и перенастройте устройство</span><span class="sxs-lookup"><span data-stu-id="9e101-183">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="9e101-184">Другие улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-184">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="9e101-185">100.90.27</span><span class="sxs-lookup"><span data-stu-id="9e101-185">100.90.27</span></span>

- <span data-ttu-id="9e101-186">Теперь можно установить [канал обновления](mac-updates.md#set-the-channel-name) для Microsoft Defender для конечной точки для Mac, который отличается от канала обновления по всей системе.</span><span class="sxs-lookup"><span data-stu-id="9e101-186">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint for Mac that is different from the system-wide update channel</span></span>
- <span data-ttu-id="9e101-187">Значок нового продукта</span><span class="sxs-lookup"><span data-stu-id="9e101-187">New product icon</span></span>
- <span data-ttu-id="9e101-188">Другие улучшения пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="9e101-188">Other user experience improvements</span></span>
- <span data-ttu-id="9e101-189">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-189">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="9e101-190">100.86.92</span><span class="sxs-lookup"><span data-stu-id="9e101-190">100.86.92</span></span>

- <span data-ttu-id="9e101-191">Улучшения совместимости с машиной времени</span><span class="sxs-lookup"><span data-stu-id="9e101-191">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="9e101-192">Устранена проблема, из-за которой продукт иногда не очищал все файлы во время `/Library/Application Support/Microsoft/Defender` деинсталлации</span><span class="sxs-lookup"><span data-stu-id="9e101-192">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="9e101-193">Снижение использования процессора продукта при обновлении продуктов Майкрософт с помощью Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="9e101-193">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="9e101-194">Другие улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-194">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="9e101-195">100.86.91</span><span class="sxs-lookup"><span data-stu-id="9e101-195">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="9e101-196">Чтобы обеспечить самую полную защиту для устройств macOS и в соответствии с Apple, прекращая доставку обновлений macOS нативную безопасность для версий ОС старше [текущего — 2], развертывание и обновления MDATP для Mac больше не будут поддерживаться на macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="9e101-196">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="9e101-197">MDATP для обновлений и улучшений Mac будут доставлены устройствам с версиями Catalina [10.15], Mojave [10.14], и High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="9e101-197">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="9e101-198">Если mDATP для Mac уже развернут на устройствах Sierra [10.12], перенастраивайся до последней версии macOS, чтобы исключить риски потери защиты.</span><span class="sxs-lookup"><span data-stu-id="9e101-198">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="9e101-199">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-199">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="9e101-200">100.83.73</span><span class="sxs-lookup"><span data-stu-id="9e101-200">100.83.73</span></span>

- <span data-ttu-id="9e101-201">Добавлены дополнительные элементы управления для ИТ-администраторов в области управления исключениями, управления настройками типа угроз и [](mac-preferences.md#exclusion-merge-policy) [запрета действий с угрозами](mac-preferences.md#disallowed-threat-actions) [](mac-preferences.md#threat-type-settings-merge-policy)</span><span class="sxs-lookup"><span data-stu-id="9e101-201">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="9e101-202">Если полный доступ к диску не включен на устройстве, предупреждение отображается в меню состояния</span><span class="sxs-lookup"><span data-stu-id="9e101-202">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="9e101-203">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-203">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="9e101-204">100.82.60</span><span class="sxs-lookup"><span data-stu-id="9e101-204">100.82.60</span></span>

- <span data-ttu-id="9e101-205">Устранена проблема, из-за которой продукт не может начать следовать обновлению определения.</span><span class="sxs-lookup"><span data-stu-id="9e101-205">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="9e101-206">100.80.42</span><span class="sxs-lookup"><span data-stu-id="9e101-206">100.80.42</span></span>

- <span data-ttu-id="9e101-207">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-207">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="9e101-208">100.79.42</span><span class="sxs-lookup"><span data-stu-id="9e101-208">100.79.42</span></span>

- <span data-ttu-id="9e101-209">Исправлена проблема, из-за которой Microsoft Defender для конечной точки для Mac иногда вмешивалась в машину времени</span><span class="sxs-lookup"><span data-stu-id="9e101-209">Fixed an issue where Microsoft Defender for Endpoint for Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="9e101-210">Добавлен новый переключатель в службу командной строки для тестирования подключения к службе backend</span><span class="sxs-lookup"><span data-stu-id="9e101-210">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="9e101-211">Добавлена возможность просмотра полной истории угроз в пользовательском интерфейсе (можно получить доступ из представления **истории** защиты)</span><span class="sxs-lookup"><span data-stu-id="9e101-211">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="9e101-212">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-212">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="9e101-213">100.72.15</span><span class="sxs-lookup"><span data-stu-id="9e101-213">100.72.15</span></span>

- <span data-ttu-id="9e101-214">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-214">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="9e101-215">100.70.99</span><span class="sxs-lookup"><span data-stu-id="9e101-215">100.70.99</span></span>

- <span data-ttu-id="9e101-216">Устранена проблема, которая влияет на возможность некоторых пользователей перейти на macOS Catalina при включенной защите в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="9e101-216">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="9e101-217">Эта спорадическая проблема была вызвана блокировкой файлов Microsoft Defender для конечной точки в пакете обновления Catalina при сканировании их на угрозы, что привело к сбоям в последовательности обновления.</span><span class="sxs-lookup"><span data-stu-id="9e101-217">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="9e101-218">100.68.99</span><span class="sxs-lookup"><span data-stu-id="9e101-218">100.68.99</span></span>

- <span data-ttu-id="9e101-219">Добавлена возможность настройки функции антивируса для работы в [пассивном режиме](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="9e101-219">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="9e101-220">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-220">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="9e101-221">100.65.28</span><span class="sxs-lookup"><span data-stu-id="9e101-221">100.65.28</span></span>

- <span data-ttu-id="9e101-222">Добавлена поддержка macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="9e101-222">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="9e101-223">MacOS 10.15 (Catalina) содержит новые улучшения безопасности и конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="9e101-223">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="9e101-224">Начиная с этой версии, по умолчанию приложения не могут получить доступ к определенным расположениям на диске (например, документы, скачивания, настольные компьютеры и т.д.) без явного согласия.</span><span class="sxs-lookup"><span data-stu-id="9e101-224">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="9e101-225">При отсутствии такого согласия Microsoft Defender для конечной точки не может полностью защитить ваше устройство.</span><span class="sxs-lookup"><span data-stu-id="9e101-225">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="9e101-226">Механизм предоставления такого согласия зависит от того, как вы развернули Microsoft Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="9e101-226">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="9e101-227">Для ручных развертываний см. обновленные инструкции в разделе [Ручное](mac-install-manually.md#how-to-allow-full-disk-access) развертывание.</span><span class="sxs-lookup"><span data-stu-id="9e101-227">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="9e101-228">Для управляемых развертываний см. обновленные инструкции в темах развертывания на основе [JAMF](mac-install-with-jamf.md) и [Microsoft Intune.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="9e101-228">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="9e101-229">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="9e101-229">Performance improvements & bug fixes</span></span>
