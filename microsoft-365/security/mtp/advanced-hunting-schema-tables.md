---
title: Таблицы данных в схеме advanced hunting в Microsoft 365 Defender
description: Ознакомьтесь со сведениями о таблицах в схеме расширенной охоты на угрозы, чтобы понять, для каких типов данных можно выполнять запросы на охоту на угрозы
keywords: расширенный поиск, охота на угрозы, поиск киберугроз, защита от угроз (Майкрософт), Microsoft 365, mtp, m365, поиск, запрос, телеметрия, справочник по схеме, kusto, таблица, данные
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
ms.technology: m365d
ms.openlocfilehash: b335ba90479c670d918226caa18f80ee5535f0a1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925056"
---
# <a name="understand-the-advanced-hunting-schema"></a>Общие сведения о схеме расширенной охоты на угрозы

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Схема [повышенной охоты](advanced-hunting-overview.md) состоит из нескольких таблиц, которые предоставляют сведения о событиях или сведения об устройствах, оповещениях, удостоверениях и других типах сущений. Для эффективного построения запросов, охватывающих несколько таблиц, необходимо понимать, что такое таблицы и столбцы в схеме расширенной охоты на угрозы

## <a name="get-schema-information-in-the-security-center"></a>Получить сведения о схеме в Центре безопасности
При построении запросов используйте встроенную ссылку на схему, чтобы быстро получить следующие сведения о каждой таблице в схеме:

- **Описание таблиц**— тип данных, содержащихся в таблице, и источник этих данных.
- **Столбцы**— все столбцы в таблице.
- **Типы действий**— возможные значения в столбце, представляющие типы событий, `ActionType` поддерживаемые таблицей. Эти сведения предоставляются только для таблиц, содержащих сведения о событиях.
- **Пример запроса**— примеры запросов с возможностью использования таблицы.

### <a name="access-the-schema-reference"></a>Доступ к справочнику по схеме
Чтобы быстро получить доступ к  ссылке на схему, выберите действие ссылки "Просмотр" рядом с именем таблицы в представлении схемы. Вы также можете выбрать **ссылку на схему** для поиска таблицы.   

![Изображение доступа к справке по схеме портала ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>Изучите таблицы схемы
В приведенной ниже ссылке перечислены все таблицы в схеме. Каждое название таблицы содержит ссылку на страницу, описывающую имена столбцов для этой таблицы. Имена таблиц и столбцов также перечислены в Центре безопасности как часть представления схемы на экране "Расширенный поиск".

| Имя таблицы | Описание |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Оповещения из Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для удостоверений, включая сведения о серьезности и категоризации угроз  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Действия, связанные с файлами, в облачных приложениях и службах |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | События, включающие учетные записи и объекты в Office 365 и других облачных приложениях и службах |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Несколько типов событий, в том числе события, запускаемые такими элементами управления безопасностью, как антивирусная программа "Защитник Windows" и защита от эксплойтов |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Сведения о сертификате подписанных файлов, полученных из событий проверки сертификатов на конечных точках |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Создание файла, изменение и другие события файловой системы |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | События загрузки библиотек DLL |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Сведения о компьютере, в том числе данные об ОС |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Входы и другие события проверки подлинности на устройствах |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Сетевое подключение и связанные события |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Свойства сети устройств, включая физические адаптеры, IP- и MAC-адреса, а также подключенные сети и домены |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Создание процессов и связанных с ними событий |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Создание и изменение записей реестра |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | События по оценке контроля угроз и уязвимостей, указывающие состояние различных конфигураций безопасности на устройствах |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | База знаний различных конфигураций безопасности, используемых системой контроля угроз и уязвимостей для оценки устройств; включает в себя сопоставления с различными стандартами и контрольными показателями  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Инвентаризация программного обеспечения на устройствах и все известные уязвимости в этих программных продуктах |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | База знаний уязвимостей, о которых сообщалось в открытых источниках, включая информацию о том, является ли эксплойт общедоступным. |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Сведения о файлах, вложенных в сообщения электронной почты |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | События электронной почты Microsoft 365, включая события доставки и блокирования электронной почты |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | События безопасности, которые происходят после доставки, после того как Microsoft 365 доставляет сообщения электронной почты в почтовый ящик получателя |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Сведения об URL-адресах в электронных письмах |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | События с использованием локального контроллера домена с Active Directory (AD). В этой таблице описывается ряд событий, связанных с удостоверением, и системных событий на контроллере домена. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Сведения об учетной записи из различных источников, включая Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | События проверки подлинности в Active Directory и веб-службах Майкрософт |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Запросы объектов Active Directory, таких как пользователи, группы, устройства и домены |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
