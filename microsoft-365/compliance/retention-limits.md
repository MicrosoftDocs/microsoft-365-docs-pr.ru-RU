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
ms.openlocfilehash: 92647911cfc3435c2d88ce5caa0624a34467a60f
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908105"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="3b518-103">Ограничения для политик хранения и политик меток хранения</span><span class="sxs-lookup"><span data-stu-id="3b518-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="3b518-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="3b518-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="3b518-105">При использовании [политик хранения и политик меток хранения](retention.md#retention-policies-and-retention-labels), чтобы автоматически сохранять или удалять данные в организации, следует учитывать некоторые максимальные значения.</span><span class="sxs-lookup"><span data-stu-id="3b518-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="3b518-106">Максимальное количество политик для каждого клиента</span><span class="sxs-lookup"><span data-stu-id="3b518-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="3b518-107">В одном клиенте может быть не более 10 000 политик (в любой конфигурации).</span><span class="sxs-lookup"><span data-stu-id="3b518-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="3b518-108">Это максимальное количество включает различные политики хранения и другие политики соответствия требованиям, например политики защиты от потери данных, информационные барьеры, удержания для обнаружения электронных данных и метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="3b518-108">This maximum number includes the different policies for retention, and other policies for compliance such as policies for DLP, information barriers, eDiscovery holds, and sensitivity labels.</span></span>

<span data-ttu-id="3b518-109">В рамках этого ограничения в 10 000 политиках также есть некоторые ограничения на максимальное количество политик для хранения для одной рабочей нагрузки:</span><span class="sxs-lookup"><span data-stu-id="3b518-109">Within this 10,000 policies limit, there are also some limits on the maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="3b518-110">Exchange (любая конфигурация): 1 800</span><span class="sxs-lookup"><span data-stu-id="3b518-110">Exchange (any configuration): 1,800</span></span>
- <span data-ttu-id="3b518-111">SharePoint или OneDrive (автоматически включаются все сайты): 13</span><span class="sxs-lookup"><span data-stu-id="3b518-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="3b518-112">SharePoint или OneDrive (определенные расположения включаются или исключаются): 2 600</span><span class="sxs-lookup"><span data-stu-id="3b518-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

<span data-ttu-id="3b518-113">Хотя политики хранения для Microsoft Teams и Yammer используют почтовые ящики для хранения данных, максимальное количество политик для Exchange Online исключает политики хранения для Teams и Yammer.</span><span class="sxs-lookup"><span data-stu-id="3b518-113">Although retention policies for Microsoft Teams and Yammer use mailboxes to store data for retention purposes, the maximum number of policies for Exchange Online exclude retention policies for Teams and Yammer.</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="3b518-114">Максимальное количество элементов в каждой политике</span><span class="sxs-lookup"><span data-stu-id="3b518-114">Maximum number of items per policy</span></span>

<span data-ttu-id="3b518-115">Для каждой политики существуют некоторые ограничения, которые нужно учитывать в случае использования дополнительной конфигурации при определении области ваших параметров хранения для конкретных пользователей, групп Microsoft 365 или сайтов:</span><span class="sxs-lookup"><span data-stu-id="3b518-115">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="3b518-116">Максимальное количество элементов в каждой политике хранения:</span><span class="sxs-lookup"><span data-stu-id="3b518-116">Maximum numbers of items per policy for retention:</span></span>

- <span data-ttu-id="3b518-117">Почтовые ящики Exchange: 1000</span><span class="sxs-lookup"><span data-stu-id="3b518-117">Exchange mailboxes: 1,000</span></span>
- <span data-ttu-id="3b518-118">Группы Microsoft 365: 1000</span><span class="sxs-lookup"><span data-stu-id="3b518-118">Microsoft 365 Groups: 1,000</span></span>
- <span data-ttu-id="3b518-119">Сообщения каналов Teams: 1000</span><span class="sxs-lookup"><span data-stu-id="3b518-119">Teams channel messages: 1,000</span></span>
- <span data-ttu-id="3b518-120">Чаты Teams: 1000</span><span class="sxs-lookup"><span data-stu-id="3b518-120">Teams chats: 1,000</span></span>
- <span data-ttu-id="3b518-121">Сообщения сообщества Yammer: 1000</span><span class="sxs-lookup"><span data-stu-id="3b518-121">Yammer community messages: 1,000</span></span>
- <span data-ttu-id="3b518-122">Сообщения пользователей Yammer: 1000</span><span class="sxs-lookup"><span data-stu-id="3b518-122">Yammer user messages: 1,000</span></span>
- <span data-ttu-id="3b518-123">Сайты SharePoint: 100</span><span class="sxs-lookup"><span data-stu-id="3b518-123">SharePoint sites: 100</span></span>
- <span data-ttu-id="3b518-124">Учетные записи OneDrive: 100</span><span class="sxs-lookup"><span data-stu-id="3b518-124">OneDrive accounts: 100</span></span>

<span data-ttu-id="3b518-125">Область действия Skype для бизнеса должна ограничиваться определенными пользователями, а максимальное количество поддерживаемых политик — 1000.</span><span class="sxs-lookup"><span data-stu-id="3b518-125">Skype for Business has to be scoped to specific users and the maximum number supported per policy is 1,000.</span></span>

<span data-ttu-id="3b518-126">Так как эти ограничения относятся к отдельным политикам, при необходимости использования конкретных включений или исключений, приводящих к превышению этих значений, вы можете создать дополнительные политики с такими же параметрами хранения.</span><span class="sxs-lookup"><span data-stu-id="3b518-126">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="3b518-127">В следующем разделе приведено несколько [примерных сценариев и решений](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers), в которых с этой целью использовано несколько политик хранения.</span><span class="sxs-lookup"><span data-stu-id="3b518-127">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="3b518-128">Но применение нескольких политик приводит к более высокой административной нагрузке, поэтому всегда подтверждайте, действительно ли необходимы включения и исключения.</span><span class="sxs-lookup"><span data-stu-id="3b518-128">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="3b518-129">Следует помнить, что конфигурация по умолчанию, применяемая ко всему расположению, не имеет никаких ограничений, и выбор такой конфигурации может быть предпочтительнее создания и обслуживания нескольких политик.</span><span class="sxs-lookup"><span data-stu-id="3b518-129">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="3b518-130">При необходимости создания и поддержки нескольких политик для этого сценария можно воспользоваться [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels), чтобы повысить эффективность конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3b518-130">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="3b518-131">Примеры использования нескольких политик, чтобы избежать превышения максимальных количеств</span><span class="sxs-lookup"><span data-stu-id="3b518-131">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="3b518-132">В следующих примерах приведены некоторые конструктивные решения для случаев, когда нельзя указать конкретное расположение для политики хранения и необходимо принимать во внимание максимальное количество элементов, указанное в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="3b518-132">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="3b518-133">Пример Exchange.</span><span class="sxs-lookup"><span data-stu-id="3b518-133">Exchange example:</span></span>

- <span data-ttu-id="3b518-134">**Требование**. В организации с более чем 40 000 почтовых ящиков пользователей электронные сообщения большинства пользователей должны храниться 7 лет, но электронные сообщения подмножества конкретных пользователей (425) должны храниться только 5 лет.</span><span class="sxs-lookup"><span data-stu-id="3b518-134">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="3b518-135">**Решение**. Создайте одну политику хранения для электронных сообщений Exchange с продолжительностью хранения 7 лет и исключите подмножество пользователей.</span><span class="sxs-lookup"><span data-stu-id="3b518-135">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="3b518-136">Затем создайте вторую политику хранения для электронных сообщений Exchange с периодом хранения 5 лет и включите в нее это подмножество пользователей.</span><span class="sxs-lookup"><span data-stu-id="3b518-136">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="3b518-137">В обоих случаях число включаемых и исключаемых почтовых ящиков не превышает максимума для одной политики, а подмножество пользователей должно быть явным образом исключено из первой политики, так как в ней определен более [долгий период хранения](retention.md#the-principles-of-retention-or-what-takes-precedence), чем во второй политике.</span><span class="sxs-lookup"><span data-stu-id="3b518-137">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="3b518-138">Если бы для подмножества пользователей требовалась политика с более долгим периодом хранения, его не нужно было бы исключать из первой политики.</span><span class="sxs-lookup"><span data-stu-id="3b518-138">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="3b518-139">С этим решением при присоединении к организации нового пользователя на его почтовый ящик автоматически распространяется первая политика со сроком хранения 7 лет, и на максимальное число поддерживаемых почтовых ящиков это не влияет.</span><span class="sxs-lookup"><span data-stu-id="3b518-139">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="3b518-140">Однако новые пользователи, для которых требуется период хранения в 5 лет, добавляются в число включений и исключений, которое не должно превышать 1000.</span><span class="sxs-lookup"><span data-stu-id="3b518-140">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="3b518-141">Пример SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3b518-141">SharePoint example:</span></span>

- <span data-ttu-id="3b518-142">**Требование**. В организации есть несколько тысяч сайтов SharePoint, но только для 2000 сайтов требуется период хранения 10 лет, а для 8000 сайтов требуется период хранения 4 года.</span><span class="sxs-lookup"><span data-stu-id="3b518-142">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="3b518-143">**Решение**. Создается 20 политик хранения для SharePoint с периодом хранения 10 лет, каждая из которых распространяется на 100 конкретных сайтов, и 80 политик хранения для SharePoint с периодом хранения 4 года, каждая из которых распространяется на 100 конкретных сайтов.</span><span class="sxs-lookup"><span data-stu-id="3b518-143">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="3b518-144">Так как хранить все сайты SharePoint не нужно, достаточно создать политики хранения, в которых указаны конкретные сайты.</span><span class="sxs-lookup"><span data-stu-id="3b518-144">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="3b518-145">Так как политика хранения поддерживает не более 100 конкретных сайтов, необходимо создать несколько политик хранения для каждого из двух периодов хранения.</span><span class="sxs-lookup"><span data-stu-id="3b518-145">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="3b518-146">Так как в эти политики хранения включено максимальное число сайтов, то для следующего нового сайта, требующего хранения, необходима новая политика хранения вне зависимости от длительности необходимого периода хранения.</span><span class="sxs-lookup"><span data-stu-id="3b518-146">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>

## <a name="maximum-number-of-items-for-disposition"></a><span data-ttu-id="3b518-147">Максимальное количество элементов для ликвидации</span><span class="sxs-lookup"><span data-stu-id="3b518-147">Maximum number of items for disposition</span></span>

<span data-ttu-id="3b518-148">Для [ликвидации содержимого](disposition.md) существуют некоторые ограничения, которые следует учитывать:</span><span class="sxs-lookup"><span data-stu-id="3b518-148">For the [disposition of content](disposition.md), there are some limits to be aware of:</span></span>

- <span data-ttu-id="3b518-149">1 000 000 элементов, ожидающих ликвидации на этап для каждой метки хранения</span><span class="sxs-lookup"><span data-stu-id="3b518-149">1,000,000 items pending disposition per stage for each retention label</span></span>

- <span data-ttu-id="3b518-150">Подтверждение ликвидации в течение семи лет после ликвидации элемента с ограничением в 1 000 000 элементов на метку хранения в течение этого периода.</span><span class="sxs-lookup"><span data-stu-id="3b518-150">Proof of disposition for up to seven years after the item was disposed, with a limit of 1,000,000 items per retention label for that period.</span></span> 
    
<span data-ttu-id="3b518-151">Если вам требуется подтверждение ликвидации с превышением этого ограничения (1 000 000) для элементов, помеченных как записи, обратитесь в [службу поддержки Microsoft](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="3b518-151">If you need proof of disposition higher than this limit of 1,000,000 for items that are marked as records, contact [Microsoft Support](../business-video/get-help-support.md).</span></span>
