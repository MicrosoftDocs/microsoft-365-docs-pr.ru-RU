---
title: Функции предварительного просмотра ATP Защитника Майкрософт
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
ms.openlocfilehash: 370048586c5ddfa6fa9ea265e929608357adf5df
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186885"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="03db6-104">Функции предварительного просмотра в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="03db6-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="03db6-105">Предварительные версии предоставляются без соглашения об уровне обслуживания и не рекомендуется для рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="03db6-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="03db6-106">Некоторые функции могут не поддерживаться или иметь ограниченные возможности.</span><span class="sxs-lookup"><span data-stu-id="03db6-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="03db6-107">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="03db6-107">**Applies to:**</span></span>
- [<span data-ttu-id="03db6-108">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="03db6-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="03db6-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03db6-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="03db6-110">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="03db6-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="03db6-111">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="03db6-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="03db6-112">Служба Defender for Endpoint постоянно обновляется, чтобы включить новые возможности и возможности.</span><span class="sxs-lookup"><span data-stu-id="03db6-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

> [!TIP]
> <span data-ttu-id="03db6-113">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="03db6-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="03db6-114">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="03db6-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-abovefoldlink)

<span data-ttu-id="03db6-115">Узнайте о новых функциях в выпуске предварительного просмотра Defender для конечной точки и одними из первых попробуйте новые функции, включив функцию предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="03db6-115">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="03db6-116">Получите уведомление, когда эта страница обновляется путем копирования и вклейки следующего URL-адреса в читателя каналов: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span><span class="sxs-lookup"><span data-stu-id="03db6-116">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span></span>

<span data-ttu-id="03db6-117">Дополнительные сведения о новых возможностях, которые, как правило, доступны, см. в дополнительных сведениях о новых возможностях [в Defender для конечной точки.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="03db6-117">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="03db6-118">Включение предварительных функций</span><span class="sxs-lookup"><span data-stu-id="03db6-118">Turn on preview features</span></span>

<span data-ttu-id="03db6-119">У вас будет доступ к предстоящим функциям, на которые можно предоставить обратную связь, чтобы улучшить общее впечатление до того, как функции будут доступны.</span><span class="sxs-lookup"><span data-stu-id="03db6-119">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="03db6-120">Включите параметр предварительной версии, чтобы быть в числе тех, кто первым попробует новые функции.</span><span class="sxs-lookup"><span data-stu-id="03db6-120">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="03db6-121">В области навигации выберите **параметры**  >  **Расширенные функции**  >  **Preview.**</span><span class="sxs-lookup"><span data-stu-id="03db6-121">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="03db6-122">Переключите параметр между **параметром "Включай** и **выключи"** и выберите **параметр Сохранить предпочтения.**</span><span class="sxs-lookup"><span data-stu-id="03db6-122">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="03db6-123">Функции предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="03db6-123">Preview features</span></span>

<span data-ttu-id="03db6-124">В предварительный выпуск добавлены следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="03db6-124">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="03db6-125">Фильтрация веб-контента</span><span class="sxs-lookup"><span data-stu-id="03db6-125">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="03db6-126">Фильтрация веб-контента является частью возможностей веб-защиты в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="03db6-126">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="03db6-127">Это позволяет организации отслеживать и регулировать доступ к веб-сайтам в зависимости от их категорий контента.</span><span class="sxs-lookup"><span data-stu-id="03db6-127">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="03db6-128">Многие из этих веб-сайтов, хотя и не являются вредоносными, могут быть проблематичными из-за правил соответствия требованиям, использования пропускной способности или других проблем.</span><span class="sxs-lookup"><span data-stu-id="03db6-128">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="03db6-129">Отчет о состоянии и соответствии требованиям к устройству</span><span class="sxs-lookup"><span data-stu-id="03db6-129">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="03db6-130">Отчет о состоянии устройств и соответствие требованиям предоставляет информацию на высоком уровне о устройствах в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="03db6-130">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

- [<span data-ttu-id="03db6-131">Защита информации</span><span class="sxs-lookup"><span data-stu-id="03db6-131">Information protection</span></span>](information-protection-in-windows-overview.md)<BR>
<span data-ttu-id="03db6-132">Защита информации является неотъемлемой частью пакета Microsoft 365 Enterprise, обеспечивая интеллектуальную защиту для обеспечения безопасности конфиденциальных данных, обеспечивая при этом производительность на рабочем месте.</span><span class="sxs-lookup"><span data-stu-id="03db6-132">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span> <span data-ttu-id="03db6-133">Microsoft Defender для конечной точки интегрирована в Microsoft Threat Protection, чтобы обеспечить полное и комплексное решение по предотвращению потери данных (DLP) для устройств Windows.</span><span class="sxs-lookup"><span data-stu-id="03db6-133">Microsoft Defender for Endpoint is seamlessly integrated in Microsoft Threat Protection to provide a complete and comprehensive data loss prevention (DLP) solution for Windows devices.</span></span>

    >[!NOTE]
    ><span data-ttu-id="03db6-134">Частично доступна в Windows 10 версии 1809.</span><span class="sxs-lookup"><span data-stu-id="03db6-134">Partially available from Windows 10, version 1809.</span></span>

- [<span data-ttu-id="03db6-135">На борту Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="03db6-135">Onboard Windows Server 2019</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-version-1803-and-windows-server-2019) <BR> <span data-ttu-id="03db6-136">Microsoft Defender для конечной точки теперь добавляет поддержку Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="03db6-136">Microsoft Defender for Endpoint now adds support for Windows Server 2019.</span></span> <span data-ttu-id="03db6-137">Вы сможете использовать Windows Server 2019 в том же методе, который доступен для клиентских устройств Windows 10.</span><span class="sxs-lookup"><span data-stu-id="03db6-137">You'll be able to onboard Windows Server 2019 in the same method available for Windows 10 client devices.</span></span>


> [!TIP] 
> <span data-ttu-id="03db6-138">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="03db6-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="03db6-139">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="03db6-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
