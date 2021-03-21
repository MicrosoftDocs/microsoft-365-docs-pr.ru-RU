---
title: Ограничения для политик хранения и политик меток хранения
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Сведения о максимальном количестве политик и элементов в каждой политике для политик хранения и политик меток хранения
ms.openlocfilehash: 53539df4d36fab02171e1ac06ba944ed3bea34e8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917245"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="6e982-103">Ограничения для политик хранения и политик меток хранения</span><span class="sxs-lookup"><span data-stu-id="6e982-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="6e982-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="6e982-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="6e982-105">При использовании [политик хранения и политик меток хранения](retention.md#retention-policies-and-retention-labels), чтобы автоматически сохранять или удалять данные в организации, следует учитывать некоторые максимальные значения.</span><span class="sxs-lookup"><span data-stu-id="6e982-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="6e982-106">Максимальное количество политик для каждого клиента</span><span class="sxs-lookup"><span data-stu-id="6e982-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="6e982-107">В одном клиенте может быть не более 10 000 политик (в любой конфигурации).</span><span class="sxs-lookup"><span data-stu-id="6e982-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="6e982-108">Это максимальное количество включает различные политики хранения и другие политики соответствия требованиям, например политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="6e982-108">This maximum number includes the different policies for retention and other policies for compliance, such as DLP policies.</span></span>

<span data-ttu-id="6e982-109">Максимальное количество политик хранения для каждой рабочей нагрузки:</span><span class="sxs-lookup"><span data-stu-id="6e982-109">Maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="6e982-110">Exchange Online (любая конфигурация): 1 800</span><span class="sxs-lookup"><span data-stu-id="6e982-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="6e982-111">SharePoint или OneDrive (автоматически включаются все сайты): 13</span><span class="sxs-lookup"><span data-stu-id="6e982-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="6e982-112">SharePoint или OneDrive (определенные расположения включаются или исключаются): 2 600</span><span class="sxs-lookup"><span data-stu-id="6e982-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="6e982-113">Максимальное количество элементов в каждой политике</span><span class="sxs-lookup"><span data-stu-id="6e982-113">Maximum number of items per policy</span></span>

<span data-ttu-id="6e982-114">Для каждой политики существуют некоторые ограничения, которые нужно учитывать в случае использования дополнительной конфигурации при определении области ваших параметров хранения для конкретных пользователей, групп Microsoft 365 или сайтов:</span><span class="sxs-lookup"><span data-stu-id="6e982-114">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="6e982-115">Максимальное количество элементов в каждой политике хранения:</span><span class="sxs-lookup"><span data-stu-id="6e982-115">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="6e982-116">1000 почтовых ящиков (почтовых ящиков пользователей или групп)</span><span class="sxs-lookup"><span data-stu-id="6e982-116">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="6e982-117">1 000 групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6e982-117">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="6e982-118">1 000 пользователей приватных чатов Teams</span><span class="sxs-lookup"><span data-stu-id="6e982-118">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="6e982-119">100 сайтов (OneDrive или SharePoint)</span><span class="sxs-lookup"><span data-stu-id="6e982-119">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="6e982-120">Так как эти ограничения относятся к отдельным политикам, при необходимости использования конкретных включений или исключений, приводящих к превышению этих значений, вы можете создать дополнительные политики с такими же параметрами хранения.</span><span class="sxs-lookup"><span data-stu-id="6e982-120">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="6e982-121">В следующем разделе приведено несколько [примерных сценариев и решений](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers), в которых с этой целью использовано несколько политик хранения.</span><span class="sxs-lookup"><span data-stu-id="6e982-121">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="6e982-122">Но применение нескольких политик приводит к более высокой административной нагрузке, поэтому всегда подтверждайте, действительно ли необходимы включения и исключения.</span><span class="sxs-lookup"><span data-stu-id="6e982-122">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="6e982-123">Следует помнить, что конфигурация по умолчанию, применяемая ко всему расположению, не имеет никаких ограничений, и выбор такой конфигурации может быть предпочтительнее создания и обслуживания нескольких политик.</span><span class="sxs-lookup"><span data-stu-id="6e982-123">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="6e982-124">При необходимости создания и поддержки нескольких политик для этого сценария можно воспользоваться [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels), чтобы повысить эффективность конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6e982-124">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="6e982-125">Примеры использования нескольких политик, чтобы избежать превышения максимальных количеств</span><span class="sxs-lookup"><span data-stu-id="6e982-125">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="6e982-126">В следующих примерах приведены некоторые конструктивные решения для случаев, когда нельзя указать конкретное расположение для политики хранения и необходимо принимать во внимание максимальное количество элементов, указанное в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="6e982-126">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="6e982-127">Пример Exchange.</span><span class="sxs-lookup"><span data-stu-id="6e982-127">Exchange example:</span></span>

- <span data-ttu-id="6e982-128">**Требование**. В организации с более чем 40 000 почтовых ящиков пользователей электронные сообщения большинства пользователей должны храниться 7 лет, но электронные сообщения подмножества конкретных пользователей (425) должны храниться только 5 лет.</span><span class="sxs-lookup"><span data-stu-id="6e982-128">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="6e982-129">**Решение**. Создайте одну политику хранения для электронных сообщений Exchange с продолжительностью хранения 7 лет и исключите подмножество пользователей.</span><span class="sxs-lookup"><span data-stu-id="6e982-129">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="6e982-130">Затем создайте вторую политику хранения для электронных сообщений Exchange с периодом хранения 5 лет и включите в нее это подмножество пользователей.</span><span class="sxs-lookup"><span data-stu-id="6e982-130">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="6e982-131">В обоих случаях число включаемых и исключаемых почтовых ящиков не превышает максимума для одной политики, а подмножество пользователей должно быть явным образом исключено из первой политики, так как в ней определен более [долгий период хранения](retention.md#the-principles-of-retention-or-what-takes-precedence), чем во второй политике.</span><span class="sxs-lookup"><span data-stu-id="6e982-131">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="6e982-132">Если бы для подмножества пользователей требовалась политика с более долгим периодом хранения, его не нужно было бы исключать из первой политики.</span><span class="sxs-lookup"><span data-stu-id="6e982-132">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="6e982-133">С этим решением при присоединении к организации нового пользователя на его почтовый ящик автоматически распространяется первая политика со сроком хранения 7 лет, и на максимальное число поддерживаемых почтовых ящиков это не влияет.</span><span class="sxs-lookup"><span data-stu-id="6e982-133">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="6e982-134">Однако новые пользователи, для которых требуется период хранения в 5 лет, добавляются в число включений и исключений, которое не должно превышать 1000.</span><span class="sxs-lookup"><span data-stu-id="6e982-134">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="6e982-135">Пример SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6e982-135">SharePoint example:</span></span>

- <span data-ttu-id="6e982-136">**Требование**. В организации есть несколько тысяч сайтов SharePoint, но только для 2000 сайтов требуется период хранения 10 лет, а для 8000 сайтов требуется период хранения 4 года.</span><span class="sxs-lookup"><span data-stu-id="6e982-136">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="6e982-137">**Решение**. Создается 20 политик хранения для SharePoint с периодом хранения 10 лет, каждая из которых распространяется на 100 конкретных сайтов, и 80 политик хранения для SharePoint с периодом хранения 4 года, каждая из которых распространяется на 100 конкретных сайтов.</span><span class="sxs-lookup"><span data-stu-id="6e982-137">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="6e982-138">Так как хранить все сайты SharePoint не нужно, достаточно создать политики хранения, в которых указаны конкретные сайты.</span><span class="sxs-lookup"><span data-stu-id="6e982-138">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="6e982-139">Так как политика хранения поддерживает не более 100 конкретных сайтов, необходимо создать несколько политик хранения для каждого из двух периодов хранения.</span><span class="sxs-lookup"><span data-stu-id="6e982-139">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="6e982-140">Так как в эти политики хранения включено максимальное число сайтов, то для следующего нового сайта, требующего хранения, необходима новая политика хранения вне зависимости от длительности необходимого периода хранения.</span><span class="sxs-lookup"><span data-stu-id="6e982-140">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>