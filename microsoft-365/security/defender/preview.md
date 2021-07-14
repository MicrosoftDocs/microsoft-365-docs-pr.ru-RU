---
title: Функции предварительного просмотра в Microsoft 365 Defender
description: Сведения о новых функциях безопасности Microsoft 365
keywords: предварительная версия, новое, безопасность m365, безопасность, 365, возможности
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
ms.openlocfilehash: 088dbd16c3667331843ff934c80f85aa8d3a837f
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430820"
---
# <a name="microsoft-365-defender-preview-features"></a><span data-ttu-id="f7249-104">Microsoft 365 Defender функции предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="f7249-104">Microsoft 365 Defender preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f7249-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f7249-105">**Applies to:**</span></span>
- <span data-ttu-id="f7249-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7249-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f7249-107">Служба Microsoft 365 Defender постоянно обновляется, включая в нее новые возможности и возможности.</span><span class="sxs-lookup"><span data-stu-id="f7249-107">The Microsoft 365 Defender service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="f7249-108">Узнайте о новых функциях в Microsoft 365 Defender предварительного просмотра и одними из первых опробуйте предстоящие функции, включив функцию предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="f7249-108">Learn about new features in the Microsoft 365 Defender preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="f7249-109">Дополнительные сведения о новых возможностях, которые обычно доступны, см. в [Microsoft 365 Defender.](whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="f7249-109">For more information on new capabilities that are generally available, see [What's new in Microsoft 365 Defender](whats-new.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="f7249-110">Что нужно знать</span><span class="sxs-lookup"><span data-stu-id="f7249-110">What you need to know</span></span>

<span data-ttu-id="f7249-111">При работе с функциями в общедоступных предварительных просмотрах эти функции:</span><span class="sxs-lookup"><span data-stu-id="f7249-111">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="f7249-112">Может иметь ограниченные или ограниченные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="f7249-112">May have restricted or limited functionality.</span></span> <span data-ttu-id="f7249-113">Например, эта функция может применяться только к одной платформе.</span><span class="sxs-lookup"><span data-stu-id="f7249-113">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="f7249-114">Как правило, перед тем, как они будут доступны (GA), изменения функций проходят.</span><span class="sxs-lookup"><span data-stu-id="f7249-114">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="f7249-115">Полностью поддерживается Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f7249-115">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="f7249-116">Может быть доступно только в отдельных географических регионах или облачных средах.</span><span class="sxs-lookup"><span data-stu-id="f7249-116">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="f7249-117">Например, эта функция может не существовать в облаке правительства.</span><span class="sxs-lookup"><span data-stu-id="f7249-117">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="f7249-118">Отдельные функции в предварительном просмотре могут иметь больше ограничений на использование и поддержку.</span><span class="sxs-lookup"><span data-stu-id="f7249-118">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="f7249-119">Если это так, эти сведения обычно отмечаются в документации по функциям.</span><span class="sxs-lookup"><span data-stu-id="f7249-119">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="f7249-120">Предварительные версии обеспечиваются стандартным уровнем поддержки и могут использоваться для производственных сред.</span><span class="sxs-lookup"><span data-stu-id="f7249-120">The preview versions are provided with a standard support level, and can be used for production environments.</span></span> 



## <a name="required-permissions"></a><span data-ttu-id="f7249-121">Обязательные разрешения</span><span class="sxs-lookup"><span data-stu-id="f7249-121">Required permissions</span></span>

<span data-ttu-id="f7249-122">Учетные записи, задав следующие роли Azure Active Directory (Azure AD), могут включить функции Microsoft 365 Defender предварительного просмотра:</span><span class="sxs-lookup"><span data-stu-id="f7249-122">Accounts assigned the following Azure Active Directory (Azure AD) roles can turn on Microsoft 365 Defender Preview features:</span></span>

- <span data-ttu-id="f7249-123">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="f7249-123">Global administrator</span></span>
- <span data-ttu-id="f7249-124">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="f7249-124">Security administrator</span></span>
- <span data-ttu-id="f7249-125">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="f7249-125">Security Operator</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="f7249-126">Включение предварительных функций</span><span class="sxs-lookup"><span data-stu-id="f7249-126">Turn on preview features</span></span>

<span data-ttu-id="f7249-127">У вас будет доступ к предстоящим функциям, на которые можно предоставить обратную связь, чтобы улучшить общее впечатление до того, как функции будут доступны.</span><span class="sxs-lookup"><span data-stu-id="f7249-127">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="f7249-128">Включите параметр предварительной версии, чтобы быть в числе тех, кто первым попробует новые функции.</span><span class="sxs-lookup"><span data-stu-id="f7249-128">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="f7249-129">В области навигации выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="f7249-129">In the navigation pane, select **Settings**.</span></span>
2. <span data-ttu-id="f7249-130">Выберите **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="f7249-130">Select **Microsoft 365 Defender**.</span></span>
3. <span data-ttu-id="f7249-131">Выберите **Предварительные функции** > **Включить предварительные функции**.</span><span class="sxs-lookup"><span data-stu-id="f7249-131">Select **Preview features** > **Turn on preview features**.</span></span> 
4. <span data-ttu-id="f7249-132">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f7249-132">Select **Save**.</span></span>

<span data-ttu-id="f7249-133">Вы узнаете, что предварительные функции включены, когда увидите установленный флажок **Включить предварительные функции**.</span><span class="sxs-lookup"><span data-stu-id="f7249-133">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="f7249-134">Предварительные функции</span><span class="sxs-lookup"><span data-stu-id="f7249-134">Preview features</span></span>

<span data-ttu-id="f7249-135">В настоящий момент в предварительной версии доступны следующие функции и улучшения.</span><span class="sxs-lookup"><span data-stu-id="f7249-135">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="f7249-136">**[Просмотр отчетов по тегам](threat-analytics.md#view-reports-per-threat-tags)** угроз . Теги угроз помогают сосредоточиться на определенных категориях угроз и просмотреть наиболее релевантные отчеты.</span><span class="sxs-lookup"><span data-stu-id="f7249-136">**[View reports per threat tags](threat-analytics.md#view-reports-per-threat-tags)** - Threat tags help you focus on specific threat categories and review the most relevant reports.</span></span>
- <span data-ttu-id="f7249-137">**[Потоковый API](../defender-endpoint/raw-data-export.md)** Microsoft 365 Defender поддерживает потоковую трансляцию всех событий, доступных с помощью Advanced Hunting, в концентраторы событий и/или учетную запись хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="f7249-137">**[Streaming API](../defender-endpoint/raw-data-export.md)** - Microsoft 365 Defender supports streaming all the events available through Advanced Hunting to an Event Hubs and/or Azure storage account.</span></span>
- <span data-ttu-id="f7249-138">**[Microsoft 365 Defender API](api-overview.md)** — API верхнего уровня Microsoft 365 Defender позволяют автоматизировать рабочий процесс на основе общих таблиц инцидента и расширенных таблиц охоты.</span><span class="sxs-lookup"><span data-stu-id="f7249-138">**[Microsoft 365 Defender APIs](api-overview.md)** - The top-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span> 
- <span data-ttu-id="f7249-139">**[Примите меры в продвинутой охоте](advanced-hunting-take-action.md)** . Быстро сдержать угрозы или решить скомпрометированную активов, которые вы найдете в [продвинутой охоте](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f7249-139">**[Take action in advanced hunting](advanced-hunting-take-action.md)** - Quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md).</span></span>
- <span data-ttu-id="f7249-140">**[Ссылка на схему на](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** портале — сведения о таблицах расширенных схем охоты непосредственно в центре безопасности.</span><span class="sxs-lookup"><span data-stu-id="f7249-140">**[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - Get information about advanced hunting schema tables directly in the security center.</span></span> <span data-ttu-id="f7249-141">Помимо описаний таблиц и столбцов, эта ссылка включает поддерживаемые типы событий `ActionType` (значения) и примеры запросов.</span><span class="sxs-lookup"><span data-stu-id="f7249-141">In addition to table and column descriptions, this reference includes supported event types (`ActionType` values) and sample queries.</span></span>
- <span data-ttu-id="f7249-142">**[Функция DeviceFromIP()](advanced-hunting-devicefromip-function.md)** — получить сведения о том, какие устройства были назначены определенному IP-адресу или адресам в определенном диапазоне времени.</span><span class="sxs-lookup"><span data-stu-id="f7249-142">**[DeviceFromIP() function](advanced-hunting-devicefromip-function.md)** - Get information about which devices have been assigned a specific IP address or addresses at a given time range.</span></span>
