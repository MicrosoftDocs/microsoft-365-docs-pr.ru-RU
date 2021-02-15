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
description: 'Узнайте, как найти значения и сведения, необходимые для создания записей DNS для Microsoft 365. '
ms.openlocfilehash: 45994139b11a2fd5a03b2e979dd6af334bc1f00b
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126375"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="bdb12-103">Сбор сведений, необходимых для создания записей DNS</span><span class="sxs-lookup"><span data-stu-id="bdb12-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="bdb12-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="bdb12-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="bdb12-105">Шаг 1. Поиск значения записи TXT и проверка</span><span class="sxs-lookup"><span data-stu-id="bdb12-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bdb12-106">В Центре администрирования Microsoft 365 перейдите на страницу **"Домены** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">установки".</a></span><span class="sxs-lookup"><span data-stu-id="bdb12-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bdb12-107">В Центре администрирования перейдите на страницу **"Домены** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">установки".</a></span><span class="sxs-lookup"><span data-stu-id="bdb12-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bdb12-108">В Центре администрирования перейдите на страницу **"Домены** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">установки".</a></span><span class="sxs-lookup"><span data-stu-id="bdb12-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="bdb12-109">На странице **"Домены"** выберите свой домен, а затем выберите **"Начать установку".**</span><span class="sxs-lookup"><span data-stu-id="bdb12-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="bdb12-110">Вы вернетесь в мастер настройки доменов, чтобы просмотреть значение, которое нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="bdb12-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="bdb12-111">На странице **"Проверка домена"** выберите **"Добавить запись TXT",** а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="bdb12-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="bdb12-112">Скопируйте **показанные значения TXT.**</span><span class="sxs-lookup"><span data-stu-id="bdb12-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="bdb12-113">Он выглядит так: **MS=msXXXXXXXXX.**</span><span class="sxs-lookup"><span data-stu-id="bdb12-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="bdb12-114">Перейдите к созданию [записей DNS](create-dns-records-at-any-dns-hosting-provider.md)у любого поставщика услуг размещения DNS и выберите свой хост DNS в списке регистраторов, чтобы увидеть пошаговых инструкций.</span><span class="sxs-lookup"><span data-stu-id="bdb12-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="bdb12-115">Выполните действия по созданию TXT-записи (или записи MX) на своем DNS-сайте, а затем проверьте домен обратно в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bdb12-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="bdb12-116">Удалите запись TXT (или запись MX) с хоста DNS после проверки домена в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bdb12-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="bdb12-117">Шаг 2. Поиск значения записи MX для электронной почты и других</span><span class="sxs-lookup"><span data-stu-id="bdb12-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bdb12-118">В Центре администрирования Microsoft 365 перейдите на страницу **"Домены** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">установки".</a></span><span class="sxs-lookup"><span data-stu-id="bdb12-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="bdb12-119">В Центре администрирования перейдите на страницу **"Настройка** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">доменов".</a></span><span class="sxs-lookup"><span data-stu-id="bdb12-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bdb12-120">В Центре администрирования перейдите на страницу **"Домены** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">установки".</a></span><span class="sxs-lookup"><span data-stu-id="bdb12-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="bdb12-121">На странице **Домены** щелкните свой домен.</span><span class="sxs-lookup"><span data-stu-id="bdb12-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="bdb12-122">В разделе **Обязательные параметры DNS** вы увидите записи DNS, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="bdb12-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="bdb12-123">Эти сведения понадобятся во время внесения изменений на узле DNS, чтобы можно было скопировать и вставить значения.</span><span class="sxs-lookup"><span data-stu-id="bdb12-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="bdb12-124">То, какие группы записей DNS будут перечислены на странице, зависит от выбранных вами параметров в разделе **Назначение домена**.</span><span class="sxs-lookup"><span data-stu-id="bdb12-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="bdb12-125">Перейдите к созданию записей DNS у любого поставщика услуг размещения [DNS,](create-dns-records-at-any-dns-hosting-provider.md)а затем выберите свой DNS-сайт в списке регистраторов, чтобы увидеть пошаговых инструкций по добавлению записей на веб-сайте этого DNS-сайта.</span><span class="sxs-lookup"><span data-stu-id="bdb12-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="bdb12-126">Следуйте указаниям, чтобы создать записи в своем узле DNS.</span><span class="sxs-lookup"><span data-stu-id="bdb12-126">Follow the steps for creating the records at your DNS host.</span></span>
