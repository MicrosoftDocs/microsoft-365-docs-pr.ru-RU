---
title: Перенос дополнительных запросов на Поиск от защитника Майкрософт для конечной точки
description: Узнайте, как настроить защитник Майкрософт для запросов к конечным точкам, чтобы их можно было использовать в защитнике Microsoft 365.
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
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846860"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Перенос дополнительных запросов на Поиск от защитника Майкрософт для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Защитник Microsoft 365

Перемещение расширенных рабочих процессов поиска из защитника Майкрософт для конечной точки для профилактического поиска угроз с помощью более широкого набора данных. В защитнике Microsoft 365 вы получаете доступ к данным из других решений для обеспечения безопасности Microsoft 365, в том числе:

- Microsoft Defender для конечной точки
- Защитник Майкрософт для Office 365
- Microsoft Cloud App Security
- Microsoft Defender для удостоверений

>[!NOTE]
>Большинство защитника Майкрософт для конечных пользователей могут [использовать защитник microsoft 365 без дополнительных лицензий](prerequisites.md#licensing-requirements). Чтобы начать переводить расширенные рабочие процессы подпоиска из защитника для конечной точки, [включите Защитник Microsoft 365](mtp-enable.md).

Вы можете выполнить переход, не затрагивая существующий защитник для рабочих процессов конечной точки. Сохраненные запросы остаются без изменений, а пользовательские правила обнаружения продолжают выполняться и создавать оповещения. Однако они будут отображаться в защитнике Microsoft 365. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Таблицы схем только для защитника Microsoft 365
[Схема расширенного контроля за защитником microsoft 365](advanced-hunting-schema-tables.md) содержит дополнительные таблицы, содержащие данные из различных решений по безопасности Microsoft 365. Следующие таблицы доступны только в защитнике Microsoft 365:

| Имя таблицы | Описание |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Оповещения от защитника Майкрософт для конечной точки, защитник Майкрософт для Office 365, Microsoft Cloud App Security и защитник Майкрософт для удостоверения, в том числе сведения о степени серьезности и категории угроз  |
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
Таблицы `AlertInfo` и `AlertEvidence` таблицы заменяют `DeviceAlertEvents` таблицу в схеме "защитник Майкрософт для конечной точки". В дополнение к данным о предупреждениях устройств эти две таблицы содержат сведения об оповещениях для удостоверений, приложений и сообщений электронной почты.

Используйте приведенную ниже таблицу, чтобы проверить `DeviceAlertEvents` , как столбцы сопоставляются со столбцами в `AlertInfo` `AlertEvidence` таблицах и.

>[!TIP]
>Помимо столбцов, приведенных в следующей таблице, `AlertEvidence` таблица включает многие другие столбцы, которые обеспечивают более целостное изображение оповещений из различных источников. [Просмотр всех столбцов Алертевиденце](advanced-hunting-alertevidence-table.md) 

| Столбец Девицеалертевентс | Где найти те же данные в защитнике Microsoft 365 |
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
| `ReportId` | Этот столбец обычно используется в защитнике Майкрософт для конечной точки для обнаружения связанных записей в других таблицах. В защитнике Microsoft 365 можно получить связанные данные непосредственно из `AlertEvidence` таблицы. |
| `Table` | Этот столбец обычно используется в защитнике Майкрософт для конечной точки для дополнительных сведений о событиях в других таблицах. В защитнике Microsoft 365 можно получить связанные данные непосредственно из `AlertEvidence` таблицы. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Настройка существующего защитника Майкрософт для запросов к конечным точкам
Защитник Майкрософт для запросов к конечным точкам будет работать как есть, если они не ссылаются на `DeviceAlertEvents` таблицу. Чтобы использовать эти запросы в защитнике Microsoft 365, примените следующие изменения:

- Замените `DeviceAlertEvents` на `AlertInfo` .
- Присоединитесь к `AlertInfo` `AlertEvidence` таблицам, `AlertId` чтобы получить эквивалентные данные.

### <a name="original-query"></a>Исходный запрос
Следующий запрос использует `DeviceAlertEvents` в защитнике Майкрософт для конечной точки, чтобы получать оповещения, включающие _powershell.exe_ :

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Измененный запрос
Следующий запрос был настроен для использования в защитнике Microsoft 365. Вместо того чтобы проверять имя файла непосредственно из `DeviceAlertEvents` , он присоединяется `AlertEvidence` и проверяет имя файла в этой таблице.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Статьи по теме
- [Включение защитника Microsoft 365](advanced-hunting-query-language.md)
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Расширенный поиск в защитнике Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)