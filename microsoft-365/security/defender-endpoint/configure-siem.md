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
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222339"
---
# <a name="pull-detections-to-your-siem-tools"></a><span data-ttu-id="aded4-104">Притягивать обнаружения к средствам SIEM</span><span class="sxs-lookup"><span data-stu-id="aded4-104">Pull detections to your SIEM tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aded4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="aded4-105">**Applies to:**</span></span>
- [<span data-ttu-id="aded4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="aded4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aded4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aded4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="aded4-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="aded4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aded4-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="aded4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a><span data-ttu-id="aded4-110">Вытягивать обнаружения с помощью средств управления сведениями о безопасности и событиями (SIEM)</span><span class="sxs-lookup"><span data-stu-id="aded4-110">Pull detections using security information and events management (SIEM) tools</span></span>

>[!NOTE]
>- <span data-ttu-id="aded4-111">[Microsoft Defender for Endpoint Alert](alerts.md) состоит из одного или нескольких обнаружений.</span><span class="sxs-lookup"><span data-stu-id="aded4-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="aded4-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) состоит из подозрительного события, произошедшего на устройстве, и связанных с ним сведений оповещения.</span><span class="sxs-lookup"><span data-stu-id="aded4-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="aded4-113">-API оповещений Microsoft Defender для конечной точки является последним API для потребления оповещений и содержит подробный список связанных данных для каждого оповещения.</span><span class="sxs-lookup"><span data-stu-id="aded4-113">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="aded4-114">Дополнительные сведения см. в [дополнительных сведениях о](alerts.md) методах и свойствах alert и [list alerts.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="aded4-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="aded4-115">Defender for Endpoint поддерживает средства управления сведениями о безопасности и событиями (SIEM) для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="aded4-115">Defender for Endpoint supports security information and event management (SIEM) tools to pull detections.</span></span> <span data-ttu-id="aded4-116">Defender for Endpoint предоставляет оповещений через конечную точку HTTPS, организованную в Azure.</span><span class="sxs-lookup"><span data-stu-id="aded4-116">Defender for Endpoint exposes alerts through an HTTPS endpoint hosted in Azure.</span></span> <span data-ttu-id="aded4-117">Конечную точку можно настроить, чтобы вытащить обнаружения из корпоративного клиента в Azure Active Directory (AAD) с помощью протокола проверки подлинности OAuth 2.0 для приложения AAD, которое представляет определенный соединителем SIEM, установленным в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="aded4-117">The endpoint can be configured to pull detections from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.</span></span>

<span data-ttu-id="aded4-118">Defender for Endpoint в настоящее время поддерживает следующие конкретные средства решения SIEM с помощью выделенной модели интеграции SIEM:</span><span class="sxs-lookup"><span data-stu-id="aded4-118">Defender for Endpoint currently supports the following specific SIEM solution tools through a dedicated SIEM integration model:</span></span>

- <span data-ttu-id="aded4-119">IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="aded4-119">IBM QRadar</span></span>
- <span data-ttu-id="aded4-120">Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="aded4-120">Micro Focus ArcSight</span></span>

<span data-ttu-id="aded4-121">Другие решения SIEM (такие как Splunk, RSA NetWitness) поддерживаются с помощью другой модели интеграции на основе нового API оповещения.</span><span class="sxs-lookup"><span data-stu-id="aded4-121">Other SIEM solutions (such as Splunk, RSA NetWitness) are supported through a different integration model based on the new Alert API.</span></span> <span data-ttu-id="aded4-122">Дополнительные сведения можно получить на странице [приложения-партнера](https://securitycenter.microsoft.com/interoperability/partners) и в разделе Сведения о безопасности и аналитике.</span><span class="sxs-lookup"><span data-stu-id="aded4-122">For more information, view the [Partner application](https://securitycenter.microsoft.com/interoperability/partners) page and select the Security Information and Analytics section for full details.</span></span>

<span data-ttu-id="aded4-123">Чтобы использовать любой из этих поддерживаемых инструментов SIEM, необходимо:</span><span class="sxs-lookup"><span data-stu-id="aded4-123">To use either of these supported SIEM tools, you'll need to:</span></span>

- [<span data-ttu-id="aded4-124">Включение интеграции SIEM в Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="aded4-124">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- <span data-ttu-id="aded4-125">Настройте поддерживаемый инструмент SIEM:</span><span class="sxs-lookup"><span data-stu-id="aded4-125">Configure the supported SIEM tool:</span></span>
     - [<span data-ttu-id="aded4-126">Настройте Micro Focus ArcSight, чтобы вытащить Defender для обнаружения конечных точек</span><span class="sxs-lookup"><span data-stu-id="aded4-126">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>](configure-arcsight.md)
     - <span data-ttu-id="aded4-127">Настройка IBM QRadar, чтобы вытащить defender для обнаружения конечных точек, дополнительные сведения см. в [центре знаний IBM.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)</span><span class="sxs-lookup"><span data-stu-id="aded4-127">Configure IBM QRadar to pull Defender for Endpoint detections For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

<span data-ttu-id="aded4-128">Дополнительные сведения о списке полей, выставленных в API обнаружения, см. в поле [Defender for Endpoint Detection.](api-portal-mapping.md)</span><span class="sxs-lookup"><span data-stu-id="aded4-128">For more information on the list of fields exposed in the Detection API, see [Defender for Endpoint Detection fields](api-portal-mapping.md).</span></span>
