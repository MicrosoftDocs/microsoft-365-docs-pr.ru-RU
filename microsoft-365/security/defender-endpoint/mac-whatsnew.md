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
ms.openlocfilehash: edbabf83c7bf1ac8dbe1ca9451ad191b45a862ac
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932731"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="ffa0c-104">Новые возможности в Microsoft Defender для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="ffa0c-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ffa0c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ffa0c-105">**Applies to:**</span></span>
- [<span data-ttu-id="ffa0c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ffa0c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ffa0c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ffa0c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ffa0c-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ffa0c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ffa0c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="ffa0c-110">В macOS 11 (Big Sur) Microsoft Defender для конечной точки требует дополнительных профилей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="ffa0c-111">Если вы существующий клиент, обновляющийся из более ранних версий macOS, не забудьте развернуть дополнительные профили конфигурации, перечисленные [на этой странице.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="ffa0c-112">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-112">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="ffa0c-113">Microsoft Defender для конечной точки на macOS теперь доступен в предварительном просмотре для клиентов правительства США.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-113">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="ffa0c-114">Дополнительные сведения см. в [веб-сайте Microsoft Defender for Endpoint для государственных клиентов США.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-114">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="ffa0c-115">Улучшения производительности (в частности, для ситуации, когда используется приложение XCode Simulator) & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-115">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="ffa0c-116">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-116">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="ffa0c-117">Добавлен новый параметр в средство командной строки для просмотра сведений о последнем проверке по запросу.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-117">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="ffa0c-118">Чтобы просмотреть сведения о последнем проверке по запросу, запустите `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="ffa0c-118">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="ffa0c-119">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-119">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="ffa0c-120">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-120">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="ffa0c-121">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-121">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="ffa0c-122">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-122">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="ffa0c-123">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-123">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="ffa0c-124">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-124">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="ffa0c-125">Старый синтаксис средства командной строки был обесценит с помощью этого выпуска.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-125">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="ffa0c-126">Сведения о новом синтаксисе см. в [сайте Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="ffa0c-126">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="ffa0c-127">Добавлен новый переключатель командной строки, чтобы отключить расширение сети: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="ffa0c-127">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="ffa0c-128">Эта команда может быть полезна для устранения проблем с сетью, которые могут быть связаны с Microsoft Defender для конечной точки на Mac</span><span class="sxs-lookup"><span data-stu-id="ffa0c-128">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="ffa0c-129">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-129">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="ffa0c-130">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-130">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="ffa0c-131">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-131">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="ffa0c-132">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-132">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="ffa0c-133">Улучшена надежность агента при работе на macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="ffa0c-133">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="ffa0c-134">Добавлен новый переключатель командной строки () для игнорирования исключений `--ignore-exclusions` av во время пользовательских сканирований ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="ffa0c-134">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="ffa0c-135">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-135">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="ffa0c-136">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-136">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="ffa0c-137">Устранены условия, когда Microsoft Defender для конечной точки запускала ошибку macOS 11 (Big Sur), которая проявляется в панике ядра</span><span class="sxs-lookup"><span data-stu-id="ffa0c-137">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="ffa0c-138">Исправлена утечка памяти в расширении системы безопасности конечных точек при работе на mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-138">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="ffa0c-139">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-139">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="ffa0c-140">101.10.72</span><span class="sxs-lookup"><span data-stu-id="ffa0c-140">101.10.72</span></span>

- <span data-ttu-id="ffa0c-141">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-141">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="ffa0c-142">101.09.61</span><span class="sxs-lookup"><span data-stu-id="ffa0c-142">101.09.61</span></span>

- <span data-ttu-id="ffa0c-143">Добавлено новое управляемое предпочтение для [отключения параметра отправки отзывов](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-143">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="ffa0c-144">Значок меню состояния теперь показывает здоровое состояние при настройке параметров продукта.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-144">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="ffa0c-145">Ранее значок меню состояния отображал состояние предупреждения или ошибки, даже если параметры продукта управлялись администратором.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-145">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="ffa0c-146">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-146">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="ffa0c-147">101.09.50</span><span class="sxs-lookup"><span data-stu-id="ffa0c-147">101.09.50</span></span>

- <span data-ttu-id="ffa0c-148">Эта версия продукта была проверена на macOS Big Sur 11 бета-версии 9</span><span class="sxs-lookup"><span data-stu-id="ffa0c-148">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="ffa0c-149">Новый синтаксис для средства `mdatp` командной строки теперь является по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-149">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="ffa0c-150">Дополнительные сведения о новом синтаксисе см. в ссылке [Ресурсы для Microsoft Defender для конечной точки на macOS](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-150">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="ffa0c-151">Старый синтаксис средства командной строки будет удален из продукта 1 января **2021 г.**</span><span class="sxs-lookup"><span data-stu-id="ffa0c-151">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="ffa0c-152">Расширенный `mdatp diagnostic create` с помощью нового параметра (), который позволяет сохранить журналы диагностики в другом `--path [directory]` каталоге</span><span class="sxs-lookup"><span data-stu-id="ffa0c-152">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="ffa0c-153">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-153">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="ffa0c-154">101.09.49</span><span class="sxs-lookup"><span data-stu-id="ffa0c-154">101.09.49</span></span>

- <span data-ttu-id="ffa0c-155">Улучшения пользовательского интерфейса для различия исключений, управляемых ИТ-администратором, и исключений, определенных локальным пользователем</span><span class="sxs-lookup"><span data-stu-id="ffa0c-155">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="ffa0c-156">Улучшение использования ЦП во время проверки по запросу</span><span class="sxs-lookup"><span data-stu-id="ffa0c-156">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="ffa0c-157">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-157">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="ffa0c-158">101.07.23</span><span class="sxs-lookup"><span data-stu-id="ffa0c-158">101.07.23</span></span>

- <span data-ttu-id="ffa0c-159">Добавлены новые поля для проверки состояния пассивного режима и ID группы `mdatp --health` EDR</span><span class="sxs-lookup"><span data-stu-id="ffa0c-159">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="ffa0c-160">`mdatp --health` будет заменено `mdatp health` в будущем обновлении продукта.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-160">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="ffa0c-161">Исправлена ошибка, при которой автоматическая отправка образца не была помечена как управляемой в пользовательском интерфейсе</span><span class="sxs-lookup"><span data-stu-id="ffa0c-161">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="ffa0c-162">Добавлены новые параметры для управления хранением элементов в истории антивирусного сканирования.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-162">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="ffa0c-163">Теперь можно [указать количество](mac-preferences.md#antivirus-scan-history-retention-in-days) дней для сохранения элементов в истории сканирования и указать максимальное число элементов [в истории сканирования.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-163">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="ffa0c-164">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-164">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="ffa0c-165">101.06.63</span><span class="sxs-lookup"><span data-stu-id="ffa0c-165">101.06.63</span></span>

- <span data-ttu-id="ffa0c-166">Устранена регрессия производительности, представленная в версии `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="ffa0c-166">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="ffa0c-167">Регрессия была введена с исправлением для устранения паники ядра, наблюдаемой некоторыми клиентами при доступе к акциям SMB.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-167">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="ffa0c-168">Мы вернули это изменение кода и исследуем альтернативные способы устранения паники ядра.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-168">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="ffa0c-169">101.05.17</span><span class="sxs-lookup"><span data-stu-id="ffa0c-169">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ffa0c-170">Мы работаем над новым и расширенным синтаксисом для средства `mdatp` командной строки.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-170">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="ffa0c-171">Новый синтаксис в настоящее время является по умолчанию в каналах обновления Insider Fast и Insider Slow.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-171">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="ffa0c-172">Мы рекомендуем вам famliliarize себя с помощью этого нового синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-172">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="ffa0c-173">Мы продолжим поддерживать старый синтаксис параллельно с новым синтаксисом и в предстоящие месяцы будем предоставлять дополнительные возможности связи по плану амортизации для старого синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-173">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="ffa0c-174">Устранена паника ядра, которая иногда возникла при доступе к акциям SMB-файла</span><span class="sxs-lookup"><span data-stu-id="ffa0c-174">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="ffa0c-175">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-175">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="ffa0c-176">101.05.16</span><span class="sxs-lookup"><span data-stu-id="ffa0c-176">101.05.16</span></span>

- <span data-ttu-id="ffa0c-177">Улучшение логики быстрого сканирования, чтобы значительно сократить число отсканированных файлов</span><span class="sxs-lookup"><span data-stu-id="ffa0c-177">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="ffa0c-178">Добавлена [поддержка автозаполнения](mac-resources.md#how-to-enable-autocompletion) для средства командной строки</span><span class="sxs-lookup"><span data-stu-id="ffa0c-178">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="ffa0c-179">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-179">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="ffa0c-180">101.03.12</span><span class="sxs-lookup"><span data-stu-id="ffa0c-180">101.03.12</span></span>

- <span data-ttu-id="ffa0c-181">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-181">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="ffa0c-182">101.01.54</span><span class="sxs-lookup"><span data-stu-id="ffa0c-182">101.01.54</span></span>

- <span data-ttu-id="ffa0c-183">Улучшения совместимости с машиной времени</span><span class="sxs-lookup"><span data-stu-id="ffa0c-183">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="ffa0c-184">Улучшения доступности</span><span class="sxs-lookup"><span data-stu-id="ffa0c-184">Accessibility improvements</span></span>
- <span data-ttu-id="ffa0c-185">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-185">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="ffa0c-186">101.00.31</span><span class="sxs-lookup"><span data-stu-id="ffa0c-186">101.00.31</span></span>

- <span data-ttu-id="ffa0c-187">Улучшенный опыт работы [с onboarding продуктов для пользователей Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-187">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="ffa0c-188">Исключения [антивирусов теперь поддерживают подкарды](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-188">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="ffa0c-189">Добавлена возможность запуска антивирусных сканов из контекстного меню macOS.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-189">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="ffa0c-190">Теперь вы можете щелкнуть правой кнопкой мыши файл или папку в Finder и выбрать сканирование с **помощью Microsoft Defender для конечной точки**</span><span class="sxs-lookup"><span data-stu-id="ffa0c-190">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="ffa0c-191">В настоящее время установщик явно запрещает понижение продуктов на месте.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-191">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="ffa0c-192">Если требуется понизить рейтинг, сначала отсоедините существующую версию и перенастройте устройство</span><span class="sxs-lookup"><span data-stu-id="ffa0c-192">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="ffa0c-193">Другие улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-193">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="ffa0c-194">100.90.27</span><span class="sxs-lookup"><span data-stu-id="ffa0c-194">100.90.27</span></span>

- <span data-ttu-id="ffa0c-195">Теперь вы можете [установить канал](mac-updates.md#set-the-channel-name) обновления для Microsoft Defender для конечной точки на macOS, который отличается от канала обновления для всей системы.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-195">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="ffa0c-196">Значок нового продукта</span><span class="sxs-lookup"><span data-stu-id="ffa0c-196">New product icon</span></span>
- <span data-ttu-id="ffa0c-197">Другие улучшения пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ffa0c-197">Other user experience improvements</span></span>
- <span data-ttu-id="ffa0c-198">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-198">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="ffa0c-199">100.86.92</span><span class="sxs-lookup"><span data-stu-id="ffa0c-199">100.86.92</span></span>

- <span data-ttu-id="ffa0c-200">Улучшения совместимости с машиной времени</span><span class="sxs-lookup"><span data-stu-id="ffa0c-200">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="ffa0c-201">Устранена проблема, из-за которой продукт иногда не очищал все файлы во время `/Library/Application Support/Microsoft/Defender` деинсталлации</span><span class="sxs-lookup"><span data-stu-id="ffa0c-201">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="ffa0c-202">Снижение использования процессора продукта при обновлении продуктов Майкрософт с помощью Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="ffa0c-202">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="ffa0c-203">Другие улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-203">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="ffa0c-204">100.86.91</span><span class="sxs-lookup"><span data-stu-id="ffa0c-204">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="ffa0c-205">Чтобы обеспечить самую полную защиту для устройств macOS и в соответствии с Apple, прекращая доставку обновлений macOS нативную безопасность для версий ОС старше [текущего — 2], развертывание и обновления MDATP для Mac больше не будут поддерживаться на macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="ffa0c-205">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="ffa0c-206">MDATP для обновлений и улучшений Mac будут доставлены устройствам с версиями Catalina [10.15], Mojave [10.14], и High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="ffa0c-206">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="ffa0c-207">Если mDATP для Mac уже развернут на устройствах Sierra [10.12], перенастраивайся до последней версии macOS, чтобы исключить риски потери защиты.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-207">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="ffa0c-208">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-208">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="ffa0c-209">100.83.73</span><span class="sxs-lookup"><span data-stu-id="ffa0c-209">100.83.73</span></span>

- <span data-ttu-id="ffa0c-210">Добавлены дополнительные элементы управления для ИТ-администраторов в области управления исключениями, управления настройками типа угроз и [](mac-preferences.md#exclusion-merge-policy) [запрета действий с угрозами](mac-preferences.md#disallowed-threat-actions) [](mac-preferences.md#threat-type-settings-merge-policy)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-210">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="ffa0c-211">Если полный доступ к диску не включен на устройстве, предупреждение отображается в меню состояния</span><span class="sxs-lookup"><span data-stu-id="ffa0c-211">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="ffa0c-212">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-212">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="ffa0c-213">100.82.60</span><span class="sxs-lookup"><span data-stu-id="ffa0c-213">100.82.60</span></span>

- <span data-ttu-id="ffa0c-214">Устранена проблема, из-за которой продукт не может начать следовать обновлению определения.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-214">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="ffa0c-215">100.80.42</span><span class="sxs-lookup"><span data-stu-id="ffa0c-215">100.80.42</span></span>

- <span data-ttu-id="ffa0c-216">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-216">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="ffa0c-217">100.79.42</span><span class="sxs-lookup"><span data-stu-id="ffa0c-217">100.79.42</span></span>

- <span data-ttu-id="ffa0c-218">Исправлена проблема, из-за которой Microsoft Defender для конечной точки на Mac иногда вмешивалась в машину времени</span><span class="sxs-lookup"><span data-stu-id="ffa0c-218">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="ffa0c-219">Добавлен новый переключатель в службу командной строки для тестирования подключения к службе backend</span><span class="sxs-lookup"><span data-stu-id="ffa0c-219">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="ffa0c-220">Добавлена возможность просмотра полной истории угроз в пользовательском интерфейсе (можно получить доступ из представления **истории** защиты)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-220">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="ffa0c-221">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-221">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="ffa0c-222">100.72.15</span><span class="sxs-lookup"><span data-stu-id="ffa0c-222">100.72.15</span></span>

- <span data-ttu-id="ffa0c-223">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-223">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="ffa0c-224">100.70.99</span><span class="sxs-lookup"><span data-stu-id="ffa0c-224">100.70.99</span></span>

- <span data-ttu-id="ffa0c-225">Устранена проблема, которая влияет на возможность некоторых пользователей перейти на macOS Catalina при включенной защите в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-225">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="ffa0c-226">Эта спорадическая проблема была вызвана блокировкой файлов Microsoft Defender для конечной точки в пакете обновления Catalina при сканировании их на угрозы, что привело к сбоям в последовательности обновления.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-226">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="ffa0c-227">100.68.99</span><span class="sxs-lookup"><span data-stu-id="ffa0c-227">100.68.99</span></span>

- <span data-ttu-id="ffa0c-228">Добавлена возможность настройки функции антивируса для работы в [пассивном режиме](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-228">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="ffa0c-229">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-229">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="ffa0c-230">100.65.28</span><span class="sxs-lookup"><span data-stu-id="ffa0c-230">100.65.28</span></span>

- <span data-ttu-id="ffa0c-231">Добавлена поддержка macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="ffa0c-231">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="ffa0c-232">MacOS 10.15 (Catalina) содержит новые улучшения безопасности и конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-232">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="ffa0c-233">Начиная с этой версии, по умолчанию приложения не могут получить доступ к определенным расположениям на диске (например, документы, скачивания, настольные компьютеры и т.д.) без явного согласия.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-233">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="ffa0c-234">При отсутствии такого согласия Microsoft Defender для конечной точки не может полностью защитить ваше устройство.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-234">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="ffa0c-235">Механизм предоставления такого согласия зависит от того, как вы развернули Microsoft Defender для конечной точки:</span><span class="sxs-lookup"><span data-stu-id="ffa0c-235">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="ffa0c-236">Для ручных развертываний см. обновленные инструкции в разделе [Ручное](mac-install-manually.md#how-to-allow-full-disk-access) развертывание.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-236">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="ffa0c-237">Для управляемых развертываний см. обновленные инструкции в темах развертывания на основе [JAMF](mac-install-with-jamf.md) и [Microsoft Intune.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="ffa0c-237">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="ffa0c-238">Улучшения производительности & исправлений ошибок</span><span class="sxs-lookup"><span data-stu-id="ffa0c-238">Performance improvements & bug fixes</span></span>
