---
title: Как работают безопасные ссылки ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Функция "безопасные ссылки" обеспечивает проверку гиперссылок в документах Office и в сообщениях электронной почты. Прочтите эту статью, чтобы узнать, как работают безопасные ссылки ATP.
ms.openlocfilehash: e79c44b91eb5de7564058b4dc50c94d2a4223f08
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046368"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="d9477-104">Как работают безопасные ссылки ATP</span><span class="sxs-lookup"><span data-stu-id="d9477-104">How ATP Safe Links works</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="d9477-105">Для правильной работы ссылок на Office 365 ATP для безопасной работы все службы должны иметь одинаковую версию.</span><span class="sxs-lookup"><span data-stu-id="d9477-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="d9477-106">Как безопасные ссылки ATP работают с URL-адресами в электронной почте</span><span class="sxs-lookup"><span data-stu-id="d9477-106">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="d9477-107">На высоком уровне: в этой статье описывается работа защиты [ATP-ссылок](atp-safe-links.md) в адресах электронной почты (размещенной в Office 365, а не в локальной среде).</span><span class="sxs-lookup"><span data-stu-id="d9477-107">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="d9477-108">Пользователи получают сообщения электронной почты, некоторые из которых содержат URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="d9477-108">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="d9477-109">Вся электронная почта проходит через Exchange Online Protection, в которой применяются фильтры IP-адресов и конвертов, защита от вредоносных программ на основе подписей, защита от нежелательной почты и фильтры защиты от вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="d9477-109">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="d9477-110">Сообщения электронной почты приходят в папках "Входящие" пользователей.</span><span class="sxs-lookup"><span data-stu-id="d9477-110">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="d9477-111">Пользователь входит в Office 365 и отправляется в папку "Входящие" электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d9477-111">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="d9477-112">Пользователь открывает сообщение электронной почты и щелкает URL-адрес в сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d9477-112">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="d9477-113">Функция безопасных ссылок ATP немедленно проверяет URL-адрес перед открытием веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="d9477-113">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="d9477-114">URL-адрес идентифицируется как заблокированный, злонамеренный или безопасный.</span><span class="sxs-lookup"><span data-stu-id="d9477-114">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="d9477-115">Если URL-адрес относится к веб-сайту, который включен в [список пользовательских заблокированных URL-адресов](set-up-a-custom-blocked-urls-list-atp.md)Организации, откроется [Страница с предупреждением](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="d9477-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="d9477-116">Если URL-адрес относится к веб-сайту, который был определен как вредоносный, откроется [Страница с предупреждением](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="d9477-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="d9477-117">Если URL-адрес помещается в загружаемый файл, а [политики безопасных ссылок ATP](set-up-atp-safe-links-policies.md) в организации настроены на проверку такого содержимого, загружаемый файл проверяется.</span><span class="sxs-lookup"><span data-stu-id="d9477-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="d9477-118">Если URL-адрес определен как безопасный, откроется веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="d9477-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="d9477-119">Как безопасные ссылки ATP работают с URL-адресами в документах Office</span><span class="sxs-lookup"><span data-stu-id="d9477-119">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="d9477-120">На высоком уровне ниже показано, как работает защита [ATP: безопасные ссылки](atp-safe-links.md) для URL-адресов в приложениях Microsoft 365 для корпоративных или бизнес-приложений (текущие версии Word, Excel и PowerPoint в Windows, Mac или в браузере, приложения Office на устройствах с iOS или Android, Visio в Windows, OneNote в браузере):</span><span class="sxs-lookup"><span data-stu-id="d9477-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="d9477-121">Пользователи установили приложения Microsoft 365 для Enterprise или Business Premium на своем компьютере, смартфоне или планшете.</span><span class="sxs-lookup"><span data-stu-id="d9477-121">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="d9477-122">(Или они используют Office в браузере.)</span><span class="sxs-lookup"><span data-stu-id="d9477-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="d9477-123">Пользователь открывает Word, Excel, PowerPoint, OneNote (в браузере) или Visio (на настольном компьютере) и входит в Office 365 корпоративный с помощью рабочей или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d9477-123">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="d9477-124">Документ содержит URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="d9477-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="d9477-125">Когда пользователь щелкает URL-адрес в документе, эта ссылка проверяется службой "безопасные ссылки ATP".</span><span class="sxs-lookup"><span data-stu-id="d9477-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="d9477-126">Если URL-адрес относится к веб-сайту, который включен в [список пользовательских заблокированных URL-адресов](set-up-a-custom-blocked-urls-list-atp.md)Организации, пользователь переводится на [страницу предупреждения](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="d9477-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="d9477-127">Если URL-адрес относится к веб-сайту, который был определен как вредоносный, пользователь переводится на [страницу предупреждения](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="d9477-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="d9477-128">Если URL-адрес помещается в загружаемый файл, а [политики безопасных ссылок ATP](set-up-atp-safe-links-policies.md) настроены на проверку таких загружаемых файлов, то загружаемый файл проверяется.</span><span class="sxs-lookup"><span data-stu-id="d9477-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="d9477-129">Если URL-адрес считается безопасным, пользователь передается на веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="d9477-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="d9477-130">Если проверка URL-адреса завершается неудачно, защита безопасных ссылок не будет инициироваться.</span><span class="sxs-lookup"><span data-stu-id="d9477-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="d9477-131">На настольных компьютерах перед переходом на сайт будет выводиться предупреждение пользователя.</span><span class="sxs-lookup"><span data-stu-id="d9477-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="d9477-132">В начале каждого сеанса может потребоваться несколько секунд, чтобы убедиться, что пользователь обладает безопасными ссылками ATP для Office Enabled.</span><span class="sxs-lookup"><span data-stu-id="d9477-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
