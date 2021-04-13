---
title: Настройка Microsoft Defender для конечной точки на android-функции
description: Описывает настройку Microsoft Defender для конечной точки на Android
keywords: Microsoft, defender, atp, mde, android, configuration
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8ec4a19bdd641c721bfcd7be2ceb59de1de92963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688037"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a>Настройка защитника для конечной точки для функций Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a>Условный доступ с защитником для конечной точки для Android  
Microsoft Defender для конечной точки на Android вместе с Microsoft Intune и Azure Active Directory позволяют применять политики соответствия требованиям устройств и условного доступа на основе уровней риска устройств. Defender for Endpoint — это решение mobile Threat Defense (MTD), которое можно развернуть для использования этой возможности с помощью Intune.

Дополнительные сведения о том, как настроить Defender для конечной точки для Android и условного доступа, см. в дополнительных сведениях [Defender for Endpoint и Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)

## <a name="configure-custom-indicators"></a>Настройка настраиваемых индикаторов  

> [!NOTE]
> Defender for Endpoint для Android поддерживает создание настраиваемой индикаторов для IP-адресов и URL-адресов/доменов.

Defender for Endpoint для Android позволяет администраторам настраивать настраиваемые индикаторы для поддержки устройств Android. Дополнительные сведения о настройке настраиваемых индикаторов см. в см. [в руб. Управление индикаторами.](manage-indicators.md)

## <a name="configure-web-protection"></a>Настройка веб-защиты
Defender for Endpoint для Android позволяет ИТ-администраторам настраивать функцию веб-защиты. Эта возможность доступна в центре администрирования microsoft Endpoint Manager.

> [!NOTE]
> Защитник для конечной точки для Android будет использовать VPN для предоставления функции веб-защиты. Это не обычный VPN и локальный или самоциклинг VPN, который не принимает трафик за пределами устройства. Дополнительные сведения см. в [странице Configure web protection on devices that run Android.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)

## <a name="related-topics"></a>Статьи по теме
- [Обзор Microsoft Defender для конечной точки на Android](microsoft-defender-endpoint-android.md)
- [Развертывание Microsoft Defender для конечной точки на Android с помощью Microsoft Intune](android-intune.md)
