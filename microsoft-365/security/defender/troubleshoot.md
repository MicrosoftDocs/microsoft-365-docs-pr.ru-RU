---
title: Устранение Microsoft 365 Defender проблем службы
description: Поиск решений и обходных решений известных Microsoft 365 Defender проблем
keywords: устранение Microsoft 365 Defender, устранение неполадок, microsoft Defender для удостоверений, проблемы, надстройка, страница параметров
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7891d61de7581a896a6599004eae91a4e47e1581
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029949"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Устранение Microsoft 365 Defender проблем службы

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

В этом разделе будут решаться проблемы, которые могут возникнуть при использовании Microsoft 365 Defender службы.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Я не вижу Microsoft 365 Defender контента

Если на области навигации нет таких возможностей, как Инциденты, Центр действий или Охота на портале, необходимо убедиться, что у клиента есть соответствующие лицензии.

Дополнительные сведения см. в разделе [Предварительные требования](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Оповещения Microsoft Defender для удостоверений не отображаются в Microsoft 365 Defender инцидентах

Если в вашей среде развернут Microsoft Defender для удостоверений, но оповещения Defender для удостоверений не видятся в Microsoft 365 Defender инцидентов, необходимо убедиться, что интеграция Microsoft Cloud App Security и Defender для удостоверений включена.

Дополнительные сведения см. в [веб-сайте Microsoft Defender для интеграции удостоверений.](/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>Где страница параметров для включаемой службы?

Чтобы включить Microsoft 365 Defender, **Параметры** доступ из области навигации в центре Microsoft 365 безопасности. Этот элемент навигации виден только в том случае, если у вас есть необходимые разрешения [и лицензии.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>Как создать исключение для файла или URL-адреса?

Ложный срабатывка — это файл или URL-адрес, который обнаруживается как вредоносный, но не представляет угрозы. Можно создавать индикаторы и определять исключения для разблокировки и допуска определенных файлов и URL-адресов. См. [адрес ложных срабатыва-срабатыва-минусов в Защитнике для конечной точки.](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)
