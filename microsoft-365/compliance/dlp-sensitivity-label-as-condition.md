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
ms.openlocfilehash: 19bd80de225f703b5c280163e94826498fa097bd
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876298"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="730d1-103">Использование меток конфиденциальности в качестве условия в политиках защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="730d1-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="730d1-104">Использование [меток конфиденциальности](sensitivity-labels.md) в качестве условия в политиках защиты от потери данных для указанных ниже расположений.</span><span class="sxs-lookup"><span data-stu-id="730d1-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="730d1-105">Сообщения электронной почты Exchange Online</span><span class="sxs-lookup"><span data-stu-id="730d1-105">Exchange Online email messages</span></span>
- <span data-ttu-id="730d1-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="730d1-106">SharePoint Online</span></span>
- <span data-ttu-id="730d1-107">Сайты OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="730d1-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="730d1-108">Устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="730d1-108">Windows 10 devices</span></span>

<span data-ttu-id="730d1-109">Метки конфиденциальности отображаются в качестве варианта в списке **Контент содержит**.</span><span class="sxs-lookup"><span data-stu-id="730d1-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="730d1-110">![метка конфиденциальности в качестве условия](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="730d1-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="730d1-111">**Метки конфиденциальности** как условие будут недоступны, если вы выделили **чат и сообщения канала Teams** в качестве расположения, где необходимо применить политику защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="730d1-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="730d1-112">Поддерживаемые элементы, сценарии и подсказки политик</span><span class="sxs-lookup"><span data-stu-id="730d1-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="730d1-113">Метки чувствительности можно использовать в качестве условий для этих элементов и в таких сценариях.</span><span class="sxs-lookup"><span data-stu-id="730d1-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="730d1-114">Поддерживаемые элементы</span><span class="sxs-lookup"><span data-stu-id="730d1-114">Supported items</span></span>

|<span data-ttu-id="730d1-115">Служба</span><span class="sxs-lookup"><span data-stu-id="730d1-115">Service</span></span>  |<span data-ttu-id="730d1-116">Тип элемента</span><span class="sxs-lookup"><span data-stu-id="730d1-116">Item type</span></span>  |<span data-ttu-id="730d1-117">Доступно для подсказки политики</span><span class="sxs-lookup"><span data-stu-id="730d1-117">Available to policy tip</span></span>  |<span data-ttu-id="730d1-118">Применимо</span><span class="sxs-lookup"><span data-stu-id="730d1-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="730d1-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="730d1-119">Exchange</span></span>    |<span data-ttu-id="730d1-120">сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="730d1-120">email message</span></span>         |<span data-ttu-id="730d1-121">да</span><span class="sxs-lookup"><span data-stu-id="730d1-121">yes</span></span>         |<span data-ttu-id="730d1-122">да</span><span class="sxs-lookup"><span data-stu-id="730d1-122">yes</span></span>         |
|<span data-ttu-id="730d1-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="730d1-123">Exchange</span></span>    |<span data-ttu-id="730d1-124">вложение электронной почты</span><span class="sxs-lookup"><span data-stu-id="730d1-124">email attachment</span></span>         |<span data-ttu-id="730d1-125">Нет</span><span class="sxs-lookup"><span data-stu-id="730d1-125">no \*</span></span>         |<span data-ttu-id="730d1-126">Да</span><span class="sxs-lookup"><span data-stu-id="730d1-126">yes \*</span></span>         |
|<span data-ttu-id="730d1-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="730d1-127">SharePoint Online</span></span>     |<span data-ttu-id="730d1-128">элементы в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="730d1-128">items in SharePoint Online</span></span>         |<span data-ttu-id="730d1-129">да</span><span class="sxs-lookup"><span data-stu-id="730d1-129">yes</span></span>         |<span data-ttu-id="730d1-130">да</span><span class="sxs-lookup"><span data-stu-id="730d1-130">yes</span></span>         |
|<span data-ttu-id="730d1-131">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="730d1-131">OneDrive for Business</span></span>     |<span data-ttu-id="730d1-132">элементы</span><span class="sxs-lookup"><span data-stu-id="730d1-132">items</span></span>         |<span data-ttu-id="730d1-133">да</span><span class="sxs-lookup"><span data-stu-id="730d1-133">yes</span></span>         |<span data-ttu-id="730d1-134">да</span><span class="sxs-lookup"><span data-stu-id="730d1-134">yes</span></span>         |
|<span data-ttu-id="730d1-135">Teams</span><span class="sxs-lookup"><span data-stu-id="730d1-135">Teams</span></span>     |<span data-ttu-id="730d1-136">Teams и сообщения в каналах</span><span class="sxs-lookup"><span data-stu-id="730d1-136">Teams and channel messages</span></span>         |<span data-ttu-id="730d1-137">неприменимо</span><span class="sxs-lookup"><span data-stu-id="730d1-137">not applicable</span></span>         |<span data-ttu-id="730d1-138">неприменимо</span><span class="sxs-lookup"><span data-stu-id="730d1-138">not applicable</span></span>         |
|<span data-ttu-id="730d1-139">Teams</span><span class="sxs-lookup"><span data-stu-id="730d1-139">Teams</span></span>     |<span data-ttu-id="730d1-140">вложения</span><span class="sxs-lookup"><span data-stu-id="730d1-140">attachments</span></span>         |<span data-ttu-id="730d1-141">да</span><span class="sxs-lookup"><span data-stu-id="730d1-141">yes \*\*</span></span>         |<span data-ttu-id="730d1-142">да</span><span class="sxs-lookup"><span data-stu-id="730d1-142">yes \*\*</span></span>         |
|<span data-ttu-id="730d1-143">Устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="730d1-143">Windows 10 devices</span></span>     |<span data-ttu-id="730d1-144">элементы</span><span class="sxs-lookup"><span data-stu-id="730d1-144">items</span></span>         |<span data-ttu-id="730d1-145">да</span><span class="sxs-lookup"><span data-stu-id="730d1-145">yes</span></span>         |<span data-ttu-id="730d1-146">да</span><span class="sxs-lookup"><span data-stu-id="730d1-146">yes</span></span>         |
|<span data-ttu-id="730d1-147">МКАС (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="730d1-147">MCAS (preview)</span></span> |<span data-ttu-id="730d1-148">элементы</span><span class="sxs-lookup"><span data-stu-id="730d1-148">items</span></span>         |<span data-ttu-id="730d1-149">да</span><span class="sxs-lookup"><span data-stu-id="730d1-149">yes</span></span>         |<span data-ttu-id="730d1-150">да</span><span class="sxs-lookup"><span data-stu-id="730d1-150">yes</span></span>         |

<span data-ttu-id="730d1-151">\* Обнаружение DLP и обеспечение использования меток конфиденциальности для сообщений электронной почты и вложений поддерживаются в процессе.</span><span class="sxs-lookup"><span data-stu-id="730d1-151">\* DLP detection and enforcement of sensitivity labels on emails and attachments are supported in-transit.</span></span> <span data-ttu-id="730d1-152">Подсказки политики защиты от потери данных вложений электронной почты с метками конфиденциальности не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="730d1-152">DLP policy tips of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="730d1-153">\*\* Вложения, отправленные в Teams через личный чат или каналы, автоматически добавляются в OneDrive для бизнеса и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="730d1-153">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="730d1-154">Таким образом, если SharePoint Online или OneDrive для бизнеса включены в качестве расположений в политику защиты от потери данных, вложения с метками, отправленные в Teams, автоматически включаются в область действия этого условия.</span><span class="sxs-lookup"><span data-stu-id="730d1-154">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="730d1-155">В политике защиты от потери данных Teams не обязательно выбирать в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="730d1-155">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="730d1-156">Поддерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="730d1-156">Supported scenarios</span></span>

- <span data-ttu-id="730d1-157">Администратор защиты от потери данных сможет видеть в клиенте список всех меток конфиденциальности, если включит одну или несколько меток конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="730d1-157">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="730d1-158">Использование меток конфиденциальности в качестве условия поддерживается во всех рабочих нагрузках, как указано в приведенной выше матрице поддержки.</span><span class="sxs-lookup"><span data-stu-id="730d1-158">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="730d1-159">Подсказки политики защиты от потери данных будут по-прежнему отображаться для рабочих нагрузок (за исключением Outlook Win32) для тех политик защиты от потери данных, в которых есть метка конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="730d1-159">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="730d1-160">Метки конфиденциальности также появляются в сообщении электронной почты с отчетом об инциденте в случае совпадения с политикой защиты от потери данных с меткой конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="730d1-160">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="730d1-161">Кроме того, подробности о метке конфиденциальности также отобразятся в журнале аудита соответствия правилам защиты от потери данных в случае совпадения с политикой защиты от потери данных, которая содержит пометку в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="730d1-161">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="730d1-162">Подсказки политики поддержки</span><span class="sxs-lookup"><span data-stu-id="730d1-162">Support policy tips</span></span>


|<span data-ttu-id="730d1-163">Рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="730d1-163">Workload</span></span>  |<span data-ttu-id="730d1-164">Подсказки политики поддерживаются / не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="730d1-164">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="730d1-165">OWA</span><span class="sxs-lookup"><span data-stu-id="730d1-165">OWA</span></span> |    <span data-ttu-id="730d1-166">поддерживается</span><span class="sxs-lookup"><span data-stu-id="730d1-166">supported</span></span>     |
|<span data-ttu-id="730d1-167">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="730d1-167">Outlook Win 32</span></span>    |  <span data-ttu-id="730d1-168">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="730d1-168">not supported</span></span>       |
|<span data-ttu-id="730d1-169">SharePoint</span><span class="sxs-lookup"><span data-stu-id="730d1-169">SharePoint</span></span>   |   <span data-ttu-id="730d1-170">поддерживается</span><span class="sxs-lookup"><span data-stu-id="730d1-170">supported</span></span>      |
|<span data-ttu-id="730d1-171">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="730d1-171">OneDrive for Business</span></span>    |    <span data-ttu-id="730d1-172">поддерживается</span><span class="sxs-lookup"><span data-stu-id="730d1-172">supported</span></span>     |
|<span data-ttu-id="730d1-173">устройства конечных точек</span><span class="sxs-lookup"><span data-stu-id="730d1-173">endpoint devices</span></span>   |  <span data-ttu-id="730d1-174">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="730d1-174">not supported</span></span>       |
