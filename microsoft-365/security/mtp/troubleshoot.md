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
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="e6a19-104">Устранение проблем со службой защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6a19-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e6a19-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e6a19-105">**Applies to:**</span></span>
- <span data-ttu-id="e6a19-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6a19-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e6a19-107">В этом разделе рассматриваются проблемы, которые могут возникнуть при использовании службы защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6a19-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>


## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="e6a19-108">Я не вижу содержимого защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6a19-108">I don't see Microsoft 365 Defender content</span></span>
<span data-ttu-id="e6a19-109">Если вы не видите возможности в области навигации, такие как инциденты, Центр уведомлений или поиск на портале, необходимо убедиться, что у клиента есть соответствующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="e6a19-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="e6a19-110">Дополнительные сведения см. в статье [Предварительные требования](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="e6a19-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="e6a19-111">Защитник Майкрософт для оповещений об удостоверениях не отображается в происшествиях защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6a19-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>
<span data-ttu-id="e6a19-112">Если у вас есть защитник Майкрософт для удостоверения, развернутого в вашей среде, но вы не видите компонент "уведомления об удостоверениях" в ходе инцидентов защитника Microsoft 365, то необходимо убедиться в том, что Microsoft Cloud App Security and защитник для интеграции удостоверений включен.</span><span class="sxs-lookup"><span data-stu-id="e6a19-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span> 

<span data-ttu-id="e6a19-113">Для получения дополнительных сведений обратитесь [к защитнику Майкрософт для интеграции удостоверений](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="e6a19-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="e6a19-114">Где находится страница параметров для включения службы?</span><span class="sxs-lookup"><span data-stu-id="e6a19-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="e6a19-115">Чтобы включить защитник Microsoft 365, **Параметры** доступа из области навигации центра безопасности Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="e6a19-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="e6a19-116">Этот элемент навигации отображается, только если у вас есть необходимые [разрешения и лицензии](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="e6a19-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

