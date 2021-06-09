---
title: Используйте cmdlets PowerShell для настройки и запуска microsoft Defender AV
description: В Windows 10 вы можете использовать cmdlets PowerShell для запуска сканирования, обновления сведений о безопасности и изменения параметров в антивирусная программа в Microsoft Defender.
keywords: сканирование, командная строка, mpcmdrun, защитник
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765303"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>Для настройки и управления антивирусная программа в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Вы можете использовать PowerShell для выполнения различных функций в Защитник Windows. Как и командная строка или командная строка, PowerShell — это командная строка на основе задач и язык скриптов, разработанный специально для системного администрирования. Подробнее об этом можно узнать в центре [PowerShell на MSDN.](/previous-versions/msdn10/mt173057(v=msdn.10))

Список cmdlets, их функций и доступных параметров см. в разделе [Defender.](/powershell/module/defender)

Cmdlets PowerShell наиболее полезны в среде Windows Server, которая не полагается на графический пользовательский интерфейс (GUI) для настройки программного обеспечения.

> [!NOTE]
> Команды PowerShell не следует использовать в качестве замены для полной инфраструктуры управления сетевой политикой, например [Microsoft Endpoint Configuration Manager,](/configmgr)консоли управления групповой политикой или [шаблонов групповой политики антивирусная программа в Microsoft Defender ADMX.](https://www.microsoft.com/download/101445) [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

Изменения, внесенные в PowerShell, будут влиять на локальные параметры конечной точки, где эти изменения развернуты или внесены. Это означает, что развертывание политики с помощью групповой политики, Microsoft Endpoint Configuration Manager или Microsoft Intune может переписать изменения, внесенные в PowerShell.

Можно настроить параметры, которые можно переопределять локально, с помощью [переопределеемых локальных политик.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

PowerShell обычно устанавливается в `%SystemRoot%\system32\WindowsPowerShell` папке.

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>Использование антивирусная программа в Microsoft Defender PowerShell

1. В панели Windows поиска введите **powershell**.
2. Выберите **Windows PowerShell** из результатов, чтобы открыть интерфейс.
3. Введите команду PowerShell и любые параметры.

> [!NOTE]
> Возможно, потребуется открыть PowerShell в режиме администратора. Щелкните правой кнопкой мыши элемент в меню "Пуск", нажмите кнопку **Запустить** в качестве администратора и нажмите **кнопку Да** по запросу разрешений.

Чтобы открыть онлайн-справку для любого из пользователей, введите следующее:

```PowerShell
Get-Help <cmdlet> -Online
```

Ограничь `-online` параметр, чтобы получить локализованную кэшную помощь.

## <a name="related-topics"></a>Статьи по теме

- [Справочные темы для средств управления и конфигурации](configuration-management-reference-microsoft-defender-antivirus.md)
- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [антивирусная программа в Microsoft Defender Cmdlets](/powershell/module/defender)