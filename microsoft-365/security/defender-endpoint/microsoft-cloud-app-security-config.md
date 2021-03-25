---
title: Настройка интеграции microsoft Cloud App Security
ms.reviewer: ''
description: Узнайте, как включить параметры, чтобы включить интеграцию Microsoft Defender для конечных точек с безопасностью облачных приложений Microsoft.
keywords: облако, приложение, безопасность, параметры, интеграция, обнаружение, отчет
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ddf32b26191826ab6ecbad6b9d047ac7bbb6276a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076573"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Настройка безопасности облачных приложений Майкрософт в Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Чтобы воспользоваться сигналами обнаружения облачных приложений Microsoft Defender для конечных точек, включим интеграцию microsoft Cloud App Security.

>[!NOTE]
>Эта функция будет доступна с лицензией E5 для корпоративной мобильности [и](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) безопасности на устройствах под управлением Windows 10, версии 1709 (СБОРКА ОС 16299.1085 с [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, версия 1803 (сборка ОС 17134.704 с [KB4493464),](https://support.microsoft.com/help/4493464)Windows 10, версия 1809 (СБОРКА ОС 17763.379 с [KB4489899)](https://support.microsoft.com/help/4489899)или более поздние версии Windows 10.

> Подробные сведения о интеграции Microsoft Defender для конечной точки с [безопасностью облачных](https://docs.microsoft.com/cloud-app-security/mde-integration) приложений Microsoft Для подробной интеграции Microsoft Defender для конечной точки с безопасностью облачных приложений Microsoft. 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Включить безопасность облачных приложений Майкрософт в Microsoft Defender для конечной точки

1. В области навигации выберите **Параметры настройки**  >  **Расширенные функции**.
2. Выберите **microsoft Cloud App Security** и переключить переключатель на **On**.
3. Нажмите **кнопку Сохранить предпочтения**.

После активации Microsoft Defender для конечной точки немедленно начнет переададировать сигналы обнаружения в cloud App Security.

## <a name="view-the-data-collected"></a>Просмотр собранных данных

Сведения о просмотре и доступе к данным Microsoft Defender для конечных точек в microsoft Cloud Apps Security см. в обзоре устройств [в области безопасности облачных приложений.](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)


Дополнительные сведения об обнаружении облачных данных см. в [ссылке Работа с обнаруженными приложениями.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

Если вы хотите попробовать microsoft Cloud App Security, см. в [приложении Microsoft Cloud Security Trial.](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)

## <a name="related-topic"></a>Связанная тема
- [Интеграция microsoft Cloud App Security](microsoft-cloud-app-security-integration.md)
