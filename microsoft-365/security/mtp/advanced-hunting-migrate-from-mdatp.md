---
title: Перенос запросов на расширенный поиск из Microsoft Defender для конечной точки
description: Узнайте, как настроить Microsoft Defender для запросов конечных точек, чтобы использовать их в Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, microsoft defender atp, mdatp, search, query, telemetry, custom detections, schema, kusto, microsoft 365, mapping
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094811"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Перенос запросов на расширенный поиск из Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

Переместите ваши расширенные процессы выслеки из Microsoft Defender для конечной точки, чтобы заблаговременно искать угрозы с использованием более широкого набора данных. В Microsoft 365 Defender вы получаете доступ к данным из других решений для обеспечения безопасности Microsoft 365, в том числе:

- Microsoft Defender для конечной точки
- Microsoft Defender для Office 365
- Microsoft Cloud App Security
- Microsoft Defender для удостоверений

>[!NOTE]
>Большинство пользователей Endpoint в Microsoft Defender могут использовать [Microsoft 365 Defender без дополнительных лицензий.](prerequisites.md#licensing-requirements) Чтобы начать переключение расширенных процессов охоты из Защитника для конечной точки, включите [Microsoft 365 Defender.](mtp-enable.md)

Переход можно без влияния на существующие процессы Защитника для конечных точек. Сохраненные запросы остаются без изменений, а пользовательские правила обнаружения продолжают запускаться и создавать оповещения. Однако они будут видны в Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Таблицы схемы только в Microsoft 365 Defender
Схема advanced hunting в [Microsoft 365 Defender](advanced-hunting-schema-tables.md) предоставляет дополнительные таблицы, содержащие данные из различных решений для обеспечения безопасности Microsoft 365. Следующие таблицы доступны только в Microsoft 365 Defender:

| Имя таблицы | Описание |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Оповещения из Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для удостоверений, включая сведения о серьезности и категории угроз  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Действия, связанные с файлами, в облачных приложениях и службах |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Сведения о файлах, вложенных в сообщения электронной почты |
| [EmailEvents](advanced-hunting-emailevents-table.md) | События электронной почты Microsoft 365, в том числе события доставки и блокирования электронной почты |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | События безопасности, которые происходят после доставки, после того как Microsoft 365 доставляет сообщения электронной почты в почтовый ящик получателя |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Сведения об URL-адресах в электронных письмах |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | События, связанные с контроллером локального домена под управлением Active Directory (AD). В этой таблице описывается ряд событий, связанных с удостоверением, и системных событий на контроллере домена. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Сведения об учетной записи из различных источников, включая Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | События проверки подлинности в Active Directory и веб-службах Майкрософт |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Запросы объектов Active Directory, таких как пользователи, группы, устройства и домены |

## <a name="map-devicealertevents-table"></a>Таблица Map DeviceAlertEvents
Таблицы `AlertInfo` `AlertEvidence` и `DeviceAlertEvents` таблицы заменяют таблицу в схеме Microsoft Defender для конечных точек. Помимо данных об оповещениях устройств эти две таблицы включают данные об оповещениях для удостоверений, приложений и электронных писем.

Используйте следующую таблицу для проверки того, как `DeviceAlertEvents` столбцы соеблюют столбцы в `AlertInfo` таблицах и `AlertEvidence` столбцах.

>[!TIP]
>Помимо столбцов в следующей таблице, в таблице содержится множество других столбцов, которые предоставляют более целостную картину оповещений из `AlertEvidence` различных источников. [См. все столбцы AlertEvidence](advanced-hunting-alertevidence-table.md) 

| Столбец DeviceAlertEvents | Где найти те же данные в Microsoft 365 Defender |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` и  `AlertEvidence` таблицы |
| `Timestamp` | `AlertInfo` и  `AlertEvidence` таблицы |
| `DeviceId` | `AlertEvidence` table |
| `DeviceName` | `AlertEvidence` table |
| `Severity` | `AlertInfo` table |
| `Category` | `AlertInfo` table |
| `Title` | `AlertInfo` table |
| `FileName` | `AlertEvidence` table |
| `SHA1` | `AlertEvidence` table |
| `RemoteUrl` | `AlertEvidence` table |
| `RemoteIP` | `AlertEvidence` table |
| `AttackTechniques` | `AlertInfo` table |
| `ReportId` | Этот столбец обычно используется в Microsoft Defender для конечной точки для поиска связанных записей в других таблицах. В Microsoft 365 Defender вы можете получить связанные данные непосредственно из `AlertEvidence` таблицы. |
| `Table` | Этот столбец обычно используется в Microsoft Defender для конечной точки для получения дополнительных сведений о событиях в других таблицах. В Microsoft 365 Defender вы можете получить связанные данные непосредственно из `AlertEvidence` таблицы. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Настройка существующего Защитника Майкрософт для запросов конечных точек
Microsoft Defender для запросов конечных точек будет работать без ссылки на `DeviceAlertEvents` таблицу. Чтобы использовать эти запросы в Microsoft 365 Defender, внесите указанные здесь изменения.

- Замените `DeviceAlertEvents` на `AlertInfo` .
- Присоединитесь `AlertInfo` к `AlertEvidence` таблицам и таблицам, чтобы получить `AlertId` эквивалентные данные.

### <a name="original-query"></a>Исходный запрос
Следующий запрос использует в Microsoft Defender для конечной точки для получения оповещений, `DeviceAlertEvents` в том числеpowershell.exe: __

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Изменен запрос
Следующий запрос был настроен для использования в Microsoft 365 Defender. Вместо того чтобы проверять имя файла непосредственно из, он присоединяется и проверяет имя `DeviceAlertEvents` `AlertEvidence` файла в этой таблице.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a>См. также
- [Включить Защитник Microsoft 365](advanced-hunting-query-language.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Расширенный поиск в Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)