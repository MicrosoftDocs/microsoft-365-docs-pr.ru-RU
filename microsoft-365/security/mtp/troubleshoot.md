---
title: Устранение проблем со службой защитника Microsoft 365
description: Поиск решений и обход известных проблем защитника Microsoft 365
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
ms.openlocfilehash: 16cb1116f400c8d0a83ccc4cac23da06cd1be2a4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844672"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Устранение проблем со службой защитника Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защитник Microsoft 365

В этом разделе рассматриваются проблемы, которые могут возникнуть при использовании службы защитника Microsoft 365.


## <a name="i-dont-see-microsoft-365-defender-content"></a>Я не вижу содержимого защитника Microsoft 365
Если вы не видите возможности в области навигации, такие как инциденты, Центр уведомлений или поиск на портале, необходимо убедиться, что у клиента есть соответствующие лицензии. 

Дополнительные сведения см. в статье [Предварительные требования](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Защитник Майкрософт для оповещений об удостоверениях не отображается в происшествиях защитника Microsoft 365
Если у вас есть защитник Майкрософт для удостоверения, развернутого в вашей среде, но вы не видите компонент "уведомления об удостоверениях" в ходе инцидентов защитника Microsoft 365, то необходимо убедиться в том, что Microsoft Cloud App Security and защитник для интеграции удостоверений включен. 

Для получения дополнительных сведений обратитесь [к защитнику Майкрософт для интеграции удостоверений](https://docs.microsoft.com/cloud-app-security/aatp-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Где находится страница параметров для включения службы?
Чтобы включить защитник Microsoft 365, **Параметры** доступа из области навигации центра безопасности Майкрософт 365. Этот элемент навигации отображается, только если у вас есть необходимые [разрешения и лицензии](mtp-enable.md#check-license-eligibility-and-required-permissions).
 

