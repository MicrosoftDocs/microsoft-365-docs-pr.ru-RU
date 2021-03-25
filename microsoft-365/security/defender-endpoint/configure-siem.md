---
title: Извлеките обнаружения в инструменты SIEM из Microsoft Defender для конечной точки
description: Узнайте, как использовать API REST и настроить поддерживаемые средства управления сведениями о безопасности и событиями для получения и обнаружения.
keywords: настройка siem, средства управления сведениями о безопасности и событиями, splunk, arcsight, настраиваемые индикаторы, api отдыха, определения оповещений, индикаторы компромисса
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
ms.openlocfilehash: 0b9ce376736e5f00ee0f6a4f308d783e75052357
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163305"
---
# <a name="pull-detections-to-your-siem-tools"></a>Притягивать обнаружения к средствам SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a>Вытягивать обнаружения с помощью средств управления сведениями о безопасности и событиями (SIEM)

>[!NOTE]
>- [Microsoft Defender for Endpoint Alert](alerts.md) состоит из одного или нескольких обнаружений.
>- [Microsoft Defender for Endpoint Detection](api-portal-mapping.md) состоит из подозрительного события, произошедшего на устройстве, и связанных с ним сведений оповещения.
>-API оповещений Microsoft Defender для конечной точки является последним API для потребления оповещений и содержит подробный список связанных данных для каждого оповещения. Дополнительные сведения см. в [дополнительных сведениях о](alerts.md) методах и свойствах alert и [list alerts.](get-alerts.md)

Defender for Endpoint поддерживает средства управления сведениями о безопасности и событиями (SIEM) для обнаружения. Defender for Endpoint предоставляет оповещений через конечную точку HTTPS, организованную в Azure. Конечную точку можно настроить, чтобы вытащить обнаружения из корпоративного клиента в Azure Active Directory (AAD) с помощью протокола проверки подлинности OAuth 2.0 для приложения AAD, которое представляет определенный соединителем SIEM, установленным в вашей среде.

Defender for Endpoint в настоящее время поддерживает следующие конкретные средства решения SIEM с помощью выделенной модели интеграции SIEM:

- IBM QRadar
- Micro Focus ArcSight

Другие решения SIEM (такие как Splunk, RSA NetWitness) поддерживаются с помощью другой модели интеграции на основе нового API оповещения. Дополнительные сведения можно получить на странице [приложения-партнера](https://securitycenter.microsoft.com/interoperability/partners) и в разделе Сведения о безопасности и аналитике.

Чтобы использовать любой из этих поддерживаемых инструментов SIEM, необходимо:

- [Включение интеграции SIEM в Defender для конечной точки](enable-siem-integration.md)
- Настройте поддерживаемый инструмент SIEM:
     - [Настройка HP ArcSight, чтобы вытащить Defender для обнаружения конечных точек](configure-arcsight.md)
     - Настройка IBM QRadar, чтобы вытащить defender для обнаружения конечных точек, дополнительные сведения см. в [центре знаний IBM.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)

Дополнительные сведения о списке полей, выставленных в API обнаружения, см. в [поле Defender for Endpoint Detection.](api-portal-mapping.md)
