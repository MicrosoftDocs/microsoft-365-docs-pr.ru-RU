---
title: Обзор интеграции Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender для конечной точки интегрируется с Cloud App Security путем переададки всех действий в сети облачных приложений.
keywords: облако, приложение, сеть, видимость, использование
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
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844746"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Microsoft Cloud App Security в обзоре Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) — это комплексное решение, которое обеспечивает видимость облачных приложений и служб, позволяя контролировать и ограничивать доступ к облачным приложениям, при этом соблюдая требования соответствия требованиям к данным, хранимым в облаке. Дополнительные сведения см. [в Cloud App Security.](/cloud-app-security/what-is-cloud-app-security)

>[!NOTE]
>Эта функция доступна с лицензией E5 для Enterprise Mobility + Security [устройств,](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) работающих Windows 10 версии 1809 или более поздней версии.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender для конечной точки и Cloud App Security интеграции 

Cloud App Security зависит от журналов облачного трафика, которые перенаправлются в него с корпоративных брандмауэров и прокси-серверов. Microsoft Defender для конечной точки интегрируется с Cloud App Security, собирая и переадребуя все действия сети облачных приложений, обеспечивая беспрецедентную видимость для использования облачных приложений. Функция мониторинга встроена в устройство, обеспечивая полное освещение сетевой активности.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


Интеграция обеспечивает следующие основные улучшения существующего Cloud App Security обнаружения: 

- Доступно везде . Так как сетевое действие собирается непосредственно из конечной точки, оно доступно везде, где устройство находится, в корпоративной сети или отключено, так как это больше не зависит от трафика, переназначенного через корпоративный брандмауэр или прокси-серверы. 

- Работает вне коробки, конфигурация не требуется - перенакладка журналов облачного трафика в Cloud App Security требует конфигурации брандмауэра и прокси-сервера. При интеграции Defender для Cloud App Security и конечной точки конфигурация не требуется. Просто включи его в Центр безопасности в Microsoft Defender параметры, и вы хорошо идти. 

- Контекст устройства — в журналах облачного трафика отсутствует контекст устройства. Защитник для сетевой активности Endpoint сообщается в контексте устройства (какое устройство было доступно облачному приложению), поэтому вы можете точно понять, где (устройство) проходило сетевое действие, помимо того, кто (пользователь) выполнял его. 

Дополнительные сведения об обнаружении облачных данных см. в [ссылке Работа с обнаруженными приложениями.](/cloud-app-security/discovered-apps)

## <a name="related-topic"></a>Связанная тема

- [Настройка интеграции Microsoft Cloud App Security](microsoft-cloud-app-security-config.md)
