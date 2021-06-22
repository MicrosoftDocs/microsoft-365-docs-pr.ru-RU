---
title: Функции предварительного просмотра в Microsoft Defender для конечной точки
description: Узнайте, как получить доступ к функциям предварительного просмотра в Microsoft Defender для конечной точки.
keywords: предварительный просмотр, опыт предварительного просмотра, Microsoft Defender для конечной точки, функции, обновления
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 65edf54ea0bf5cb0a0210dd306db07c756149f65
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062137"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="ad0a7-104">Функции предварительного просмотра в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ad0a7-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="ad0a7-105">Предварительные версии предоставляются без соглашения об уровне обслуживания и не рекомендуется для рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="ad0a7-106">Некоторые функции могут не поддерживаться или иметь ограниченные возможности.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="ad0a7-107">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ad0a7-107">**Applies to:**</span></span>
- [<span data-ttu-id="ad0a7-108">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ad0a7-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ad0a7-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad0a7-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ad0a7-110">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ad0a7-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ad0a7-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="ad0a7-112">Служба Defender for Endpoint постоянно обновляется, чтобы включить новые возможности и возможности.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="ad0a7-113">Узнайте о новых функциях в выпуске предварительного просмотра Defender для конечной точки и одними из первых попробуйте новые функции, включив функцию предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-113">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="ad0a7-114">Получите уведомление, когда эта страница обновляется путем копирования и вклейки следующего URL-адреса в читателя каналов: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="ad0a7-114">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="ad0a7-115">Дополнительные сведения о новых возможностях, которые, как правило, доступны, см. в дополнительных сведениях о новых возможностях [в Defender для конечной точки.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="ad0a7-115">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="ad0a7-116">Включение предварительных функций</span><span class="sxs-lookup"><span data-stu-id="ad0a7-116">Turn on preview features</span></span>

<span data-ttu-id="ad0a7-117">У вас будет доступ к предстоящим функциям, на которые можно предоставить обратную связь, чтобы улучшить общее впечатление до того, как функции будут доступны.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-117">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="ad0a7-118">Включите параметр предварительной версии, чтобы быть в числе тех, кто первым попробует новые функции.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-118">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="ad0a7-119">В области навигации выберите **Параметры**  >  **расширенные функции**  >  **Preview.**</span><span class="sxs-lookup"><span data-stu-id="ad0a7-119">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="ad0a7-120">Переключите параметр между **параметром "Включай** и **выключи"** и выберите **параметр Сохранить предпочтения.**</span><span class="sxs-lookup"><span data-stu-id="ad0a7-120">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="ad0a7-121">Функции предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="ad0a7-121">Preview features</span></span>

<span data-ttu-id="ad0a7-122">В предварительный выпуск добавлены следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="ad0a7-122">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="ad0a7-123">Фильтрация веб-контента</span><span class="sxs-lookup"><span data-stu-id="ad0a7-123">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="ad0a7-124">Фильтрация веб-контента является частью возможностей веб-защиты в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-124">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ad0a7-125">Это позволяет организации отслеживать и регулировать доступ к веб-сайтам в зависимости от их категорий контента.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-125">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="ad0a7-126">Многие из этих веб-сайтов, хотя и не являются вредоносными, могут быть проблематичными из-за правил соответствия требованиям, использования пропускной способности или других проблем.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-126">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="ad0a7-127">Отчет о состоянии и соответствии требованиям к устройству</span><span class="sxs-lookup"><span data-stu-id="ad0a7-127">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="ad0a7-128">Отчет о состоянии устройств и соответствие требованиям предоставляет информацию на высоком уровне о устройствах в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-128">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="ad0a7-129">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="ad0a7-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ad0a7-130">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="ad0a7-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
