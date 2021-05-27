---
title: Настройка антивирусная программа в Microsoft Defender с помощью Microsoft Endpoint Manager
description: Используйте Microsoft Endpoint Manager Microsoft Intune и Microsoft Intune Microsoft Defender AV и Endpoint Protection
keywords: scep, intune, endpoint protection, configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683755"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Используйте Microsoft Endpoint Manager для настройки и управления антивирусная программа в Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Вы можете использовать [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) для настройки антивирусная программа в Microsoft Defender сканирования. [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) и [Диспетчер конфигурации](/mem/configmgr/core/understand/introduction) теперь являются частью Endpoint Manager.  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>Настройка антивирусная программа в Microsoft Defender в Endpoint Manager

1. Перейдите в центр Microsoft Endpoint Manager администратора [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите.

2. Перейдите к **безопасности конечных точек**.

3. В **статье Управление** выберите **антивирус**.

4. Выберите антивирусная программа в Microsoft Defender политику. 

5. В разделе **Управление** выберите **Свойства**.

6. Рядом с **Параметры конфигурации** выберите **Изменить**.

7. **Расширите раздел Scan** и просмотрите или отредактируйте параметры сканирования.

8. Выберите **Обзор + сохранить**


> [!TIP]
> Нужна помощь? См. [в Microsoft Intune Управление безопасностью конечных точек.](/mem/intune/protect/endpoint-security)


## <a name="related-articles"></a>Связанные статьи

- [Справочные статьи для средств управления и конфигурации](configuration-management-reference-microsoft-defender-antivirus.md)
- [Антивирусная программа в Microsoft Defender (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)