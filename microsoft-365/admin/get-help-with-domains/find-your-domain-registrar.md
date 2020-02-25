---
title: Поиск регистратора доменных имен для Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Узнайте, как найти регистратора доменных имен и поставщика услуг размещения DNS с помощью поиска InterNIC.
ms.openlocfilehash: 058eb4468e073b6929fbc763b3d9bdb189063213
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255135"
---
# <a name="find-your-domain-registrar-for-office-365"></a><span data-ttu-id="c94c4-103">Поиск регистратора доменных имен для Office 365</span><span class="sxs-lookup"><span data-stu-id="c94c4-103">Find your domain registrar for Office 365</span></span>

 <span data-ttu-id="c94c4-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="c94c4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="c94c4-105">Регистратор доменных имен</span><span class="sxs-lookup"><span data-stu-id="c94c4-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="c94c4-106">Поиск регистратора доменных имен</span><span class="sxs-lookup"><span data-stu-id="c94c4-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="c94c4-107">С этим средством работают только домены, заканчивающиеся на *.COM*, *.NET* и *.EDU*.</span><span class="sxs-lookup"><span data-stu-id="c94c4-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="c94c4-108">На [странице поиска InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770) в поле **Whois Search** (Поиск в Whois) введите имя своего домена,</span><span class="sxs-lookup"><span data-stu-id="c94c4-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="c94c4-109">например, *contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="c94c4-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="c94c4-110">Установите переключатель в положение **Domain** (Домен) и нажмите кнопку **Submit** (Отправить).</span><span class="sxs-lookup"><span data-stu-id="c94c4-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="c94c4-111">На странице **Whois Search Results** (Результаты поиска Whois) найдите запись **Registrar** (Регистратор).</span><span class="sxs-lookup"><span data-stu-id="c94c4-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="c94c4-112">Эта запись соответствует организации, предоставляющей услуги регистрации для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="c94c4-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="c94c4-113">Поставщик услуг размещения DNS</span><span class="sxs-lookup"><span data-stu-id="c94c4-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="c94c4-114">Поиск поставщика услуг размещения DNS</span><span class="sxs-lookup"><span data-stu-id="c94c4-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="c94c4-115">С этим средством работают только домены, заканчивающиеся на *.COM*, *.NET* и *.EDU*.</span><span class="sxs-lookup"><span data-stu-id="c94c4-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="c94c4-116">На [странице поиска InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770) в поле **Whois Search** (Поиск в Whois) введите имя своего домена,</span><span class="sxs-lookup"><span data-stu-id="c94c4-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="c94c4-117">например, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c94c4-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="c94c4-118">Установите переключатель в положение **Domain** (Домен) и нажмите кнопку **Submit** (Отправить).</span><span class="sxs-lookup"><span data-stu-id="c94c4-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="c94c4-119">На странице **Whois Search Results** (Результаты поиска Whois) найдите первую запись **Name Server** (Сервер доменных имен).</span><span class="sxs-lookup"><span data-stu-id="c94c4-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="c94c4-120">Скопируйте сведения о сервере доменных имен после двоеточия (:) и вставьте их в поле **Search** (Поиск) вверху страницы.</span><span class="sxs-lookup"><span data-stu-id="c94c4-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="c94c4-121">Установите переключатель в положение **Nameserver** (Сервер доменных имен) и нажмите кнопку **Submit** (Отправить).</span><span class="sxs-lookup"><span data-stu-id="c94c4-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="c94c4-p105">На странице **Whois Search Results** (Результаты поиска Whois) найдите запись **Registrar** (Регистратор). В этой записи содержится название поставщика услуг размещения DNS, которому принадлежит сервер имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="c94c4-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

