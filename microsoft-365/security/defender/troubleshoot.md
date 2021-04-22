---
title: Устранение неполадок с обслуживанием Microsoft 365 Defender
description: Поиск решений и обходных решений известных проблем Microsoft 365 Defender
keywords: устранение неполадок в Microsoft 365 Defender, устранение неполадок, microsoft Defender для удостоверений, проблемы, надстройка, страница параметров
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
ms.openlocfilehash: 0c933edfe80275dbfa60464ff862a7609b269332
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933401"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="c5f34-104">Устранение неполадок с обслуживанием Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5f34-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c5f34-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c5f34-105">**Applies to:**</span></span>
- <span data-ttu-id="c5f34-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5f34-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c5f34-107">В этом разделе будут решаться проблемы, которые могут возникнуть при использовании службы Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c5f34-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="c5f34-108">Я не вижу контента Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5f34-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="c5f34-109">Если на области навигации нет возможностей, таких как Incidents, Action Center или Hunting на портале, необходимо убедиться, что у клиента есть соответствующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="c5f34-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="c5f34-110">Дополнительные сведения см. в статье [Предварительные требования](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="c5f34-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="c5f34-111">Оповещения Microsoft Defender для удостоверений не отображаются в инцидентах Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5f34-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="c5f34-112">Если в вашей среде развернут Microsoft Defender для удостоверений, но вы не видите оповещений Defender для удостоверений в рамках инцидентов с Microsoft 365 Defender, необходимо убедиться, что интеграция microsoft Cloud App Security и Defender для удостоверений включена.</span><span class="sxs-lookup"><span data-stu-id="c5f34-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="c5f34-113">Дополнительные сведения см. в [веб-сайте Microsoft Defender для интеграции удостоверений.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="c5f34-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="c5f34-114">Где страница параметров для включаемой службы?</span><span class="sxs-lookup"><span data-stu-id="c5f34-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="c5f34-115">Чтобы включить Microsoft 365 Defender, необходимо получить доступ **к** настройкам с области навигации в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c5f34-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="c5f34-116">Этот элемент навигации виден только в том случае, если у вас есть необходимые разрешения [и лицензии.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="c5f34-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="c5f34-117">Как создать исключение для файла или URL-адреса?</span><span class="sxs-lookup"><span data-stu-id="c5f34-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="c5f34-118">Ложный срабатывка — это файл или URL-адрес, который обнаруживается как вредоносный, но не представляет угрозы.</span><span class="sxs-lookup"><span data-stu-id="c5f34-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="c5f34-119">Можно создавать индикаторы и определять исключения для разблокировки и допуска определенных файлов и URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="c5f34-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="c5f34-120">См. [адрес ложных срабатыва-срабатыва-минусов в Защитнике для конечной точки.](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)</span><span class="sxs-lookup"><span data-stu-id="c5f34-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


