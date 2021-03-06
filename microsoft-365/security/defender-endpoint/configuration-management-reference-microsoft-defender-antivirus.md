---
title: Управление Защитник Windows бизнесом
description: Узнайте, как использовать групповую политику, диспетчер конфигурации, PowerShell, WMI, Intune и командную строку для управления AV Microsoft Defender
keywords: групповой политики, gpo, config manager, sccm, scep, powershell, wmi, intune, defender, antivirus, antimalware, security, protection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/13/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f9ecade23964db88076347b3a89085b25c1b1538
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415567"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>Управление антивирусная программа в Microsoft Defender бизнесом

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)
- [Антивирусная программа в Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)

Вы можете управлять и настраивать антивирусная программа в Microsoft Defender с помощью следующих средств:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (теперь часть Microsoft Endpoint Manager)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (теперь часть Microsoft Endpoint Manager)
- [Групповая политика](./use-group-policy-microsoft-defender-antivirus.md)
- [Командлеты PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Инструментарий управления Windows (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- Командная [строка Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (именуемая как *mpcmdrun.exe* утилита

В следующих статьях данная статья предоставляет дополнительные сведения, ссылки и ресурсы для использования этих средств для управления и настройки антивирусная программа в Microsoft Defender.

| Статья | Описание |
|:---|:---|
|[Управление антивирусная программа в Microsoft Defender с Microsoft Intune и Microsoft Endpoint Configuration Manager](use-intune-config-manager-microsoft-defender-antivirus.md)|Сведения об использовании Intune и Configuration Manager для развертывания, управления, отчета и настройки антивирусная программа в Microsoft Defender |
|[Управление антивирусная программа в Microsoft Defender с помощью параметров групповой политики](use-group-policy-microsoft-defender-antivirus.md)|Список всех параметров групповой политики, расположенных в шаблонах ADMX |
|[Управление антивирусная программа в Microsoft Defender с помощью cmdlets PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Инструкции по использованию cmdlets PowerShell для управления антивирусная программа в Microsoft Defender, а также ссылки на документацию для всех cmdlets и разрешенных параметров |
|[Управление антивирусная программа в Microsoft Defender с помощью Windows инструментов управления (WMI)](use-wmi-microsoft-defender-antivirus.md)| Инструкции по использованию WMI для управления антивирусная программа в Microsoft Defender, а также ссылки на документацию для API WMIv2 (включая все классы, методы и свойства) |
|[Управление антивирусная программа в Microsoft Defender с помощью MpCmdRun.exe командной строки](command-line-arguments-microsoft-defender-antivirus.md)| Инструкции по использованию выделенного средства командной строки для управления и использования антивирусная программа в Microsoft Defender |
