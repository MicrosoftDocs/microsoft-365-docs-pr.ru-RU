---
title: Использование подключения к домену
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
description: Узнайте, как работать с регистраторами с поддержкой подключения к домену и добавлять свой домен в Microsoft 365.
ms.openlocfilehash: e907317ec5b606c2fe73232a73c9abdfce26feea
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645351"
---
# <a name="using-domain-connect"></a><span data-ttu-id="caa48-103">Использование подключения к домену</span><span class="sxs-lookup"><span data-stu-id="caa48-103">Using Domain Connect</span></span>

 <span data-ttu-id="caa48-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="caa48-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="caa48-105">Регистраторы с поддержкой [подключения к домену](https://www.domainconnect.org/) позволяют добавить свой домен в Microsoft 365 в процессе, сокоторый в течение трех этапов.</span><span class="sxs-lookup"><span data-stu-id="caa48-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="caa48-106">В мастере мы просто подтверждаю, что вы владеете доменом и автоматически настроили записи вашего домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Майкрософт 365, например команды, работающие с доменом.</span><span class="sxs-lookup"><span data-stu-id="caa48-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="caa48-107">Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.</span><span class="sxs-lookup"><span data-stu-id="caa48-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="caa48-108">Служба регистраторов подключений к доменам интеграция с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="caa48-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="caa48-109">1 &amp; 1 ионос</span><span class="sxs-lookup"><span data-stu-id="caa48-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="caa48-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="caa48-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="caa48-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="caa48-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="caa48-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="caa48-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="caa48-113">плеск</span><span class="sxs-lookup"><span data-stu-id="caa48-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="caa48-114">медиатемпле</span><span class="sxs-lookup"><span data-stu-id="caa48-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="caa48-115">Секуресервер или Вилдвестдомаинс (GoDaddy торговые посредники, использующие службу хостинга на Секуресервер DNS)</span><span class="sxs-lookup"><span data-stu-id="caa48-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="caa48-116">Домены Маддог</span><span class="sxs-lookup"><span data-stu-id="caa48-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="caa48-117">чеапнамес</span><span class="sxs-lookup"><span data-stu-id="caa48-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="caa48-118">Что происходит с электронной почтой и веб-сайтом?</span><span class="sxs-lookup"><span data-stu-id="caa48-118">What happens to my email and website?</span></span>

<span data-ttu-id="caa48-119">После завершения установки запись MX для вашего домена будет обновлена, чтобы она ссылалась на Microsoft 365, а вся электронная почта для вашего домена будет начинаться с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="caa48-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="caa48-120">Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту в вашем домене.</span><span class="sxs-lookup"><span data-stu-id="caa48-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="caa48-121">Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде.</span><span class="sxs-lookup"><span data-stu-id="caa48-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="caa48-122">Действия по настройке подключения к домену не повлияют на ваш веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="caa48-122">The Domain Connect setup steps don't affect your website.</span></span>
