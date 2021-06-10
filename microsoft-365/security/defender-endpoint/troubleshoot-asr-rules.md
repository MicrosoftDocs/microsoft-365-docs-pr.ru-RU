---
title: Отчет и устранение неполадок в Microsoft Defender для правил ASR конечной точки
description: В этом разделе описаны отчеты и устранение неполадок Microsoft Defender для правил ASR конечной точки
keywords: Правила уменьшения поверхности атаки, asr, hips, система предотвращения вторжения хостов, правила защиты, антиэкспозиция, антиэкспозит, эксплойт, профилактика инфекций, защитник Майкрософт для конечной точки
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246257"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a>Отчет и устранение неполадок Microsoft Defender для правил ASR ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Центр Microsoft 365 безопасности — это новый интерфейс для мониторинга и управления безопасностью в идентификаторах, данных, устройствах, приложениях и инфраструктуре Майкрософт. Здесь можно просмотреть сведения о работоспособности системы безопасности вашей организации, настроить устройства, пользователей и приложения, а также проверить оповещения о подозрительных действиях. Центр безопасности Microsoft 365 создан для того чтобы администраторы безопасности и группы операций безопасности могли лучше управлять вашей организацией и защищать ее. Посетите центр Microsoft 365 безопасности на https://security.microsoft.com сайте .
В Microsoft 365 центре безопасности мы предлагаем вам полный взгляд на текущую конфигурацию правил ASR и события в вашем имении. Обратите внимание, что для заполнения этих отчетов необходимо ввести устройства в службу Microsoft Defender for Endpoint.
Вот снимок экрана из центра безопасности Microsoft 365 (в статье **Reports**  >  **Devices**  >  **Attack surface reduction).** На уровне устройства выберите **Конфигурация** из области правил уменьшения поверхности **Attack.** Отображается следующий экран, на котором можно выбрать определенное устройство и проверить его индивидуальную конфигурацию правил ASR.

:::image type="content" source="images/asrrulesnew.png" alt-text="Экран правил ASR":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a>Microsoft Defender для конечной точки — расширенный поиск

Одна из самых мощных функций Microsoft Defender для конечной точки — это продвинутая охота. Если вы не знакомы с развитой охотой, обратитесь к активной охоте на угрозы [с помощью расширенных охоты.](advanced-hunting-overview.md)

Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that MDE Endpoint Detection and Response (EDR) collects from all your machines. С помощью продвинутой охоты можно активно проверять события, чтобы найти интересные индикаторы и объекты. Гибкий доступ к данным помогает безудержно искать как известные, так и потенциальные угрозы.

С помощью продвинутой охоты можно извлечь сведения о правилах ASR, создавать отчеты и получать углубленные сведения о контексте данного аудита или события блокировки правил ASR.

События правил ASR доступны для запроса из таблицы DeviceEvents в разделе расширенный раздел Центр безопасности в Microsoft Defender. Например, простой запрос, например ниже, может сообщать о всех событиях, которые имеют правила ASR в качестве источника данных, за последние 30 дней и суммировать их по подсчету ActionType, что в этом случае это будет фактическое кодовое имя правила ASR.

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Расширенный запрос на охоту":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="расширенный экран охоты":::

С помощью продвинутой охоты вы можете формировать запросы по своему вкусу, чтобы вы могли видеть, что происходит, независимо от того, хотите ли вы что-то определить на отдельной машине, или вы хотите извлечь сведения из всей среды.

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Шкала microsoft Defender для конечной точки

Альтернативой передовой охоте, но с более узкой областью, является временная шкала машины Microsoft Defender для конечной точки. Вы можете просмотреть все собранные события устройства за последние шесть месяцев в Центр безопасности в Microsoft Defender, переехав в список Машин, выберите заданную машину и нажмите на вкладку Timeline.

На рисунке ниже приведен снимок экрана представления Временной шкалы этих событий на данной конечной точке.  Из этого представления можно отфильтровать список событий на основе любой из групп событий на правой стороне области. Вы также можете включить или отключить события с флагом и вербозией во время просмотра оповещений и прокрутки по исторической шкале.

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Хронология центра безопасности защитника Майкрософт":::

## <a name="how-to-troubleshoot-asr-rules"></a>Устранение неполадок в правилах ASR?

Первый и самый непосредственный способ — проверить локально на устройстве Windows, в котором включены правила ASR (и их конфигурация) с помощью cmdlets PowerShell.

Вот несколько других источников информации, которые Windows, чтобы устранить влияние и работу правил ASR.

### <a name="querying-which-rules-are-active"></a>Запрашивание активных правил
Один из самых простых способов определить, включены ли правила ASR, — и с помощью комлета PowerShell Get-MpPreference.
Пример:

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="получить сценарий mppreference":::

Существует несколько активных правил ASR с различными настроенными действиями.

Чтобы расширить вышеуказанные сведения о правилах ASR, можно использовать свойства AttackSurfaceReductionRules_Ids  **и/или AttackSurfaceReductionRules_Actions.**

Пример.

*Get-MPPreference | Select-Object-ExpandProperty**AttackSurfaceReductionRules_Ids*

:::image type="content" source="images/getmpref-examplenew.png" alt-text="пример mpreference":::

Выше показаны все ID-данные для правил ASR, которые имеют параметр, отличаемый от 0 (Не настроен).

Затем необходимо перечислить фактические действия (блок или аудит), с помощью которых настраивается каждое правило. 

*Get-MPPreference | Select-Object-ExpandProperty**AttackSurfaceReductionRules_Actions*

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a>Запрос событий блокировки и аудита
События правил ASR можно просмотреть в журнале Защитник Windows.

Чтобы получить к нему доступ, откройте Windows для просмотра событий и просмотрите журналы приложений и служб  >  **Microsoft**  >  **Windows**  >  **Защитник Windows**  >  **operational**.

:::image type="content" source="images/eventviewerscrnew.png" alt-text="SCR просмотра событий":::

## <a name="microsoft-defender-malware-protection-logs"></a>Журналы защиты от вредоносных программ Microsoft Defender
Вы также можете просматривать события правил с помощью антивирусная программа в Microsoft Defender средства командной строки, называемого , который можно использовать для управления и настройки и автоматизации задач, если `*mpcmdrun.exe*` это необходимо.

Эту утилиту можно найти в *%ProgramFiles%\Windows Defender\MpCmdRun.exe.* Вы должны запустить его из команды с повышенным запросом (то есть выполнить в качестве администратора).

Чтобы создать сведения о поддержке, *введитеMpCmdRun.exe -getfiles*. Через некоторое время несколько журналов будут упакованы в архив (MpSupportFiles.cab) и доступны в *C:\ProgramData\Microsoft\Защитник Windows\Support*.

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="журналы защиты от вредоносных программ":::

Извлекать этот архив, и у вас будет много файлов, доступных для устранения неполадок.

Наиболее релевантные файлы:

- **MPOperationalEvents.txt** - Этот файл содержит тот же уровень сведений, что и в Защитник Windows журнала операционной службы.
- **MPRegistry.txt** — В этом файле вы сможете проанализировать все текущие конфигурации Защитник Windows с момента захвата журналов поддержки.
- **MPLog.txt** — Этот журнал содержит более подробные сведения обо всех действиях и операциях Защитник Windows.
