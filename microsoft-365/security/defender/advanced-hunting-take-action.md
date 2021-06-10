---
title: Действие по расширенным запросам на охоту приводит к Microsoft 365 Defender
description: Быстрое устранение угроз и затронутых активов в результатах предварительного запроса на охоту
keywords: продвинутая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, принять меры
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 15eebbba102640a92f9c7712194aaef685a96cfb
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952612"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="5b20c-104">Принять меры по расширенным результатам запроса на охоту</span><span class="sxs-lookup"><span data-stu-id="5b20c-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5b20c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5b20c-105">**Applies to:**</span></span>
- <span data-ttu-id="5b20c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b20c-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="5b20c-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5b20c-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="5b20c-108">Вы можете быстро содержать угрозы или обращаться к скомпрометированным активам, которые находятся в продвинутой охоте с [помощью](advanced-hunting-overview.md) мощных и комплексных вариантов действий.</span><span class="sxs-lookup"><span data-stu-id="5b20c-108">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="5b20c-109">С помощью этих параметров можно:</span><span class="sxs-lookup"><span data-stu-id="5b20c-109">With these options, you can:</span></span>

- <span data-ttu-id="5b20c-110">Различные действия на устройствах</span><span class="sxs-lookup"><span data-stu-id="5b20c-110">Take various actions on devices</span></span>
- <span data-ttu-id="5b20c-111">Файлы карантина</span><span class="sxs-lookup"><span data-stu-id="5b20c-111">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="5b20c-112">Обязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="5b20c-112">Required permissions</span></span>
<span data-ttu-id="5b20c-113">Чтобы иметь возможность действовать с помощью продвинутой охоты, вам потребуется роль в Microsoft Defender для конечной точки с разрешениями на отправку действий по исправлению на [устройствах.](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="5b20c-113">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="5b20c-114">Если вы не можете принять меры, обратитесь к глобальному администратору, чтобы получить следующее разрешение:</span><span class="sxs-lookup"><span data-stu-id="5b20c-114">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="5b20c-115">*Активные действия по исправлению > и управление уязвимостями - обработка исправлений*</span><span class="sxs-lookup"><span data-stu-id="5b20c-115">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="5b20c-116">Различные действия на устройствах</span><span class="sxs-lookup"><span data-stu-id="5b20c-116">Take various actions on devices</span></span>
<span data-ttu-id="5b20c-117">Вы можете принять следующие действия на устройствах, идентифицированных `DeviceId` столбцом в результатах запроса:</span><span class="sxs-lookup"><span data-stu-id="5b20c-117">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="5b20c-118">Изолировать затронутые устройства для сдерживания инфекции или предотвращения атак с последующим перемещением</span><span class="sxs-lookup"><span data-stu-id="5b20c-118">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="5b20c-119">Сбор пакета расследований для получения дополнительных сведений судебной экспертизы</span><span class="sxs-lookup"><span data-stu-id="5b20c-119">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="5b20c-120">Запустите антивирусное сканирование, чтобы найти и удалить угрозы с помощью последних обновлений разведки безопасности</span><span class="sxs-lookup"><span data-stu-id="5b20c-120">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="5b20c-121">Инициировать автоматическое расследование для проверки и устранения угроз на устройстве и, возможно, других затронутых устройствах.</span><span class="sxs-lookup"><span data-stu-id="5b20c-121">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="5b20c-122">Ограничить выполнение приложений только исполняемыми файлами, подписанными Корпорацией Майкрософт, предотвращая последующие действия с помощью вредоносных программ или других ненарушаемых исполняемых файлов.</span><span class="sxs-lookup"><span data-stu-id="5b20c-122">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="5b20c-123">Дополнительные данные о том, как эти действия реагирования выполняются с помощью Microsoft Defender для конечной точки, ознакомьтесь с действиями [реагирования на устройствах.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)</span><span class="sxs-lookup"><span data-stu-id="5b20c-123">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="5b20c-124">Файлы карантина</span><span class="sxs-lookup"><span data-stu-id="5b20c-124">Quarantine files</span></span>
<span data-ttu-id="5b20c-125">Вы можете развернуть действие *карантина* в файлах, чтобы они автоматически были на карантине при встрече.</span><span class="sxs-lookup"><span data-stu-id="5b20c-125">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="5b20c-126">При выборе этого действия можно выбрать между следующими столбцами, чтобы определить, какие файлы в результатах запроса будут карантином:</span><span class="sxs-lookup"><span data-stu-id="5b20c-126">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="5b20c-127">`SHA1` — В большинстве расширенных таблиц охоты это SHA-1 файла, на который повлияло записанное действие.</span><span class="sxs-lookup"><span data-stu-id="5b20c-127">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="5b20c-128">Например, если файл был скопирован, это будет скопирован файл.</span><span class="sxs-lookup"><span data-stu-id="5b20c-128">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="5b20c-129">`InitiatingProcessSHA1` — В большинстве расширенных таблиц охоты это файл, ответственный за инициирование записанного действия.</span><span class="sxs-lookup"><span data-stu-id="5b20c-129">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="5b20c-130">Например, если запущен детский процесс, это будет родительский процесс.</span><span class="sxs-lookup"><span data-stu-id="5b20c-130">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="5b20c-131">`SHA256` — Это эквивалент SHA-256 файла, идентифицированного `SHA1` столбцом.</span><span class="sxs-lookup"><span data-stu-id="5b20c-131">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="5b20c-132">`InitiatingProcessSHA256` — Это эквивалент SHA-256 файла, идентифицированного `InitiatingProcessSHA1` столбцом.</span><span class="sxs-lookup"><span data-stu-id="5b20c-132">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="5b20c-133">Дополнительные данные о том, как принимаются карантиные действия и как можно восстановить файлы, см. в материале о действиях [реагирования на файлы.](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)</span><span class="sxs-lookup"><span data-stu-id="5b20c-133">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="5b20c-134">Для обнаружения файлов и их карантина результаты запроса должны также включать значения `DeviceId` в качестве идентификаторов устройств.</span><span class="sxs-lookup"><span data-stu-id="5b20c-134">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="5b20c-135">Действия</span><span class="sxs-lookup"><span data-stu-id="5b20c-135">Take action</span></span>
<span data-ttu-id="5b20c-136">Чтобы принять любое из описанных действий, выберите одну или несколько записей в результатах запроса и выберите **Действие.**</span><span class="sxs-lookup"><span data-stu-id="5b20c-136">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="5b20c-137">Мастер поможет вам в процессе выбора и отправки предпочтительных действий.</span><span class="sxs-lookup"><span data-stu-id="5b20c-137">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Изображение выбранной записи с панелью для проверки записи](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="5b20c-139">Проверка принятых действий</span><span class="sxs-lookup"><span data-stu-id="5b20c-139">Review actions taken</span></span>
<span data-ttu-id="5b20c-140">Каждое действие индивидуально записывают в [центре](m365d-action-center.md) действий в статье **История** центра действий  >   [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="5b20c-140">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="5b20c-141">Перейдите в центр действий, чтобы проверить состояние каждого действия.</span><span class="sxs-lookup"><span data-stu-id="5b20c-141">Go to the action center to check the status of each action.</span></span>
 
>[!NOTE]
><span data-ttu-id="5b20c-142">Некоторые таблицы в этой статье могут быть недоступны в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5b20c-142">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="5b20c-143">[Включи Microsoft 365 Defender,](m365d-enable.md) чтобы искать угрозы с помощью дополнительных источников данных.</span><span class="sxs-lookup"><span data-stu-id="5b20c-143">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="5b20c-144">Вы можете переместить расширенные процессы охоты из Microsoft Defender для endpoint в Microsoft 365 Defender, следуя шагам в миграции расширенных запросов охоты из [Microsoft Defender для конечной точки](advanced-hunting-migrate-from-mde.md).</span><span class="sxs-lookup"><span data-stu-id="5b20c-144">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5b20c-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5b20c-145">Related topics</span></span>
- [<span data-ttu-id="5b20c-146">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="5b20c-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5b20c-147">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="5b20c-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5b20c-148">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="5b20c-148">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="5b20c-149">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="5b20c-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5b20c-150">Обзор центра действий</span><span class="sxs-lookup"><span data-stu-id="5b20c-150">Action center overview</span></span>](m365d-action-center.md)
