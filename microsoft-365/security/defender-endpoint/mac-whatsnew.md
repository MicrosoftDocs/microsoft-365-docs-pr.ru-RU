---
title: Новые возможности в Microsoft Defender для конечной точки на Mac
description: Узнайте о главных изменениях для предыдущих версий Microsoft Defender для конечной точки на Mac.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, installation, macos, Whatsnew
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
ms.openlocfilehash: fc162939e12f0bd55da5847c6bc1bda4b3761fd7
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276909"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="4d734-104">Новые возможности в Microsoft Defender для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="4d734-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4d734-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4d734-105">**Applies to:**</span></span>
- [<span data-ttu-id="4d734-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4d734-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4d734-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d734-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4d734-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="4d734-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4d734-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="4d734-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="4d734-110">В macOS 11 (Big Sur) Microsoft Defender для конечной точки требует дополнительных профилей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4d734-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="4d734-111">Если вы существующий клиент, обновляющийся из более ранних версий macOS, не забудьте развернуть дополнительные профили конфигурации, перечисленные [на этой странице.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4d734-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1013420-20121051134200"></a><span data-ttu-id="4d734-112">101.34.20 (20.121051.13420.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-112">101.34.20 (20.121051.13420.0)</span></span>

- <span data-ttu-id="4d734-113">Устранена проблема, из-за которой быстрое сканирование не удалось начать из меню состояния на macOS 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="4d734-113">Addressed an issue where a quick scan could not be started from the status menu on macOS 11 (Big Sur)</span></span>
- <span data-ttu-id="4d734-114">Другие исправления ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-114">Other bug fixes</span></span>

## <a name="1013269-20121042132690"></a><span data-ttu-id="4d734-115">101.32.69 (20.121042.13269.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-115">101.32.69 (20.121042.13269.0)</span></span>

- <span data-ttu-id="4d734-116">Устранена проблема, из-за которой одновременное получение доступа к ключу от Microsoft Defender для конечной точки и других приложений может привести к коррупции keychain.</span><span class="sxs-lookup"><span data-stu-id="4d734-116">Addressed an issue where concurrent access to the keychain from Microsoft Defender for Endpoint and other applications can lead to keychain corruption.</span></span>

## <a name="1012964-20121042129640"></a><span data-ttu-id="4d734-117">101.29.64 (20.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-117">101.29.64 (20.121042.12964.0)</span></span>

- <span data-ttu-id="4d734-118">Начиная с этой версии, угрозы, обнаруженные во время проверки антивирусов по запросу, срабатываемой через клиент командной строки, автоматически устраняются.</span><span class="sxs-lookup"><span data-stu-id="4d734-118">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="4d734-119">Угрозы, обнаруженные во время сканирования, срабатываемого с помощью пользовательского интерфейса, по-прежнему требуют ручного действия.</span><span class="sxs-lookup"><span data-stu-id="4d734-119">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="4d734-120">`mdatp diagnostic real-time-protection-statistics` теперь поддерживает два дополнительных коммутатора:</span><span class="sxs-lookup"><span data-stu-id="4d734-120">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="4d734-121">`--sort`: сортирует выход, убывающий по общему количеству отсканированных файлов</span><span class="sxs-lookup"><span data-stu-id="4d734-121">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="4d734-122">`--top N`: отображает верхние результаты N (работает только в том `--sort` случае, если указано)</span><span class="sxs-lookup"><span data-stu-id="4d734-122">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="4d734-123">Улучшения производительности (особенно для использования YARN) & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-123">Performance improvements (specifically for when YARN is used) & bug fixes</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="4d734-124">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-124">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="4d734-125">Исправление для размещения срока действия сертификата Apple для macOS Catalina и ранее.</span><span class="sxs-lookup"><span data-stu-id="4d734-125">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="4d734-126">Это исправление восстанавливает функциональность управления & уязвимостей (TVM).</span><span class="sxs-lookup"><span data-stu-id="4d734-126">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="4d734-127">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-127">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="4d734-128">Microsoft Defender для конечной точки на macOS теперь доступен в предварительном просмотре для клиентов правительства США.</span><span class="sxs-lookup"><span data-stu-id="4d734-128">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="4d734-129">Дополнительные сведения см. в [веб-сайте Microsoft Defender for Endpoint для государственных клиентов США.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="4d734-129">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="4d734-130">Улучшения производительности (в частности, для ситуации, когда используется приложение XCode Simulator) & ошибки.</span><span class="sxs-lookup"><span data-stu-id="4d734-130">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="4d734-131">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-131">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="4d734-132">Добавлен новый параметр в средство командной строки для просмотра сведений о последнем проверке по запросу.</span><span class="sxs-lookup"><span data-stu-id="4d734-132">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="4d734-133">Чтобы просмотреть сведения о последнем проверке по запросу, запустите `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="4d734-133">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="4d734-134">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-134">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="4d734-135">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-135">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="4d734-136">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-136">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="4d734-137">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-137">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="4d734-138">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-138">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="4d734-139">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-139">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="4d734-140">Старый синтаксис средства командной строки был обесценит с помощью этого выпуска.</span><span class="sxs-lookup"><span data-stu-id="4d734-140">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="4d734-141">Сведения о новом синтаксисе см. в [сайте Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="4d734-141">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="4d734-142">Добавлен новый переключатель командной строки, чтобы отключить расширение сети: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="4d734-142">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="4d734-143">Эта команда может быть полезна для устранения проблем с сетью, которые могут быть связаны с Microsoft Defender для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="4d734-143">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="4d734-144">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-144">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="4d734-145">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-145">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="4d734-146">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-146">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="4d734-147">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-147">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="4d734-148">Улучшена надежность агента при работе на macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="4d734-148">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="4d734-149">Добавлен новый переключатель командной строки () для игнорирования исключений `--ignore-exclusions` av во время пользовательских сканирований ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="4d734-149">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="4d734-150">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-150">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="4d734-151">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="4d734-151">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="4d734-152">Устранены условия, когда Microsoft Defender для конечной точки запускала ошибку macOS 11 (Big Sur), которая проявляется в панике ядра</span><span class="sxs-lookup"><span data-stu-id="4d734-152">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="4d734-153">Исправлена утечка памяти в расширении системы безопасности конечных точек при работе на mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="4d734-153">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="4d734-154">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-154">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="4d734-155">101.10.72</span><span class="sxs-lookup"><span data-stu-id="4d734-155">101.10.72</span></span>

- <span data-ttu-id="4d734-156">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-156">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="4d734-157">101.09.61</span><span class="sxs-lookup"><span data-stu-id="4d734-157">101.09.61</span></span>

- <span data-ttu-id="4d734-158">Добавлено новое управляемое предпочтение для [отключения параметра отправки отзывов](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="4d734-158">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="4d734-159">Значок меню состояния теперь показывает здоровое состояние при настройке параметров продукта.</span><span class="sxs-lookup"><span data-stu-id="4d734-159">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="4d734-160">Ранее значок меню состояния отображал состояние предупреждения или ошибки, даже если параметры продукта управлялись администратором.</span><span class="sxs-lookup"><span data-stu-id="4d734-160">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="4d734-161">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-161">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="4d734-162">101.09.50</span><span class="sxs-lookup"><span data-stu-id="4d734-162">101.09.50</span></span>

- <span data-ttu-id="4d734-163">Эта версия продукта была проверена на macOS Big Sur 11 бета-версии 9</span><span class="sxs-lookup"><span data-stu-id="4d734-163">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="4d734-164">Новый синтаксис для средства `mdatp` командной строки теперь является по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d734-164">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="4d734-165">Дополнительные сведения о новом синтаксисе см. в ссылке [Ресурсы для Microsoft Defender для конечной точки на macOS](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="4d734-165">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="4d734-166">Старый синтаксис средства командной строки будет удален из продукта 1 января **2021 г.**</span><span class="sxs-lookup"><span data-stu-id="4d734-166">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="4d734-167">Расширенный `mdatp diagnostic create` с помощью нового параметра (), который позволяет сохранить журналы диагностики в другом `--path [directory]` каталоге</span><span class="sxs-lookup"><span data-stu-id="4d734-167">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="4d734-168">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-168">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="4d734-169">101.09.49</span><span class="sxs-lookup"><span data-stu-id="4d734-169">101.09.49</span></span>

- <span data-ttu-id="4d734-170">Улучшения пользовательского интерфейса для различия исключений, управляемых ИТ-администратором, и исключений, определенных локальным пользователем</span><span class="sxs-lookup"><span data-stu-id="4d734-170">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="4d734-171">Улучшение использования ЦП во время проверки по запросу</span><span class="sxs-lookup"><span data-stu-id="4d734-171">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="4d734-172">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-172">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="4d734-173">101.07.23</span><span class="sxs-lookup"><span data-stu-id="4d734-173">101.07.23</span></span>

- <span data-ttu-id="4d734-174">Добавлены новые поля для проверки состояния пассивного режима и `mdatp --health` EDR группы</span><span class="sxs-lookup"><span data-stu-id="4d734-174">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="4d734-175">`mdatp --health` будет заменено `mdatp health` в будущем обновлении продукта.</span><span class="sxs-lookup"><span data-stu-id="4d734-175">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="4d734-176">Исправлена ошибка, при которой автоматическая отправка образца не была помечена как управляемой в пользовательском интерфейсе</span><span class="sxs-lookup"><span data-stu-id="4d734-176">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="4d734-177">Добавлены новые параметры для управления хранением элементов в истории антивирусного сканирования.</span><span class="sxs-lookup"><span data-stu-id="4d734-177">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="4d734-178">Теперь можно [указать количество](mac-preferences.md#antivirus-scan-history-retention-in-days) дней для сохранения элементов в истории сканирования и указать максимальное число элементов [в истории сканирования.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="4d734-178">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="4d734-179">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-179">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="4d734-180">101.06.63</span><span class="sxs-lookup"><span data-stu-id="4d734-180">101.06.63</span></span>

- <span data-ttu-id="4d734-181">Устранена регрессия производительности, представленная в версии `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="4d734-181">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="4d734-182">Регрессия была введена с исправлением для устранения паники ядра, наблюдаемой некоторыми клиентами при доступе к акциям SMB.</span><span class="sxs-lookup"><span data-stu-id="4d734-182">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="4d734-183">Мы вернули это изменение кода и исследуем альтернативные способы устранения паники ядра.</span><span class="sxs-lookup"><span data-stu-id="4d734-183">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="4d734-184">101.05.17</span><span class="sxs-lookup"><span data-stu-id="4d734-184">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d734-185">Мы работаем над новым и расширенным синтаксисом для средства `mdatp` командной строки.</span><span class="sxs-lookup"><span data-stu-id="4d734-185">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="4d734-186">Новый синтаксис в настоящее время является по умолчанию в каналах обновления Insider Fast и Insider Slow.</span><span class="sxs-lookup"><span data-stu-id="4d734-186">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="4d734-187">Мы рекомендуем вам famliliarize себя с помощью этого нового синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="4d734-187">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="4d734-188">Мы продолжим поддерживать старый синтаксис параллельно с новым синтаксисом и в предстоящие месяцы будем предоставлять дополнительные возможности связи по плану амортизации для старого синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="4d734-188">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="4d734-189">Устранена паника ядра, которая иногда возникла при доступе к акциям SMB-файла</span><span class="sxs-lookup"><span data-stu-id="4d734-189">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="4d734-190">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-190">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="4d734-191">101.05.16</span><span class="sxs-lookup"><span data-stu-id="4d734-191">101.05.16</span></span>

- <span data-ttu-id="4d734-192">Улучшение логики быстрого сканирования, чтобы значительно сократить число отсканированных файлов</span><span class="sxs-lookup"><span data-stu-id="4d734-192">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="4d734-193">Добавлена [поддержка автозаполнения](mac-resources.md#how-to-enable-autocompletion) для средства командной строки</span><span class="sxs-lookup"><span data-stu-id="4d734-193">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="4d734-194">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-194">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="4d734-195">101.03.12</span><span class="sxs-lookup"><span data-stu-id="4d734-195">101.03.12</span></span>

- <span data-ttu-id="4d734-196">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-196">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="4d734-197">101.01.54</span><span class="sxs-lookup"><span data-stu-id="4d734-197">101.01.54</span></span>

- <span data-ttu-id="4d734-198">Улучшения совместимости с машиной времени</span><span class="sxs-lookup"><span data-stu-id="4d734-198">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="4d734-199">Улучшения доступности</span><span class="sxs-lookup"><span data-stu-id="4d734-199">Accessibility improvements</span></span>
- <span data-ttu-id="4d734-200">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-200">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="4d734-201">101.00.31</span><span class="sxs-lookup"><span data-stu-id="4d734-201">101.00.31</span></span>

- <span data-ttu-id="4d734-202">Улучшенный опыт работы [с onboarding продуктов для пользователей Intune](/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="4d734-202">Improved [product onboarding experience for Intune users](/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="4d734-203">Исключения [антивирусов теперь поддерживают подкарды](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="4d734-203">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="4d734-204">Добавлена возможность запуска антивирусных сканов из контекстного меню macOS.</span><span class="sxs-lookup"><span data-stu-id="4d734-204">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="4d734-205">Теперь вы можете щелкнуть правой кнопкой мыши файл или папку в Finder и выбрать сканирование с **помощью Microsoft Defender для конечной точки**</span><span class="sxs-lookup"><span data-stu-id="4d734-205">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="4d734-206">В настоящее время установщик явно запрещает понижение продуктов на месте.</span><span class="sxs-lookup"><span data-stu-id="4d734-206">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="4d734-207">Если требуется понизить рейтинг, сначала отсоедините существующую версию и перенастройте устройство</span><span class="sxs-lookup"><span data-stu-id="4d734-207">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="4d734-208">Другие улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-208">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="4d734-209">100.90.27</span><span class="sxs-lookup"><span data-stu-id="4d734-209">100.90.27</span></span>

- <span data-ttu-id="4d734-210">Теперь вы можете [установить канал](mac-updates.md#set-the-channel-name) обновления для Microsoft Defender для конечной точки на macOS, который отличается от канала обновления для всей системы.</span><span class="sxs-lookup"><span data-stu-id="4d734-210">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="4d734-211">Значок нового продукта</span><span class="sxs-lookup"><span data-stu-id="4d734-211">New product icon</span></span>
- <span data-ttu-id="4d734-212">Другие улучшения пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="4d734-212">Other user experience improvements</span></span>
- <span data-ttu-id="4d734-213">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-213">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="4d734-214">100.86.92</span><span class="sxs-lookup"><span data-stu-id="4d734-214">100.86.92</span></span>

- <span data-ttu-id="4d734-215">Улучшения совместимости с машиной времени</span><span class="sxs-lookup"><span data-stu-id="4d734-215">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="4d734-216">Устранена проблема, из-за которой продукт иногда не очищал все файлы во время `/Library/Application Support/Microsoft/Defender` деинсталлации</span><span class="sxs-lookup"><span data-stu-id="4d734-216">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="4d734-217">Снижение использования процессора продукта при обновлении продуктов Майкрософт с помощью Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="4d734-217">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="4d734-218">Другие улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-218">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="4d734-219">100.86.91</span><span class="sxs-lookup"><span data-stu-id="4d734-219">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="4d734-220">Чтобы обеспечить самую полную защиту для устройств macOS и в соответствии с Apple, прекращая доставку обновлений macOS нативную безопасность для версий ОС старше [текущего — 2], развертывание и обновления MDATP для Mac больше не будут поддерживаться на macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="4d734-220">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="4d734-221">MDATP для обновлений и улучшений Mac будут доставлены устройствам с версиями Catalina [10.15], Mojave [10.14], и High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="4d734-221">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="4d734-222">Если mDATP для Mac уже развернут на устройствах Sierra [10.12], перенастраивайся до последней версии macOS, чтобы исключить риски потери защиты.</span><span class="sxs-lookup"><span data-stu-id="4d734-222">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="4d734-223">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-223">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="4d734-224">100.83.73</span><span class="sxs-lookup"><span data-stu-id="4d734-224">100.83.73</span></span>

- <span data-ttu-id="4d734-225">Добавлены дополнительные элементы управления для ИТ-администраторов в области управления исключениями, управления настройками типа угроз и [](mac-preferences.md#exclusion-merge-policy) [запрета действий с угрозами](mac-preferences.md#disallowed-threat-actions) [](mac-preferences.md#threat-type-settings-merge-policy)</span><span class="sxs-lookup"><span data-stu-id="4d734-225">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="4d734-226">Если полный доступ к диску не включен на устройстве, предупреждение отображается в меню состояния</span><span class="sxs-lookup"><span data-stu-id="4d734-226">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="4d734-227">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-227">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="4d734-228">100.82.60</span><span class="sxs-lookup"><span data-stu-id="4d734-228">100.82.60</span></span>

- <span data-ttu-id="4d734-229">Устранена проблема, из-за которой продукт не может начать следовать обновлению определения.</span><span class="sxs-lookup"><span data-stu-id="4d734-229">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="4d734-230">100.80.42</span><span class="sxs-lookup"><span data-stu-id="4d734-230">100.80.42</span></span>

- <span data-ttu-id="4d734-231">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-231">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="4d734-232">100.79.42</span><span class="sxs-lookup"><span data-stu-id="4d734-232">100.79.42</span></span>

- <span data-ttu-id="4d734-233">Исправлена проблема, из-за которой Microsoft Defender для конечной точки на Mac иногда вмешивалась в машину времени</span><span class="sxs-lookup"><span data-stu-id="4d734-233">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="4d734-234">Добавлен новый переключатель в службу командной строки для тестирования подключения к службе backend</span><span class="sxs-lookup"><span data-stu-id="4d734-234">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="4d734-235">Добавлена возможность просмотра полной истории угроз в пользовательском интерфейсе (можно получить доступ из представления **истории** защиты)</span><span class="sxs-lookup"><span data-stu-id="4d734-235">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="4d734-236">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-236">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="4d734-237">100.72.15</span><span class="sxs-lookup"><span data-stu-id="4d734-237">100.72.15</span></span>

- <span data-ttu-id="4d734-238">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-238">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="4d734-239">100.70.99</span><span class="sxs-lookup"><span data-stu-id="4d734-239">100.70.99</span></span>

- <span data-ttu-id="4d734-240">Устранена проблема, которая влияет на возможность некоторых пользователей перейти на macOS Catalina при включенной защите в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="4d734-240">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="4d734-241">Эта спорадическая проблема была вызвана блокировкой файлов Microsoft Defender для конечной точки в пакете обновления Catalina при сканировании их на угрозы, что привело к сбоям в последовательности обновления.</span><span class="sxs-lookup"><span data-stu-id="4d734-241">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="4d734-242">100.68.99</span><span class="sxs-lookup"><span data-stu-id="4d734-242">100.68.99</span></span>

- <span data-ttu-id="4d734-243">Добавлена возможность настройки функции антивируса для работы в [пассивном режиме](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="4d734-243">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="4d734-244">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-244">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="4d734-245">100.65.28</span><span class="sxs-lookup"><span data-stu-id="4d734-245">100.65.28</span></span>

- <span data-ttu-id="4d734-246">Добавлена поддержка macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="4d734-246">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="4d734-247">MacOS 10.15 (Catalina) содержит новые улучшения безопасности и конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="4d734-247">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="4d734-248">Начиная с этой версии, по умолчанию приложения не могут получить доступ к определенным расположениям на диске (например, документы, скачивания, настольные компьютеры и т.д.) без явного согласия.</span><span class="sxs-lookup"><span data-stu-id="4d734-248">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="4d734-249">При отсутствии такого согласия Microsoft Defender для конечной точки не может полностью защитить ваше устройство.</span><span class="sxs-lookup"><span data-stu-id="4d734-249">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="4d734-250">Механизм предоставления такого согласия зависит от того, как вы развернули Microsoft Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="4d734-250">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="4d734-251">Для ручных развертываний см. обновленные инструкции в разделе [Ручное](mac-install-manually.md#how-to-allow-full-disk-access) развертывание.</span><span class="sxs-lookup"><span data-stu-id="4d734-251">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="4d734-252">Для управляемых развертываний см. обновленные инструкции в темах развертывания на основе [JAMF](mac-install-with-jamf.md) [Microsoft Intune развертывания.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="4d734-252">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="4d734-253">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="4d734-253">Performance improvements & bug fixes</span></span>
