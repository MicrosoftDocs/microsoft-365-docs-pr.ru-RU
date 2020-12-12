---
title: Использование Подключения к домену
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
description: Узнайте, как работать с регистраторами с поддержкой Domain Connect и добавлять домен в Microsoft 365.
ms.openlocfilehash: 109255d82100e636e3472242866a519ff64a9e54
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655616"
---
# <a name="using-domain-connect"></a><span data-ttu-id="eb1ba-103">Использование Подключения к домену</span><span class="sxs-lookup"><span data-stu-id="eb1ba-103">Using Domain Connect</span></span>

 <span data-ttu-id="eb1ba-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="eb1ba-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="eb1ba-105">[Регистраторы ](https://www.domainconnect.org/) с включенным подключением к домену позволяют добавлять домен в Microsoft 365 в течение трех этапов, который занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="eb1ba-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="eb1ba-106">В мастере мы просто подтвердим, что вы владеете доменом, а затем автоматически настроим записи домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Microsoft 365, например Teams, работают с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="eb1ba-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eb1ba-107">Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.</span><span class="sxs-lookup"><span data-stu-id="eb1ba-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="eb1ba-108">Интеграция регистраторов Domain Connect с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eb1ba-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="eb1ba-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="eb1ba-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="eb1ba-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="eb1ba-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="eb1ba-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="eb1ba-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="eb1ba-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="eb1ba-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="eb1ba-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="eb1ba-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="eb1ba-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="eb1ba-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="eb1ba-115">SecureServer или WildWestDomains (resellers GoDaddy using SecureServer DNS hosting)</span><span class="sxs-lookup"><span data-stu-id="eb1ba-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="eb1ba-116">Домены MadDog</span><span class="sxs-lookup"><span data-stu-id="eb1ba-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="eb1ba-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="eb1ba-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="eb1ba-118">Что происходит с электронной почтой и веб-сайтом?</span><span class="sxs-lookup"><span data-stu-id="eb1ba-118">What happens to my email and website?</span></span>

<span data-ttu-id="eb1ba-119">После завершения настройки запись MX для вашего домена будет обновлена так, чтобы она указыировала на Microsoft 365, и вся электронная почта для вашего домена начнет приходить в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb1ba-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="eb1ba-120">Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту в вашем домене!</span><span class="sxs-lookup"><span data-stu-id="eb1ba-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="eb1ba-121">Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде.</span><span class="sxs-lookup"><span data-stu-id="eb1ba-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="eb1ba-122">Действия по настройке Domain Connect не влияют на ваш веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="eb1ba-122">The Domain Connect setup steps don't affect your website.</span></span>
