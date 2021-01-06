---
title: Устранение неполадок службы Microsoft 365 Defender
description: Поиск решений и решений для известных проблем с Защитником Microsoft 365
keywords: устранение неполадок Защиты от угроз (Майкрософт), устранение неполадок, Azure ATP, проблемы, надстройка, страница параметров
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
ms.openlocfilehash: b7b6ea55d084c114b79dfee0e061b09c8ede8632
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760462"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="1624b-104">Устранение неполадок службы Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1624b-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1624b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1624b-105">**Applies to:**</span></span>
- <span data-ttu-id="1624b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1624b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1624b-107">В этом разделе решается проблема, которая может возникнуть при использовании службы Защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1624b-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="1624b-108">Содержимое Защитника Microsoft 365 не видно</span><span class="sxs-lookup"><span data-stu-id="1624b-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="1624b-109">Если в области навигации нет таких возможностей, как "Инциденты", "Центр действий" или "Охота" на портале, необходимо убедиться, что у вашего клиента есть соответствующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="1624b-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="1624b-110">Дополнительные сведения см. в статье [Предварительные требования](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="1624b-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="1624b-111">Оповещения Microsoft Defender для удостоверений не отображаются в инцидентах Защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1624b-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="1624b-112">Если в вашей среде развернут Microsoft Defender для удостоверений, но оповещения Защитника удостоверений не видятся как часть инцидентов в Microsoft 365 Defender, необходимо убедиться, что интеграция Microsoft Cloud App Security и Защитника удостоверений включена.</span><span class="sxs-lookup"><span data-stu-id="1624b-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="1624b-113">Дополнительные сведения см. в [microsoft Defender для интеграции удостоверений.](https://docs.microsoft.com/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="1624b-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="1624b-114">Где находится страница параметров для включаемой службы?</span><span class="sxs-lookup"><span data-stu-id="1624b-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="1624b-115">Чтобы включить Microsoft 365  Defender, можно получить доступ к параметрам из области навигации в Центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1624b-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="1624b-116">Этот элемент навигации виден, только если у вас есть необходимые [разрешения и лицензии.](mtp-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="1624b-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
