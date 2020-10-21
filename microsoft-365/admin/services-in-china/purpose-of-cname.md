---
title: Зачем нужна запись CNAME в Office 365 для MSOID?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Узнайте больше о записи CNAME "MSOID" в Office 365, которая направляет вас на лучший сервер для процессов проверки подлинности, чтобы вы могли быстрее отреагировать на них.
monikerRange: o365-21vianet
ms.openlocfilehash: ac9ad3ad9f860722760d59c54570a453146a3a93
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644643"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a><span data-ttu-id="a2175-103">Зачем нужна запись CNAME в Office 365 для MSOID?</span><span class="sxs-lookup"><span data-stu-id="a2175-103">What's the purpose of the Office 365 CNAME record for MSOID?</span></span>

 <span data-ttu-id="a2175-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="a2175-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
> [!NOTE]
> <span data-ttu-id="a2175-105">Следующий пример относится только к \* \* Office 365 под управлением 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="a2175-105">The following only Applies to \*\*Office 365 operated by 21Vianet.</span></span>
  
<span data-ttu-id="a2175-p101">У вас может возникнуть вопрос: зачем нужно добавлять в Office 365 запись CNAME "MSOID"? Эту запись необходимо добавить для всех личных доменов независимо от вида подписки. Зачем она нужна? Это технический, но важный вопрос. Запись направляет вас на лучший сервер проверки подлинности, позволяющий вам получить самый быстрый отклик.</span><span class="sxs-lookup"><span data-stu-id="a2175-p101">You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.</span></span>
  
<span data-ttu-id="a2175-p102">Технические подробности: при запуске клиентского приложения, взаимодействующего с Office 365, например Skype для бизнеса online, Outlook, Windows PowerShell или средства синхронизации Microsoft Azure Active Directory, ваши учетные данные должны пройти проверку подлинности. В Office 365 используется запись CNAME, которая указывает на оптимальную конечную точку проверки подлинности для вашего региона. Это позволяет уменьшить время отклика при проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="a2175-p102">Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.</span></span>
  
<span data-ttu-id="a2175-p103">Если эта запись CNAME не указана для вашего домена, то в приложениях будет использоваться конечная точка по умолчанию, которая находится в США. Это может замедлить проверку. Если же запись CNAME настроена неправильно (например, неверно введен адрес в поле **Указывает на**), то приложения вообще не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="a2175-p103">If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.</span></span>
  
 <span data-ttu-id="a2175-114">**Если Office 365 управляет записями DNS вашего домена,** Office 365 настраивает эту запись CNAME.</span><span class="sxs-lookup"><span data-stu-id="a2175-114">**If Office 365 manages your domain's DNS records,** Office 365 sets up this CNAME record for you.</span></span> 
  
 <span data-ttu-id="a2175-115">**Если вы управляете записями DNS для своего домена на узле DNS,** вы самостоятельно создадите эту запись, [следуя инструкциям для узла DNS](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="a2175-115">**If you are managing DNS records for your domain at your DNS host,** you create this record yourself by [following the instructions for your DNS host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>
  
<span data-ttu-id="a2175-116">Если вы планируете развертывание Office 365 и хотите узнать больше о всех записях DNS, которые может потребоваться добавить или обновить, ознакомьтесь со сведениями о них в [справочной системе: внешние DNS-записи службы доменных имен для Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).</span><span class="sxs-lookup"><span data-stu-id="a2175-116">If you're planning an Office 365 deployment and want to learn more about all the DNS records that you may need to add or update, read about them in [Reference: External Domain Name System records for Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).</span></span>
  

