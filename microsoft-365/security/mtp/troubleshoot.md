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
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661985"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Устранение проблем службы защиты от угроз (Майкрософт)

**Область применения:**
- Защита от угроз (Майкрософт)

В этом разделе рассматриваются проблемы, которые могут возникать при использовании службы защиты от угроз (Майкрософт).


## <a name="i-dont-see-microsoft-threat-protection-content"></a>Я не вижу содержимого системы защиты от угроз Майкрософт
Если вы не видите возможности в области навигации, такие как инциденты, Центр уведомлений или поиск на портале, необходимо убедиться, что у клиента есть соответствующие лицензии. 

Дополнительные сведения см. в статье [Предварительные требования](prerequisites.md).

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Оповещения Azure ATP не отображаются в инцидентах защиты от угроз (Майкрософт)
Если в вашей среде развернута служба Azure ATP, но вы не видите оповещений Azure ATP в рамках инцидентов защиты от угроз (Майкрософт), вам требуется убедиться, что включена интеграция Microsoft Cloud App Security и Azure ATP. 

Дополнительные сведения см. в статье [Интеграция Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration).

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Доступна ли защита от угроз (Майкрософт) в облаке сообщества для государственных учреждений США (GCC) или GCC High?
В настоящее время она недоступна.

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Где находится страница параметров для включения службы?
Чтобы включить защиту от угроз Майкрософт, **Параметры** доступа из области навигации центра безопасности Microsoft 365. Этот элемент навигации отображается, только если у вас есть необходимые [разрешения и лицензии](mtp-enable.md#check-license-eligibility-and-required-permissions).

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a>Можно ли использовать надстройку вместо обязательных лицензий на водопериод?
В настоящее время нет надстроек для защиты от угроз Майкрософт. [Просмотр требований к лицензированию](prerequisites.md) 

