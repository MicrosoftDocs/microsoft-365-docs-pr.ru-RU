---
title: Совместимость антивирусного решения с Защитником для конечной точки
description: Узнайте, как Защитник Windows с Microsoft Defender для конечной точки и как он функционирует при работе с сторонним клиентом противомалярийных программ.
keywords: совместимость защитника windows, защитника, защитника Microsoft для конечной точки, защитника конечной точки, антивируса, mde
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782889"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Совместимость антивирусных решений с Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Агент Microsoft Defender для конечной точки зависит от антивирусная программа в Microsoft Defender некоторых возможностей, таких как сканирование файлов.

>[!IMPORTANT]
>Defender for Endpoint не придерживается параметров антивирусная программа в Microsoft Defender исключений. 

Необходимо настроить обновления аналитики безопасности на устройствах Defender для конечных точек независимо антивирусная программа в Microsoft Defender является активным антивирусом или нет. Дополнительные сведения см. в [антивирусная программа в Microsoft Defender обновления и применение базовых показателей.](manage-updates-baselines-microsoft-defender-antivirus.md)

Если бортовые устройства защищены сторонним клиентом противомалярийных программ, антивирусная программа в Microsoft Defender на этой конечной точке вступает в пассивный режим.

антивирусная программа в Microsoft Defender будет продолжать получать обновления, и  процессmspeng.exeбудет указан как запущенная служба, но она не будет выполнять проверки и не заменит запущенный сторонний клиент антивирусного программного обеспечения.

Интерфейс антивирусная программа в Microsoft Defender будет отключен, а пользователи на устройстве не смогут использовать антивирусная программа в Microsoft Defender для выполнения сканов по запросу или настройки большинства параметров.

Дополнительные сведения см. в [разделе антивирусная программа в Microsoft Defender и Defender для конечной точки совместимости.](microsoft-defender-antivirus-compatibility.md)
