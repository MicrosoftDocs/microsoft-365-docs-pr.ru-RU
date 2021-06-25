---
title: Функции предварительного просмотра в Microsoft 365 Defender
description: Сведения о новых функциях безопасности Microsoft 365
keywords: предварительная версия, новое, безопасность m365, безопасность, 365, возможности
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b852071c3fbfe12aac62e1d309fa130a4cd81e9c
ms.sourcegitcommit: b42dd3e706ebf9638cd893b35f75eaa56dd8fd7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2021
ms.locfileid: "53125402"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender функции предварительного просмотра

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Предварительные версии предоставляются без соглашения об уровне обслуживания и не рекомендуется для рабочих нагрузок. Некоторые функции могут не поддерживаться или иметь ограниченные возможности.

**Область применения:**
- Microsoft 365 Defender

Служба Microsoft 365 Defender постоянно обновляется, включая в нее новые возможности и возможности.

Узнайте о новых функциях в Microsoft 365 Defender предварительного просмотра и одними из первых опробуйте предстоящие функции, включив функцию предварительного просмотра.

Дополнительные сведения о новых возможностях, которые обычно доступны, см. в [Microsoft 365 Defender.](whats-new.md)

## <a name="required-permissions"></a>Обязательные разрешения

Учетные записи, задав следующие роли Azure Active Directory (Azure AD), могут включить функции Microsoft 365 Defender предварительного просмотра:

- Глобальный администратор
- Администратор безопасности
- Оператор безопасности

## <a name="turn-on-preview-features"></a>Включение предварительных функций

У вас будет доступ к предстоящим функциям, на которые можно предоставить обратную связь, чтобы улучшить общее впечатление до того, как функции будут доступны.

Включите параметр предварительной версии, чтобы быть в числе тех, кто первым попробует новые функции.

1. В области навигации выберите **Параметры**.
2. Выберите **Microsoft 365 Defender**.
3. Выберите **Предварительные функции** > **Включить предварительные функции**. 
4. Нажмите **Сохранить**.

Вы узнаете, что предварительные функции включены, когда увидите установленный флажок **Включить предварительные функции**. 

## <a name="preview-features"></a>Предварительные функции

В настоящий момент в предварительной версии доступны следующие функции и улучшения.

- **[Просмотр отчетов по тегам](threat-analytics.md#view-reports-per-threat-tags)** угроз . Теги угроз помогают сосредоточиться на определенных категориях угроз и просмотреть наиболее релевантные отчеты.
- **[Потоковый API](../defender-endpoint/raw-data-export.md)** Microsoft 365 Defender поддерживает потоковую трансляцию всех событий, доступных с помощью Advanced Hunting, в концентраторы событий и/или учетную запись хранилища Azure.
- **[Microsoft 365 Defender API](api-overview.md)** — API верхнего уровня Microsoft 365 Defender позволяют автоматизировать рабочий процесс на основе общих таблиц инцидента и расширенных таблиц охоты. 
- **[Примите меры в продвинутой охоте](advanced-hunting-take-action.md)** . Быстро сдержать угрозы или решить скомпрометированную активов, которые вы найдете в [продвинутой охоте](advanced-hunting-overview.md).
- **[Ссылка на схему на](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** портале — сведения о таблицах расширенных схем охоты непосредственно в центре безопасности. Помимо описаний таблиц и столбцов, эта ссылка включает поддерживаемые типы событий `ActionType` (значения) и примеры запросов.
- **[Функция DeviceFromIP()](advanced-hunting-devicefromip-function.md)** — получить сведения о том, какие устройства были назначены определенному IP-адресу или адресам в определенном диапазоне времени.
