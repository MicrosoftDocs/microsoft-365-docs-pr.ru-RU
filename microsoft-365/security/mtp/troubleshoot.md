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
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="59ab0-104">Устранение проблем службы защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="59ab0-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="59ab0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="59ab0-105">**Applies to:**</span></span>
- <span data-ttu-id="59ab0-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="59ab0-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="59ab0-107">В этом разделе рассматриваются проблемы, которые могут возникать при использовании службы защиты от угроз (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="59ab0-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="59ab0-108">Я не вижу содержимого системы защиты от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="59ab0-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="59ab0-109">Если вы не видите возможности в области навигации, такие как инциденты, Центр уведомлений или поиск на портале, необходимо убедиться, что у клиента есть соответствующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="59ab0-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="59ab0-110">Дополнительные сведения см. в статье [Предварительные требования](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="59ab0-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="59ab0-111">Оповещения Azure ATP не отображаются в инцидентах защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="59ab0-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="59ab0-112">Если в вашей среде развернута служба Azure ATP, но вы не видите оповещений Azure ATP в рамках инцидентов защиты от угроз (Майкрософт), вам требуется убедиться, что включена интеграция Microsoft Cloud App Security и Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="59ab0-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="59ab0-113">Дополнительные сведения см. в статье [Интеграция Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="59ab0-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="59ab0-114">Доступна ли защита от угроз (Майкрософт) в облаке сообщества для государственных учреждений США (GCC) или GCC High?</span><span class="sxs-lookup"><span data-stu-id="59ab0-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="59ab0-115">В настоящее время она недоступна.</span><span class="sxs-lookup"><span data-stu-id="59ab0-115">At the moment, it is not available.</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="59ab0-116">Где находится страница параметров для включения службы?</span><span class="sxs-lookup"><span data-stu-id="59ab0-116">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="59ab0-117">Чтобы включить защиту от угроз Майкрософт, **Параметры** доступа из области навигации центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59ab0-117">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="59ab0-118">Этот элемент навигации отображается, только если у вас есть необходимые [разрешения и лицензии](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="59ab0-118">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a><span data-ttu-id="59ab0-119">Можно ли использовать надстройку вместо обязательных лицензий на водопериод?</span><span class="sxs-lookup"><span data-stu-id="59ab0-119">Can I use an add-on instead of the required E5 licenses?</span></span>
<span data-ttu-id="59ab0-120">В настоящее время нет надстроек для защиты от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="59ab0-120">There are currently no add-ons for Microsoft Threat Protection.</span></span> [<span data-ttu-id="59ab0-121">Просмотр требований к лицензированию</span><span class="sxs-lookup"><span data-stu-id="59ab0-121">See licensing requirements</span></span>](prerequisites.md) 

