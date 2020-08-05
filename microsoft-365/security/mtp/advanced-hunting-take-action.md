---
title: Выполнение действий с расширенными результатами запроса поиска при поиске в Microsoft Threat protection
description: Быстрое устранение угроз и затронутых ресурсов в расширенных результатах поиска
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, выполнение действий
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4ebf220472db69d48127b805256e15246bd400cb
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552741"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="afb02-104">Выполнение действий с расширенными результатами запроса поиска</span><span class="sxs-lookup"><span data-stu-id="afb02-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="afb02-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="afb02-105">**Applies to:**</span></span>
- <span data-ttu-id="afb02-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="afb02-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="afb02-107">Вы можете быстро содержать угрозы или адрес скомпрометированных ресурсов, которые вы найдете в [расширенном поиске](advanced-hunting-overview.md) с помощью мощных и подробных параметров действий.</span><span class="sxs-lookup"><span data-stu-id="afb02-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="afb02-108">С помощью этих параметров можно выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="afb02-108">With these options, you can:</span></span>

- <span data-ttu-id="afb02-109">Выполнение различных действий на устройствах</span><span class="sxs-lookup"><span data-stu-id="afb02-109">Take various actions on devices</span></span>
- <span data-ttu-id="afb02-110">Файлы на карантине</span><span class="sxs-lookup"><span data-stu-id="afb02-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="afb02-111">Обязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="afb02-111">Required permissions</span></span>
<span data-ttu-id="afb02-112">Чтобы обеспечить возможность выполнения действий с помощью расширенного поискового значения, вам потребуется роль в Microsoft Defender ATP с [разрешениями на отправку действий по исправлению на устройствах](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="afb02-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender ATP with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="afb02-113">Если вы не можете выполнить действие, обратитесь к глобальному администратору, чтобы получить следующее разрешение:</span><span class="sxs-lookup"><span data-stu-id="afb02-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="afb02-114">*Действия по устранению неполадок > угроз и уязвимостей управления угрозами — обработка исправлений*</span><span class="sxs-lookup"><span data-stu-id="afb02-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="afb02-115">Выполнение различных действий на устройствах</span><span class="sxs-lookup"><span data-stu-id="afb02-115">Take various actions on devices</span></span>
<span data-ttu-id="afb02-116">На устройствах, определяемых `DeviceId` столбцом в результатах запроса, можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="afb02-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="afb02-117">Обнаружение затронутых устройств на наличие заражения или предотвращение последующего перемещения атак</span><span class="sxs-lookup"><span data-stu-id="afb02-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="afb02-118">Сбор пакета для расследования для получения дополнительных сведений об судебном разбирательстве</span><span class="sxs-lookup"><span data-stu-id="afb02-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="afb02-119">Запуск антивирусной проверки для обнаружения и удаления угроз с использованием последних обновлений для системы безопасности</span><span class="sxs-lookup"><span data-stu-id="afb02-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="afb02-120">Запуск автоматического исследования для проверки и исправления угроз на устройстве и на других затронутых устройствах</span><span class="sxs-lookup"><span data-stu-id="afb02-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="afb02-121">Ограничьте выполнение приложения только исполняемыми файлами, подписанными корпорацией Майкрософт, что предотвращает последующие действия с угрозами с помощью вредоносных программ или других недоверенных исполняемых файлов</span><span class="sxs-lookup"><span data-stu-id="afb02-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="afb02-122">Чтобы узнать больше о том, как эти действия отклика выполняются с помощью пакета ATP для защитника Microsoft, [прочитайте о действиях с откликом на устройствах](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span><span class="sxs-lookup"><span data-stu-id="afb02-122">To learn more about how these response actions are performed through Microsoft Defender ATP, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="afb02-123">Файлы на карантине</span><span class="sxs-lookup"><span data-stu-id="afb02-123">Quarantine files</span></span>
<span data-ttu-id="afb02-124">Вы можете развернуть действие *карантина* для файлов, чтобы они автоматически помещаются в карантин при обнаружении.</span><span class="sxs-lookup"><span data-stu-id="afb02-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="afb02-125">При выборе этого действия можно выбрать один из следующих столбцов, чтобы определить, какие файлы в результатах запроса следует присвоить карантину:</span><span class="sxs-lookup"><span data-stu-id="afb02-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="afb02-126">`SHA1`— В большинстве расширенных таблиц поиске это SHA-1 файла, на который влияет записанное действие.</span><span class="sxs-lookup"><span data-stu-id="afb02-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="afb02-127">Например, если скопировать файл, это будет скопированный файл.</span><span class="sxs-lookup"><span data-stu-id="afb02-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="afb02-128">`InitiatingProcessSHA1`— В большинстве расширенных таблиц подпоиска это файл, отвечающий за инициирование записанного действия.</span><span class="sxs-lookup"><span data-stu-id="afb02-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="afb02-129">Например, если был запущен дочерний процесс, это будет родительским процессом.</span><span class="sxs-lookup"><span data-stu-id="afb02-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="afb02-130">`SHA256`— Это эквивалент SHA-256 для файла, указанного в `SHA1` столбце.</span><span class="sxs-lookup"><span data-stu-id="afb02-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="afb02-131">`InitiatingProcessSHA256`— Это эквивалент SHA-256 для файла, указанного в `InitiatingProcessSHA1` столбце.</span><span class="sxs-lookup"><span data-stu-id="afb02-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="afb02-132">Чтобы узнать больше о том, как выполняются действия карантина и как можно восстановить файлы, [прочитайте сведения об ответных действиях для файлов](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="afb02-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="afb02-133">Чтобы получить файлы и поместить их в карантин, результаты запроса также должны включать `DeviceId` значения в качестве идентификаторов устройств.</span><span class="sxs-lookup"><span data-stu-id="afb02-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="afb02-134">Выполнение действий</span><span class="sxs-lookup"><span data-stu-id="afb02-134">Take action</span></span>
<span data-ttu-id="afb02-135">Чтобы выполнить любое из описанных действий, выберите одну или несколько записей в результатах запроса, а затем выберите команду **выполнить действия**.</span><span class="sxs-lookup"><span data-stu-id="afb02-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="afb02-136">Мастер поможет вам выбрать и затем отправить предпочтительные действия.</span><span class="sxs-lookup"><span data-stu-id="afb02-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Изображение выбранной записи с панелью для проверки записи](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="afb02-138">Просмотр выполненных действий</span><span class="sxs-lookup"><span data-stu-id="afb02-138">Review actions taken</span></span>
<span data-ttu-id="afb02-139">Каждое действие записывается отдельно в [центре действий](mtp-action-center.md) в **журнале центра уведомлений**  >  **History** ([Security.Microsoft.com/Action-Center/History](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="afb02-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="afb02-140">Перейдите в центр уведомлений, чтобы проверить состояние каждого действия.</span><span class="sxs-lookup"><span data-stu-id="afb02-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="afb02-141">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="afb02-141">Related topics</span></span>
- [<span data-ttu-id="afb02-142">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="afb02-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="afb02-143">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="afb02-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="afb02-144">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="afb02-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="afb02-145">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="afb02-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="afb02-146">Общие сведения о центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="afb02-146">Action center overview</span></span>](mtp-action-center.md)