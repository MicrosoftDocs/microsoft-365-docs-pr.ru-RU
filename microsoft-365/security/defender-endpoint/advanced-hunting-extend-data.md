---
title: Расширение расширенного охвата охоты с помощью правильных параметров
description: Проверьте параметры аудита на устройствах Windows и другие параметры, чтобы убедиться в том, что вы получаете самые исчерпывающие данные в ходе предварительной охоты
keywords: advanced hunting, incident, pivot, entity, audit settings, user account management, security group management, threat hunting, cyber threat hunting, search, query, telemetry, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Защитник Windows, Защитник Windows ATP, Защитник Windows Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: 60e8710415e328d06fac4c02e428094e5e4bcc92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075501"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Расширение расширенного охвата охоты с помощью правильных параметров

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[Расширенный поиск](advanced-hunting-overview.md) зависит от данных, исходя из всей организации. Чтобы получить наиболее исчерпывающие данные, убедитесь, что у вас есть правильные параметры в соответствующих источниках данных.

## <a name="advanced-security-auditing-on-windows-devices"></a>Расширенный аудит безопасности на устройствах Windows

Включите эти расширенные параметры аудита, чтобы получить данные о действиях на устройствах, включая локальное управление учетной записью, локальное управление группой безопасности и создание службы.

Data | Описание | Таблица схемы | Способ настройки
-|-|-|-
Управление учетными записями | События, запечатленные в качестве различных значений, указывающих на локальное создание учетной записи, удаление и другие действия, связанные `ActionType` с учетной записью | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Развертывание усовершенствованой политики аудита безопасности: [управление учетной записью пользователей аудита](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Дополнительные политики аудита безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Управление группой безопасности | События, запечатленные в качестве различных значений, указывающих на создание локальной группы безопасности и другие локальные действия `ActionType` по управлению группой | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Развертывание усовершенствованой политики аудита безопасности: [управление группой аудита безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Дополнительные политики аудита безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Установка службы | События, захваченные со `ActionType` значением, указывающие на то, что `ServiceInstalled` была создана служба | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Развертывание усовершенствованой политики аудита безопасности: [расширение системы безопасности аудита](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Дополнительные политики аудита безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)

## <a name="related-topics"></a>Статьи по теме

- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Сведения о схеме](advanced-hunting-schema-reference.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
- [Обзор настраиваемых обнаружений](overview-custom-detections.md)
