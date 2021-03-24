---
title: Устранение неполадок с обслуживанием Microsoft 365 Defender
description: Поиск решений и работа с известными вопросами Microsoft 365 Defender
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
ms.openlocfilehash: 8d8083cbba3582c41ca91c57978675987822d0d9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073934"
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

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Где страница параметров для включаемой службы?

Чтобы включить Microsoft 365 Defender, необходимо получить доступ **к** настройкам с области навигации в центре безопасности Microsoft 365. Этот элемент навигации виден только в том случае, если у вас есть необходимые разрешения [и лицензии.](m365d-enable.md#check-license-eligibility-and-required-permissions)
