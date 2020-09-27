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
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235726"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="98255-103">Использование меток конфиденциальности в качестве условия в политиках защиты от потери данных (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="98255-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="98255-104">Использование [меток конфиденциальности](sensitivity-labels.md) в качестве условия в политиках защиты от потери данных для указанных ниже расположений.</span><span class="sxs-lookup"><span data-stu-id="98255-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="98255-105">Сообщения электронной почты Exchange Online</span><span class="sxs-lookup"><span data-stu-id="98255-105">Exchange Online email messages</span></span>
- <span data-ttu-id="98255-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="98255-106">SharePoint Online</span></span>
- <span data-ttu-id="98255-107">Сайты OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="98255-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="98255-108">Устройства с Windows 10</span><span class="sxs-lookup"><span data-stu-id="98255-108">Windows 10 devices</span></span>

<span data-ttu-id="98255-109">Метки конфиденциальности отображаются в качестве варианта в списке **Контент содержит**.</span><span class="sxs-lookup"><span data-stu-id="98255-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![метка конфиденциальности в качестве условия](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="98255-111">Поддерживаемые элементы, сценарии и подсказки политик</span><span class="sxs-lookup"><span data-stu-id="98255-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="98255-112">Метки чувствительности можно использовать в качестве условий для этих элементов и в таких сценариях.</span><span class="sxs-lookup"><span data-stu-id="98255-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="98255-113">Поддерживаемые элементы</span><span class="sxs-lookup"><span data-stu-id="98255-113">Supported items</span></span>

|<span data-ttu-id="98255-114">служба</span><span class="sxs-lookup"><span data-stu-id="98255-114">service</span></span>  |<span data-ttu-id="98255-115">тип элемента</span><span class="sxs-lookup"><span data-stu-id="98255-115">item type</span></span>  |<span data-ttu-id="98255-116">доступно для подсказки политики</span><span class="sxs-lookup"><span data-stu-id="98255-116">available to policy tip</span></span>  |<span data-ttu-id="98255-117">применимо</span><span class="sxs-lookup"><span data-stu-id="98255-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="98255-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="98255-118">Exchange</span></span>    |<span data-ttu-id="98255-119">сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="98255-119">email message</span></span>         |<span data-ttu-id="98255-120">да</span><span class="sxs-lookup"><span data-stu-id="98255-120">yes</span></span>         |<span data-ttu-id="98255-121">да</span><span class="sxs-lookup"><span data-stu-id="98255-121">yes</span></span>         |
|<span data-ttu-id="98255-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="98255-122">Exchange</span></span>    |<span data-ttu-id="98255-123">вложение электронной почты</span><span class="sxs-lookup"><span data-stu-id="98255-123">email attachment</span></span>         |<span data-ttu-id="98255-124">Нет</span><span class="sxs-lookup"><span data-stu-id="98255-124">no \*</span></span>         |<span data-ttu-id="98255-125">Нет</span><span class="sxs-lookup"><span data-stu-id="98255-125">no \*</span></span>         |
|<span data-ttu-id="98255-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="98255-126">SharePoint Online</span></span>     |<span data-ttu-id="98255-127">элементы в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="98255-127">items in SharePoint Online</span></span>         |<span data-ttu-id="98255-128">да</span><span class="sxs-lookup"><span data-stu-id="98255-128">yes</span></span>         |<span data-ttu-id="98255-129">да</span><span class="sxs-lookup"><span data-stu-id="98255-129">yes</span></span>         |
|<span data-ttu-id="98255-130">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="98255-130">OneDrive for Business</span></span>     |<span data-ttu-id="98255-131">элементы</span><span class="sxs-lookup"><span data-stu-id="98255-131">items</span></span>         |<span data-ttu-id="98255-132">да</span><span class="sxs-lookup"><span data-stu-id="98255-132">yes</span></span>         |<span data-ttu-id="98255-133">да</span><span class="sxs-lookup"><span data-stu-id="98255-133">yes</span></span>         |
|<span data-ttu-id="98255-134">Teams</span><span class="sxs-lookup"><span data-stu-id="98255-134">Teams</span></span>     |<span data-ttu-id="98255-135">Teams и сообщения в каналах</span><span class="sxs-lookup"><span data-stu-id="98255-135">Teams and channel messages</span></span>         |<span data-ttu-id="98255-136">неприменимо</span><span class="sxs-lookup"><span data-stu-id="98255-136">not applicable</span></span>         |<span data-ttu-id="98255-137">неприменимо</span><span class="sxs-lookup"><span data-stu-id="98255-137">not applicable</span></span>         |
|<span data-ttu-id="98255-138">Teams</span><span class="sxs-lookup"><span data-stu-id="98255-138">Teams</span></span>     |<span data-ttu-id="98255-139">вложения</span><span class="sxs-lookup"><span data-stu-id="98255-139">attachements</span></span>         |<span data-ttu-id="98255-140">да</span><span class="sxs-lookup"><span data-stu-id="98255-140">yes \*\*</span></span>         |<span data-ttu-id="98255-141">да</span><span class="sxs-lookup"><span data-stu-id="98255-141">yes \*\*</span></span>         |
|<span data-ttu-id="98255-142">Устройства с Windows 10 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="98255-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="98255-143">элементы</span><span class="sxs-lookup"><span data-stu-id="98255-143">items</span></span>         |<span data-ttu-id="98255-144">да</span><span class="sxs-lookup"><span data-stu-id="98255-144">yes</span></span>         |<span data-ttu-id="98255-145">да</span><span class="sxs-lookup"><span data-stu-id="98255-145">yes</span></span>         |
|<span data-ttu-id="98255-146">МКАС (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="98255-146">MCAS (preview)</span></span> |<span data-ttu-id="98255-147">элементы</span><span class="sxs-lookup"><span data-stu-id="98255-147">items</span></span>         |<span data-ttu-id="98255-148">да</span><span class="sxs-lookup"><span data-stu-id="98255-148">yes</span></span>         |<span data-ttu-id="98255-149">да</span><span class="sxs-lookup"><span data-stu-id="98255-149">yes</span></span>         |

<span data-ttu-id="98255-150">Поддерживается обнаружение защитой от потери данных \* меток конфиденциальности на сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="98255-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="98255-151">Обнаружение защитой от потери данных вложений с метками конфиденциальности не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="98255-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="98255-152">Вложения \*\*, отправленные в Teams через личный чат или каналы, автоматически выгружаются на One Drive для бизнеса и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98255-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to One drive for business and SharePoint.</span></span> <span data-ttu-id="98255-153">Таким образом, если SharePoint Online или One Drive для бизнеса включены в качестве расположений в политику защиты от потери данных, то вложения с метками, отправленные в Teams, автоматически включается в область действия этого условия.</span><span class="sxs-lookup"><span data-stu-id="98255-153">So if SharePoint Online or One Drive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="98255-154">В политике защиты от потери данных Teams не обязательно выбирать в качестве расположения.</span><span class="sxs-lookup"><span data-stu-id="98255-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="98255-155">Поддерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="98255-155">Supported scenarios</span></span>

- <span data-ttu-id="98255-156">Администратор защиты от потери данных сможет видеть в клиенте список всех меток конфиденциальности, если включит одну или несколько меток конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="98255-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="98255-157">Использование меток конфиденциальности в качестве условия поддерживается во всех рабочих нагрузках, как указано в приведенной выше матрице поддержки.</span><span class="sxs-lookup"><span data-stu-id="98255-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="98255-158">Подсказки политики защиты от потери данных будут по-прежнему отображаться для рабочих нагрузок (за исключением Outlook Win32) для тех политик защиты от потери данных, в которых есть метка конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="98255-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="98255-159">Метки конфиденциальности также появляются в сообщении электронной почты с отчетом об инциденте в случае совпадения с политикой защиты от потери данных с меткой конфиденциальности в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="98255-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="98255-160">Кроме того, подробности о метке конфиденциальности также отобразятся в журнале аудита соответствия правилам защиты от потери данных в случае совпадения с политикой защиты от потери данных, которая содержит пометку в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="98255-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="98255-161">Подсказки политики поддержки</span><span class="sxs-lookup"><span data-stu-id="98255-161">Support policy tips</span></span>


|<span data-ttu-id="98255-162">рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="98255-162">workload</span></span>  |<span data-ttu-id="98255-163">подсказки политики поддерживаются/не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="98255-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="98255-164">OWA</span><span class="sxs-lookup"><span data-stu-id="98255-164">OWA</span></span> |    <span data-ttu-id="98255-165">поддерживается</span><span class="sxs-lookup"><span data-stu-id="98255-165">supported</span></span>     |
|<span data-ttu-id="98255-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="98255-166">Outlook Win 32</span></span>    |  <span data-ttu-id="98255-167">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="98255-167">not supported</span></span>       |
|<span data-ttu-id="98255-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="98255-168">SharePoint</span></span>   |   <span data-ttu-id="98255-169">поддерживается</span><span class="sxs-lookup"><span data-stu-id="98255-169">supported</span></span>      |
|<span data-ttu-id="98255-170">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="98255-170">OneDrive for Business</span></span>    |    <span data-ttu-id="98255-171">поддерживается</span><span class="sxs-lookup"><span data-stu-id="98255-171">supported</span></span>     |
|<span data-ttu-id="98255-172">устройства конечных точек</span><span class="sxs-lookup"><span data-stu-id="98255-172">endpoint devices</span></span>   |  <span data-ttu-id="98255-173">не поддерживается</span><span class="sxs-lookup"><span data-stu-id="98255-173">not supported</span></span>       |
