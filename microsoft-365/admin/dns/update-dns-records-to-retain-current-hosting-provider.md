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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Узнайте, как маршрутизировать трафик на существующий общедоступный веб-сайт, размещенный вне Office 365, если вы настроили Office 365 для управления записями DNS для вашего личного домена.
ms.openlocfilehash: de95818eea729cb11972faf986c9be40bb6e76da
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255354"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="2fd66-103">Обновление DNS-записей для сохранения веб-сайта у текущего поставщика услуг размещения веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="2fd66-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="2fd66-p101">**Если вы управляете записями Office 365 домена на ресурсе поставщика услуг размещения DNS**, вам не нужно выполнять действия, описанные в этом разделе. Ваш веб-сайт останется там же, где и прежде, и будет доступен пользователям.</span><span class="sxs-lookup"><span data-stu-id="2fd66-p101">**If you manage your domain's Office 365 records at your DNS hosting provider**, you don't have to worry about the steps in this topic. Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="2fd66-106">**Если записями DNS управляет Office 365**, выполните указанные ниже действия, чтобы настроить маршрутизацию трафика на существующий общедоступный веб-сайт за пределами Office 365 после добавления домена в Office 365.</span><span class="sxs-lookup"><span data-stu-id="2fd66-106">**If Office 365 manages your DNS records**, to route traffic to an existing public website hosted outside of Office 365, after you add your domain to Office 365, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="2fd66-107">Обновление записей DNS в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2fd66-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="2fd66-108">В центре администрирования перейдите на страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">домены</a> **параметров** \> ".</span><span class="sxs-lookup"><span data-stu-id="2fd66-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="2fd66-109">На странице **Домены** в списке доменов выберите домен, который используете для своего веб-сайта, а затем щелкните **Параметры DNS** на панели управления.</span><span class="sxs-lookup"><span data-stu-id="2fd66-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="2fd66-110">Нажмите кнопку **+ Создать настраиваемую запись** и введите указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="2fd66-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="2fd66-111">В поле **Тип DNS** введите **A (адрес)**.</span><span class="sxs-lookup"><span data-stu-id="2fd66-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="2fd66-112">В поле **Имя узла или псевдоним** введите **@**.</span><span class="sxs-lookup"><span data-stu-id="2fd66-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="2fd66-113">В поле **IP-адрес** введите текущий IP-адрес веб-сайта, например 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="2fd66-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="2fd66-p102">Это должен быть  *статический*  , а не  *динамический*  IP-адрес веб-сайта. Уточнить возможность получения статического IP-адреса можно у поставщика услуг размещения, у которого находится ваш общедоступный веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="2fd66-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="2fd66-116">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2fd66-116">Select **Save**.</span></span> 
    
<span data-ttu-id="2fd66-117">Кроме того, можно создать запись CNAME, чтобы упростить поиск веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="2fd66-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="2fd66-118">Нажмите кнопку **+ Создать настраиваемую запись** и введите указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="2fd66-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="2fd66-119">В поле **Тип DNS** введите **CNAME (псевдоним)**.</span><span class="sxs-lookup"><span data-stu-id="2fd66-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="2fd66-120">В поле **Имя узла или псевдоним** введите **www**.</span><span class="sxs-lookup"><span data-stu-id="2fd66-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="2fd66-121">В качестве значения **Адрес "указывает на"** введите полное доменное имя (FQDN) своего веб-сайта, например contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2fd66-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="2fd66-122">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2fd66-122">Select **Save**.</span></span> 
    
<span data-ttu-id="2fd66-123">Напоследок выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="2fd66-123">Finally, do the following:</span></span>
  
<span data-ttu-id="2fd66-124">[Измените NS-записи домена](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) так, чтобы они указывали на Office 365.</span><span class="sxs-lookup"><span data-stu-id="2fd66-124">[Update your domain's NS records](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) to point to Office 365.</span></span> 
  
<span data-ttu-id="2fd66-p103">Изменив NS-записи таким образом, чтобы они указывали на Office 365, вы завершите настройку домена: почта будет направляться в Office 365, а трафик к вашему веб-сайту будет по-прежнему поступать в систему его текущего поставщика услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="2fd66-p103">When the NS records have been updated to point to Office 365, your domain is all set up. Email will be routed to Office 365, and traffic to your website address will continue to go to your current website host.</span></span>
 