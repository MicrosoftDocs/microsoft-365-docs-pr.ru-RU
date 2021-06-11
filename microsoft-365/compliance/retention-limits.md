---
title: Ограничения для политик хранения и политик меток хранения
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Сведения о максимальном количестве политик и элементов в каждой политике для политик хранения и политик меток хранения
ms.openlocfilehash: 2dac852342c080c4f8334562dc76449d6963facc
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878056"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="538c0-103">Ограничения для политик хранения и политик меток хранения</span><span class="sxs-lookup"><span data-stu-id="538c0-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="538c0-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="538c0-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="538c0-105">При использовании [политик хранения и политик меток хранения](retention.md#retention-policies-and-retention-labels), чтобы автоматически сохранять или удалять данные в организации, следует учитывать некоторые максимальные значения.</span><span class="sxs-lookup"><span data-stu-id="538c0-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="538c0-106">Максимальное количество политик для каждого клиента</span><span class="sxs-lookup"><span data-stu-id="538c0-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="538c0-107">В одном клиенте может быть не более 10 000 политик (в любой конфигурации).</span><span class="sxs-lookup"><span data-stu-id="538c0-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="538c0-108">Это максимальное количество включает различные политики хранения и другие политики соответствия требованиям, например политики защиты от потери данных, информационные барьеры, удержания для обнаружения электронных данных и метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="538c0-108">This maximum number includes the different policies for retention, and other policies for compliance such as policies for DLP, information barriers, eDiscovery holds, and sensitivity labels.</span></span>

<span data-ttu-id="538c0-109">В рамках этого ограничения в 10 000 политиках также есть некоторые ограничения на максимальное количество политик для хранения для одной рабочей нагрузки:</span><span class="sxs-lookup"><span data-stu-id="538c0-109">Within this 10,000 policies limit, there are also some limits on the maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="538c0-110">Exchange Online (любая конфигурация): 1 800</span><span class="sxs-lookup"><span data-stu-id="538c0-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="538c0-111">SharePoint или OneDrive (автоматически включаются все сайты): 13</span><span class="sxs-lookup"><span data-stu-id="538c0-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="538c0-112">SharePoint или OneDrive (определенные расположения включаются или исключаются): 2 600</span><span class="sxs-lookup"><span data-stu-id="538c0-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

<span data-ttu-id="538c0-113">Хотя политики хранения для Microsoft Teams и Yammer используют почтовые ящики для хранения данных, максимальное количество политик для Exchange Online исключает политики хранения для Teams и Yammer.</span><span class="sxs-lookup"><span data-stu-id="538c0-113">Although retention policies for Microsoft Teams and Yammer use mailboxes to store data for retention purposes, the maximum number of policies for Exchange Online exclude retention policies for Teams and Yammer.</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="538c0-114">Максимальное количество элементов в каждой политике</span><span class="sxs-lookup"><span data-stu-id="538c0-114">Maximum number of items per policy</span></span>

<span data-ttu-id="538c0-115">Для каждой политики существуют некоторые ограничения, которые нужно учитывать в случае использования дополнительной конфигурации при определении области ваших параметров хранения для конкретных пользователей, групп Microsoft 365 или сайтов:</span><span class="sxs-lookup"><span data-stu-id="538c0-115">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="538c0-116">Максимальное количество элементов в каждой политике хранения:</span><span class="sxs-lookup"><span data-stu-id="538c0-116">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="538c0-117">1000 почтовых ящиков (почтовых ящиков пользователей или групп)</span><span class="sxs-lookup"><span data-stu-id="538c0-117">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="538c0-118">1 000 групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="538c0-118">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="538c0-119">1 000 пользователей приватных чатов Teams</span><span class="sxs-lookup"><span data-stu-id="538c0-119">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="538c0-120">100 сайтов (OneDrive или SharePoint)</span><span class="sxs-lookup"><span data-stu-id="538c0-120">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="538c0-121">Так как эти ограничения относятся к отдельным политикам, при необходимости использования конкретных включений или исключений, приводящих к превышению этих значений, вы можете создать дополнительные политики с такими же параметрами хранения.</span><span class="sxs-lookup"><span data-stu-id="538c0-121">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="538c0-122">В следующем разделе приведено несколько [примерных сценариев и решений](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers), в которых с этой целью использовано несколько политик хранения.</span><span class="sxs-lookup"><span data-stu-id="538c0-122">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="538c0-123">Но применение нескольких политик приводит к более высокой административной нагрузке, поэтому всегда подтверждайте, действительно ли необходимы включения и исключения.</span><span class="sxs-lookup"><span data-stu-id="538c0-123">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="538c0-124">Следует помнить, что конфигурация по умолчанию, применяемая ко всему расположению, не имеет никаких ограничений, и выбор такой конфигурации может быть предпочтительнее создания и обслуживания нескольких политик.</span><span class="sxs-lookup"><span data-stu-id="538c0-124">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="538c0-125">При необходимости создания и поддержки нескольких политик для этого сценария можно воспользоваться [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels), чтобы повысить эффективность конфигурации.</span><span class="sxs-lookup"><span data-stu-id="538c0-125">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="538c0-126">Примеры использования нескольких политик, чтобы избежать превышения максимальных количеств</span><span class="sxs-lookup"><span data-stu-id="538c0-126">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="538c0-127">В следующих примерах приведены некоторые конструктивные решения для случаев, когда нельзя указать конкретное расположение для политики хранения и необходимо принимать во внимание максимальное количество элементов, указанное в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="538c0-127">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="538c0-128">Пример Exchange.</span><span class="sxs-lookup"><span data-stu-id="538c0-128">Exchange example:</span></span>

- <span data-ttu-id="538c0-129">**Требование**. В организации с более чем 40 000 почтовых ящиков пользователей электронные сообщения большинства пользователей должны храниться 7 лет, но электронные сообщения подмножества конкретных пользователей (425) должны храниться только 5 лет.</span><span class="sxs-lookup"><span data-stu-id="538c0-129">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="538c0-130">**Решение**. Создайте одну политику хранения для электронных сообщений Exchange с продолжительностью хранения 7 лет и исключите подмножество пользователей.</span><span class="sxs-lookup"><span data-stu-id="538c0-130">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="538c0-131">Затем создайте вторую политику хранения для электронных сообщений Exchange с периодом хранения 5 лет и включите в нее это подмножество пользователей.</span><span class="sxs-lookup"><span data-stu-id="538c0-131">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="538c0-132">В обоих случаях число включаемых и исключаемых почтовых ящиков не превышает максимума для одной политики, а подмножество пользователей должно быть явным образом исключено из первой политики, так как в ней определен более [долгий период хранения](retention.md#the-principles-of-retention-or-what-takes-precedence), чем во второй политике.</span><span class="sxs-lookup"><span data-stu-id="538c0-132">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="538c0-133">Если бы для подмножества пользователей требовалась политика с более долгим периодом хранения, его не нужно было бы исключать из первой политики.</span><span class="sxs-lookup"><span data-stu-id="538c0-133">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="538c0-134">С этим решением при присоединении к организации нового пользователя на его почтовый ящик автоматически распространяется первая политика со сроком хранения 7 лет, и на максимальное число поддерживаемых почтовых ящиков это не влияет.</span><span class="sxs-lookup"><span data-stu-id="538c0-134">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="538c0-135">Однако новые пользователи, для которых требуется период хранения в 5 лет, добавляются в число включений и исключений, которое не должно превышать 1000.</span><span class="sxs-lookup"><span data-stu-id="538c0-135">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="538c0-136">Пример SharePoint.</span><span class="sxs-lookup"><span data-stu-id="538c0-136">SharePoint example:</span></span>

- <span data-ttu-id="538c0-137">**Требование**. В организации есть несколько тысяч сайтов SharePoint, но только для 2000 сайтов требуется период хранения 10 лет, а для 8000 сайтов требуется период хранения 4 года.</span><span class="sxs-lookup"><span data-stu-id="538c0-137">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="538c0-138">**Решение**. Создается 20 политик хранения для SharePoint с периодом хранения 10 лет, каждая из которых распространяется на 100 конкретных сайтов, и 80 политик хранения для SharePoint с периодом хранения 4 года, каждая из которых распространяется на 100 конкретных сайтов.</span><span class="sxs-lookup"><span data-stu-id="538c0-138">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="538c0-139">Так как хранить все сайты SharePoint не нужно, достаточно создать политики хранения, в которых указаны конкретные сайты.</span><span class="sxs-lookup"><span data-stu-id="538c0-139">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="538c0-140">Так как политика хранения поддерживает не более 100 конкретных сайтов, необходимо создать несколько политик хранения для каждого из двух периодов хранения.</span><span class="sxs-lookup"><span data-stu-id="538c0-140">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="538c0-141">Так как в эти политики хранения включено максимальное число сайтов, то для следующего нового сайта, требующего хранения, необходима новая политика хранения вне зависимости от длительности необходимого периода хранения.</span><span class="sxs-lookup"><span data-stu-id="538c0-141">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>

## <a name="maximum-number-of-items-for-disposition"></a><span data-ttu-id="538c0-142">Максимальное количество элементов для ликвидации</span><span class="sxs-lookup"><span data-stu-id="538c0-142">Maximum number of items for disposition</span></span>

<span data-ttu-id="538c0-143">Для [ликвидации содержимого](disposition.md) существуют некоторые ограничения, которые следует учитывать:</span><span class="sxs-lookup"><span data-stu-id="538c0-143">For the [disposition of content](disposition.md), there are some limits to be aware of:</span></span>

- <span data-ttu-id="538c0-144">1 000 000 элементов, ожидающих ликвидации на этап для каждой метки хранения</span><span class="sxs-lookup"><span data-stu-id="538c0-144">1,000,000 items pending disposition per stage for each retention label</span></span>

- <span data-ttu-id="538c0-145">Подтверждение ликвидации в течение семи лет после ликвидации элемента с ограничением в 1 000 000 элементов на метку хранения в течение этого периода.</span><span class="sxs-lookup"><span data-stu-id="538c0-145">Proof of disposition for up to seven years after the item was disposed, with a limit of 1,000,000 items per retention label for that period.</span></span> 
    
    <span data-ttu-id="538c0-146">Если вам требуется подтверждение ликвидации с превышением этого ограничения (1 000 000) для элементов, помеченных как записи, обратитесь в [службу поддержки Microsoft](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="538c0-146">If you need proof of disposition higher than this limit of 1,000,000 for items that are marked as records, contact [Microsoft Support](../business-video/get-help-support.md).</span></span>