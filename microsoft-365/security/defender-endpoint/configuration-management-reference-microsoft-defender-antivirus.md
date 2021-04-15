---
title: Управление Защитник Windows бизнесом
description: Узнайте, как использовать групповую политику, диспетчер конфигурации, PowerShell, WMI, Intune и командную строку для управления AV Microsoft Defender
keywords: групповой политики, gpo, config manager, sccm, scep, powershell, wmi, intune, defender, antivirus, antimalware, security, protection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b9845812763f9e3f1fdecf5566824eb76971dad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764871"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>Управление антивирусом Microsoft Defender в вашем бизнесе

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Вы можете управлять и настраивать антивирус Microsoft Defender с помощью следующих средств:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (теперь входит в состав Microsoft Endpoint Manager)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (теперь является частью Microsoft Endpoint Manager)
- [Групповая политика](./use-group-policy-microsoft-defender-antivirus.md)
- [Командлеты PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Инструментарий управления Windows (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- Командная [строка Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (именуемая как *mpcmdrun.exe* утилита

В следующих статьях данная статья предоставляет дополнительные сведения, ссылки и ресурсы для использования этих средств для управления и настройки антивируса Microsoft Defender.

| Статья | Описание |
|:---|:---|
|[Управление антивирусом Microsoft Defender с помощью Microsoft Intune и Microsoft Endpoint Configuration Manager](use-intune-config-manager-microsoft-defender-antivirus.md)|Сведения об использовании Intune и Configuration Manager для развертывания, управления, отчета и настройки антивируса Microsoft Defender |
|[Управление антивирусом Microsoft Defender с помощью параметров групповой политики](use-group-policy-microsoft-defender-antivirus.md)|Список всех параметров групповой политики, расположенных в шаблонах ADMX |
|[Управление антивирусной программой Microsoft Defender с помощью cmdlets PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Инструкции по использованию команды PowerShell для управления антивирусом Microsoft Defender, а также ссылки на документацию для всех cmdlets и разрешенных параметров |
|[Управление антивирусом Microsoft Defender с помощью инструментов управления Windows (WMI)](use-wmi-microsoft-defender-antivirus.md)| Инструкции по использованию WMI для управления антивирусом Microsoft Defender, а также ссылки на документацию для API WMIv2 (включая все классы, методы и свойства) |
|[Управление антивирусом Microsoft Defender с помощью mpcmdrun.exe командной строки](command-line-arguments-microsoft-defender-antivirus.md)|Инструкции по использованию специального средства командной строки для управления и использования антивируса Microsoft Defender |