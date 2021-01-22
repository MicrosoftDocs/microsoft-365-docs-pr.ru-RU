---
title: Устранение неполадок службы Microsoft 365 Defender
description: Поиск решений и решений для известных проблем с Защитником Microsoft 365
keywords: устранение неполадок Защиты от угроз (Майкрософт), устранение неполадок, Azure ATP, проблемы, надстройка, страница параметров
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925722"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Устранение неполадок службы Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

В этом разделе решается проблема, которая может возникнуть при использовании службы Защитника Microsoft 365.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Содержимое Защитника Microsoft 365 не видно

Если в области навигации нет таких возможностей, как "Инциденты", "Центр действий" или "Охота" на портале, необходимо убедиться, что у вашего клиента есть соответствующие лицензии.

Дополнительные сведения см. в статье [Предварительные требования](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Оповещения Microsoft Defender для удостоверений не отображаются в инцидентах Защитника Microsoft 365

Если в вашей среде развернут Microsoft Defender для удостоверений, но оповещения Защитника удостоверений не видятся как часть инцидентов в Microsoft 365 Defender, необходимо убедиться, что интеграция Microsoft Cloud App Security и Защитника удостоверений включена.

Дополнительные сведения см. в [microsoft Defender для интеграции удостоверений.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Где находится страница параметров для включаемой службы?

Чтобы включить Microsoft 365  Defender, можно получить доступ к параметрам из области навигации в Центре безопасности Microsoft 365. Этот элемент навигации виден, только если у вас есть необходимые [разрешения и лицензии.](mtp-enable.md#check-license-eligibility-and-required-permissions)
