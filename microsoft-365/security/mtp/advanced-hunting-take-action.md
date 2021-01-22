---
title: Действие над результатами запросов на расширенный поиск в Microsoft 365 Defender
description: Быстрое устранение угроз и затронутых ресурсов в результатах запроса на расширенный поиск
keywords: расширенный поиск, охота на угрозы, поиск киберугроз, защита от угроз (Майкрософт), Microsoft 365, mtp, m365, поиск, запрос, телеметрия, действие
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932182"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="af4b5-104">Действие с результатами запроса на расширенный поиск</span><span class="sxs-lookup"><span data-stu-id="af4b5-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="af4b5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="af4b5-105">**Applies to:**</span></span>
- <span data-ttu-id="af4b5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af4b5-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="af4b5-107">Вы можете быстро сдержать угрозы или обратиться [](advanced-hunting-overview.md) к скомпрометированным активам, которые находятся в расширенных охотах, используя мощные и комплексные варианты действий.</span><span class="sxs-lookup"><span data-stu-id="af4b5-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="af4b5-108">С помощью этих параметров вы можете:</span><span class="sxs-lookup"><span data-stu-id="af4b5-108">With these options, you can:</span></span>

- <span data-ttu-id="af4b5-109">Различные действия на устройствах</span><span class="sxs-lookup"><span data-stu-id="af4b5-109">Take various actions on devices</span></span>
- <span data-ttu-id="af4b5-110">Файлы карантина</span><span class="sxs-lookup"><span data-stu-id="af4b5-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="af4b5-111">Обязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="af4b5-111">Required permissions</span></span>
<span data-ttu-id="af4b5-112">Чтобы иметь возможность действовать через расширенный поиск, необходима роль в Microsoft Defender для конечной точки с разрешениями на отправку действий по исправлению [на устройствах.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="af4b5-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="af4b5-113">Если вы не можете принять меры, обратитесь к глобальному администратору, чтобы получить следующее разрешение:</span><span class="sxs-lookup"><span data-stu-id="af4b5-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="af4b5-114">*Активные действия по исправлению > управления угрозами и уязвимости - обработка исправлений*</span><span class="sxs-lookup"><span data-stu-id="af4b5-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="af4b5-115">Различные действия на устройствах</span><span class="sxs-lookup"><span data-stu-id="af4b5-115">Take various actions on devices</span></span>
<span data-ttu-id="af4b5-116">На устройствах, которые определены столбцом в результатах запроса, можно `DeviceId` сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="af4b5-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="af4b5-117">Изолировать затронутые устройства, чтобы они содержали заражение, или предотвратить дальнейшее перемещение атак</span><span class="sxs-lookup"><span data-stu-id="af4b5-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="af4b5-118">Сбор пакета исследования для получения дополнительной экспертной информации</span><span class="sxs-lookup"><span data-stu-id="af4b5-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="af4b5-119">Запуск антивирусной проверки для поиска и удаления угроз с помощью последних обновлений аналитики безопасности</span><span class="sxs-lookup"><span data-stu-id="af4b5-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="af4b5-120">Инициировать автоматизированное исследование для проверки и устранения угроз на устройстве и, возможно, других затронутых устройствах</span><span class="sxs-lookup"><span data-stu-id="af4b5-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="af4b5-121">Ограничив выполнение приложения только подписанными Корпорацией Майкрософт исполняемыми файлами, предотвращая последующие действия с помощью вредоносных программ или других недоверных исполняемых файлов</span><span class="sxs-lookup"><span data-stu-id="af4b5-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="af4b5-122">Чтобы узнать больше о том, как эти ответные действия выполняются через Microsoft Defender для конечной точки, ознакомьтесь с ответными [действиями на устройствах.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)</span><span class="sxs-lookup"><span data-stu-id="af4b5-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="af4b5-123">Файлы карантина</span><span class="sxs-lookup"><span data-stu-id="af4b5-123">Quarantine files</span></span>
<span data-ttu-id="af4b5-124">Вы можете развернуть *действие* карантина для файлов, чтобы они автоматически были на карантине при их встрече.</span><span class="sxs-lookup"><span data-stu-id="af4b5-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="af4b5-125">При выборе этого действия вы можете выбрать один из следующих столбцов, чтобы определить, какие файлы в результатах запроса будут на карантине:</span><span class="sxs-lookup"><span data-stu-id="af4b5-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="af4b5-126">`SHA1` — В большинстве таблиц расширенных поисков это SHA-1 файла, на который повлияло записанное действие.</span><span class="sxs-lookup"><span data-stu-id="af4b5-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="af4b5-127">Например, если файл был скопирован, это будет скопирован файл.</span><span class="sxs-lookup"><span data-stu-id="af4b5-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="af4b5-128">`InitiatingProcessSHA1` — в большинстве таблиц расширенных поисков это файл, отвечающий за инициирование записанного действия.</span><span class="sxs-lookup"><span data-stu-id="af4b5-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="af4b5-129">Например, если был запущен родительский процесс, это будет родительский процесс.</span><span class="sxs-lookup"><span data-stu-id="af4b5-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="af4b5-130">`SHA256` — это эквивалент SHA-256 файла, заданной `SHA1` столбцом.</span><span class="sxs-lookup"><span data-stu-id="af4b5-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="af4b5-131">`InitiatingProcessSHA256` — это эквивалент SHA-256 файла, заданной `InitiatingProcessSHA1` столбцом.</span><span class="sxs-lookup"><span data-stu-id="af4b5-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="af4b5-132">Чтобы узнать больше о действиях карантина и восстановлении файлов, ознакомьтесь с ответными [действиями с файлами.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)</span><span class="sxs-lookup"><span data-stu-id="af4b5-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="af4b5-133">Для поиска файлов и их карантина результаты запроса также должны включать значения `DeviceId` в качестве идентификаторов устройств.</span><span class="sxs-lookup"><span data-stu-id="af4b5-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="af4b5-134">Действие</span><span class="sxs-lookup"><span data-stu-id="af4b5-134">Take action</span></span>
<span data-ttu-id="af4b5-135">Чтобы принять любое из описанных действий, выберите одну или несколько записей в результатах запроса, а затем выберите **"Действия".**</span><span class="sxs-lookup"><span data-stu-id="af4b5-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="af4b5-136">Мастер поможет вам выбрать и затем представить предпочтительные действия.</span><span class="sxs-lookup"><span data-stu-id="af4b5-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Изображение выбранной записи с панелью для проверки записи](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="af4b5-138">Проверка принятых действий</span><span class="sxs-lookup"><span data-stu-id="af4b5-138">Review actions taken</span></span>
<span data-ttu-id="af4b5-139">Каждое действие отдельно записи в центре [действий](mtp-action-center.md) в **центре** обработки данных  >   ([security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="af4b5-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="af4b5-140">Перейдите в центр действий, чтобы проверить состояние каждого действия.</span><span class="sxs-lookup"><span data-stu-id="af4b5-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="af4b5-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="af4b5-141">Related topics</span></span>
- [<span data-ttu-id="af4b5-142">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="af4b5-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="af4b5-143">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="af4b5-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="af4b5-144">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="af4b5-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="af4b5-145">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="af4b5-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="af4b5-146">Обзор центра действий</span><span class="sxs-lookup"><span data-stu-id="af4b5-146">Action center overview</span></span>](mtp-action-center.md)
