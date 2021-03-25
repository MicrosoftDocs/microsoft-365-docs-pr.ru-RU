---
title: Устранение неполадок с лицензиями для ATP Microsoft Defender для Mac
description: Устранение неполадок в лицензии Microsoft Defender ATP для Mac.
keywords: Microsoft, defender, atp, mac, performance
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 645c3657bdd1540ac95b68460b4dff6d25627c2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185934"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Устранение неполадок с лицензиями для Microsoft Defender для конечной точки для Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки для Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

При проверке microsoft [Defender для конечной](microsoft-defender-endpoint-mac.md) точки для Mac и [ручного](mac-install-manually.md) тестирования развертывания или проверки концепции (PoC) вы можете получить следующую ошибку:

![Изображение ошибки лицензии](images/no-license-found.png)

**Сообщение:** 

Лицензия не найдена

Похоже, у вашей организации нет лицензии на подписку microsoft 365 Enterprise.

Обратитесь к системному администратору.

**Причина:** 

Вы развернули и/или установили Microsoft Defender для конечной точки для пакета macOS ("Пакет установки загрузки"), но, возможно, вы запустите сценарий конфигурации ("Скачайте пакет onboarding").

**Решение:**

Следуйте инструкциям MicrosoftDefenderATPOnboardingMacOs.py, задокументированным здесь: [конфигурация клиента](mac-install-manually.md#client-configuration)

