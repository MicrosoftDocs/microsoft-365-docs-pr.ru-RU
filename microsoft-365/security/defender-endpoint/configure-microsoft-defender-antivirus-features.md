---
title: Настройка функций антивирусной программы в Microsoft Defender
description: Вы можете настроить антивирусная программа в Microsoft Defender с помощью Intune, Microsoft Endpoint Configuration Manager, групповой политики и PowerShell.
keywords: антивирусная программа в Microsoft Defender, антивирусное программное обеспечение, безопасность, защитник, настройка, конфигурация, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, управление мобильными устройствами, GP, групповой политики, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275112"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Настройка функций антивирусной программы в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Вы можете настроить антивирусная программа в Microsoft Defender с помощью нескольких инструментов, в том числе:

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- Групповая политика
- Командлеты PowerShell
- Инструментарий управления Windows (WMI)

Можно настроить следующие широкие категории функций:

- Облачная защита
- Защита в режиме реального времени, включая защиту на основе поведенческих, увристических и машинных знаний
- Взаимодействие конечных пользователей с клиентом на отдельных конечных точках

В следующих статьях описывается выполнение ключевых задач при настройке антивирусная программа в Microsoft Defender. Каждая статья содержит инструкции для применимого средства конфигурации (или инструментов).

|Статья  |Описание  |
|---------|---------|
|[Использование облачной антивирусная программа в Microsoft Defender Майкрософт](cloud-protection-microsoft-defender-antivirus.md)     | Использование облачной защиты для быстрого и надежного обнаружения антивирусов.        |
|[Настройка поведенческой, эвристической защиты и защиты в режиме реального времени](configure-protection-features-microsoft-defender-antivirus.md)     |Включить антивирусную защиту на основе поведения, а также защиту от вирусов в режиме реального времени.         |
|[Настройка взаимодействия конечных пользователей с антивирусная программа в Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md) | Настройте, как конечные пользователи в организации взаимодействуют с антивирусная программа в Microsoft Defender, какие уведомления они видят и могут ли они переопределять параметры. |

> [!TIP]
> Вы также можете просмотреть раздел [Справочные темы](configuration-management-reference-microsoft-defender-antivirus.md) для управления и инструментов конфигурации для обзора каждого средства и ссылок на дополнительную помощь.