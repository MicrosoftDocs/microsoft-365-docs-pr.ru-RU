---
title: Использование подключения домена
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Узнайте, как работать с регистраторами включенного подключения домена и добавить домен в Microsoft 365.
ms.openlocfilehash: 5dec69f70273e6a9430ce5926ed07888e197adcd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860659"
---
# <a name="using-domain-connect"></a><span data-ttu-id="5c2e5-103">Использование подключения домена</span><span class="sxs-lookup"><span data-stu-id="5c2e5-103">Using Domain Connect</span></span>

 <span data-ttu-id="5c2e5-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="5c2e5-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="5c2e5-105">[Регистраторы ](https://www.domainconnect.org/) подключения к домену позволяют добавлять домен в Microsoft 365 в трехшаговом процессе, который занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="5c2e5-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="5c2e5-106">В мастере мы просто подтвердим, что вы владеете доменом, а затем автоматически настроим записи домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Microsoft 365, такие как Teams, работайте с доменом.</span><span class="sxs-lookup"><span data-stu-id="5c2e5-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c2e5-107">Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.</span><span class="sxs-lookup"><span data-stu-id="5c2e5-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="5c2e5-108">Регистраторы Domain Connect, интегрируясь с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5c2e5-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="5c2e5-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="5c2e5-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="5c2e5-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="5c2e5-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="5c2e5-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="5c2e5-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="5c2e5-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="5c2e5-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="5c2e5-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="5c2e5-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="5c2e5-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="5c2e5-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="5c2e5-115">SecureServer или WildWestDomains (реселлеры GoDaddy с помощью DNS-хостинга SecureServer)</span><span class="sxs-lookup"><span data-stu-id="5c2e5-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="5c2e5-116">Веб-хостинг MadDog</span><span class="sxs-lookup"><span data-stu-id="5c2e5-116">MadDog Web Hosting</span></span>](https://maddogwebhosting.com/domains/)
    - [<span data-ttu-id="5c2e5-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="5c2e5-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="5c2e5-118">Что происходит с моей электронной почтой и веб-сайтом?</span><span class="sxs-lookup"><span data-stu-id="5c2e5-118">What happens to my email and website?</span></span>

<span data-ttu-id="5c2e5-119">После завершения настройки запись MX для вашего домена обновляется, чтобы указать на Microsoft 365, и вся электронная почта для вашего домена начнет приходить в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5c2e5-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="5c2e5-120">Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту на вашем домене!</span><span class="sxs-lookup"><span data-stu-id="5c2e5-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="5c2e5-121">Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде.</span><span class="sxs-lookup"><span data-stu-id="5c2e5-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="5c2e5-122">Действия установки подключения к домену не влияют на веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="5c2e5-122">The Domain Connect setup steps don't affect your website.</span></span>
