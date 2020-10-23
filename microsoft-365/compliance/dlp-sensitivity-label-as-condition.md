---
title: Использование меток конфиденциальности в качестве условия в политиках защиты от потери данных (предварительная версия)
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
ms.openlocfilehash: 2f8eb30e23d722a5e8faf7d0ddaca6b9a94e279b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649638"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="83b56-103">Использование меток конфиденциальности в качестве условия в политиках защиты от потери данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="83b56-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="83b56-104">Использование [меток конфиденциальности](sensitivity-labels.md) в качестве условия в политиках защиты от потери данных для указанных ниже расположений.</span><span class="sxs-lookup"><span data-stu-id="83b56-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="83b56-105">Сообщения электронной почты Exchange Online</span><span class="sxs-lookup"><span data-stu-id="83b56-105">Exchange Online email messages</span></span>
- <span data-ttu-id="83b56-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="83b56-106">SharePoint Online</span></span>
- <span data-ttu-id="83b56-107">Сайты OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="83b56-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="83b56-108">Устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="83b56-108">Windows 10 devices</span></span>

<span data-ttu-id="83b56-109">Метки конфиденциальности отображаются в качестве варианта в списке **Контент содержит**.</span><span class="sxs-lookup"><span data-stu-id="83b56-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="83b56-110">![метка конфиденциальности в качестве условия](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="83b56-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83b56-111">**Метки конфиденциальности** как условие будут недоступны, если вы выделили \*\*чат и сообщения канала Teams \*\*в качестве расположения, где необходимо применить политику защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="83b56-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="83b56-112">Поддерживаемые элементы, сценарии и подсказки политик</span><span class="sxs-lookup"><span data-stu-id="83b56-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="83b56-113">Метки чувствительности можно использовать в качестве условий для этих элементов и в таких сценариях.</span><span class="sxs-lookup"><span data-stu-id="83b56-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="83b56-114">Поддерживаемые элементы</span><span class="sxs-lookup"><span data-stu-id="83b56-114">Supported items</span></span>

|<span data-ttu-id="83b56-115">Служба</span><span class="sxs-lookup"><span data-stu-id="83b56-115">Service</span></span>  |<span data-ttu-id="83b56-116">Тип элемента</span><span class="sxs-lookup"><span data-stu-id="83b56-116">Item type</span></span>  |<span data-ttu-id="83b56-117">Доступно для подсказки политики</span><span class="sxs-lookup"><span data-stu-id="83b56-117">Available to policy tip</span></span>  |<span data-ttu-id="83b56-118">Применимо</span><span class="sxs-lookup"><span data-stu-id="83b56-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="83b56-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="83b56-119">Exchange</span></span>    |<span data-ttu-id="83b56-120">сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="83b56-120">email message</span></span>         |<span data-ttu-id="83b56-121">да</span><span class="sxs-lookup"><span data-stu-id="83b56-121">yes</span></span>         |<span data-ttu-id="83b56-122">да</span><span class="sxs-lookup"><span data-stu-id="83b56-122">yes</span></span>         |
|<span data-ttu-id="83b56-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="83b56-123">Exchange</span></span>    |<span data-ttu-id="83b56-124">вложение электронной почты</span><span class="sxs-lookup"><span data-stu-id="83b56-124">email attachment</span></span>         |<span data-ttu-id="83b56-125">Нет</span><span class="sxs-lookup"><span data-stu-id="83b56-125">no \*</span></span>         |<span data-ttu-id="83b56-126">Нет</span><span class="sxs-lookup"><span data-stu-id="83b56-126">no \*</span></span>         |
|<span data-ttu-id="83b56-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="83b56-127">SharePoint Online</span></span>     |<span data-ttu-id="83b56-128">элементы в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="83b56-128">items in SharePoint Online</span></span>         |<span data-ttu-id="83b56-129">да</span><span class="sxs-lookup"><span data-stu-id="83b56-129">yes</span></span>         |<span data-ttu-id="83b56-130">да</span><span class="sxs-lookup"><span data-stu-id="83b56-130">yes</span></span>         |
|<span data-ttu-id="83b56-131">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="83b56-131">OneDrive for Business</span></span>     |<span data-ttu-id="83b56-132">элементы</span><span class="sxs-lookup"><span data-stu-id="83b56-132">items</span></span>         |<span data-ttu-id="83b56-133">да</span><span class="sxs-lookup"><span data-stu-id="83b56-133">yes</span></span>         |<span data-ttu-id="83b56-134">да</span><span class="sxs-lookup"><span data-stu-id="83b56-134">yes</span></span>         |
|<span data-ttu-id="83b56-135">Teams</span><span class="sxs-lookup"><span data-stu-id="83b56-135">Teams</span></span>     |<span data-ttu-id="83b56-136">Teams и сообщения в каналах</span><span class="sxs-lookup"><span data-stu-id="83b56-136">Teams and channel messages</span></span>         |<span data-ttu-id="83b56-137">неприменимо</span><span class="sxs-lookup"><span data-stu-id="83b56-137">not applicable</span></span>         |<span data-ttu-id="83b56-138">неприменимо</span><span class="sxs-lookup"><span data-stu-id="83b56-138">not applicable</span></span>         |
|<span data-ttu-id="83b56-139">Teams</span><span class="sxs-lookup"><span data-stu-id="83b56-139">Teams</span></span>     |<span data-ttu-id="83b56-140">вложения</span><span class="sxs-lookup"><span data-stu-id="83b56-140">attachments</span></span>         |<span data-ttu-id="83b56-141">да</span><span class="sxs-lookup"><span data-stu-id="83b56-141">yes \*\*</span></span>         |<span data-ttu-id="83b56-142">да</span><span class="sxs-lookup"><span data-stu-id="83b56-142">yes \*\*</span></span>         |
|<span data-ttu-id="83b56-143">Устройства с Windows 10 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="83b56-143">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="83b56-144">элементы</span><span class="sxs-lookup"><span data-stu-id="83b56-144">items</span></span>         |<span data-ttu-id="83b56-145">да</span><span class="sxs-lookup"><span data-stu-id="83b56-145">yes</span></span>         |<span data-ttu-id="83b56-146">да</span><span class="sxs-lookup"><span data-stu-id="83b56-146">yes</span></span>         |
|<span data-ttu-id="83b56-147">МКАС (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="83b56-147">MCAS (preview)</span></span> |<span data-ttu-id="83b56-148">элементы</span><span class="sxs-lookup"><span data-stu-id="83b56-148">items</span></span>         |<span data-ttu-id="83b56-149">да</span><span class="sxs-lookup"><span data-stu-id="83b56-149">yes</span></span>         |<span data-ttu-id="83b56-150">да</span><span class="sxs-lookup"><span data-stu-id="83b56-150">yes</span></span>         |

<span data-ttu-id="83b56-151">Поддерживается обнаружение защитой от потери данных \* меток конфиденциальности на сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="83b56-151">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="83b56-152">Обнаружение защитой от потери данных вложений с метками конфиденциальности не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="83b56-152">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="83b56-153">\*\* Вложения, отправленные в Teams через личный чат или каналы, автоматически добавляются в OneDrive для бизнеса и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="83b56-153">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="83b56-154">Таким образом, если SharePoint Online или OneDrive для бизнеса включены в качестве расположений в политику защиты от потери данных, вложения с метками, отправленные в Teams, автоматически включаются в область действия этого условия.</span><span class="sxs-lookup"><span data-stu-id="83b56-154">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="83b56-155">В политике защиты от потери данных Teams не обязательно выбирать в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="83b56-155">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="83b56-156">Поддерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="83b56-156">Supported scenarios</span></span>

- <span data-ttu-id="83b56-157">Администратор защиты от потери данных сможет видеть в клиенте список всех меток конфиденциальности, если включит одну или несколько меток конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="83b56-157">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="83b56-158">Использование меток конфиденциальности в качестве условия поддерживается во всех рабочих нагрузках, как указано в приведенной выше матрице поддержки.</span><span class="sxs-lookup"><span data-stu-id="83b56-158">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="83b56-159">Подсказки политики защиты от потери данных будут по-прежнему отображаться для рабочих нагрузок (за исключением Outlook Win32) для тех политик защиты от потери данных, в которых есть метка конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="83b56-159">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="83b56-160">Метки конфиденциальности также появляются в сообщении электронной почты с отчетом об инциденте в случае совпадения с политикой защиты от потери данных с меткой конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="83b56-160">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="83b56-161">Кроме того, подробности о метке конфиденциальности также отобразятся в журнале аудита соответствия правилам защиты от потери данных в случае совпадения с политикой защиты от потери данных, которая содержит пометку в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="83b56-161">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="83b56-162">Подсказки политики поддержки</span><span class="sxs-lookup"><span data-stu-id="83b56-162">Support policy tips</span></span>


|<span data-ttu-id="83b56-163">Рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="83b56-163">Workload</span></span>  |<span data-ttu-id="83b56-164">Подсказки политики поддерживаются / не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="83b56-164">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="83b56-165">OWA</span><span class="sxs-lookup"><span data-stu-id="83b56-165">OWA</span></span> |    <span data-ttu-id="83b56-166">поддерживается</span><span class="sxs-lookup"><span data-stu-id="83b56-166">supported</span></span>     |
|<span data-ttu-id="83b56-167">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="83b56-167">Outlook Win 32</span></span>    |  <span data-ttu-id="83b56-168">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="83b56-168">not supported</span></span>       |
|<span data-ttu-id="83b56-169">SharePoint</span><span class="sxs-lookup"><span data-stu-id="83b56-169">SharePoint</span></span>   |   <span data-ttu-id="83b56-170">поддерживается</span><span class="sxs-lookup"><span data-stu-id="83b56-170">supported</span></span>      |
|<span data-ttu-id="83b56-171">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="83b56-171">OneDrive for Business</span></span>    |    <span data-ttu-id="83b56-172">поддерживается</span><span class="sxs-lookup"><span data-stu-id="83b56-172">supported</span></span>     |
|<span data-ttu-id="83b56-173">устройства конечных точек</span><span class="sxs-lookup"><span data-stu-id="83b56-173">endpoint devices</span></span>   |  <span data-ttu-id="83b56-174">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="83b56-174">not supported</span></span>       |
