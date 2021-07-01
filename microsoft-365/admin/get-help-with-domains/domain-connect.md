---
title: Использование доменных Подключение
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
description: Узнайте, как работать с регистраторами Подключение домена и добавить домен в Microsoft 365.
ms.openlocfilehash: 12e1f227c0a157414b56fd04f99e5460a1eb05d4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228017"
---
# <a name="using-domain-connect"></a><span data-ttu-id="6d4b7-103">Использование доменных Подключение</span><span class="sxs-lookup"><span data-stu-id="6d4b7-103">Using Domain Connect</span></span>

 <span data-ttu-id="6d4b7-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="6d4b7-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="6d4b7-105">[Регистраторы Подключение](https://www.domainconnect.org/) домена позволяют добавлять домен в Microsoft 365 в трехшаговом процессе, который занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="6d4b7-105">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span>

<span data-ttu-id="6d4b7-106">В мастере мы просто подтвердим, что вы владеете доменом, а затем автоматически настроим записи вашего домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Microsoft 365, например Teams, работают с доменом.</span><span class="sxs-lookup"><span data-stu-id="6d4b7-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>

> [!NOTE]
> <span data-ttu-id="6d4b7-107">Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.</span><span class="sxs-lookup"><span data-stu-id="6d4b7-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="6d4b7-108">Регистраторы Подключение доменов, интегрируясь с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d4b7-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="6d4b7-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="6d4b7-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="6d4b7-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="6d4b7-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="6d4b7-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="6d4b7-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="6d4b7-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="6d4b7-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="6d4b7-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="6d4b7-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="6d4b7-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="6d4b7-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="6d4b7-115">SecureServer или WildWestDomains (реселлеры GoDaddy с помощью DNS-хостинга SecureServer)</span><span class="sxs-lookup"><span data-stu-id="6d4b7-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
  - [<span data-ttu-id="6d4b7-116">Веб-хостинг MadDog</span><span class="sxs-lookup"><span data-stu-id="6d4b7-116">MadDog Web Hosting</span></span>](https://maddogwebhosting.com/domains/)
  - [<span data-ttu-id="6d4b7-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="6d4b7-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="6d4b7-118">Что происходит с моей электронной почтой и веб-сайтом?</span><span class="sxs-lookup"><span data-stu-id="6d4b7-118">What happens to my email and website?</span></span>

<span data-ttu-id="6d4b7-119">После завершения настройки записи MX для вашего домена обновляется, чтобы указать на Microsoft 365 и вся электронная почта для вашего домена начнет приходить в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d4b7-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="6d4b7-120">Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту на вашем домене!</span><span class="sxs-lookup"><span data-stu-id="6d4b7-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>

<span data-ttu-id="6d4b7-121">Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде.</span><span class="sxs-lookup"><span data-stu-id="6d4b7-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="6d4b7-122">Действия Подключение домена не влияют на веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="6d4b7-122">The Domain Connect setup steps don't affect your website.</span></span>
