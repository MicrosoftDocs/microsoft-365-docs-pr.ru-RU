---
title: Настройка функций Microsoft Defender для конечной точки на Android
description: Описывает настройку Microsoft Defender для конечной точки на Android
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mde, android, configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935321"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a><span data-ttu-id="a1765-104">Настройка защитника для конечной точки на android-функции</span><span class="sxs-lookup"><span data-stu-id="a1765-104">Configure Defender for Endpoint on Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a1765-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a1765-105">**Applies to:**</span></span>
- [<span data-ttu-id="a1765-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a1765-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a1765-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1765-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a><span data-ttu-id="a1765-108">Условный доступ с защитником для конечной точки на Android</span><span class="sxs-lookup"><span data-stu-id="a1765-108">Conditional Access with Defender for Endpoint on Android</span></span>  
<span data-ttu-id="a1765-109">Microsoft Defender для конечной точки на Android вместе с Microsoft Intune и Azure Active Directory позволяют применять политики соответствия требованиям устройств и условного доступа на основе уровней риска устройств.</span><span class="sxs-lookup"><span data-stu-id="a1765-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="a1765-110">Defender for Endpoint — это решение mobile Threat Defense (MTD), которое можно развернуть для использования этой возможности с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="a1765-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="a1765-111">Дополнительные сведения о том, как настроить Defender для конечной точки на Android и условном доступе, см. в дополнительных сведениях [Defender for Endpoint и Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="a1765-111">For more information about how to set up Defender for Endpoint on Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="a1765-112">Настройка настраиваемых индикаторов</span><span class="sxs-lookup"><span data-stu-id="a1765-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="a1765-113">Defender for Endpoint на Android поддерживает создание настраиваемой индикаторов для IP-адресов и URL-адресов/доменов.</span><span class="sxs-lookup"><span data-stu-id="a1765-113">Defender for Endpoint on Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="a1765-114">Defender for Endpoint на Android позволяет администраторам настраивать настраиваемые индикаторы для поддержки устройств Android.</span><span class="sxs-lookup"><span data-stu-id="a1765-114">Defender for Endpoint on Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="a1765-115">Дополнительные сведения о настройке настраиваемых индикаторов см. в см. [в руб. Управление индикаторами.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="a1765-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="a1765-116">Настройка веб-защиты</span><span class="sxs-lookup"><span data-stu-id="a1765-116">Configure web protection</span></span>
<span data-ttu-id="a1765-117">Defender for Endpoint на Android позволяет ИТ-администраторам настраивать функцию веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="a1765-117">Defender for Endpoint on Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="a1765-118">Эта возможность доступна в центре администрирования microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="a1765-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="a1765-119">Защитник для конечной точки на Android будет использовать VPN для предоставления функции веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="a1765-119">Defender for Endpoint on Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="a1765-120">Это не обычный VPN и локальный или самоциклинг VPN, который не принимает трафик за пределами устройства.</span><span class="sxs-lookup"><span data-stu-id="a1765-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="a1765-121">Дополнительные сведения см. в [странице Configure web protection on devices that run Android.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="a1765-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a1765-122">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="a1765-122">Related topics</span></span>
- [<span data-ttu-id="a1765-123">Обзор Microsoft Defender для конечной точки на Android</span><span class="sxs-lookup"><span data-stu-id="a1765-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="a1765-124">Развертывание Microsoft Defender для конечной точки на Android с помощью Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a1765-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
