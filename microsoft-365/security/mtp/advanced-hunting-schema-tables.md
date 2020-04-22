---
title: Таблицы данных в схеме расширенной охоты на угрозы в службе защиты от угроз (Майкрософт)
description: Ознакомьтесь со сведениями о таблицах в схеме расширенной охоты на угрозы, чтобы понять, для каких типов данных можно выполнять запросы на охоту на угрозы
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схеме, Кусто, таблица, данные
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
ms.openlocfilehash: 93da55287c3b7d7498a9c25f4deeb2615da81675
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633499"
---
# <a name="understand-the-advanced-hunting-schema"></a>Общие сведения о схеме расширенной охоты на угрозы

**Область применения:**
- Защита от угроз (Майкрософт)



Схема [расширенной охоты на угрозы](advanced-hunting-overview.md) состоит из нескольких таблиц, которые содержат сведения о событиях или информацию о компьютерах и объектах. Для эффективного построения запросов, охватывающих несколько таблиц, необходимо понимать, что такое таблицы и столбцы в схеме расширенной охоты на угрозы

## <a name="schema-tables"></a>Таблицы схем

В приведенной ниже ссылке перечислены все таблицы в схеме. Каждое название таблицы содержит ссылку на страницу, описывающую имена столбцов для этой таблицы. Имена таблиц и столбцов также указаны в центре безопасности в составе схемы на экране расширенной охоты на угрозы

| Имя таблицы | Описание |
|------------|-------------|
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Оповещения от Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security и Azure ATP, включая сведения о степени серьезности и классификацию угроз  |
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями |
| **[AccountInfo](advanced-hunting-accountinfo-table.md)** | Сведения об учетных записях из различных источников, в том числе Azure Active Directory |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | События электронной почты Microsoft 365, в том числе события доставки и блокировки электронной почты |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Сведения о файлах, вложенных в сообщения электронной почты |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Сведения об URL-адресах в сообщениях электронной почты Microsoft 365 |
| **[девицеинфо](advanced-hunting-deviceinfo-table.md)** | Сведения о компьютере, в том числе данные об ОС |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Свойства сети компьютеров, включая адаптеры, IP-и MAC-адреса, а также подключенные сети и домены. |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Создание процессов и связанных с ними событий |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Сетевое подключение и связанные события |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Создание файла, изменение и другие события файловой системы |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Создание и изменение записей реестра |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Входы и другие события проверки подлинности |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | События загрузки библиотек DLL |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Несколько типов событий, в том числе события, запускаемые такими элементами управления безопасностью, как антивирусная программа "Защитник Windows" и защита от эксплойтов |
| **[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)** | Сведения о сертификате подписанных файлов, полученные из событий проверки сертификатов в конечных точках |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | Перечень программного обеспечения на устройствах, а также всех известных уязвимостей в этих программных продуктах |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | База знаний уязвимостей, о которых сообщалось в открытых источниках, включая информацию о том, является ли эксплойт общедоступным. |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | События по оценке контроля угроз и уязвимостей, указывающие состояние различных конфигураций безопасности на устройствах |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | База знаний различных конфигураций безопасности, используемых системой контроля угроз и уязвимостей для оценки устройств; включает в себя сопоставления с различными стандартами и контрольными показателями  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Действия, связанные с файлами, в облачных приложениях и службах |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | События проверки подлинности, регистрируемые Active Directory и другими службами Microsoft Online |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Действия запросов, выполняемые для объектов Active Directory, таких как пользователи, группы, устройства и домены |


## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
