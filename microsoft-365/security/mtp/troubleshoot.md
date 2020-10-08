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
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="457c4-104">Устранение проблем службы защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="457c4-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="457c4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="457c4-105">**Applies to:**</span></span>
- <span data-ttu-id="457c4-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="457c4-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="457c4-107">В этом разделе рассматриваются проблемы, которые могут возникать при использовании службы защиты от угроз (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="457c4-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="457c4-108">Я не вижу содержимого системы защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="457c4-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="457c4-109">Если вы не видите возможности в области навигации, такие как инциденты, Центр уведомлений или поиск на портале, необходимо убедиться, что у клиента есть соответствующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="457c4-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="457c4-110">Дополнительные сведения см. в статье [Предварительные требования](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="457c4-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="457c4-111">Оповещения Azure ATP не отображаются в инцидентах защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="457c4-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="457c4-112">Если в вашей среде развернута служба Azure ATP, но вы не видите оповещений Azure ATP в рамках инцидентов защиты от угроз (Майкрософт), вам требуется убедиться, что включена интеграция Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="457c4-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="457c4-113">Дополнительные сведения см. в статье [Интеграция Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="457c4-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="457c4-114">Где находится страница параметров для включения службы?</span><span class="sxs-lookup"><span data-stu-id="457c4-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="457c4-115">Чтобы включить защиту от угроз Майкрософт, **Параметры** доступа из области навигации центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="457c4-115">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="457c4-116">Этот элемент навигации отображается, только если у вас есть необходимые [разрешения и лицензии](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="457c4-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

