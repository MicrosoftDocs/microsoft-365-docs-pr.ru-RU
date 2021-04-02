---
title: Таблицы данных в схеме расширенных охотничьих данных Microsoft 365 Defender
description: Ознакомьтесь со сведениями о таблицах в схеме расширенной охоты на угрозы, чтобы понять, для каких типов данных можно выполнять запросы на охоту на угрозы
keywords: передовая охота, охота на угрозы, поиск киберугроз, защита от угроз Майкрософт, Microsoft 365, mtp, m365, поиск, запрос, телеметрия, ссылка схемы, кусто, таблица, данные
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 48e72bf2384361315c1ed94e83f3e61f667da714
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499709"
---
# <a name="understand-the-advanced-hunting-schema"></a>Общие сведения о схеме расширенной охоты на угрозы

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Передовая схема охоты](advanced-hunting-overview.md) состоит из нескольких таблиц, которые предоставляют информацию о событиях или сведения об устройствах, оповещениях, удостоверениях и других типах сущности. Для эффективного построения запросов, охватывающих несколько таблиц, необходимо понимать, что такое таблицы и столбцы в схеме расширенной охоты на угрозы

## <a name="get-schema-information-in-the-security-center"></a>Получить сведения о схеме в центре безопасности
При построении запросов используйте встроенную ссылку на схему, чтобы быстро получить следующую информацию о каждой таблице в схеме:

- **Описание таблиц**— тип данных, содержащихся в таблице, и источник этих данных.
- **Столбцы**— все столбцы в таблице.
- **Типы действий**— возможные значения в `ActionType` столбце, представляющего типы событий, поддерживаемые таблицей. Эта информация предоставляется только для таблиц, содержащих сведения о событиях.
- **Пример запроса**— например, запросы, которые повеяют, как можно использовать таблицу.

### <a name="access-the-schema-reference"></a>Доступ к ссылке схемы
Чтобы быстро получить доступ к ссылке схемы, выберите действие **View reference** рядом с именем таблицы в представлении схемы. Вы также можете выбрать **ссылку схемы** для поиска таблицы.   

![Изображение, показывающая доступ к ссылке на схему на портале ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>Узнайте таблицы схем
В приведенной ниже ссылке перечислены все таблицы в схеме. Каждое название таблицы содержит ссылку на страницу, описывающую имена столбцов для этой таблицы. Имена таблиц и столбцов также перечислены в центре безопасности в рамках представления схемы на продвинутом экране охоты.

| Имя таблицы | Описание |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Оповещения от Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender for Identity, включая сведения о серьезности и категоризации угроз  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Действия, связанные с файлами в облачных приложениях и службах |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | События, связанные с учетными записями и объектами в Office 365 и другими облачными приложениями и службами |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Несколько типов событий, в том числе события, запускаемые такими элементами управления безопасностью, как антивирусная программа "Защитник Windows" и защита от эксплойтов |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Сведения о сертификатах подписанных файлов, полученных в ходе событий проверки сертификатов на конечных точках |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Создание файла, изменение и другие события файловой системы |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | События загрузки библиотек DLL |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Сведения о компьютере, в том числе данные об ОС |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Входы и другие события проверки подлинности на устройствах |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Сетевое подключение и связанные события |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Сетевые свойства устройств, включая физические адаптеры, IP и MAC-адреса, а также подключенные сети и домены |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Создание процессов и связанных с ними событий |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Создание и изменение записей реестра |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | События по оценке контроля угроз и уязвимостей, указывающие состояние различных конфигураций безопасности на устройствах |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | База знаний различных конфигураций безопасности, используемых системой контроля угроз и уязвимостей для оценки устройств; включает в себя сопоставления с различными стандартами и контрольными показателями  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Инвентаризация программного обеспечения, установленного на устройствах, включая сведения о версии и состояние конечной поддержки |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Уязвимости программного обеспечения, найденные на устройствах, и список доступных обновлений безопасности, которые будут рассматривать каждую уязвимость. |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | База знаний уязвимостей, о которых сообщалось в открытых источниках, включая информацию о том, является ли эксплойт общедоступным. |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Сведения о файлах, присоединенных к электронным письмам |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | События электронной почты Microsoft 365, включая доставку электронной почты и блокировку событий |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | События безопасности, которые происходят после доставки, после того, как Microsoft 365 доставила сообщения электронной почты в почтовый ящик получателя |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Сведения об URL-адресах в электронных письмах |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | События с участием локального контроллера домена под управлением Active Directory (AD). В этой таблице описывается ряд событий, связанных с удостоверением, и системных событий на контроллере домена. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Сведения об учетных записях из различных источников, включая Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | События проверки подлинности в службах Active Directory и Microsoft online |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Запросы для объектов Active Directory, таких как пользователи, группы, устройства и домены |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
