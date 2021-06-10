---
title: Исследование проблем работоспособности агента
description: Узнайте о значениях, возвращаемых при запуске команды здоровья mdatp
keywords: mdatp health, command, health, status, command, onboarding status
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
ms.openlocfilehash: acc75a931cb14a7aab729c09a7b835fb9f26d1d1
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281304"
---
# <a name="investigate-agent-health-issues"></a>Исследование проблем работоспособности агента

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


В следующей таблице приводится информация о значениях, возвращаемых при запуске `mdatp health` команды, и их соответствующих описаниях.

| Значение | Описание |
|-|-|
| automatic_definition_update_enabled | True, если автоматические обновления определения антивируса включены, ложные в противном случае. |
|  cloud_automatic_sample_submission_consent | Текущий уровень отправки образца. Любое из следующих значений:     <br><br>  - **Нет.** Подозрительные образцы не отправлены в Корпорацию Майкрософт.  <br> <br>     - **Сейф:** Автоматически подано только подозрительные образцы, которые не содержат личных идентифицируемых сведений (PII). Это значение по умолчанию для этого параметра.    <br> <br>   - **Все.** Все подозрительные образцы отправлены в Корпорацию Майкрософт.   |
| cloud_diagnostic_enabled | True, если включен необязательный диагностический сбор данных, ложное в противном случае. Дополнительные сведения, относящиеся к Defender для конечной точки и другим продуктам и службам, таким как антивирусная программа в Microsoft Defender и Windows 10, см. в [заявлении Microsoft Privacy.](https://go.microsoft.com/fwlink/?linkid=827576) |
| cloud_enabled | True, если включена облачная защита, ложное в противном случае. |
| conflicting_applications | Список приложений, которые, возможно, конфликтуют с Microsoft Defender для конечной точки. Этот список включает, но не ограничивается, другими продуктами безопасности и другими приложениями, которые, как известно, вызывают проблемы с совместимостью. |
| definitions_status | Состояние определений антивирусов. |
| definitions_updated | Дата и время последнего обновления определения антивируса. |
| definitions_updated_minutes_ago | Количество минут с момента последнего обновления определения антивируса. |
| definitions_version | Версия определения антивируса. |
| edr_client_version | Версия EDR клиента, запущенного на устройстве. |
| edr_configuration_version | EDR конфигурации. |
| edr_device_tags | Список тегов, связанных с устройством. |
| edr_group_ids | Групповой ID, с который связано устройство. |
| edr_machine_id | Идентификатор устройства, используемый в Центр безопасности в Microsoft Defender. |
| engine_version | Версия антивирусного двигателя. |
| здоровый | True, если продукт является здоровым, ложным в противном случае. |
| лицензированный | True, если устройство находится на борту для клиента, ложное в противном случае. |
| log_level | Текущий уровень журнала для продукта. |
| machine_guid | Уникальный идентификатор компьютера, используемый антивирусным компонентом. |
| network_protection_status                 | Состояние компонента защиты сети (только macOS). Любое из следующих значений:       <br> <br>- **Ъ** - Начинается защита сети  <br> <br>     - **failed_to_start** . Не удалось начать защиту сети из-за ошибки   <br> <br>    - **Ъ** - Защита сети в настоящее время запущена на устройстве     <br> <br>  - **перезапуск** . Защита сети в настоящее время перезапущена   <br> <br>    - **остановка** — защита сети останавливается     <br> <br>  - **остановлено** . Защита сети не запущена |
| org_id | Организация, в которую вошел устройство. Если устройство еще не установлено в какой-либо организации, этот отпечаток недоступен. Дополнительные сведения о onboarding см. в таблице [Onboard to Microsoft Defender for Endpoint.](onboarding.md) |
| passive_mode_enabled | True, если антивирусный компонент настроен на запуск в пассивном режиме, ложный в противном случае. |
| product_expiration | Дата и время, когда текущая версия продукта достигнет конца поддержки. |
| real_time_protection_available | True, если компонент защиты в режиме реального времени является здоровым, ложным в противном случае. |
| real_time_protection_enabled | True, если включена антивирусная защита в режиме реального времени, ложное в противном случае. |
| real_time_protection_subsystem | Подсистема, используемая для защиты в режиме реального времени. Если защита в режиме реального времени работает не так, как ожидалось, эти отпечатки недоступны. |
| release_ring | Кольцо выпуска. Дополнительные сведения см. в [см. в ленте "Кольца развертывания".](deployment-rings.md) |