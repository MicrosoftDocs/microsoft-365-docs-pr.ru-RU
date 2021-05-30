---
title: Поиск регистратора доменных имен
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Узнайте, как найти регистратора доменных имен и поставщика услуг размещения DNS с помощью поиска InterNIC.
ms.openlocfilehash: af883f53c8c45aee2594b0f5b8b9da57e5717f9e
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706398"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="0c04b-103">Поиск регистратора доменных имен</span><span class="sxs-lookup"><span data-stu-id="0c04b-103">Find your domain registrar</span></span>

 <span data-ttu-id="0c04b-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="0c04b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="0c04b-105">Регистратор доменных имен</span><span class="sxs-lookup"><span data-stu-id="0c04b-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="0c04b-106">Поиск регистратора доменных имен</span><span class="sxs-lookup"><span data-stu-id="0c04b-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="0c04b-107">С этим средством работают только домены, заканчивающиеся на *.COM*, *.NET* и *.EDU*.</span><span class="sxs-lookup"><span data-stu-id="0c04b-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="0c04b-p101">На [странице поиска InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770) в поле **Whois Search** (Поиск в Whois) введите имя своего домена, например *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="0c04b-p101">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="0c04b-110">Выберите **Domain** (Домен) и нажмите кнопку **Submit** (Отправить).</span><span class="sxs-lookup"><span data-stu-id="0c04b-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="0c04b-p102">На странице **Whois Search Results** (Результаты поиска Whois) найдите запись **Registrar** (Регистратор). Эта запись относится к организации, предоставляющей услуги регистрации для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="0c04b-p102">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="0c04b-113">Поставщик услуг размещения DNS</span><span class="sxs-lookup"><span data-stu-id="0c04b-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="0c04b-114">Поиск поставщика услуг размещения DNS</span><span class="sxs-lookup"><span data-stu-id="0c04b-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="0c04b-115">С этим средством работают только домены, заканчивающиеся на *.COM*, *.NET* и *.EDU*.</span><span class="sxs-lookup"><span data-stu-id="0c04b-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="0c04b-p103">На странице поиска [InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770) в поле **Whois Search** (Поиск в Whois) введите имя своего домена, например contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0c04b-p103">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="0c04b-118">Установите переключатель в положение **Domain** (Домен) и нажмите кнопку **Submit** (Отправить).</span><span class="sxs-lookup"><span data-stu-id="0c04b-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="0c04b-119">На странице **Whois Search Results** (Результаты поиска Whois) найдите первую запись **Name Server** (Сервер доменных имен).</span><span class="sxs-lookup"><span data-stu-id="0c04b-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="0c04b-p104">Скопируйте сведения о сервере доменных имен после двоеточия (:) и вставьте их в поле **Search** (Поиск) вверху страницы. Установите переключатель в положение **Nameserver** (Сервер доменных имен) и нажмите кнопку **Submit** (Отправить).</span><span class="sxs-lookup"><span data-stu-id="0c04b-p104">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="0c04b-p105">На странице **Whois Search Results** (Результаты поиска Whois) найдите запись **Registrar** (Регистратор). В этой записи содержится название поставщика услуг размещения DNS, которому принадлежит сервер имен для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="0c04b-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

