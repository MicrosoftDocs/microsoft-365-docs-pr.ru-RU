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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Соберите значения и сведения, необходимые для создания записей DNS для подключения домена к Microsoft 365 подписке.
ms.openlocfilehash: c9869444da2ccb7f96ee01576d966767681c5b49
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393887"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="71fc1-103">Сбор сведений, необходимых для создания записей DNS</span><span class="sxs-lookup"><span data-stu-id="71fc1-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="71fc1-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="71fc1-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="71fc1-105">Шаг 1. Поиск значения записи TXT и проверка</span><span class="sxs-lookup"><span data-stu-id="71fc1-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="71fc1-106">В Центр администрирования Microsoft 365 перейдите на **страницу Параметры** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены.</a></span><span class="sxs-lookup"><span data-stu-id="71fc1-106">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="71fc1-107">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="71fc1-107">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="71fc1-108">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="71fc1-108">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="71fc1-109">На странице **Домены** выберите домен, а затем выберите **настройку Начните.**</span><span class="sxs-lookup"><span data-stu-id="71fc1-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="71fc1-110">Вы вернетесь в мастер настройки доменов, чтобы просмотреть значение, которое нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="71fc1-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="71fc1-111">На странице **Проверка домена** выберите Добавить запись **TXT в DNS-записи** домена, а затем выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="71fc1-111">On the **Domain Verification** page, select **Add a TXT record to the domain's DNS records**, then select **Continue**.</span></span>
    
4. <span data-ttu-id="71fc1-112">Скопируйте **показанные значения TXT.**</span><span class="sxs-lookup"><span data-stu-id="71fc1-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="71fc1-113">Выглядит так: **MS=msXXXXXXXXXXX.**</span><span class="sxs-lookup"><span data-stu-id="71fc1-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="71fc1-114">Перейдите [к добавлению записей DNS](create-dns-records-at-any-dns-hosting-provider.md)для подключения домена и выполните действия по добавлению записей на веб-сайте хоста DNS.</span><span class="sxs-lookup"><span data-stu-id="71fc1-114">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>
    
6. <span data-ttu-id="71fc1-115">Выполните действия по созданию записи TXT (или записи MX) в вашем DNS-хозяйте, а затем проверьте домен в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71fc1-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="71fc1-116">Удалите запись TXT (или запись MX) с вашего DNS-хоста после проверки домена в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71fc1-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="71fc1-117">Шаг 2. Поиск значения записи MX для электронной почты и других</span><span class="sxs-lookup"><span data-stu-id="71fc1-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="71fc1-118">В Центр администрирования Microsoft 365 перейдите на **страницу Параметры** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Домены.</a></span><span class="sxs-lookup"><span data-stu-id="71fc1-118">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="71fc1-119">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="71fc1-119">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="71fc1-120">В Центре администрирования перейдите на страницу **Settings** (Параметры) > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="71fc1-120">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="71fc1-121">На странице **Домены** щелкните свой домен.</span><span class="sxs-lookup"><span data-stu-id="71fc1-121">On the **Domains** page, select your domain.</span></span>
    
3. <span data-ttu-id="71fc1-122">Выберите **Управление DNS,** выберите **дополнительные параметры** Добавить свой собственный DNS и выберите Продолжить просмотр  >   записей DNS, чтобы добавить. </span><span class="sxs-lookup"><span data-stu-id="71fc1-122">Choose  **Manage DNS**, select **More Options** > **Add your own DNS** and select **Continue** to see the DNS records to add.</span></span>
    
    <span data-ttu-id="71fc1-123">Эти сведения понадобятся во время внесения изменений на узле DNS, чтобы можно было скопировать и вставить значения.</span><span class="sxs-lookup"><span data-stu-id="71fc1-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="71fc1-124">То, какие группы записей DNS будут перечислены на странице, зависит от выбранных вами параметров в разделе **Назначение домена**.</span><span class="sxs-lookup"><span data-stu-id="71fc1-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="71fc1-125">Перейдите [к добавлению записей DNS](create-dns-records-at-any-dns-hosting-provider.md)для подключения домена и выполните действия по добавлению записей на веб-сайте хоста DNS.</span><span class="sxs-lookup"><span data-stu-id="71fc1-125">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>

5. <span data-ttu-id="71fc1-126">Следуйте указаниям, чтобы создать записи в своем узле DNS.</span><span class="sxs-lookup"><span data-stu-id="71fc1-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="71fc1-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="71fc1-127">Related content</span></span>

<span data-ttu-id="71fc1-128">[Вопросы и ответы о доменах](../setup/domains-faq.yml) (статья)</span><span class="sxs-lookup"><span data-stu-id="71fc1-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="71fc1-129">[Поиск и устранение неполадок после добавления домена и записей DNS](find-and-fix-issues.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="71fc1-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="71fc1-130">[Управление доменами](index.yml) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="71fc1-130">[Manage domains](index.yml) (link page)</span></span>