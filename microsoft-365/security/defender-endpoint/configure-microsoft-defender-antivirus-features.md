---
title: Настройка функций антивируса Microsoft Defender
description: Можно настроить антивирусные функции Microsoft Defender с помощью Intune, Microsoft Endpoint Configuration Manager, Group Policy и PowerShell.
keywords: Антивирус Microsoft Defender, антивирус, защита, защита, настройка, конфигурация, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, управление мобильными устройствами, GP, групповой политики, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3dcf0ab24541a8837fbab91049fed0157b7f1fc9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690819"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Настройка функций антивируса Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Антивирус Microsoft Defender можно настроить с помощью ряда средств, в том числе:

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- Групповая политика
- Командлеты PowerShell
- Инструментарий управления Windows (WMI)

Можно настроить следующие широкие категории функций:

- Защита с облачным доставкой
- Защита в режиме реального времени, включая защиту на основе поведенческих, увристических и машинных знаний
- Взаимодействие конечных пользователей с клиентом на отдельных конечных точках

В следующих статьях описано, как выполнять ключевые задачи при настройке антивируса Microsoft Defender. Каждая статья содержит инструкции для применимого средства конфигурации (или инструментов).

|Статья  |Описание  |
|---------|---------|
|[Использование антивирусной защиты Microsoft Defender с облачным обеспечением](cloud-protection-microsoft-defender-antivirus.md)     | Использование облачной защиты для быстрого и надежного обнаружения антивирусов.        |
|[Настройка поведенческой, севристической и защиты в режиме реального времени](configure-protection-features-microsoft-defender-antivirus.md)     |Включить антивирусную защиту на основе поведения, а также защиту от вирусов в режиме реального времени.         |
|[Настройка взаимодействия между конечными пользователями с антивирусом Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md) | Настройте, как конечные пользователи в организации взаимодействуют с антивирусом Microsoft Defender, какие уведомления они видят и могут ли они переопределять параметры. |

> [!TIP]
> Вы также можете просмотреть раздел [Справочные темы](configuration-management-reference-microsoft-defender-antivirus.md) для управления и инструментов конфигурации для обзора каждого средства и ссылок на дополнительную помощь.