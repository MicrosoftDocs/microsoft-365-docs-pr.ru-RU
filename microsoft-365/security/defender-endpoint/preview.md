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
ms.openlocfilehash: 0b6edbdcda61eaf402275ae0b6dc9a38c5fe19f7
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339494"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="21343-104">Функции предварительного просмотра в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="21343-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="21343-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="21343-105">**Applies to:**</span></span>
- [<span data-ttu-id="21343-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="21343-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="21343-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21343-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="21343-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="21343-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="21343-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="21343-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="21343-110">Служба Defender for Endpoint постоянно обновляется, чтобы включить новые возможности и возможности.</span><span class="sxs-lookup"><span data-stu-id="21343-110">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="21343-111">Узнайте о новых функциях в выпуске предварительного просмотра Defender для конечной точки и одними из первых попробуйте новые функции, включив функцию предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="21343-111">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="21343-112">Получите уведомление, когда эта страница обновляется путем копирования и вклейки следующего URL-адреса в читателя каналов: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="21343-112">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="21343-113">Дополнительные сведения о новых возможностях, которые, как правило, доступны, см. в дополнительных сведениях о новых возможностях [в Defender для конечной точки.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="21343-113">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="21343-114">Что нужно знать</span><span class="sxs-lookup"><span data-stu-id="21343-114">What you need to know</span></span>

<span data-ttu-id="21343-115">При работе с функциями в общедоступных предварительных просмотрах эти функции:</span><span class="sxs-lookup"><span data-stu-id="21343-115">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="21343-116">Может иметь ограниченные или ограниченные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="21343-116">May have restricted or limited functionality.</span></span> <span data-ttu-id="21343-117">Например, эта функция может применяться только к одной платформе.</span><span class="sxs-lookup"><span data-stu-id="21343-117">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="21343-118">Как правило, перед тем, как они будут доступны (GA), изменения функций проходят.</span><span class="sxs-lookup"><span data-stu-id="21343-118">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="21343-119">Полностью поддерживается Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="21343-119">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="21343-120">Может быть доступно только в отдельных географических регионах или облачных средах.</span><span class="sxs-lookup"><span data-stu-id="21343-120">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="21343-121">Например, эта функция может не существовать в облаке правительства.</span><span class="sxs-lookup"><span data-stu-id="21343-121">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="21343-122">Отдельные функции в предварительном просмотре могут иметь больше ограничений на использование и поддержку.</span><span class="sxs-lookup"><span data-stu-id="21343-122">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="21343-123">Если это так, эти сведения обычно отмечаются в документации по функциям.</span><span class="sxs-lookup"><span data-stu-id="21343-123">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="21343-124">Предварительные версии обеспечиваются стандартным уровнем поддержки и могут использоваться для производственных сред.</span><span class="sxs-lookup"><span data-stu-id="21343-124">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="turn-on-preview-features"></a><span data-ttu-id="21343-125">Включение предварительных функций</span><span class="sxs-lookup"><span data-stu-id="21343-125">Turn on preview features</span></span>

<span data-ttu-id="21343-126">У вас будет доступ к предстоящим функциям, на которые можно предоставить обратную связь, чтобы улучшить общее впечатление до того, как функции будут доступны.</span><span class="sxs-lookup"><span data-stu-id="21343-126">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="21343-127">Включите параметр предварительной версии, чтобы быть в числе тех, кто первым попробует новые функции.</span><span class="sxs-lookup"><span data-stu-id="21343-127">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="21343-128">В области навигации выберите **Параметры**  >  **расширенные функции**  >  **Preview.**</span><span class="sxs-lookup"><span data-stu-id="21343-128">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="21343-129">Переключите параметр между **параметром "Включай** и **выключи"** и выберите **параметр Сохранить предпочтения.**</span><span class="sxs-lookup"><span data-stu-id="21343-129">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="21343-130">Функции предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="21343-130">Preview features</span></span>

<span data-ttu-id="21343-131">В предварительный выпуск добавлены следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="21343-131">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="21343-132">Фильтрация веб-контента</span><span class="sxs-lookup"><span data-stu-id="21343-132">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="21343-133">Фильтрация веб-контента является частью возможностей веб-защиты в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="21343-133">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="21343-134">Это позволяет организации отслеживать и регулировать доступ к веб-сайтам в зависимости от их категорий контента.</span><span class="sxs-lookup"><span data-stu-id="21343-134">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="21343-135">Многие из этих веб-сайтов, хотя и не являются вредоносными, могут быть проблематичными из-за правил соответствия требованиям, использования пропускной способности или других проблем.</span><span class="sxs-lookup"><span data-stu-id="21343-135">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="21343-136">Отчеты о работоспособности устройств и соответствии требованиям</span><span class="sxs-lookup"><span data-stu-id="21343-136">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="21343-137">Отчет о состоянии устройств и соответствие требованиям предоставляет информацию на высоком уровне о устройствах в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="21343-137">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="21343-138">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="21343-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="21343-139">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="21343-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
