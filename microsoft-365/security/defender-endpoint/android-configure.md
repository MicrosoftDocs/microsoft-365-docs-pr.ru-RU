---
title: Настройка функций Microsoft Defender для конечной точки на Android
description: Описывает настройку Microsoft Defender для конечной точки на Android
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mde, android, configuration
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
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935321"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Настройка защитника для конечной точки на android-функции

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Условный доступ с защитником для конечной точки на Android  
Microsoft Defender для конечной точки на Android вместе с Microsoft Intune и Azure Active Directory позволяют применять политики соответствия требованиям устройств и условного доступа на основе уровней риска устройств. Defender for Endpoint — это решение mobile Threat Defense (MTD), которое можно развернуть для использования этой возможности с помощью Intune.

Дополнительные сведения о том, как настроить Defender для конечной точки на Android и условном доступе, см. в дополнительных сведениях [Defender for Endpoint и Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)

## <a name="configure-custom-indicators"></a>Настройка настраиваемых индикаторов  

> [!NOTE]
> Defender for Endpoint на Android поддерживает создание настраиваемой индикаторов для IP-адресов и URL-адресов/доменов.

Defender for Endpoint на Android позволяет администраторам настраивать настраиваемые индикаторы для поддержки устройств Android. Дополнительные сведения о настройке настраиваемых индикаторов см. в см. [в руб. Управление индикаторами.](manage-indicators.md)

## <a name="configure-web-protection"></a>Настройка веб-защиты
Defender for Endpoint на Android позволяет ИТ-администраторам настраивать функцию веб-защиты. Эта возможность доступна в центре администрирования microsoft Endpoint Manager.

> [!NOTE]
> Защитник для конечной точки на Android будет использовать VPN для предоставления функции веб-защиты. Это не обычный VPN и локальный или самоциклинг VPN, который не принимает трафик за пределами устройства. Дополнительные сведения см. в [странице Configure web protection on devices that run Android.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)

## <a name="related-topics"></a>Похожие темы
- [Обзор Microsoft Defender для конечной точки на Android](microsoft-defender-endpoint-android.md)
- [Развертывание Microsoft Defender для конечной точки на Android с помощью Microsoft Intune](android-intune.md)
