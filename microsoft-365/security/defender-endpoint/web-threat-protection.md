---
title: Защита организации от веб-угроз
description: Узнайте о веб-защите в Microsoft Defender для конечной точки и о том, как она может защитить организацию.
keywords: веб-защита, защита от веб-угроз, просмотр веб-сайтов, безопасность, фишинг, вредоносные программы, эксплойт, веб-сайты, защита сети, Edge, Internet Explorer, Chrome, Firefox, веб-браузер
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0c42c05e318390741b94b6d7d1b5394fca961714
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688949"
---
# <a name="protect-your-organization-against-web-threats"></a>Защита организации от веб-угроз

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Защита веб-угроз является частью [веб-защиты](web-protection-overview.md) в Defender for Endpoint. Он использует [сетевую защиту](network-protection.md) для защиты устройств от веб-угроз. Интегрируясь с Microsoft Edge и популярными сторонними браузерами, например Chrome и Firefox, защита веб-угроз останавливает веб-угрозы без прокси-сервера и может защитить устройства во время их езды или на месте. Защита от веб-угроз останавливает доступ к фишинг-сайтам, векторам вредоносных программ, сайтам эксплойтов, сайтам с недоверием или низкой репутации, а также сайтам, заблокированным в настраиваемом списке [индикаторов.](manage-indicators.md)

>[!Note]
>Получение новых настраиваемых индикаторов для устройств может занять до часа.

## <a name="prerequisites"></a>Предварительные условия
Веб-защита использует защиту сети для обеспечения безопасности просмотра веб-страниц в Microsoft Edge и сторонних веб-браузерах.

Чтобы включить защиту сети на устройствах:
- Изменить базовый уровень безопасности Defender для конечной точки в веб& **сетевой** защите, чтобы включить защиту сети перед развертыванием или ее передислокатурой. [Узнайте о проверке и назначении базового уровня безопасности Defender для конечной точки](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Включите защиту сети при использовании конфигурации устройств Intune, SCCM, групповой политики или решения MDM. [Подробнее о включаемой защите сети](enable-network-protection.md)  

>[!Note]
>Если вы установите защиту сети **только для аудита,** блокировка будет недоступной. Кроме того, вы сможете обнаруживать и фиксировать попытки доступа к вредоносным и нежелательным веб-сайтам только Microsoft Edge.

## <a name="related-topics"></a>Статьи по теме

- [Обзор веб-защиты](web-protection-overview.md)
- [Защита от веб-угроз](web-threat-protection.md)
- [Мониторинг безопасности в Интернете](web-protection-monitoring.md)
- [Реагирование на веб-угрозы](web-protection-response.md)
- [Защита сети](network-protection.md)
