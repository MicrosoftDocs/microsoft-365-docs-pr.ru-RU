---
title: Блокировка циклов обратной связи
description: Блокировка циклов обратной связи, также называемая быстрой защитой, является частью возможностей поведенческой блокировки и сдерживания в Microsoft Defender for Endpoint.
keywords: поведенческая блокировка, быстрая защита, блокировка отзывов, Microsoft Defender для конечной точки
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: b1ec879a2f05a0354b1a49cf94fccacb4a382193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076613"
---
# <a name="feedback-loop-blocking"></a>Блокировка циклов обратной связи

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>Обзор

Блокировка циклов обратной связи, также именуемая [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) быстрой защитой, является компонентом возможностей блокировки и сдерживания поведения в [Microsoft Defender для конечной точки.](https://docs.microsoft.com/windows/security/threat-protection/) При блокировке циклов обратной связи устройства в организации лучше защищены от атак. 

## <a name="how-feedback-loop-blocking-works"></a>Как работает блокировка циклов обратной связи

При обнаружении подозрительного поведения или файла, например [антивируса Microsoft Defender,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)сведения об этом артефакте отправляются нескольким классификаторам. Двигатель цикла быстрой защиты проверяет и сопоставляет информацию с другими сигналами, чтобы прийти к решению о блокировке файла. Проверка и классификация артефактов происходит быстро. Это приводит к быстрой блокировке подтвержденных вредоносных программ и приводит к защите всей экосистемы. 

При быстрой защите можно остановить атаку на устройстве, других устройствах в организации и устройствах в других организациях, так как атака пытается расширить его опорную позицию.


## <a name="configuring-feedback-loop-blocking"></a>Настройка блокировки циклов обратной связи

Если ваша организация использует Defender для конечной точки, блокировка циклов обратной связи включена по умолчанию. Однако быстрая защита возникает благодаря сочетанию возможностей Defender для конечных точек, функций защиты машинного обучения и обмена сигналами в службах безопасности Майкрософт. Убедитесь, что включены и настроены следующие функции и возможности Defender для конечной точки:

- [Базовые показатели Microsoft Defender для конечных точек](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Устройства, на борту в Microsoft Defender для конечной точки](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR в режиме блокировки](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Сокращение направлений атак](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Защита нового поколения](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (антивирус)

## <a name="related-articles"></a>Связанные статьи

- [Блокировка и сдерживание поведения](behavioral-blocking-containment.md)

- [(Блог) Блокировка и сдерживание поведения: преобразование оптики в защиту](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Полезные ресурсы Microsoft Defender для конечных точек](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
