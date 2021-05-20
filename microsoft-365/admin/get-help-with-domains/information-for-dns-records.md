---
title: Сбор сведений, необходимых для создания записей DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Соберите значения и сведения, необходимые для создания записей DNS для подключения домена к Microsoft 365 подписке.
ms.openlocfilehash: c8ff30c27e67c8a29b7122ea80a6a33f0594b1b9
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582960"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="ca9ad-103">Сбор сведений, необходимых для создания записей DNS</span><span class="sxs-lookup"><span data-stu-id="ca9ad-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="ca9ad-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="ca9ad-105">Шаг 1. Поиск значения записи TXT и проверка</span><span class="sxs-lookup"><span data-stu-id="ca9ad-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ca9ad-106">В центре Microsoft 365 администрирования перейдите на страницу **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains.</a></span><span class="sxs-lookup"><span data-stu-id="ca9ad-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ca9ad-107">В центре администрирования перейдите на страницу **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains.</a></span><span class="sxs-lookup"><span data-stu-id="ca9ad-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ca9ad-108">В центре администрирования перейдите на страницу **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains.</a></span><span class="sxs-lookup"><span data-stu-id="ca9ad-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="ca9ad-109">На странице **Домены** выберите домен, а затем выберите **настройку Начните.**</span><span class="sxs-lookup"><span data-stu-id="ca9ad-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="ca9ad-110">Вы вернетесь в мастер настройки доменов, чтобы просмотреть значение, которое нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="ca9ad-111">На странице **Проверка домена** выберите **Добавить запись TXT** вместо этого, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="ca9ad-112">Скопируйте **показанные значения TXT.**</span><span class="sxs-lookup"><span data-stu-id="ca9ad-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="ca9ad-113">Выглядит так: **MS=msXXXXXXXXXXX.**</span><span class="sxs-lookup"><span data-stu-id="ca9ad-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="ca9ad-114">Перейдите [к созданию записей DNS](create-dns-records-at-any-dns-hosting-provider.md)в любом поставщике DNS-хостинга и выберите свой DNS-хост из списка регистраторов, чтобы пошаговых инструкций.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="ca9ad-115">Выполните действия по созданию записи TXT (или записи MX) в вашем DNS-хозяйте, а затем проверьте домен в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="ca9ad-116">Удалите запись TXT (или запись MX) с вашего DNS-хоста после проверки домена в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="ca9ad-117">Шаг 2. Поиск значения записи MX для электронной почты и других</span><span class="sxs-lookup"><span data-stu-id="ca9ad-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ca9ad-118">В центре Microsoft 365 администрирования перейдите на страницу **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains.</a></span><span class="sxs-lookup"><span data-stu-id="ca9ad-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="ca9ad-119">В центре администрирования перейдите на страницу **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains.</a></span><span class="sxs-lookup"><span data-stu-id="ca9ad-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ca9ad-120">В центре администрирования перейдите на страницу **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains.</a></span><span class="sxs-lookup"><span data-stu-id="ca9ad-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="ca9ad-121">На странице **Домены** щелкните свой домен.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="ca9ad-122">В разделе **Обязательные параметры DNS** вы увидите записи DNS, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="ca9ad-123">Эти сведения понадобятся во время внесения изменений на узле DNS, чтобы можно было скопировать и вставить значения.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="ca9ad-124">То, какие группы записей DNS будут перечислены на странице, зависит от выбранных вами параметров в разделе **Назначение домена**.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="ca9ad-125">Перейдите к созданию записей [DNS](create-dns-records-at-any-dns-hosting-provider.md)в любом поставщике DNS-хостинга, а затем выберите свой DNS-хост из списка регистраторов, чтобы пошаговых инструкций по добавлению записей на веб-сайте этого ведущего DNS.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="ca9ad-126">Следуйте указаниям, чтобы создать записи в своем узле DNS.</span><span class="sxs-lookup"><span data-stu-id="ca9ad-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="ca9ad-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca9ad-127">Related content</span></span>

<span data-ttu-id="ca9ad-128">[FaQ доменов](../setup/domains-faq.yml) (статья)</span><span class="sxs-lookup"><span data-stu-id="ca9ad-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>

<span data-ttu-id="ca9ad-129">[Поиск и устранение неполадок после добавления домена и записей DNS](find-and-fix-issues.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="ca9ad-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>

<span data-ttu-id="ca9ad-130">[Управление доменами](index.yml) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="ca9ad-130">[Manage domains](index.yml) (link page)</span></span>