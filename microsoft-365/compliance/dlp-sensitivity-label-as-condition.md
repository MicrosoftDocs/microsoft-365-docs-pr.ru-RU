---
title: Использование меток конфиденциальности в качестве условия в политиках защиты от потери данных
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: сведения о службах и типах элементов, которые можно использовать метки конфиденциальности в качестве условий для политик защиты от потери данных
ms.openlocfilehash: 94d5e9f53471f6113dcc755995a3f94e95a58e53
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779847"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="da394-103">Использование меток конфиденциальности в качестве условия в политиках защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="da394-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="da394-104">Использование [меток конфиденциальности](sensitivity-labels.md) в качестве условия в политиках защиты от потери данных для указанных ниже расположений.</span><span class="sxs-lookup"><span data-stu-id="da394-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="da394-105">Сообщения электронной почты Exchange Online</span><span class="sxs-lookup"><span data-stu-id="da394-105">Exchange Online email messages</span></span>
- <span data-ttu-id="da394-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="da394-106">SharePoint Online</span></span>
- <span data-ttu-id="da394-107">Сайты OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="da394-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="da394-108">Устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="da394-108">Windows 10 devices</span></span>

<span data-ttu-id="da394-109">Метки конфиденциальности отображаются в качестве варианта в списке **Контент содержит**.</span><span class="sxs-lookup"><span data-stu-id="da394-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="da394-110">![метка конфиденциальности в качестве условия](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="da394-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da394-111">**Метки конфиденциальности** как условие будут недоступны, если вы выделили **чат и сообщения канала Teams** в качестве расположения, где необходимо применить политику защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="da394-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="da394-112">Поддерживаемые элементы, сценарии и подсказки политик</span><span class="sxs-lookup"><span data-stu-id="da394-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="da394-113">Метки чувствительности можно использовать в качестве условий для этих элементов и в таких сценариях.</span><span class="sxs-lookup"><span data-stu-id="da394-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="da394-114">Поддерживаемые элементы</span><span class="sxs-lookup"><span data-stu-id="da394-114">Supported items</span></span>

|<span data-ttu-id="da394-115">Служба</span><span class="sxs-lookup"><span data-stu-id="da394-115">Service</span></span>  |<span data-ttu-id="da394-116">Тип элемента</span><span class="sxs-lookup"><span data-stu-id="da394-116">Item type</span></span>  |<span data-ttu-id="da394-117">Доступно для подсказки политики</span><span class="sxs-lookup"><span data-stu-id="da394-117">Available to policy tip</span></span>  |<span data-ttu-id="da394-118">Применимо</span><span class="sxs-lookup"><span data-stu-id="da394-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="da394-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="da394-119">Exchange</span></span>    |<span data-ttu-id="da394-120">сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="da394-120">email message</span></span>         |<span data-ttu-id="da394-121">да</span><span class="sxs-lookup"><span data-stu-id="da394-121">yes</span></span>         |<span data-ttu-id="da394-122">да</span><span class="sxs-lookup"><span data-stu-id="da394-122">yes</span></span>         |
|<span data-ttu-id="da394-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="da394-123">Exchange</span></span>    |<span data-ttu-id="da394-124">вложение электронной почты</span><span class="sxs-lookup"><span data-stu-id="da394-124">email attachment</span></span>         |<span data-ttu-id="da394-125">нет</span><span class="sxs-lookup"><span data-stu-id="da394-125">no</span></span>         |<span data-ttu-id="da394-126">Да</span><span class="sxs-lookup"><span data-stu-id="da394-126">yes \*</span></span>         |
|<span data-ttu-id="da394-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="da394-127">SharePoint Online</span></span>     |<span data-ttu-id="da394-128">элементы в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="da394-128">items in SharePoint Online</span></span>         |<span data-ttu-id="da394-129">да</span><span class="sxs-lookup"><span data-stu-id="da394-129">yes</span></span>         |<span data-ttu-id="da394-130">да</span><span class="sxs-lookup"><span data-stu-id="da394-130">yes</span></span>         |
|<span data-ttu-id="da394-131">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="da394-131">OneDrive for Business</span></span>     |<span data-ttu-id="da394-132">элементы</span><span class="sxs-lookup"><span data-stu-id="da394-132">items</span></span>         |<span data-ttu-id="da394-133">да</span><span class="sxs-lookup"><span data-stu-id="da394-133">yes</span></span>         |<span data-ttu-id="da394-134">да</span><span class="sxs-lookup"><span data-stu-id="da394-134">yes</span></span>         |
|<span data-ttu-id="da394-135">Teams</span><span class="sxs-lookup"><span data-stu-id="da394-135">Teams</span></span>     |<span data-ttu-id="da394-136">Teams и сообщения в каналах</span><span class="sxs-lookup"><span data-stu-id="da394-136">Teams and channel messages</span></span>         |<span data-ttu-id="da394-137">неприменимо</span><span class="sxs-lookup"><span data-stu-id="da394-137">not applicable</span></span>         |<span data-ttu-id="da394-138">неприменимо</span><span class="sxs-lookup"><span data-stu-id="da394-138">not applicable</span></span>         |
|<span data-ttu-id="da394-139">Teams</span><span class="sxs-lookup"><span data-stu-id="da394-139">Teams</span></span>     |<span data-ttu-id="da394-140">вложения</span><span class="sxs-lookup"><span data-stu-id="da394-140">attachments</span></span>         |<span data-ttu-id="da394-141">да</span><span class="sxs-lookup"><span data-stu-id="da394-141">yes \*\*</span></span>         |<span data-ttu-id="da394-142">да</span><span class="sxs-lookup"><span data-stu-id="da394-142">yes \*\*</span></span>         |
|<span data-ttu-id="da394-143">Устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="da394-143">Windows 10 devices</span></span>     |<span data-ttu-id="da394-144">элементы</span><span class="sxs-lookup"><span data-stu-id="da394-144">items</span></span>         |<span data-ttu-id="da394-145">да</span><span class="sxs-lookup"><span data-stu-id="da394-145">yes</span></span>         |<span data-ttu-id="da394-146">да</span><span class="sxs-lookup"><span data-stu-id="da394-146">yes</span></span>         |
|<span data-ttu-id="da394-147">МКАС (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="da394-147">MCAS (preview)</span></span> |<span data-ttu-id="da394-148">элементы</span><span class="sxs-lookup"><span data-stu-id="da394-148">items</span></span>         |<span data-ttu-id="da394-149">да</span><span class="sxs-lookup"><span data-stu-id="da394-149">yes</span></span>         |<span data-ttu-id="da394-150">да</span><span class="sxs-lookup"><span data-stu-id="da394-150">yes</span></span>         |

<span data-ttu-id="da394-151">\* DLP-обнаружение вложений с метками конфиденциальности поддерживается только для файлов Office.</span><span class="sxs-lookup"><span data-stu-id="da394-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="da394-152">\*\* Вложения, отправленные в Teams через личный чат или каналы, автоматически добавляются в OneDrive для бизнеса и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="da394-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="da394-153">Таким образом, если SharePoint Online или OneDrive для бизнеса включены в качестве расположений в политику защиты от потери данных, вложения с метками, отправленные в Teams, автоматически включаются в область действия этого условия.</span><span class="sxs-lookup"><span data-stu-id="da394-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="da394-154">В политике защиты от потери данных Teams не обязательно выбирать в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="da394-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

> [!NOTE]
> <span data-ttu-id="da394-155">В DLP ограничена возможность обнаруживать метки конфиденциальности в SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="da394-155">DLP's ability to detect sensitivity labels in SharePoint and OneDrive for business is limited.</span></span> <span data-ttu-id="da394-156">Дополнительные сведения см. в статье [Включение меток конфиденциальности для файлов Office в SharePoint и OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations).</span><span class="sxs-lookup"><span data-stu-id="da394-156">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations).</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="da394-157">Поддерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="da394-157">Supported scenarios</span></span>

- <span data-ttu-id="da394-158">Администратор защиты от потери данных сможет видеть в клиенте список всех меток конфиденциальности, если включит одну или несколько меток конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="da394-158">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="da394-159">Использование меток конфиденциальности в качестве условия поддерживается во всех рабочих нагрузках, как указано в приведенной выше матрице поддержки.</span><span class="sxs-lookup"><span data-stu-id="da394-159">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="da394-160">Подсказки политики защиты от потери данных будут по-прежнему отображаться для рабочих нагрузок (за исключением Outlook Win32) для тех политик защиты от потери данных, в которых есть метка конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="da394-160">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="da394-161">Метки конфиденциальности также появляются в сообщении электронной почты с отчетом об инциденте в случае совпадения с политикой защиты от потери данных с меткой конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="da394-161">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="da394-162">Кроме того, подробности о метке конфиденциальности также отобразятся в журнале аудита соответствия правилам защиты от потери данных в случае совпадения с политикой защиты от потери данных, которая содержит пометку в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="da394-162">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="da394-163">Подсказки политики поддержки</span><span class="sxs-lookup"><span data-stu-id="da394-163">Support policy tips</span></span>


|<span data-ttu-id="da394-164">Рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="da394-164">Workload</span></span>  |<span data-ttu-id="da394-165">Подсказки политики поддерживаются / не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="da394-165">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="da394-166">OWA</span><span class="sxs-lookup"><span data-stu-id="da394-166">OWA</span></span> |    <span data-ttu-id="da394-167">поддерживается</span><span class="sxs-lookup"><span data-stu-id="da394-167">supported</span></span>     |
|<span data-ttu-id="da394-168">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="da394-168">Outlook Win 32</span></span>    |  <span data-ttu-id="da394-169">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="da394-169">not supported</span></span>       |
|<span data-ttu-id="da394-170">SharePoint</span><span class="sxs-lookup"><span data-stu-id="da394-170">SharePoint</span></span>   |   <span data-ttu-id="da394-171">поддерживается</span><span class="sxs-lookup"><span data-stu-id="da394-171">supported</span></span>      |
|<span data-ttu-id="da394-172">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="da394-172">OneDrive for Business</span></span>    |    <span data-ttu-id="da394-173">поддерживается</span><span class="sxs-lookup"><span data-stu-id="da394-173">supported</span></span>     |
|<span data-ttu-id="da394-174">устройства конечных точек</span><span class="sxs-lookup"><span data-stu-id="da394-174">endpoint devices</span></span>   |  <span data-ttu-id="da394-175">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="da394-175">not supported</span></span>       |
