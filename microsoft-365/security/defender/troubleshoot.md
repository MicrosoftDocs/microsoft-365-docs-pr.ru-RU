---
title: Устранение неполадок Microsoft 365 службы Defender
description: Поиск решений и обходов известных проблем Microsoft 365 Defender
keywords: устранение неполадок Microsoft 365, устранение неполадок, Microsoft Defender для удостоверений, проблемы, надстройка, страница параметров
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
ms.openlocfilehash: 81da6c6ef46798ac656e7d5f0f374bf2c722583d
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782745"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="647a2-104">Устранение неполадок Microsoft 365 службы Defender</span><span class="sxs-lookup"><span data-stu-id="647a2-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="647a2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="647a2-105">**Applies to:**</span></span>
- <span data-ttu-id="647a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="647a2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="647a2-107">В этом разделе будут решаться проблемы, которые могут возникнуть при использовании службы Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="647a2-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="647a2-108">Я не вижу контента Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="647a2-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="647a2-109">Если на области навигации нет таких возможностей, как Инциденты, Центр действий или Охота на портале, необходимо убедиться, что у клиента есть соответствующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="647a2-109">If you don't see capabilities on the navigation pane such as the Incidents, Action center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="647a2-110">Дополнительные сведения см. в разделе [Предварительные требования](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="647a2-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="647a2-111">Оповещения Microsoft Defender для удостоверений не отображаются в инцидентах Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="647a2-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="647a2-112">Если в вашей среде развернут защитник microsoft Defender для удостоверений, но оповещения Defender для удостоверений не будут включены в Microsoft 365 Defender, необходимо убедиться, что интеграция Microsoft Cloud App Security и Defender для удостоверений включена.</span><span class="sxs-lookup"><span data-stu-id="647a2-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="647a2-113">Дополнительные сведения см. в [веб-сайте Microsoft Defender для интеграции удостоверений.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="647a2-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="647a2-114">Где страница параметров для включаемой службы?</span><span class="sxs-lookup"><span data-stu-id="647a2-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="647a2-115">Чтобы включить Microsoft 365 Defender, Параметры  доступ из области навигации в центре Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="647a2-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="647a2-116">Этот элемент навигации виден только в том случае, если у вас есть необходимые разрешения [и лицензии.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="647a2-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="647a2-117">Как создать исключение для файла или URL-адреса?</span><span class="sxs-lookup"><span data-stu-id="647a2-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="647a2-118">Ложный срабатывка — это файл или URL-адрес, который обнаруживается как вредоносный, но не представляет угрозы.</span><span class="sxs-lookup"><span data-stu-id="647a2-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="647a2-119">Можно создавать индикаторы и определять исключения для разблокировки и допуска определенных файлов и URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="647a2-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="647a2-120">См. [адрес ложных срабатыва-срабатыва-минусов в Защитнике для конечной точки.](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)</span><span class="sxs-lookup"><span data-stu-id="647a2-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


