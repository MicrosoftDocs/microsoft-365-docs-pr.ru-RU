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
ms.openlocfilehash: b33e6704a3311740c1e386f77f1c751382ee6958
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651096"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="b7079-103">Использование меток конфиденциальности в качестве условия в политиках защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="b7079-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="b7079-104">Использование [меток конфиденциальности](sensitivity-labels.md) в качестве условия в политиках защиты от потери данных для указанных ниже расположений.</span><span class="sxs-lookup"><span data-stu-id="b7079-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="b7079-105">Сообщения электронной почты Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b7079-105">Exchange Online email messages</span></span>
- <span data-ttu-id="b7079-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b7079-106">SharePoint Online</span></span>
- <span data-ttu-id="b7079-107">Сайты OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b7079-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="b7079-108">Устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="b7079-108">Windows 10 devices</span></span>

<span data-ttu-id="b7079-109">Метки конфиденциальности отображаются в качестве варианта в списке **Контент содержит**.</span><span class="sxs-lookup"><span data-stu-id="b7079-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b7079-110">![метка конфиденциальности в качестве условия](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="b7079-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7079-111">**Метки конфиденциальности** как условие будут недоступны, если вы выделили **чат и сообщения канала Teams** в качестве расположения, где необходимо применить политику защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="b7079-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="b7079-112">Поддерживаемые элементы, сценарии и подсказки политик</span><span class="sxs-lookup"><span data-stu-id="b7079-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="b7079-113">Метки чувствительности можно использовать в качестве условий для этих элементов и в таких сценариях.</span><span class="sxs-lookup"><span data-stu-id="b7079-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="b7079-114">Поддерживаемые элементы</span><span class="sxs-lookup"><span data-stu-id="b7079-114">Supported items</span></span>

|<span data-ttu-id="b7079-115">Служба</span><span class="sxs-lookup"><span data-stu-id="b7079-115">Service</span></span>  |<span data-ttu-id="b7079-116">Тип элемента</span><span class="sxs-lookup"><span data-stu-id="b7079-116">Item type</span></span>  |<span data-ttu-id="b7079-117">Доступно для подсказки политики</span><span class="sxs-lookup"><span data-stu-id="b7079-117">Available to policy tip</span></span>  |<span data-ttu-id="b7079-118">Применимо</span><span class="sxs-lookup"><span data-stu-id="b7079-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="b7079-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="b7079-119">Exchange</span></span>    |<span data-ttu-id="b7079-120">сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="b7079-120">email message</span></span>         |<span data-ttu-id="b7079-121">да</span><span class="sxs-lookup"><span data-stu-id="b7079-121">yes</span></span>         |<span data-ttu-id="b7079-122">да</span><span class="sxs-lookup"><span data-stu-id="b7079-122">yes</span></span>         |
|<span data-ttu-id="b7079-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="b7079-123">Exchange</span></span>    |<span data-ttu-id="b7079-124">вложение электронной почты</span><span class="sxs-lookup"><span data-stu-id="b7079-124">email attachment</span></span>         |<span data-ttu-id="b7079-125">нет</span><span class="sxs-lookup"><span data-stu-id="b7079-125">no</span></span>         |<span data-ttu-id="b7079-126">Да</span><span class="sxs-lookup"><span data-stu-id="b7079-126">yes \*</span></span>         |
|<span data-ttu-id="b7079-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b7079-127">SharePoint Online</span></span>     |<span data-ttu-id="b7079-128">элементы в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b7079-128">items in SharePoint Online</span></span>         |<span data-ttu-id="b7079-129">да</span><span class="sxs-lookup"><span data-stu-id="b7079-129">yes</span></span>         |<span data-ttu-id="b7079-130">да</span><span class="sxs-lookup"><span data-stu-id="b7079-130">yes</span></span>         |
|<span data-ttu-id="b7079-131">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b7079-131">OneDrive for Business</span></span>     |<span data-ttu-id="b7079-132">элементы</span><span class="sxs-lookup"><span data-stu-id="b7079-132">items</span></span>         |<span data-ttu-id="b7079-133">да</span><span class="sxs-lookup"><span data-stu-id="b7079-133">yes</span></span>         |<span data-ttu-id="b7079-134">да</span><span class="sxs-lookup"><span data-stu-id="b7079-134">yes</span></span>         |
|<span data-ttu-id="b7079-135">Teams</span><span class="sxs-lookup"><span data-stu-id="b7079-135">Teams</span></span>     |<span data-ttu-id="b7079-136">Teams и сообщения в каналах</span><span class="sxs-lookup"><span data-stu-id="b7079-136">Teams and channel messages</span></span>         |<span data-ttu-id="b7079-137">неприменимо</span><span class="sxs-lookup"><span data-stu-id="b7079-137">not applicable</span></span>         |<span data-ttu-id="b7079-138">неприменимо</span><span class="sxs-lookup"><span data-stu-id="b7079-138">not applicable</span></span>         |
|<span data-ttu-id="b7079-139">Teams</span><span class="sxs-lookup"><span data-stu-id="b7079-139">Teams</span></span>     |<span data-ttu-id="b7079-140">вложения</span><span class="sxs-lookup"><span data-stu-id="b7079-140">attachments</span></span>         |<span data-ttu-id="b7079-141">да</span><span class="sxs-lookup"><span data-stu-id="b7079-141">yes \*\*</span></span>         |<span data-ttu-id="b7079-142">да</span><span class="sxs-lookup"><span data-stu-id="b7079-142">yes \*\*</span></span>         |
|<span data-ttu-id="b7079-143">Устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="b7079-143">Windows 10 devices</span></span>     |<span data-ttu-id="b7079-144">элементы</span><span class="sxs-lookup"><span data-stu-id="b7079-144">items</span></span>         |<span data-ttu-id="b7079-145">да</span><span class="sxs-lookup"><span data-stu-id="b7079-145">yes</span></span>         |<span data-ttu-id="b7079-146">да</span><span class="sxs-lookup"><span data-stu-id="b7079-146">yes</span></span>         |
|<span data-ttu-id="b7079-147">МКАС (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="b7079-147">MCAS (preview)</span></span> |<span data-ttu-id="b7079-148">элементы</span><span class="sxs-lookup"><span data-stu-id="b7079-148">items</span></span>         |<span data-ttu-id="b7079-149">да</span><span class="sxs-lookup"><span data-stu-id="b7079-149">yes</span></span>         |<span data-ttu-id="b7079-150">да</span><span class="sxs-lookup"><span data-stu-id="b7079-150">yes</span></span>         |

<span data-ttu-id="b7079-151">\* DLP-обнаружение вложений с метками конфиденциальности поддерживается только для файлов Office.</span><span class="sxs-lookup"><span data-stu-id="b7079-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="b7079-152">\*\* Вложения, отправленные в Teams через личный чат или каналы, автоматически добавляются в OneDrive для бизнеса и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b7079-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="b7079-153">Таким образом, если SharePoint Online или OneDrive для бизнеса включены в качестве расположений в политику защиты от потери данных, вложения с метками, отправленные в Teams, автоматически включаются в область действия этого условия.</span><span class="sxs-lookup"><span data-stu-id="b7079-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="b7079-154">В политике защиты от потери данных Teams не обязательно выбирать в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="b7079-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="b7079-155">Поддерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="b7079-155">Supported scenarios</span></span>

- <span data-ttu-id="b7079-156">Администратор защиты от потери данных сможет видеть в клиенте список всех меток конфиденциальности, если включит одну или несколько меток конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="b7079-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="b7079-157">Использование меток конфиденциальности в качестве условия поддерживается во всех рабочих нагрузках, как указано в приведенной выше матрице поддержки.</span><span class="sxs-lookup"><span data-stu-id="b7079-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="b7079-158">Подсказки политики защиты от потери данных будут по-прежнему отображаться для рабочих нагрузок (за исключением Outlook Win32) для тех политик защиты от потери данных, в которых есть метка конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="b7079-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="b7079-159">Метки конфиденциальности также появляются в сообщении электронной почты с отчетом об инциденте в случае совпадения с политикой защиты от потери данных с меткой конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="b7079-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="b7079-160">Кроме того, подробности о метке конфиденциальности также отобразятся в журнале аудита соответствия правилам защиты от потери данных в случае совпадения с политикой защиты от потери данных, которая содержит пометку в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="b7079-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="b7079-161">Подсказки политики поддержки</span><span class="sxs-lookup"><span data-stu-id="b7079-161">Support policy tips</span></span>


|<span data-ttu-id="b7079-162">Рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="b7079-162">Workload</span></span>  |<span data-ttu-id="b7079-163">Подсказки политики поддерживаются / не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="b7079-163">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="b7079-164">OWA</span><span class="sxs-lookup"><span data-stu-id="b7079-164">OWA</span></span> |    <span data-ttu-id="b7079-165">поддерживается</span><span class="sxs-lookup"><span data-stu-id="b7079-165">supported</span></span>     |
|<span data-ttu-id="b7079-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="b7079-166">Outlook Win 32</span></span>    |  <span data-ttu-id="b7079-167">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="b7079-167">not supported</span></span>       |
|<span data-ttu-id="b7079-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b7079-168">SharePoint</span></span>   |   <span data-ttu-id="b7079-169">поддерживается</span><span class="sxs-lookup"><span data-stu-id="b7079-169">supported</span></span>      |
|<span data-ttu-id="b7079-170">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b7079-170">OneDrive for Business</span></span>    |    <span data-ttu-id="b7079-171">поддерживается</span><span class="sxs-lookup"><span data-stu-id="b7079-171">supported</span></span>     |
|<span data-ttu-id="b7079-172">устройства конечных точек</span><span class="sxs-lookup"><span data-stu-id="b7079-172">endpoint devices</span></span>   |  <span data-ttu-id="b7079-173">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="b7079-173">not supported</span></span>       |
