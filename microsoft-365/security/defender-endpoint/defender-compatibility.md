---
title: Совместимость антивирусного решения с Защитником для конечной точки
description: Узнайте, как Защитник Windows с Microsoft Defender для endpoint и как он функционирует при работе с сторонним клиентом антивирусных программ.
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
ms.openlocfilehash: 84c523b721596d9c467f01cf6b8a0685b2091669
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274884"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Совместимость антивирусных решений с Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Агент Microsoft Defender для конечной точки зависит от антивируса Microsoft Defender для некоторых возможностей, таких как сканирование файлов.

>[!IMPORTANT]
>Защитник для конечной точки не придерживается параметров исключения антивируса Microsoft Defender. 

Необходимо настроить обновления аналитики безопасности на устройствах Defender для конечных точек независимо от того, является ли антивирус Microsoft Defender активным антивирусом или нет. Дополнительные сведения см. в [веб-сайте Управление обновлениями антивирусного](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)антивируса Microsoft Defender и применение базовых данных.

Если бортовые устройства защищены сторонним клиентом антивирусных программ, антивирус Microsoft Defender на этой конечной точке вступает в пассивный режим.

Антивирус Microsoft Defender будет по-прежнему получать  обновления, и процессmspeng.exeбудет указан как запущенная служба, но она не будет выполнять проверки и не заменит запущенный сторонний клиент антивирусного программного обеспечения.

Антивирусный интерфейс Microsoft Defender будет отключен, а пользователи на устройстве не смогут использовать антивирус Microsoft Defender для выполнения проверки по запросу или настройки большинства параметров.

Дополнительные сведения см. в разделе [Антивирус Microsoft Defender и Defender для конечной точки совместимости.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
