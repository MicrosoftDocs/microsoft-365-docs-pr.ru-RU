---
title: Обзор Information Protection в Windows
ms.reviewer: ''
description: Сведения о том, как работает защита информации в Windows для идентификации и защиты конфиденциальной информации
keywords: сведения, защита, dlp, данные, потери, предотвращение, защита
search.product: eADQiWindows 10XVcnh
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9d68f879fe8fd9379b286c106ed9229895f91b9a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841113"
---
# <a name="information-protection-in-windows-overview"></a>Обзор Information Protection в Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

Защита информации является неотъемлемой частью Microsoft 365 корпоративный, обеспечивая интеллектуальную защиту для обеспечения безопасности конфиденциальных данных, обеспечивая при этом производительность на рабочем месте.


>[!TIP]
> Ознакомьтесь с нашим сообщением в блоге о том, как Microsoft Defender для конечной точки интегрируется с Microsoft Information Protection для обнаружения, защиты и мониторинга конфиденциальных данных на Windows [устройствах.](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)

Defender for Endpoint применяет следующие методы обнаружения, классификации и защиты данных:

- **Обнаружение данных** . Определение конфиденциальных данных на Windows устройствах с риском
- **Классификация** данных — автоматически классифицировать данные на основе общих политик microsoft Information Protection (MIP), управляемых в центре Office 365 безопасности & соответствия требованиям. Автоматическая классификация позволяет защищать конфиденциальные данные, даже если конечный пользователь не классифицировал их вручную.


## <a name="data-discovery-and-data-classification"></a>Обнаружение данных и классификация данных

Defender for Endpoint автоматически обнаруживает файлы с метами конфиденциальности и файлы, содержащие типы конфиденциальной информации.

Метки конфиденциальности классифицируют и помогают защитить конфиденциальный контент.

Типы конфиденциальной информации в реализации Office 365 защиты от потери данных (DLP) подпадают под две категории:

- Значение, используемое по умолчанию
- Пользовательские

Типы конфиденциальной информации по умолчанию включают такие сведения, как номера банковских счетов, номера социального страхования или национальные ID. Дополнительные сведения см. [в дополнительных сведениях о том, как выглядит тип конфиденциальной информации.](/office365/securitycompliance/what-the-sensitive-information-types-look-for)

Настраиваемые типы — это те типы, которые вы определяете и предназначено для защиты конфиденциальной информации другого типа (например, номеров сотрудников или номеров проектов). Дополнительные сведения см. [введите настраиваемый тип конфиденциальной информации.](/office365/securitycompliance/create-a-custom-sensitive-information-type)

Когда файл создается или редактируется на устройстве Windows, Defender for Endpoint сканирует содержимое, чтобы оценить, содержится ли в нем конфиденциальную информацию.

Включив интеграцию Azure Information Protection, чтобы когда файл, содержащий конфиденциальные сведения, был обнаружен Защитником для конечной точки, хотя метки или типы информации, он автоматически передается в Azure Information Protection с устройства.

![Изображение страницы параметров с помощью Azure Information Protection](images/atp-settings-aip.png)

Отчетные сигналы можно просмотреть на панели данных Azure Information Protection — Data discovery.

## <a name="azure-information-protection---data-discovery-dashboard"></a>Azure Information Protection — панель мониторинга обнаружения данных

На этой панели мониторинга представлена сводная информация об обнаружении данных, обнаруженных как Защитником для конечной точки, так и Azure Information Protection. Данные из Defender для конечной точки отмечены типом расположения — конечной точкой.

![Изображение Azure Information Protection — обнаружение данных](images/azure-data-discovery.png)

Обратите внимание на столбец риск устройства справа, этот риск устройства выводится непосредственно из Defender для конечной точки, указав уровень риска устройства безопасности, на котором был обнаружен файл, на основе активных угроз безопасности, обнаруженных Defender для конечной точки.

Щелкните на устройстве, чтобы просмотреть список файлов, наблюдаемых на этом устройстве, с метами и типами сведений о конфиденциальности.

>[!NOTE]
>Дайте примерно 15-20 минут на обнаружение панели мониторинга информационной защиты Azure для отражения обнаруженных файлов.

## <a name="log-analytics"></a>Аналитика журналов

Обнаружение данных на основе Defender для конечной точки также доступно в [Azure Log Analytics,](/azure/log-analytics/log-analytics-overview)где можно выполнять сложные запросы по необработанных данных.

Дополнительные сведения об аналитике azure Information Protection см. в центре [отчетов для Azure Information Protection.](/azure/information-protection/reports-aip)

Откройте Azure Log Analytics на портале Azure и откройте строитель запросов (стандартный или классический).

Чтобы просмотреть данные Defender для конечных точек, выполните запрос, содержащий:

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

**Необходимые условия:**

- Клиенты должны иметь подписку на Azure Information Protection.
- Включение интеграции Azure information Protection в Центр безопасности в Microsoft Defender:
    - Перейдите **Параметры** в Центр безопасности в Microsoft Defender, нажмите кнопку **Расширенный** Параметры под **общим .**



