---
title: Управление индикаторами
ms.reviewer: ''
description: Управление индикаторами для хеш-файлов, IP-адресов, URL-адресов или доменов, определяющих обнаружение, предотвращение и исключение сущностями.
keywords: импорт, индикатор, список, мок, csv, управление, разрешено, заблокировано, блок, чистый, вредоносный, файл hash, IP-адрес, URL-адреса, домен
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185949"
---
# <a name="manage-indicators"></a>Управление индикаторами

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. В области навигации выберите **Параметры**  >  **Индикаторы**.

2. Выберите вкладку типа сущности, которая будет управляться.  

3. Обновите сведения о индикаторе и нажмите кнопку **Сохранить** или нажмите кнопку **Удалить,** если вы хотите удалить объект из списка.

## <a name="import-a-list-of-iocs"></a>Импорт списка IoCs

Вы также можете загрузить CSV-файл, который определяет атрибуты индикаторов, действия, которые необходимо принять, и другие сведения.

Скачайте пример CSV, чтобы узнать поддерживаемые атрибуты столбца.

1. В области навигации выберите **Параметры**  >  **Индикаторы**.

2. Выберите вкладку типа сущности, для нее необходимо импортировать индикаторы.

3. Выберите **файл Import**  >  **Choose**. 

4. Нажмите кнопку **Импорт**. Сделайте это для всех файлов, которые необходимо импортировать. 

5. Нажмите кнопку **Готово**.

В следующей таблице показаны поддерживаемые параметры.

Параметр | Тип    |   Описание
:---|:---|:---
indicatorType | Перечисление | Тип индикатора. Возможные значения: "FileSha1", "FileSha256", "IpAddress", "DomainName" и "URL". **Required**
indicatorValue | Строка | Удостоверение сущности [индикатора.](ti-indicator.md) **Required**
action | Перечисление | Действие, которое будет принято, если индикатор будет обнаружен в организации. Возможные значения: "Alert", "AlertAndBlock" и "Allowed". **Required**
title | Строка | Название оповещений индикатора. **Required**
description | Строка |  Описание индикатора. **Required**
expirationTime | DateTimeOffset | Срок действия индикатора в следующем формате YYYY-MM-DDTHH:MM:SS.0Z. **Необязательное**
severity | Перечисление | Серьезность индикатора. Возможные значения: "Информационная", "Низкая", "Средняя" и "Высокая". **Необязательное**
recommendedActions | Строка | Предупреждение индикатора TI рекомендуемые действия. **Необязательное**
rbacGroupNames | Строка | Разделенный запятой список имен групп RBAC, к который будет применен индикатор. **Необязательное**
category | String | Категория оповещения. Примеры: выполнение и доступ к учетным данным. **Необязательное**
mitretechniques| Строка | Методы MITRE code/id (разделенная запятая). Дополнительные сведения см. в [теме Корпоративная тактика.](https://attack.mitre.org/tactics/enterprise/) **Необязательный** Рекомендуется добавлять значение в категории при приеме MITRE.

Дополнительные сведения см. в [рубрике Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)


## <a name="see-also"></a>См. также
- [Создание индикаторов](manage-indicators.md)
- [Создание индикаторов для файлов](indicator-file.md)
- [Создание индикаторов для IPs и URL-адресов/доменов](indicator-ip-domain.md)
- [Создание индикаторов на основе сертификатов](indicator-certificates.md)
