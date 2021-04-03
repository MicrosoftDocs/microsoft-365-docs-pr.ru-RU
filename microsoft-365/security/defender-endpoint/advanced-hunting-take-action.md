---
title: Действия по расширенным запросам на охоту в Microsoft Threat Protection
description: Быстрое устранение угроз и затронутых активов в результатах предварительного запроса на охоту
keywords: передовая охота, охота на угрозы, охота на киберугрозы, mdatp, защита microsoft atp, поиск wdatp, запрос, телеметрия, настраиваемые обнаружения, схема, кусто, избегайте времени, командных строк, id процесса
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: d1dbe226cef5e94b36fcd6c35b839118b200f85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500534"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="e0635-104">Принять меры по расширенным результатам запроса на охоту</span><span class="sxs-lookup"><span data-stu-id="e0635-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="e0635-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e0635-105">**Applies to:**</span></span>
- [<span data-ttu-id="e0635-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e0635-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="e0635-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="e0635-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e0635-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="e0635-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="e0635-109">Вы можете быстро содержать угрозы или обращаться к скомпрометированным активам, которые находятся в продвинутой охоте с [помощью](advanced-hunting-overview.md) мощных и комплексных вариантов действий.</span><span class="sxs-lookup"><span data-stu-id="e0635-109">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="e0635-110">С помощью этих параметров можно:</span><span class="sxs-lookup"><span data-stu-id="e0635-110">With these options, you can:</span></span>

- <span data-ttu-id="e0635-111">Различные действия на устройствах</span><span class="sxs-lookup"><span data-stu-id="e0635-111">Take various actions on devices</span></span>
- <span data-ttu-id="e0635-112">Файлы карантина</span><span class="sxs-lookup"><span data-stu-id="e0635-112">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="e0635-113">Обязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="e0635-113">Required permissions</span></span>

<span data-ttu-id="e0635-114">Чтобы иметь возможность действовать с помощью продвинутой охоты, вам потребуется роль в Defender для конечной точки с разрешениями на отправку действий по исправлению на [устройствах.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="e0635-114">To be able to take action through advanced hunting, you need a role in Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span></span> <span data-ttu-id="e0635-115">Если вы не можете принять меры, обратитесь к глобальному администратору, чтобы получить следующее разрешение:</span><span class="sxs-lookup"><span data-stu-id="e0635-115">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="e0635-116">*Активные действия по исправлению > управления угрозами и уязвимостью — обработка исправлений*</span><span class="sxs-lookup"><span data-stu-id="e0635-116">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="e0635-117">Различные действия на устройствах</span><span class="sxs-lookup"><span data-stu-id="e0635-117">Take various actions on devices</span></span>

<span data-ttu-id="e0635-118">Вы можете принять следующие действия на устройствах, идентифицированных `DeviceId` столбцом в результатах запроса:</span><span class="sxs-lookup"><span data-stu-id="e0635-118">You can take the following actions on devices identified by the `DeviceId` column in your query results:</span></span>

- <span data-ttu-id="e0635-119">Изолировать затронутые устройства для сдерживания инфекции или предотвращения атак с последующим перемещением</span><span class="sxs-lookup"><span data-stu-id="e0635-119">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="e0635-120">Сбор пакета расследований для получения дополнительных сведений судебной экспертизы</span><span class="sxs-lookup"><span data-stu-id="e0635-120">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="e0635-121">Запустите антивирусное сканирование, чтобы найти и удалить угрозы с помощью последних обновлений разведки безопасности</span><span class="sxs-lookup"><span data-stu-id="e0635-121">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="e0635-122">Инициировать автоматическое расследование для проверки и устранения угроз на устройстве и, возможно, других затронутых устройствах.</span><span class="sxs-lookup"><span data-stu-id="e0635-122">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="e0635-123">Ограничить выполнение приложений только исполняемыми файлами, подписанными Корпорацией Майкрософт, предотвращая последующие действия с помощью вредоносных программ или других ненарушаемых исполняемых файлов.</span><span class="sxs-lookup"><span data-stu-id="e0635-123">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="e0635-124">Дополнительные данные о том, как эти действия реагирования выполняются через Defender для endpoint, читайте в материале "Действия реагирования на [устройствах".](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e0635-124">To learn more about how these response actions are performed through Defender for Endpoint, [read about response actions on devices](respond-machine-alerts.md).</span></span>

## <a name="quarantine-files"></a><span data-ttu-id="e0635-125">Файлы карантина</span><span class="sxs-lookup"><span data-stu-id="e0635-125">Quarantine files</span></span>

<span data-ttu-id="e0635-126">Вы можете развернуть действие *карантина* в файлах, чтобы они автоматически были на карантине при встрече.</span><span class="sxs-lookup"><span data-stu-id="e0635-126">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="e0635-127">При выборе этого действия можно выбрать между следующими столбцами, чтобы определить, какие файлы в результатах запроса будут карантином:</span><span class="sxs-lookup"><span data-stu-id="e0635-127">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="e0635-128">`SHA1` — В большинстве расширенных таблиц охоты это SHA-1 файла, на который повлияло записанное действие.</span><span class="sxs-lookup"><span data-stu-id="e0635-128">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="e0635-129">Например, если файл был скопирован, это будет скопирован файл.</span><span class="sxs-lookup"><span data-stu-id="e0635-129">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="e0635-130">`InitiatingProcessSHA1` — В большинстве расширенных таблиц охоты это файл, ответственный за инициирование записанного действия.</span><span class="sxs-lookup"><span data-stu-id="e0635-130">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="e0635-131">Например, если запущен детский процесс, это будет родительский процесс.</span><span class="sxs-lookup"><span data-stu-id="e0635-131">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="e0635-132">`SHA256` — Это эквивалент SHA-256 файла, идентифицированного `SHA1` столбцом.</span><span class="sxs-lookup"><span data-stu-id="e0635-132">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="e0635-133">`InitiatingProcessSHA256` — Это эквивалент SHA-256 файла, идентифицированного `InitiatingProcessSHA1` столбцом.</span><span class="sxs-lookup"><span data-stu-id="e0635-133">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="e0635-134">Дополнительные данные о том, как принимаются карантиные действия и как можно восстановить файлы, см. в материале о действиях [реагирования на файлы.](respond-file-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e0635-134">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](respond-file-alerts.md).</span></span>

>[!NOTE]
><span data-ttu-id="e0635-135">Для обнаружения файлов и их карантина результаты запроса должны также включать значения `DeviceId` в качестве идентификаторов устройств.</span><span class="sxs-lookup"><span data-stu-id="e0635-135">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="e0635-136">Принять меры</span><span class="sxs-lookup"><span data-stu-id="e0635-136">Take action</span></span>

<span data-ttu-id="e0635-137">Чтобы принять любое из описанных действий, выберите одну или несколько записей в результатах запроса и выберите **Действие.**</span><span class="sxs-lookup"><span data-stu-id="e0635-137">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="e0635-138">Мастер поможет вам в процессе выбора и отправки предпочтительных действий.</span><span class="sxs-lookup"><span data-stu-id="e0635-138">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Изображение выбранной записи с панелью для проверки записи](images/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="e0635-140">Проверка принятых действий</span><span class="sxs-lookup"><span data-stu-id="e0635-140">Review actions taken</span></span>

<span data-ttu-id="e0635-141">Каждое действие индивидуально записуется в центре действий в статье **История** центра действий  >   [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="e0635-141">Each action is individually recorded in the action center, under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="e0635-142">Перейдите в центр действий, чтобы проверить состояние каждого действия.</span><span class="sxs-lookup"><span data-stu-id="e0635-142">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="e0635-143">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e0635-143">Related topics</span></span>

- [<span data-ttu-id="e0635-144">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="e0635-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e0635-145">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="e0635-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e0635-146">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="e0635-146">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="e0635-147">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="e0635-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="e0635-148">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="e0635-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e0635-149">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="e0635-149">Custom detections overview</span></span>](overview-custom-detections.md)
