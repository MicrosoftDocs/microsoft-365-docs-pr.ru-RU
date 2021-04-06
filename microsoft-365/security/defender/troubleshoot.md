---
title: Устранение неполадок с обслуживанием Microsoft 365 Defender
description: Поиск решений и обходных решений известных проблем Microsoft 365 Defender
keywords: устранение неполадок Microsoft Threat Protection, устранение неполадок, ATP Azure, проблемы, надстройка, страница параметров
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
ms.openlocfilehash: a2cd27bf7bf8b1c4931b9d768f3a6b5e5f2a0d93
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592040"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Устранение неполадок с обслуживанием Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

В этом разделе будут решаться проблемы, которые могут возникнуть при использовании службы Защитника Microsoft 365.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Я не вижу контента Microsoft 365 Defender

Если на области навигации нет возможностей, таких как Incidents, Action Center или Hunting на портале, необходимо убедиться, что у клиента есть соответствующие лицензии.

Дополнительные сведения см. в статье [Предварительные требования](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Оповещения Microsoft Defender для удостоверений не отображаются в инцидентах Microsoft 365 Defender

Если в вашей среде развернут Microsoft Defender для удостоверений, но вы не видите оповещений Defender для удостоверений в рамках инцидентов с Microsoft 365 Defender, необходимо убедиться, что интеграция microsoft Cloud App Security и Defender для удостоверений включена.

Дополнительные сведения см. в [веб-сайте Microsoft Defender для интеграции удостоверений.](/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>Где страница параметров для включаемой службы?

Чтобы включить Microsoft 365 Defender, необходимо получить доступ **к** настройкам с области навигации в центре безопасности Microsoft 365. Этот элемент навигации виден только в том случае, если у вас есть необходимые разрешения [и лицензии.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>Как создать исключение для файла или URL-адреса?

Ложный срабатывка — это файл или URL-адрес, который обнаруживается как вредоносный, но не представляет угрозы. Можно создавать индикаторы и определять исключения для разблокировки и допуска определенных файлов и URL-адресов. См. [адрес ложных срабатыва-срабатыва-минусов в Защитнике для конечной точки.](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)


