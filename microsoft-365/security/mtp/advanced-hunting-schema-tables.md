---
title: Таблицы данных в схеме расширенной охоты на угрозы в службе защиты от угроз (Майкрософт)
description: Ознакомьтесь со сведениями о таблицах в схеме расширенной охоты на угрозы, чтобы понять, для каких типов данных можно выполнять запросы на охоту на угрозы
keywords: расширенная охота на угрозы, охота на угрозы, охота на киберугрозы, поиск, запрос, телеметрия, справка по схеме, kusto, таблица, данные
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1803445dfd9b46fce23b0dcc9585ea543f1b0347
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911514"
---
# <a name="understand-the-advanced-hunting-schema"></a>Общие сведения о схеме расширенной охоты на угрозы

**Область применения:**
- Защита от угроз (Майкрософт)

[!include[Prerelease information](prerelease.md)]

Схема [расширенной охоты на угрозы](advanced-hunting-overview.md) состоит из нескольких таблиц, которые содержат сведения о событиях или информацию о компьютерах и объектах. Для эффективного построения запросов, охватывающих несколько таблиц, необходимо понимать, что такое таблицы и столбцы в схеме расширенной охоты на угрозы

## <a name="schema-tables"></a>Таблицы схем

В приведенной ниже ссылке перечислены все таблицы в схеме. Каждое название таблицы содержит ссылку на страницу, описывающую имена столбцов для этой таблицы. Имена таблиц и столбцов также указаны в центре безопасности в составе схемы на экране расширенной охоты на угрозы

| Имя таблицы | Описание |
|------------|-------------|
| **[MachineInfo](advanced-hunting-machineinfo-table.md)** | Сведения о компьютере, в том числе данные об ОС |
| **[MachineNetworkInfo](advanced-hunting-machinenetworkinfo-table.md)** | Свойства сети компьютеров, включая адаптеры, IP-и MAC-адреса, а также подключенные сети и домены. |
| **[ProcessCreationEvents](advanced-hunting-processcreationevents-table.md)** | Создание процессов и связанных с ними событий |
| **[NetworkCommunicationEvents](advanced-hunting-networkcommunicationevents-table.md)** | Сетевое подключение и связанные события |
| **[FileCreationEvents](advanced-hunting-filecreationevents-table.md)** | Создание файла, изменение и другие события файловой системы |
| **[RegistryEvents](advanced-hunting-registryevents-table.md)** | Создание и изменение записей реестра |
| **[LogonEvents](advanced-hunting-logonevents-table.md)** | Входы и другие события проверки подлинности |
| **[ImageLoadEvents](advanced-hunting-imageloadevents-table.md)** | События загрузки библиотек DLL |
| **[MiscEvents](advanced-hunting-miscevents-table.md)** | Несколько типов событий, в том числе события, запускаемые такими элементами управления безопасностью, как антивирусная программа "Защитник Windows" и защита от эксплойтов |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | События электронной почты Office 365, в том числе события доставки и блокирования электронной почты |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Сведения о файлах, вложенных в электронные сообщения Office 365 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Сведения об URL-адресах в электронных сообщениях Office 365 |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | Перечень программного обеспечения на устройствах, а также всех известных уязвимостей в этих программных продуктах |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | База знаний уязвимостей, о которых сообщалось в открытых источниках, включая информацию о том, является ли эксплойт общедоступным. |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | События по оценке контроля угроз и уязвимостей, указывающие состояние различных конфигураций безопасности на устройствах |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | База знаний различных конфигураций безопасности, используемых системой контроля угроз и уязвимостей для оценки устройств; включает в себя сопоставления с различными стандартами и контрольными показателями  |

## <a name="related-topics"></a>Статьи по теме
- [Профилактический поиск угроз](advanced-hunting-overview.md)
- [Сведения о языке запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
