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
ms.openlocfilehash: 032368e35cdfc991df4c01643e49cee538549f39
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899367"
---
# <a name="understand-the-advanced-hunting-schema"></a>Общие сведения о схеме расширенной охоты на угрозы

**Область применения:**
- Защита от угроз (Майкрософт)

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Схема [расширенной охоты на угрозы](advanced-hunting-overview.md) состоит из нескольких таблиц, которые содержат сведения о событиях или информацию о компьютерах и объектах. Для эффективного построения запросов, охватывающих несколько таблиц, необходимо понимать, что такое таблицы и столбцы в схеме расширенной охоты на угрозы

## <a name="schema-tables"></a>Таблицы схем

В приведенной ниже ссылке перечислены все таблицы в схеме. Каждое название таблицы содержит ссылку на страницу, описывающую имена столбцов для этой таблицы. Имена таблиц и столбцов также указаны в центре безопасности в составе схемы на экране расширенной охоты на угрозы

| Имя таблицы | Описание |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Оповещения от Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security и Azure ATP, включая сведения о степени серьезности и классификацию угроз  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Действия, связанные с файлами, в облачных приложениях и службах |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Несколько типов событий, в том числе события, запускаемые такими элементами управления безопасностью, как антивирусная программа "Защитник Windows" и защита от эксплойтов |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Сведения о сертификате подписанных файлов, полученные из событий проверки сертификатов в конечных точках |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Создание файла, изменение и другие события файловой системы |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | События загрузки библиотек DLL |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Сведения о компьютере, в том числе данные об ОС |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Входы и другие события проверки подлинности |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Сетевое подключение и связанные события |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Свойства сети компьютеров, включая адаптеры, IP-и MAC-адреса, а также подключенные сети и домены. |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Создание процессов и связанных с ними событий |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Создание и изменение записей реестра |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | События по оценке контроля угроз и уязвимостей, указывающие состояние различных конфигураций безопасности на устройствах |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | База знаний различных конфигураций безопасности, используемых системой контроля угроз и уязвимостей для оценки устройств; включает в себя сопоставления с различными стандартами и контрольными показателями  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Перечень программного обеспечения на устройствах, а также всех известных уязвимостей в этих программных продуктах |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | База знаний уязвимостей, о которых сообщалось в открытых источниках, включая информацию о том, является ли эксплойт общедоступным. |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Сведения о файлах, вложенных в сообщения электронной почты |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | События электронной почты Microsoft 365, в том числе события доставки и блокировки электронной почты |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | События безопасности, происходящие после доставки, после того как Microsoft 365 доставляет сообщения в почтовый ящик получателя. |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Сведения об URL-адресах в сообщениях электронной почты |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Сведения об учетных записях из различных источников, в том числе Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | События проверки подлинности, регистрируемые Active Directory и другими службами Microsoft Online |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Действия запросов, выполняемые для объектов Active Directory, таких как пользователи, группы, устройства и домены |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
