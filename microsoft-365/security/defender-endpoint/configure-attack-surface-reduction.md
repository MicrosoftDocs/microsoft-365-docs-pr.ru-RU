---
title: Настройка уменьшения поверхности атаки
description: Чтобы настроить сокращение поверхности атаки, используйте Microsoft Intune, Microsoft Endpoint Configuration Manager, команды PowerShell и групповую политику.
keywords: asr, уменьшение поверхности атаки, защитник Windows, защитник Microsoft, антивирус, av
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166171"
---
# <a name="configure-attack-surface-reduction"></a>Настройка уменьшения поверхности атаки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Вы можете настроить уменьшение поверхности атаки с помощью множества средств, включая:

* Microsoft Intune
* Microsoft Endpoint Configuration Manager
* Групповая политика
* Командлеты PowerShell

Статья | Описание
-|-
[Включить аппаратную изоляцию для Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | Подготовка и установка Application Guard, включая требования к оборудованию и программному обеспечению
[Включить управление приложениями](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|Управление приложениями, запускаемой пользователями, и защита процессов режима ядра
[Защита от эксплойтов](./enable-exploit-protection.md)|Автоматическое применение методов смягчения эксплойтов как в операционных системах, так и в отдельных приложениях
[Защита сети](./enable-network-protection.md)|Как запретить пользователям использовать приложения для доступа к опасным доменам
[Управляемый доступ к папкам](./enable-controlled-folders.md)|Защита ценных данных от вредоносных приложений
[Сокращение направлений атак](./enable-attack-surface-reduction.md)|Предотвращение действий и приложений, которые обычно используются при поиске вредоносных программ для эксплойтов
[Брандмауэр сети](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|Защита устройств и данных в сети

