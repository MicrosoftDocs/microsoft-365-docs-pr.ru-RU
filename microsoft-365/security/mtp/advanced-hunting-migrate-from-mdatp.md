---
title: Перенос расширенных запросов на поиск из пакета ATP для защитника Майкрософт
description: Узнайте, как настроить запросы ATP для защитника Майкрософт, чтобы их можно было использовать в защите от угроз Майкрософт.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, пакет ATP ATP, мдатп, поиск, запрос, телеметрии, пользовательские обнаружения, схема, Кусто, Microsoft 365, сопоставление
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f56360b28a9fe9de4198d97954a64a429d1d99a5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429699"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a>Перенос расширенных запросов на поиск из пакета ATP для защитника Майкрософт

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Защита от угроз (Майкрософт)

Перемещение расширенных рабочих процессов поиска из пакета ATP для защитника Майкрософт в профилактическое слежение за угрозами с помощью более широкого набора данных. В целях защиты от угроз Майкрософт вы получаете доступ к данным из других решений Microsoft 365 для обеспечения безопасности, в том числе:

- Advanced Threat Protection в Microsoft Defender
- Office 365 Advanced Threat Protection
- Microsoft Cloud App Security
- Расширенная защита от угроз Azure

>[!NOTE]
>Большинство клиентов пакета ATP для защитника Майкрософт могут [использовать защиту от угроз Майкрософт без дополнительных лицензий](prerequisites.md#licensing-requirements). Чтобы начать перевод расширенных рабочих процессов с помощью средства Microsoft Defender ATP, [включите защиту от угроз Майкрософт](mtp-enable.md).

Вы можете выполнить переход, не затрагивая существующие рабочие процессы Microsoft Defender ATP. Сохраненные запросы остаются без изменений, а пользовательские правила обнаружения продолжают выполняться и создавать оповещения. Однако они будут отображаться в защите от угроз Майкрософт. 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a>Таблицы схем только в Microsoft Threat protection
[Расширенная схема подсистемы защиты от угроз Майкрософт](advanced-hunting-schema-tables.md) предоставляет дополнительные таблицы, содержащие данные из различных решений по безопасности Microsoft 365. Следующие таблицы доступны только в Microsoft Threat protection:

| Имя таблицы | Описание |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Оповещения из пакета ATP, Office 365 ATP, Microsoft Cloud App Security и Azure ATP, в том числе сведения о степени серьезности и категории угроз  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Действия, связанные с файлами, в облачных приложениях и службах |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Сведения о файлах, вложенных в сообщения электронной почты |
| [EmailEvents](advanced-hunting-emailevents-table.md) | События электронной почты Microsoft 365, в том числе события доставки и блокировки электронной почты |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | События безопасности, происходящие после доставки, после того как Microsoft 365 доставляет сообщения в почтовый ящик получателя. |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Сведения об URL-адресах в сообщениях электронной почты |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | События, связанные с локальным контроллером домена, на котором работает Active Directory (AD). В этой таблице описываются события, связанные с удостоверениями, и системные события на контроллере домена. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Сведения об учетных записях из различных источников, в том числе Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | События проверки подлинности в Active Directory и Microsoft Online Services |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Запросы для объектов Active Directory, таких как пользователи, группы, устройства и домены |

## <a name="map-devicealertevents-table"></a>Таблица Девицеалертевентс карты
Таблицы `AlertInfo` и `AlertEvidence` таблицы заменяют `DeviceAlertEvents` таблицу в схеме Microsoft Defender ATP. В дополнение к данным о предупреждениях устройств эти две таблицы содержат сведения об оповещениях для удостоверений, приложений и сообщений электронной почты.

Используйте приведенную ниже таблицу, чтобы проверить `DeviceAlertEvents` , как столбцы сопоставляются со столбцами в `AlertInfo` `AlertEvidence` таблицах и.

>[!TIP]
>Помимо столбцов, приведенных в следующей таблице, `AlertEvidence` таблица включает многие другие столбцы, которые обеспечивают более целостное изображение оповещений из различных источников. [Просмотр всех столбцов Алертевиденце](advanced-hunting-alertevidence-table.md) 

| Столбец Девицеалертевентс | Где найти те же данные в защите от угроз Майкрософт |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` и  `AlertEvidence` таблицы |
| `Timestamp` | `AlertInfo` и  `AlertEvidence` таблицы |
| `DeviceId` | `AlertEvidence` приведен |
| `DeviceName` | `AlertEvidence` приведен |
| `Severity` | `AlertInfo` приведен |
| `Category` | `AlertInfo` приведен |
| `Title` | `AlertInfo` приведен |
| `FileName` | `AlertEvidence` приведен |
| `SHA1` | `AlertEvidence` приведен |
| `RemoteUrl` | `AlertEvidence` приведен |
| `RemoteIP` | `AlertEvidence` приведен |
| `AttackTechniques` | `AlertInfo` приведен |
| `ReportId` | Этот столбец, как правило, используется в Microsoft Defender ATP для обнаружения связанных записей в других таблицах. В целях защиты от угроз Майкрософт можно получить связанные данные непосредственно из `AlertEvidence` таблицы. |
| `Table` | Этот столбец, как правило, используется в журнале Microsoft Defender ATP для получения дополнительных сведений о событиях в других таблицах. В целях защиты от угроз Майкрософт можно получить связанные данные непосредственно из `AlertEvidence` таблицы. |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a>Настройка существующих запросов ATP для защитника Microsoft
Запросы ATP для защитника Майкрософт будут работать как есть, если они не ссылаются на `DeviceAlertEvents` таблицу. Чтобы использовать эти запросы в защите от угроз Майкрософт, примените следующие изменения:

- Замените `DeviceAlertEvents` на `AlertInfo` .
- Присоединитесь к `AlertInfo` `AlertEvidence` таблицам, `AlertId` чтобы получить эквивалентные данные.

### <a name="original-query"></a>Исходный запрос
В следующем запросе `DeviceAlertEvents` для получения оповещений, включающих _powershell.exe_, используется пакет ATP для защитника:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Измененный запрос
Приведенный ниже запрос был скорректирован для использования в защите от угроз Майкрософт. Вместо того чтобы проверять имя файла непосредственно из `DeviceAlertEvents` , он присоединяется `AlertEvidence` и проверяет имя файла в этой таблице.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Статьи по теме
- [Включение Защиты от угроз (Майкрософт)](advanced-hunting-query-language.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Расширенные функции Поиск в защитнике Майкрософт ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)