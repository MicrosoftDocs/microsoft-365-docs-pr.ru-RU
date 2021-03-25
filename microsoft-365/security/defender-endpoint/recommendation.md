---
title: Рекомендации методов и свойств
description: Извлекает последние последние оповещений.
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6ab4d4e1acab0e4b837195f64c369057d7ceb417
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198237"
---
# <a name="recommendation-resource-type"></a>Тип ресурса рекомендации

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Методы
Метод |Возвращаемый тип |Описание
:---|:---|:---
[Список всех рекомендаций](get-all-recommendations.md) | Коллекция рекомендаций | Извлекает список всех рекомендаций по безопасности, влияющих на организацию
[Получить рекомендации по ID](get-recommendation-by-id.md) | Рекомендация | Извлечение рекомендации по безопасности по его ID
[Получить программное обеспечение рекомендации](get-recommendation-software.md)| [Программное обеспечение](software.md) | Извлечение рекомендации по безопасности, связанной с определенным программным обеспечением
[Получить устройства рекомендации](get-recommendation-machines.md)|Коллекция MachineRef | Извлекает список устройств, связанных с рекомендацией по безопасности
[Получить уязвимости рекомендации](get-recommendation-vulnerabilities.md) | [Коллекция уязвимостей](vulnerability.md) | Извлекает список уязвимостей, связанных с рекомендацией по безопасности


## <a name="properties"></a>Свойства
Свойство |   Тип   |   Описание
:---|:---|:---
id | Строка | ID рекомендации
productName | String | Связанное имя программного обеспечения  
recommendationName | Строка | Имя рекомендации
Недостатки | Длинное целое | Количество обнаруженных уязвимостей
Поставщик | Строка | Имя связанного поставщика
recommendedVersion | Строка | Рекомендуемая версия
recommendationCategory | Строка | Категория рекомендации. Возможные значения: "Учетные записи", "Приложение", "Сеть", "ОС", "SecurityStack"
subCategory | Строка | Под-категория Рекомендации
severityScore | Двойное с плавающей точкой | Потенциальное влияние конфигурации на оценку microsoft Secure Для устройств организации (1-10)
publicExploit | Boolean | Общедоступный эксплойт доступен 
activeAlert | Boolean | С этой рекомендацией связано активное оповещение
associatedThreats | Коллекция String | Отчет аналитики угроз связан с этой рекомендацией
remediationType | Строка | Тип исправлений. Возможные значения: "ConfigurationChange", "Update", "Upgrade", "Uninstall"
Состояние | Перечисление | Состояние исключения рекомендации. Возможные значения: "Active" и "Exception"
configScoreImpact | Двойное с плавающей точкой | Влияние Microsoft Secure Score для устройств
exposureImpacte | Двойное с плавающей точкой | Влияние оценки экспозиции
totalMachineCount | Длинное целое | Количество установленных устройств
exposedMachinesCount | Длинное целое | Количество установленных устройств, подверженных уязвимостям
nonProductivityImpactedAssets | Длинное целое | Количество устройств, не затронутых  
relatedComponent | Строка |  Связанный компонент программного обеспечения
