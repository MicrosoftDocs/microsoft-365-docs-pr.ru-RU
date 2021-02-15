---
title: Обновление DNS-записей для сохранения веб-сайта у текущего поставщика услуг размещения веб-сайтов
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Узнайте, как перенаправить трафик на существующий общедоступный веб-сайт, который находится за пределами Майкрософт, если вы настроили Корпорацию Майкрософт на управление записями DNS для вашего пользовательского домена.
ms.openlocfilehash: 5d2bf23d4052815fae210d0fdf6635288ff46b57
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645567"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="cc727-103">Обновление DNS-записей для сохранения веб-сайта у текущего поставщика услуг размещения веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="cc727-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="cc727-104">**Если вы управляете записями Майкрософт** своего домена у поставщика услуг размещения DNS, вам не нужно беспокоиться о действиях, которые необходимо предпринять в этой теме.</span><span class="sxs-lookup"><span data-stu-id="cc727-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="cc727-105">Ваш веб-сайт останется там же, где и прежде, и будет доступен пользователям.</span><span class="sxs-lookup"><span data-stu-id="cc727-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="cc727-106">Если корпорация Майкрософт управляет вашими **записями DNS,** чтобы перенаправить трафик на существующий общедоступный веб-сайт, который находится за пределами Майкрософт, после добавления домена в корпорацию Майкрософт, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="cc727-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="cc727-107">Обновление записей DNS в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc727-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="cc727-108">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="cc727-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="cc727-109">На странице **"Домены"** выберите домен и затем выберите **"Записи DNS".**</span><span class="sxs-lookup"><span data-stu-id="cc727-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="cc727-110">В **параметрах DNS выберите** **настраиваемые записи.**</span><span class="sxs-lookup"><span data-stu-id="cc727-110">Under **DNS settings**, select **Custom Records**.</span></span>

4. <span data-ttu-id="cc727-111">Нажмите кнопку **+ Создать настраиваемую запись** и введите указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="cc727-111">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="cc727-112">В поле **Тип DNS** введите **A (адрес)**.</span><span class="sxs-lookup"><span data-stu-id="cc727-112">For **DNS type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="cc727-113">В поле **Имя узла или псевдоним** введите **@**.</span><span class="sxs-lookup"><span data-stu-id="cc727-113">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="cc727-114">В поле **IP-адрес** введите текущий IP-адрес веб-сайта, например 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="cc727-114">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="cc727-p102">Это должен быть  *статический*  , а не  *динамический*  IP-адрес веб-сайта. Уточнить возможность получения статического IP-адреса можно у поставщика услуг размещения, у которого находится ваш общедоступный веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="cc727-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
5. <span data-ttu-id="cc727-117">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cc727-117">Select **Save**.</span></span> 
    
<span data-ttu-id="cc727-118">Кроме того, можно создать запись CNAME, чтобы упростить поиск веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="cc727-118">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="cc727-119">Нажмите кнопку **+ Создать настраиваемую запись** и введите указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="cc727-119">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="cc727-120">В поле **Тип DNS** введите **CNAME (псевдоним)**.</span><span class="sxs-lookup"><span data-stu-id="cc727-120">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="cc727-121">В поле **Имя узла или псевдоним** введите **www**.</span><span class="sxs-lookup"><span data-stu-id="cc727-121">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="cc727-122">В качестве значения **Адрес "указывает на"** введите полное доменное имя (FQDN) своего веб-сайта, например contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cc727-122">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="cc727-123">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cc727-123">Select **Save**.</span></span> 
    
<span data-ttu-id="cc727-124">Напоследок выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="cc727-124">Finally, do the following:</span></span>
  
<span data-ttu-id="cc727-125">[Обновите записи доменных имен,](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) указав на Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc727-125">[Update your domain's NS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to point to Microsoft.</span></span> 
  
<span data-ttu-id="cc727-126">Когда записи NS обновлены так, чтобы они указывают на Корпорацию Майкрософт, ваш домен настроен.</span><span class="sxs-lookup"><span data-stu-id="cc727-126">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="cc727-127">Электронная почта будет отправлена в корпорацию Майкрософт, а трафик на ваш адрес веб-сайта будет по-прежнему перенаходить на текущий сайт.</span><span class="sxs-lookup"><span data-stu-id="cc727-127">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
