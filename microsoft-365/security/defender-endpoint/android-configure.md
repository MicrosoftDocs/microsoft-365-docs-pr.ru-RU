---
title: Настройка ATP Защитника Майкрософт для функций Android
description: Описывает, как настроить ATP Защитника Microsoft для Android
keywords: Microsoft, defender, atp, android, configuration
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4325020e653f14898ece4192e03cbf8b90131136
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163451"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a><span data-ttu-id="091a6-104">Настройка защитника для конечной точки для функций Android</span><span class="sxs-lookup"><span data-stu-id="091a6-104">Configure Defender for Endpoint for Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="091a6-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="091a6-105">**Applies to:**</span></span>
- [<span data-ttu-id="091a6-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="091a6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="091a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="091a6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a><span data-ttu-id="091a6-108">Условный доступ с защитником для конечной точки для Android</span><span class="sxs-lookup"><span data-stu-id="091a6-108">Conditional Access with Defender for Endpoint for Android</span></span>  
<span data-ttu-id="091a6-109">Microsoft Defender для конечной точки для Android наряду с Microsoft Intune и Azure Active Directory позволяет применять политики соответствия требованиям устройств и условного доступа на основе уровней риска устройств.</span><span class="sxs-lookup"><span data-stu-id="091a6-109">Microsoft Defender for Endpoint for Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="091a6-110">Defender for Endpoint — это решение mobile Threat Defense (MTD), которое можно развернуть для использования этой возможности с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="091a6-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="091a6-111">Дополнительные сведения о том, как настроить Defender для конечной точки для Android и условного доступа, см. в дополнительных сведениях [Defender for Endpoint и Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="091a6-111">For more information about how to set up Defender for Endpoint for Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="091a6-112">Настройка настраиваемых индикаторов</span><span class="sxs-lookup"><span data-stu-id="091a6-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="091a6-113">Defender for Endpoint для Android поддерживает создание настраиваемой индикаторов для IP-адресов и URL-адресов/доменов.</span><span class="sxs-lookup"><span data-stu-id="091a6-113">Defender for Endpoint for Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="091a6-114">Defender for Endpoint для Android позволяет администраторам настраивать настраиваемые индикаторы для поддержки устройств Android.</span><span class="sxs-lookup"><span data-stu-id="091a6-114">Defender for Endpoint for Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="091a6-115">Дополнительные сведения о настройке настраиваемых индикаторов см. в см. [в руб. Управление индикаторами.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="091a6-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="091a6-116">Настройка веб-защиты</span><span class="sxs-lookup"><span data-stu-id="091a6-116">Configure web protection</span></span>
<span data-ttu-id="091a6-117">Defender for Endpoint для Android позволяет ИТ-администраторам настраивать функцию веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="091a6-117">Defender for Endpoint for Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="091a6-118">Эта возможность доступна в центре администрирования microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="091a6-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="091a6-119">Защитник для конечной точки для Android будет использовать VPN для предоставления функции веб-защиты.</span><span class="sxs-lookup"><span data-stu-id="091a6-119">Defender for Endpoint for Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="091a6-120">Это не обычный VPN и локальный или самоциклинг VPN, который не принимает трафик за пределами устройства.</span><span class="sxs-lookup"><span data-stu-id="091a6-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="091a6-121">Дополнительные сведения см. в [странице Configure web protection on devices that run Android.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="091a6-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="091a6-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="091a6-122">Related topics</span></span>
- [<span data-ttu-id="091a6-123">Обзор Microsoft Defender для конечной точки для Android</span><span class="sxs-lookup"><span data-stu-id="091a6-123">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="091a6-124">Развертывание Microsoft Defender для конечной точки для Android с помощью Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="091a6-124">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span>](android-intune.md)