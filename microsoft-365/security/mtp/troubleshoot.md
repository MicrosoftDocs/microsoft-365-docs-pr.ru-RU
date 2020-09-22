---
title: Устранение проблем службы защиты от угроз (Майкрософт)
description: Находите решения известных проблем службы защиты от угроз (Майкрософт)
keywords: Устранение неполадок в защите от угроз Майкрософт, устранение неполадок, Azure ATP, проблемы, надстройка, страница параметров
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bcf5b79fcd2fdf0a5af5648e6f6b7ea65d69594c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201295"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Устранение проблем службы защиты от угроз (Майкрософт)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

В этом разделе рассматриваются проблемы, которые могут возникать при использовании службы защиты от угроз (Майкрософт).


## <a name="i-dont-see-microsoft-threat-protection-content"></a>Я не вижу содержимого системы защиты от угроз Майкрософт
Если вы не видите возможности в области навигации, такие как инциденты, Центр уведомлений или поиск на портале, необходимо убедиться, что у клиента есть соответствующие лицензии. 

Дополнительные сведения см. в статье [Предварительные требования](prerequisites.md).

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Оповещения Azure ATP не отображаются в инцидентах защиты от угроз (Майкрософт)
Если в вашей среде развернута служба Azure ATP, но вы не видите оповещений Azure ATP в рамках инцидентов защиты от угроз (Майкрософт), вам требуется убедиться, что включена интеграция Microsoft Cloud App Security и Azure ATP. 

Дополнительные сведения см. в статье [Интеграция Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Где находится страница параметров для включения службы?
Чтобы включить защиту от угроз Майкрософт, **Параметры** доступа из области навигации центра безопасности Microsoft 365. Этот элемент навигации отображается, только если у вас есть необходимые [разрешения и лицензии](mtp-enable.md#check-license-eligibility-and-required-permissions).
 

