---
title: Расширенный справочник схемы охоты
description: Сведения о таблицах в продвинутой схеме охоты, чтобы понять данные, на которые можно запускать запросы на поиск угроз.
keywords: продвинутая охота, охота на угрозы, поиск киберугроз, mdatp, защита microsoft atp, защитник Майкрософт для конечной точки, поиск wdatp, запрос, телеметрия, ссылка схемы, кусто, таблица, данные
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: fcc7d96f51121824550128e89186074e1ebc3ce0
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228883"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a>Понимание схемы расширенных схем охоты в Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[Передовая схема охоты](advanced-hunting-overview.md) состоит из нескольких таблиц, которые предоставляют информацию о событиях или сведения о устройствах и других сущностям. Для эффективного построения запросов, охватывающих несколько таблиц, необходимо понимать, что такое таблицы и столбцы в схеме расширенной охоты на угрозы

## <a name="get-schema-information-in-the-security-center"></a>Получить сведения о схеме в центре безопасности
При построении запросов используйте встроенную ссылку на схему, чтобы быстро получить следующую информацию о каждой таблице в схеме:

- **Описание таблиц**— тип данных, содержащихся в таблице, и источник этих данных.
- **Столбцы**— все столбцы в таблице.
- **Типы действий**— возможные значения в `ActionType` столбце, представляющего типы событий, поддерживаемые таблицей. Это предоставляется только для таблиц, содержащих сведения о событиях.
- **Пример запроса**— например, запросы, которые повеяют, как можно использовать таблицу.

### <a name="access-the-schema-reference"></a>Доступ к ссылке схемы
Чтобы быстро получить доступ к ссылке схемы, выберите действие **View reference** рядом с именем таблицы в представлении схемы. Вы также можете выбрать **ссылку схемы** для поиска таблицы.

![Изображение, показывающая доступ к ссылке на схему на портале](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a>Узнайте таблицы схем

В следующей ссылке перечислены все таблицы в продвинутой схеме охоты. Каждое название таблицы содержит ссылку на страницу, описывающую имена столбцов для этой таблицы.

Имена таблиц и столбцов также перечислены в Центр безопасности в Microsoft Defender, в представлении схемы на продвинутом экране охоты.

| Имя таблицы | Описание |
|------------|-------------|
| **[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)** | Оповещения на Центр безопасности в Microsoft Defender |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Сведения об устройстве, в том числе сведения об ОС |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Сетевые свойства устройств, включая адаптеры, IP и MAC-адреса, а также подключенные сети и домены |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Создание процессов и связанных с ними событий |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Сетевое подключение и связанные события |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Создание файла, изменение и другие события файловой системы |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Создание и изменение записей реестра |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Входы и другие события проверки подлинности |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | События загрузки библиотек DLL |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Несколько типов событий, включая события, инициированные средствами управления безопасностью, такие как антивирусная программа в Microsoft Defender и защита от эксплойтов |
| **[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)** | Сведения о сертификатах подписанных файлов, полученных в ходе событий проверки сертификатов на конечных точках |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Инвентаризация программного обеспечения, установленного на устройствах, включая сведения о версии и состояние конечной поддержки |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Уязвимости программного обеспечения, найденные на устройствах, и список доступных обновлений безопасности, которые будут рассматривать каждую уязвимость. |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | База знаний уязвимостей, о которых сообщалось в открытых источниках, включая информацию о том, является ли эксплойт общедоступным. |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | События по оценке контроля угроз и уязвимостей, указывающие состояние различных конфигураций безопасности на устройствах |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | База знаний различных конфигураций безопасности, используемых системой контроля угроз и уязвимостей для оценки устройств; включает в себя сопоставления с различными стандартами и контрольными показателями |

>[!TIP]
>Используйте [расширенный](/microsoft-365/security/defender/advanced-hunting-overview) поиск в Microsoft 365 Defender для охоты на угрозы с помощью данных defender for Endpoint, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для identity. [Включение Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable)<br><br>
Узнайте больше о том, как переместить расширенные процессы охоты из Microsoft Defender для конечной точки в Microsoft 365 Defender в миграции расширенных запросов охоты из [Microsoft Defender для конечной точки](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).

## <a name="related-topics"></a>Похожие темы
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
- [Обзор настраиваемых обнаружений](overview-custom-detections.md)
- [Изменения схемы расширенных данных охоты](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
