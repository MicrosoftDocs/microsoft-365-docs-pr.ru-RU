---
title: Настройка возможностей сокращения направлений атак
description: Для настройки уменьшения поверхности атаки используйте Microsoft Intune, Microsoft Endpoint Configuration Manager, powerShell и групповой политики.
keywords: asr, уменьшение поверхности атаки, защитник Windows, защитник Microsoft, антивирус, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984452"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>Настройка возможностей сокращения направлений атак

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint включает несколько возможностей уменьшения поверхности атаки. Дополнительные сведения см. в обзоре возможностей уменьшения [поверхности атаки.](overview-attack-surface-reduction.md) Чтобы настроить уменьшение поверхности атаки в среде, выполните следующие действия:

1. [Включить аппаратную изоляцию для Microsoft Edge.](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)

2. Включить управление приложениями.

   1. Просмотрите базовые политики в Windows. См. [пример базовых политик](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).
   2. См. [руководство по Защитник Windows управления приложениями.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)
   3. Обратитесь [к политикам Защитник Windows управления приложениями (WDAC).](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)

3. [Включить управляемый доступ к папке](enable-controlled-folders.md).

4. [Включаем защиту сети.](enable-network-protection.md)

5. [Включить защиту эксплойтов.](enable-exploit-protection.md)

6. [Настройка правил уменьшения поверхности атаки.](enable-attack-surface-reduction.md)

7. Настройка сетевого брандмауэра.

   1. Получите обзор [брандмауэра Защитник Windows с расширенным обеспечением безопасности.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
   2. Используйте руководство Защитник Windows брандмауэра, чтобы решить, как вы хотите создать политики брандмауэра. [](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide)
   3. Используйте руководство [Защитник Windows](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) брандмауэра для настройки брандмауэра организации с расширенным обеспечением безопасности.

> [!TIP]
> В большинстве случаев при настройке возможностей уменьшения поверхности атаки можно выбрать один из нескольких методов:

> - Microsoft Endpoint Manager (которая теперь включает Microsoft Intune и Microsoft Endpoint Configuration Manager)
> - Групповая политика
> - Командлеты PowerShell
