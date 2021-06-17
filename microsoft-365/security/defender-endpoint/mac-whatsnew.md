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
ms.openlocfilehash: a6415ec7d39bceeb4b68de164bbdcf6ef34755ff
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984776"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="681de-104">Новые возможности в Microsoft Defender для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="681de-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="681de-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="681de-105">**Applies to:**</span></span>
- [<span data-ttu-id="681de-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="681de-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="681de-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="681de-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="681de-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="681de-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="681de-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="681de-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="681de-110">В macOS 11 (Big Sur) Microsoft Defender для конечной точки требует дополнительных профилей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="681de-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="681de-111">Если вы существующий клиент, обновляющийся из более ранних версий macOS, не забудьте развернуть дополнительные профили конфигурации, перечисленные [на этой странице.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="681de-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1013269-20121042132690"></a><span data-ttu-id="681de-112">101.32.69 (20.121042.13269.0)</span><span class="sxs-lookup"><span data-stu-id="681de-112">101.32.69 (20.121042.13269.0)</span></span>

- <span data-ttu-id="681de-113">Устранена проблема, из-за которой одновременное получение доступа к ключу от Microsoft Defender для конечной точки и других приложений может привести к коррупции keychain.</span><span class="sxs-lookup"><span data-stu-id="681de-113">Addressed an issue where concurrent access to the keychain from Microsoft Defender for Endpoint and other applications can lead to keychain corruption.</span></span>

## <a name="1012964-20121042129640"></a><span data-ttu-id="681de-114">101.29.64 (20.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="681de-114">101.29.64 (20.121042.12964.0)</span></span>

- <span data-ttu-id="681de-115">Начиная с этой версии, угрозы, обнаруженные во время проверки антивирусов по запросу, срабатываемой через клиент командной строки, автоматически устраняются.</span><span class="sxs-lookup"><span data-stu-id="681de-115">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="681de-116">Угрозы, обнаруженные во время сканирования, срабатываемого с помощью пользовательского интерфейса, по-прежнему требуют ручного действия.</span><span class="sxs-lookup"><span data-stu-id="681de-116">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="681de-117">`mdatp diagnostic real-time-protection-statistics` теперь поддерживает два дополнительных коммутатора:</span><span class="sxs-lookup"><span data-stu-id="681de-117">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="681de-118">`--sort`: сортирует выход, убывающий по общему количеству отсканированных файлов</span><span class="sxs-lookup"><span data-stu-id="681de-118">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="681de-119">`--top N`: отображает верхние результаты N (работает только в том `--sort` случае, если указано)</span><span class="sxs-lookup"><span data-stu-id="681de-119">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="681de-120">Улучшения производительности (особенно для использования YARN) & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-120">Performance improvements (specifically for when YARN is used) & bug fixes</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="681de-121">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="681de-121">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="681de-122">Исправление для размещения срока действия сертификата Apple для macOS Catalina и ранее.</span><span class="sxs-lookup"><span data-stu-id="681de-122">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="681de-123">Это исправление восстанавливает функциональность управления & уязвимостей (TVM).</span><span class="sxs-lookup"><span data-stu-id="681de-123">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="681de-124">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="681de-124">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="681de-125">Microsoft Defender для конечной точки на macOS теперь доступен в предварительном просмотре для клиентов правительства США.</span><span class="sxs-lookup"><span data-stu-id="681de-125">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="681de-126">Дополнительные сведения см. в [веб-сайте Microsoft Defender for Endpoint для государственных клиентов США.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="681de-126">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="681de-127">Улучшения производительности (в частности, для ситуации, когда используется приложение XCode Simulator) & ошибки.</span><span class="sxs-lookup"><span data-stu-id="681de-127">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="681de-128">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="681de-128">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="681de-129">Добавлен новый параметр в средство командной строки для просмотра сведений о последнем проверке по запросу.</span><span class="sxs-lookup"><span data-stu-id="681de-129">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="681de-130">Чтобы просмотреть сведения о последнем проверке по запросу, запустите `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="681de-130">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="681de-131">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-131">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="681de-132">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="681de-132">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="681de-133">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-133">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="681de-134">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="681de-134">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="681de-135">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-135">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="681de-136">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="681de-136">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="681de-137">Старый синтаксис средства командной строки был обесценит с помощью этого выпуска.</span><span class="sxs-lookup"><span data-stu-id="681de-137">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="681de-138">Сведения о новом синтаксисе см. в [сайте Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="681de-138">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="681de-139">Добавлен новый переключатель командной строки, чтобы отключить расширение сети: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="681de-139">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="681de-140">Эта команда может быть полезна для устранения проблем с сетью, которые могут быть связаны с Microsoft Defender для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="681de-140">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="681de-141">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-141">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="681de-142">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="681de-142">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="681de-143">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-143">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="681de-144">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="681de-144">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="681de-145">Улучшена надежность агента при работе на macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="681de-145">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="681de-146">Добавлен новый переключатель командной строки () для игнорирования исключений `--ignore-exclusions` av во время пользовательских сканирований ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="681de-146">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="681de-147">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-147">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="681de-148">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="681de-148">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="681de-149">Устранены условия, когда Microsoft Defender для конечной точки запускала ошибку macOS 11 (Big Sur), которая проявляется в панике ядра</span><span class="sxs-lookup"><span data-stu-id="681de-149">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="681de-150">Исправлена утечка памяти в расширении системы безопасности конечных точек при работе на mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="681de-150">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="681de-151">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-151">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="681de-152">101.10.72</span><span class="sxs-lookup"><span data-stu-id="681de-152">101.10.72</span></span>

- <span data-ttu-id="681de-153">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-153">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="681de-154">101.09.61</span><span class="sxs-lookup"><span data-stu-id="681de-154">101.09.61</span></span>

- <span data-ttu-id="681de-155">Добавлено новое управляемое предпочтение для [отключения параметра отправки отзывов](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="681de-155">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="681de-156">Значок меню состояния теперь показывает здоровое состояние при настройке параметров продукта.</span><span class="sxs-lookup"><span data-stu-id="681de-156">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="681de-157">Ранее значок меню состояния отображал состояние предупреждения или ошибки, даже если параметры продукта управлялись администратором.</span><span class="sxs-lookup"><span data-stu-id="681de-157">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="681de-158">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-158">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="681de-159">101.09.50</span><span class="sxs-lookup"><span data-stu-id="681de-159">101.09.50</span></span>

- <span data-ttu-id="681de-160">Эта версия продукта была проверена на macOS Big Sur 11 бета-версии 9</span><span class="sxs-lookup"><span data-stu-id="681de-160">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="681de-161">Новый синтаксис для средства `mdatp` командной строки теперь является по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="681de-161">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="681de-162">Дополнительные сведения о новом синтаксисе см. в ссылке [Ресурсы для Microsoft Defender для конечной точки на macOS](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="681de-162">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="681de-163">Старый синтаксис средства командной строки будет удален из продукта 1 января **2021 г.**</span><span class="sxs-lookup"><span data-stu-id="681de-163">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="681de-164">Расширенный `mdatp diagnostic create` с помощью нового параметра (), который позволяет сохранить журналы диагностики в другом `--path [directory]` каталоге</span><span class="sxs-lookup"><span data-stu-id="681de-164">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="681de-165">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-165">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="681de-166">101.09.49</span><span class="sxs-lookup"><span data-stu-id="681de-166">101.09.49</span></span>

- <span data-ttu-id="681de-167">Улучшения пользовательского интерфейса для различия исключений, управляемых ИТ-администратором, и исключений, определенных локальным пользователем</span><span class="sxs-lookup"><span data-stu-id="681de-167">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="681de-168">Улучшение использования ЦП во время проверки по запросу</span><span class="sxs-lookup"><span data-stu-id="681de-168">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="681de-169">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-169">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="681de-170">101.07.23</span><span class="sxs-lookup"><span data-stu-id="681de-170">101.07.23</span></span>

- <span data-ttu-id="681de-171">Добавлены новые поля для проверки состояния пассивного режима и `mdatp --health` EDR группы</span><span class="sxs-lookup"><span data-stu-id="681de-171">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="681de-172">`mdatp --health` будет заменено `mdatp health` в будущем обновлении продукта.</span><span class="sxs-lookup"><span data-stu-id="681de-172">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="681de-173">Исправлена ошибка, при которой автоматическая отправка образца не была помечена как управляемой в пользовательском интерфейсе</span><span class="sxs-lookup"><span data-stu-id="681de-173">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="681de-174">Добавлены новые параметры для управления хранением элементов в истории антивирусного сканирования.</span><span class="sxs-lookup"><span data-stu-id="681de-174">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="681de-175">Теперь можно [указать количество](mac-preferences.md#antivirus-scan-history-retention-in-days) дней для сохранения элементов в истории сканирования и указать максимальное число элементов [в истории сканирования.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="681de-175">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="681de-176">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-176">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="681de-177">101.06.63</span><span class="sxs-lookup"><span data-stu-id="681de-177">101.06.63</span></span>

- <span data-ttu-id="681de-178">Устранена регрессия производительности, представленная в версии `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="681de-178">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="681de-179">Регрессия была введена с исправлением для устранения паники ядра, наблюдаемой некоторыми клиентами при доступе к акциям SMB.</span><span class="sxs-lookup"><span data-stu-id="681de-179">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="681de-180">Мы вернули это изменение кода и исследуем альтернативные способы устранения паники ядра.</span><span class="sxs-lookup"><span data-stu-id="681de-180">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="681de-181">101.05.17</span><span class="sxs-lookup"><span data-stu-id="681de-181">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="681de-182">Мы работаем над новым и расширенным синтаксисом для средства `mdatp` командной строки.</span><span class="sxs-lookup"><span data-stu-id="681de-182">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="681de-183">Новый синтаксис в настоящее время является по умолчанию в каналах обновления Insider Fast и Insider Slow.</span><span class="sxs-lookup"><span data-stu-id="681de-183">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="681de-184">Мы рекомендуем вам famliliarize себя с помощью этого нового синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="681de-184">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="681de-185">Мы продолжим поддерживать старый синтаксис параллельно с новым синтаксисом и в предстоящие месяцы будем предоставлять дополнительные возможности связи по плану амортизации для старого синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="681de-185">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="681de-186">Устранена паника ядра, которая иногда возникла при доступе к акциям SMB-файла</span><span class="sxs-lookup"><span data-stu-id="681de-186">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="681de-187">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-187">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="681de-188">101.05.16</span><span class="sxs-lookup"><span data-stu-id="681de-188">101.05.16</span></span>

- <span data-ttu-id="681de-189">Улучшение логики быстрого сканирования, чтобы значительно сократить число отсканированных файлов</span><span class="sxs-lookup"><span data-stu-id="681de-189">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="681de-190">Добавлена [поддержка автозаполнения](mac-resources.md#how-to-enable-autocompletion) для средства командной строки</span><span class="sxs-lookup"><span data-stu-id="681de-190">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="681de-191">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-191">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="681de-192">101.03.12</span><span class="sxs-lookup"><span data-stu-id="681de-192">101.03.12</span></span>

- <span data-ttu-id="681de-193">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-193">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="681de-194">101.01.54</span><span class="sxs-lookup"><span data-stu-id="681de-194">101.01.54</span></span>

- <span data-ttu-id="681de-195">Улучшения совместимости с машиной времени</span><span class="sxs-lookup"><span data-stu-id="681de-195">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="681de-196">Улучшения доступности</span><span class="sxs-lookup"><span data-stu-id="681de-196">Accessibility improvements</span></span>
- <span data-ttu-id="681de-197">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-197">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="681de-198">101.00.31</span><span class="sxs-lookup"><span data-stu-id="681de-198">101.00.31</span></span>

- <span data-ttu-id="681de-199">Улучшенный опыт работы [с onboarding продуктов для пользователей Intune](/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="681de-199">Improved [product onboarding experience for Intune users](/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="681de-200">Исключения [антивирусов теперь поддерживают подкарды](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="681de-200">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="681de-201">Добавлена возможность запуска антивирусных сканов из контекстного меню macOS.</span><span class="sxs-lookup"><span data-stu-id="681de-201">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="681de-202">Теперь вы можете щелкнуть правой кнопкой мыши файл или папку в Finder и выбрать сканирование с **помощью Microsoft Defender для конечной точки**</span><span class="sxs-lookup"><span data-stu-id="681de-202">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="681de-203">В настоящее время установщик явно запрещает понижение продуктов на месте.</span><span class="sxs-lookup"><span data-stu-id="681de-203">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="681de-204">Если требуется понизить рейтинг, сначала отсоедините существующую версию и перенастройте устройство</span><span class="sxs-lookup"><span data-stu-id="681de-204">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="681de-205">Другие улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-205">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="681de-206">100.90.27</span><span class="sxs-lookup"><span data-stu-id="681de-206">100.90.27</span></span>

- <span data-ttu-id="681de-207">Теперь вы можете [установить канал](mac-updates.md#set-the-channel-name) обновления для Microsoft Defender для конечной точки на macOS, который отличается от канала обновления для всей системы.</span><span class="sxs-lookup"><span data-stu-id="681de-207">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="681de-208">Значок нового продукта</span><span class="sxs-lookup"><span data-stu-id="681de-208">New product icon</span></span>
- <span data-ttu-id="681de-209">Другие улучшения пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="681de-209">Other user experience improvements</span></span>
- <span data-ttu-id="681de-210">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-210">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="681de-211">100.86.92</span><span class="sxs-lookup"><span data-stu-id="681de-211">100.86.92</span></span>

- <span data-ttu-id="681de-212">Улучшения совместимости с машиной времени</span><span class="sxs-lookup"><span data-stu-id="681de-212">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="681de-213">Устранена проблема, из-за которой продукт иногда не очищал все файлы во время `/Library/Application Support/Microsoft/Defender` деинсталлации</span><span class="sxs-lookup"><span data-stu-id="681de-213">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="681de-214">Снижение использования процессора продукта при обновлении продуктов Майкрософт с помощью Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="681de-214">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="681de-215">Другие улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-215">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="681de-216">100.86.91</span><span class="sxs-lookup"><span data-stu-id="681de-216">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="681de-217">Чтобы обеспечить самую полную защиту для устройств macOS и в соответствии с Apple, прекращая доставку обновлений macOS нативную безопасность для версий ОС старше [текущего — 2], развертывание и обновления MDATP для Mac больше не будут поддерживаться на macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="681de-217">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="681de-218">MDATP для обновлений и улучшений Mac будут доставлены устройствам с версиями Catalina [10.15], Mojave [10.14], и High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="681de-218">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="681de-219">Если mDATP для Mac уже развернут на устройствах Sierra [10.12], перенастраивайся до последней версии macOS, чтобы исключить риски потери защиты.</span><span class="sxs-lookup"><span data-stu-id="681de-219">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="681de-220">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-220">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="681de-221">100.83.73</span><span class="sxs-lookup"><span data-stu-id="681de-221">100.83.73</span></span>

- <span data-ttu-id="681de-222">Добавлены дополнительные элементы управления для ИТ-администраторов в области управления исключениями, управления настройками типа угроз и [](mac-preferences.md#exclusion-merge-policy) [запрета действий с угрозами](mac-preferences.md#disallowed-threat-actions) [](mac-preferences.md#threat-type-settings-merge-policy)</span><span class="sxs-lookup"><span data-stu-id="681de-222">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="681de-223">Если полный доступ к диску не включен на устройстве, предупреждение отображается в меню состояния</span><span class="sxs-lookup"><span data-stu-id="681de-223">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="681de-224">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-224">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="681de-225">100.82.60</span><span class="sxs-lookup"><span data-stu-id="681de-225">100.82.60</span></span>

- <span data-ttu-id="681de-226">Устранена проблема, из-за которой продукт не может начать следовать обновлению определения.</span><span class="sxs-lookup"><span data-stu-id="681de-226">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="681de-227">100.80.42</span><span class="sxs-lookup"><span data-stu-id="681de-227">100.80.42</span></span>

- <span data-ttu-id="681de-228">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-228">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="681de-229">100.79.42</span><span class="sxs-lookup"><span data-stu-id="681de-229">100.79.42</span></span>

- <span data-ttu-id="681de-230">Исправлена проблема, из-за которой Microsoft Defender для конечной точки на Mac иногда вмешивалась в машину времени</span><span class="sxs-lookup"><span data-stu-id="681de-230">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="681de-231">Добавлен новый переключатель в службу командной строки для тестирования подключения к службе backend</span><span class="sxs-lookup"><span data-stu-id="681de-231">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="681de-232">Добавлена возможность просмотра полной истории угроз в пользовательском интерфейсе (можно получить доступ из представления **истории** защиты)</span><span class="sxs-lookup"><span data-stu-id="681de-232">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="681de-233">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-233">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="681de-234">100.72.15</span><span class="sxs-lookup"><span data-stu-id="681de-234">100.72.15</span></span>

- <span data-ttu-id="681de-235">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-235">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="681de-236">100.70.99</span><span class="sxs-lookup"><span data-stu-id="681de-236">100.70.99</span></span>

- <span data-ttu-id="681de-237">Устранена проблема, которая влияет на возможность некоторых пользователей перейти на macOS Catalina при включенной защите в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="681de-237">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="681de-238">Эта спорадическая проблема была вызвана блокировкой файлов Microsoft Defender для конечной точки в пакете обновления Catalina при сканировании их на угрозы, что привело к сбоям в последовательности обновления.</span><span class="sxs-lookup"><span data-stu-id="681de-238">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="681de-239">100.68.99</span><span class="sxs-lookup"><span data-stu-id="681de-239">100.68.99</span></span>

- <span data-ttu-id="681de-240">Добавлена возможность настройки функции антивируса для работы в [пассивном режиме](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="681de-240">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="681de-241">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-241">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="681de-242">100.65.28</span><span class="sxs-lookup"><span data-stu-id="681de-242">100.65.28</span></span>

- <span data-ttu-id="681de-243">Добавлена поддержка macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="681de-243">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="681de-244">MacOS 10.15 (Catalina) содержит новые улучшения безопасности и конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="681de-244">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="681de-245">Начиная с этой версии, по умолчанию приложения не могут получить доступ к определенным расположениям на диске (например, документы, скачивания, настольные компьютеры и т.д.) без явного согласия.</span><span class="sxs-lookup"><span data-stu-id="681de-245">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="681de-246">При отсутствии такого согласия Microsoft Defender для конечной точки не может полностью защитить ваше устройство.</span><span class="sxs-lookup"><span data-stu-id="681de-246">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="681de-247">Механизм предоставления такого согласия зависит от того, как вы развернули Microsoft Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="681de-247">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="681de-248">Для ручных развертываний см. обновленные инструкции в разделе [Ручное](mac-install-manually.md#how-to-allow-full-disk-access) развертывание.</span><span class="sxs-lookup"><span data-stu-id="681de-248">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="681de-249">Для управляемых развертываний см. обновленные инструкции в темах развертывания на основе [JAMF](mac-install-with-jamf.md) [Microsoft Intune развертывания.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="681de-249">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="681de-250">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="681de-250">Performance improvements & bug fixes</span></span>
