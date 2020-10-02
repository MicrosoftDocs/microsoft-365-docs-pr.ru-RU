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
ms.openlocfilehash: 561a6cbd7b8aeb9082862319c5cc6419fd79c896
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321114"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="a9d22-103">Использование меток конфиденциальности в качестве условия в политиках защиты от потери данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a9d22-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="a9d22-104">Использование [меток конфиденциальности](sensitivity-labels.md) в качестве условия в политиках защиты от потери данных для указанных ниже расположений.</span><span class="sxs-lookup"><span data-stu-id="a9d22-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="a9d22-105">Сообщения электронной почты Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a9d22-105">Exchange Online email messages</span></span>
- <span data-ttu-id="a9d22-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a9d22-106">SharePoint Online</span></span>
- <span data-ttu-id="a9d22-107">Сайты OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a9d22-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="a9d22-108">Устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="a9d22-108">Windows 10 devices</span></span>

<span data-ttu-id="a9d22-109">Метки конфиденциальности отображаются в качестве варианта в списке **Контент содержит**.</span><span class="sxs-lookup"><span data-stu-id="a9d22-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![метка конфиденциальности в качестве условия](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="a9d22-111">Поддерживаемые элементы, сценарии и подсказки политик</span><span class="sxs-lookup"><span data-stu-id="a9d22-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="a9d22-112">Метки чувствительности можно использовать в качестве условий для этих элементов и в таких сценариях.</span><span class="sxs-lookup"><span data-stu-id="a9d22-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="a9d22-113">Поддерживаемые элементы</span><span class="sxs-lookup"><span data-stu-id="a9d22-113">Supported items</span></span>

|<span data-ttu-id="a9d22-114">служба</span><span class="sxs-lookup"><span data-stu-id="a9d22-114">service</span></span>  |<span data-ttu-id="a9d22-115">тип элемента</span><span class="sxs-lookup"><span data-stu-id="a9d22-115">item type</span></span>  |<span data-ttu-id="a9d22-116">доступно для подсказки политики</span><span class="sxs-lookup"><span data-stu-id="a9d22-116">available to policy tip</span></span>  |<span data-ttu-id="a9d22-117">применимо</span><span class="sxs-lookup"><span data-stu-id="a9d22-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="a9d22-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="a9d22-118">Exchange</span></span>    |<span data-ttu-id="a9d22-119">сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="a9d22-119">email message</span></span>         |<span data-ttu-id="a9d22-120">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-120">yes</span></span>         |<span data-ttu-id="a9d22-121">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-121">yes</span></span>         |
|<span data-ttu-id="a9d22-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="a9d22-122">Exchange</span></span>    |<span data-ttu-id="a9d22-123">вложение электронной почты</span><span class="sxs-lookup"><span data-stu-id="a9d22-123">email attachment</span></span>         |<span data-ttu-id="a9d22-124">Нет</span><span class="sxs-lookup"><span data-stu-id="a9d22-124">no \*</span></span>         |<span data-ttu-id="a9d22-125">Нет</span><span class="sxs-lookup"><span data-stu-id="a9d22-125">no \*</span></span>         |
|<span data-ttu-id="a9d22-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a9d22-126">SharePoint Online</span></span>     |<span data-ttu-id="a9d22-127">элементы в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a9d22-127">items in SharePoint Online</span></span>         |<span data-ttu-id="a9d22-128">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-128">yes</span></span>         |<span data-ttu-id="a9d22-129">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-129">yes</span></span>         |
|<span data-ttu-id="a9d22-130">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a9d22-130">OneDrive for Business</span></span>     |<span data-ttu-id="a9d22-131">элементы</span><span class="sxs-lookup"><span data-stu-id="a9d22-131">items</span></span>         |<span data-ttu-id="a9d22-132">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-132">yes</span></span>         |<span data-ttu-id="a9d22-133">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-133">yes</span></span>         |
|<span data-ttu-id="a9d22-134">Teams</span><span class="sxs-lookup"><span data-stu-id="a9d22-134">Teams</span></span>     |<span data-ttu-id="a9d22-135">Teams и сообщения в каналах</span><span class="sxs-lookup"><span data-stu-id="a9d22-135">Teams and channel messages</span></span>         |<span data-ttu-id="a9d22-136">неприменимо</span><span class="sxs-lookup"><span data-stu-id="a9d22-136">not applicable</span></span>         |<span data-ttu-id="a9d22-137">неприменимо</span><span class="sxs-lookup"><span data-stu-id="a9d22-137">not applicable</span></span>         |
|<span data-ttu-id="a9d22-138">Teams</span><span class="sxs-lookup"><span data-stu-id="a9d22-138">Teams</span></span>     |<span data-ttu-id="a9d22-139">вложения</span><span class="sxs-lookup"><span data-stu-id="a9d22-139">attachments</span></span>         |<span data-ttu-id="a9d22-140">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-140">yes \*\*</span></span>         |<span data-ttu-id="a9d22-141">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-141">yes \*\*</span></span>         |
|<span data-ttu-id="a9d22-142">Устройства с Windows 10 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a9d22-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="a9d22-143">элементы</span><span class="sxs-lookup"><span data-stu-id="a9d22-143">items</span></span>         |<span data-ttu-id="a9d22-144">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-144">yes</span></span>         |<span data-ttu-id="a9d22-145">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-145">yes</span></span>         |
|<span data-ttu-id="a9d22-146">МКАС (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a9d22-146">MCAS (preview)</span></span> |<span data-ttu-id="a9d22-147">элементы</span><span class="sxs-lookup"><span data-stu-id="a9d22-147">items</span></span>         |<span data-ttu-id="a9d22-148">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-148">yes</span></span>         |<span data-ttu-id="a9d22-149">да</span><span class="sxs-lookup"><span data-stu-id="a9d22-149">yes</span></span>         |

<span data-ttu-id="a9d22-150">Поддерживается обнаружение защитой от потери данных \* меток конфиденциальности на сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a9d22-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="a9d22-151">Обнаружение защитой от потери данных вложений с метками конфиденциальности не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a9d22-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="a9d22-152">\*\* Вложения, отправленные в Teams через личный чат или каналы, автоматически добавляются в OneDrive для бизнеса и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a9d22-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="a9d22-153">Таким образом, если SharePoint Online или OneDrive для бизнеса включены в качестве расположений в политику защиты от потери данных, вложения с метками, отправленные в Teams, автоматически включаются в область действия этого условия.</span><span class="sxs-lookup"><span data-stu-id="a9d22-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="a9d22-154">В политике защиты от потери данных Teams не обязательно выбирать в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="a9d22-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="a9d22-155">Поддерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="a9d22-155">Supported scenarios</span></span>

- <span data-ttu-id="a9d22-156">Администратор защиты от потери данных сможет видеть в клиенте список всех меток конфиденциальности, если включит одну или несколько меток конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="a9d22-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="a9d22-157">Использование меток конфиденциальности в качестве условия поддерживается во всех рабочих нагрузках, как указано в приведенной выше матрице поддержки.</span><span class="sxs-lookup"><span data-stu-id="a9d22-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="a9d22-158">Подсказки политики защиты от потери данных будут по-прежнему отображаться для рабочих нагрузок (за исключением Outlook Win32) для тех политик защиты от потери данных, в которых есть метка конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="a9d22-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="a9d22-159">Метки конфиденциальности также появляются в сообщении электронной почты с отчетом об инциденте в случае совпадения с политикой защиты от потери данных с меткой конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="a9d22-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="a9d22-160">Кроме того, подробности о метке конфиденциальности также отобразятся в журнале аудита соответствия правилам защиты от потери данных в случае совпадения с политикой защиты от потери данных, которая содержит пометку в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="a9d22-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="a9d22-161">Подсказки политики поддержки</span><span class="sxs-lookup"><span data-stu-id="a9d22-161">Support policy tips</span></span>


|<span data-ttu-id="a9d22-162">рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="a9d22-162">workload</span></span>  |<span data-ttu-id="a9d22-163">подсказки политики поддерживаются/не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="a9d22-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="a9d22-164">OWA</span><span class="sxs-lookup"><span data-stu-id="a9d22-164">OWA</span></span> |    <span data-ttu-id="a9d22-165">поддерживается</span><span class="sxs-lookup"><span data-stu-id="a9d22-165">supported</span></span>     |
|<span data-ttu-id="a9d22-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="a9d22-166">Outlook Win 32</span></span>    |  <span data-ttu-id="a9d22-167">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a9d22-167">not supported</span></span>       |
|<span data-ttu-id="a9d22-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="a9d22-168">SharePoint</span></span>   |   <span data-ttu-id="a9d22-169">поддерживается</span><span class="sxs-lookup"><span data-stu-id="a9d22-169">supported</span></span>      |
|<span data-ttu-id="a9d22-170">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a9d22-170">OneDrive for Business</span></span>    |    <span data-ttu-id="a9d22-171">поддерживается</span><span class="sxs-lookup"><span data-stu-id="a9d22-171">supported</span></span>     |
|<span data-ttu-id="a9d22-172">устройства конечных точек</span><span class="sxs-lookup"><span data-stu-id="a9d22-172">endpoint devices</span></span>   |  <span data-ttu-id="a9d22-173">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a9d22-173">not supported</span></span>       |
