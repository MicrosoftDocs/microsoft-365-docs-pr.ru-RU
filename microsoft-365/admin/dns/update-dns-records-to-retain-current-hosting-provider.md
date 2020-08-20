---
title: Обновление DNS-записей для сохранения веб-сайта у текущего поставщика услуг размещения веб-сайтов
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: Узнайте, как маршрутизировать трафик на существующий общедоступный веб-сайт, размещенный за пределами Корпорации Майкрософт, если вы настроили корпорацию Майкрософт управление записями DNS для личного домена.
ms.openlocfilehash: 9a7090eef3ce7d1c67839e7320f31d7bd32aa6a7
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814402"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="5b8e7-103">Обновление DNS-записей для сохранения веб-сайта у текущего поставщика услуг размещения веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="5b8e7-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="5b8e7-104">**Если вы управляете записями Майкрософт**своего домена на сайте поставщика услуг размещения DNS, вам не нужно выполнять действия, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="5b8e7-105">Ваш веб-сайт останется там же, где и прежде, и будет доступен пользователям.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="5b8e7-106">**Если корпорация Майкрософт управляет записями DNS,** после добавления домена в корпорацию Майкрософт выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="5b8e7-107">Обновление записей DNS в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5b8e7-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="5b8e7-108">В Центре администрирования перейдите на страницу **Settings** (Параметры) \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> (Домены).</span><span class="sxs-lookup"><span data-stu-id="5b8e7-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="5b8e7-109">На странице **"Домены"** выберите домен, а затем выберите **"DNS-записи".**</span><span class="sxs-lookup"><span data-stu-id="5b8e7-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="5b8e7-110">В разделе **параметров DNS выберите**пункт Custom **Records (Настраиваемые записи).**</span><span class="sxs-lookup"><span data-stu-id="5b8e7-110">Under **DNS settings**, select **Custom Records**.</span></span>

4. <span data-ttu-id="5b8e7-111">Нажмите кнопку **+ Создать настраиваемую запись** и введите указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-111">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="5b8e7-112">В поле **Тип DNS** введите **A (адрес)**.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-112">For **DNS type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="5b8e7-113">В поле **Имя узла или псевдоним** введите **@**.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-113">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="5b8e7-114">В поле **IP-адрес** введите текущий IP-адрес веб-сайта, например 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-114">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="5b8e7-p102">Это должен быть  *статический*  , а не  *динамический*  IP-адрес веб-сайта. Уточнить возможность получения статического IP-адреса можно у поставщика услуг размещения, у которого находится ваш общедоступный веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
5. <span data-ttu-id="5b8e7-117">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-117">Select **Save**.</span></span> 
    
<span data-ttu-id="5b8e7-118">Кроме того, можно создать запись CNAME, чтобы упростить поиск веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-118">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="5b8e7-119">Нажмите кнопку **+ Создать настраиваемую запись** и введите указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-119">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="5b8e7-120">В поле **Тип DNS** введите **CNAME (псевдоним)**.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-120">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="5b8e7-121">В поле **Имя узла или псевдоним** введите **www**.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-121">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="5b8e7-122">В качестве значения **Адрес "указывает на"** введите полное доменное имя (FQDN) своего веб-сайта, например contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-122">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="5b8e7-123">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-123">Select **Save**.</span></span> 
    
<span data-ttu-id="5b8e7-124">Напоследок выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="5b8e7-124">Finally, do the following:</span></span>
  
<span data-ttu-id="5b8e7-125">[Обновите записи сервера доменных имен домена так, чтобы](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) он указывал на Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-125">[Update your domain's NS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to point to Microsoft.</span></span> 
  
<span data-ttu-id="5b8e7-126">Когда записи NS будут обновлены для того, чтобы указывала на Майкрософт, ваш домен настроен.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-126">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="5b8e7-127">Электронная почта будет направляться в корпорацию Майкрософт, а трафик, поступившей на ваш веб-сайт, будет по-прежнему поступить на текущий хост веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-127">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
