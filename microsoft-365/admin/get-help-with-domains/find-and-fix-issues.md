---
title: Поиск и устранение неполадок после добавления домена и записей DNS
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Узнайте, как отслеживать любые проблемы, которые могут возникнуть при настройке пользовательского домена, убедившись, что записи DNS настроены правильно.
ms.openlocfilehash: 786df75f3f8a514e9b3c2a7666d715c9abd082bd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926394"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="d3883-103">Поиск и устранение неполадок после добавления домена и записей DNS</span><span class="sxs-lookup"><span data-stu-id="d3883-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="d3883-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="d3883-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d3883-105">Настройка домена для работы с Microsoft 365 может быть сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="d3883-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="d3883-106">С DNS-системой необходимо работать, и настройка DNS для вашего домена влияет на важные бизнес-действия, такие как электронная почта!</span><span class="sxs-lookup"><span data-stu-id="d3883-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="d3883-107">Вы можете проверить, нет ли проблем с доменом, проверив его состояние.</span><span class="sxs-lookup"><span data-stu-id="d3883-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="d3883-108">Перейдите **в "Настройка**  >  **доменов"** и просмотреть уведомления в столбце **"Состояние".**</span><span class="sxs-lookup"><span data-stu-id="d3883-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="d3883-109">Если вы видите проблему, выберите "Дополнительные действия" (три точки), а затем выберите **"Проверить состояние".**</span><span class="sxs-lookup"><span data-stu-id="d3883-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="d3883-110">В открываемой области описываются все проблемы, которые произошли с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="d3883-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="d3883-111">Почему?</span><span class="sxs-lookup"><span data-stu-id="d3883-111">What's going on?</span></span>

- [<span data-ttu-id="d3883-112">Не можете проверить свой домен?</span><span class="sxs-lookup"><span data-stu-id="d3883-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="d3883-113">Outlook не работает?</span><span class="sxs-lookup"><span data-stu-id="d3883-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="d3883-114">Все сообщения электронной почты переключились на Microsoft 365, и вы хотите, чтобы ваша электронная почта переключилась?</span><span class="sxs-lookup"><span data-stu-id="d3883-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="d3883-115">Не можете подтвердить состояние некоммерческой или учебной учетной записи?</span><span class="sxs-lookup"><span data-stu-id="d3883-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="d3883-116">Службы не работают с вашим доменом?</span><span class="sxs-lookup"><span data-stu-id="d3883-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="d3883-117">Не работает доступ к веб-сайту?</span><span class="sxs-lookup"><span data-stu-id="d3883-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="d3883-118">Не удается проверить свой домен?</span><span class="sxs-lookup"><span data-stu-id="d3883-118">Can't verify your domain?</span></span>
<span data-ttu-id="d3883-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d3883-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d3883-120">Вот несколько причин, по которым может не удаваться проверить домен:</span><span class="sxs-lookup"><span data-stu-id="d3883-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="d3883-p103">**Проверочная запись неправильная.** Убедитесь, что вы скопировали и вставили точное значение в проверочную запись TXT на узле DNS. Часто пользователи забывают указать "MS =". Эта часть тоже нужна!</span><span class="sxs-lookup"><span data-stu-id="d3883-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="d3883-125">**Запись не была сохранена.**</span><span class="sxs-lookup"><span data-stu-id="d3883-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="d3883-126">На некоторых узлах DNS необходимо выполнить дополнительное действие для сохранения файла зоны (в котором хранится запись DNS), чтобы он обновился в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d3883-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="d3883-127">Убедитесь, что вы сохранили изменения, чтобы Microsoft 365 видел и проверял запись.</span><span class="sxs-lookup"><span data-stu-id="d3883-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="d3883-128">**Запись не обновилась в Интернете.**</span><span class="sxs-lookup"><span data-stu-id="d3883-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="d3883-129">Обычно новая запись становится доступна через несколько минут, но иногда ее обновление может занять до нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="d3883-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="d3883-130">Не работает Outlook?</span><span class="sxs-lookup"><span data-stu-id="d3883-130">Outlook isn't working?</span></span>
<span data-ttu-id="d3883-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="d3883-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="d3883-132">Если вы настроили свою запись MX и другие записи DNS для домена правильно, но почта не работает, мы поможем [устранить неполадки с Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="d3883-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="d3883-133">Все сообщения электронной почты переключились на Microsoft 365, и вы хотите, чтобы ваша электронная почта переключилась?</span><span class="sxs-lookup"><span data-stu-id="d3883-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="d3883-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="d3883-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="d3883-135">При добавлении домена в Microsoft 365 обычно запись MX вашего домена обновляется (вами или Microsoft 365) так, чтобы она была направлена на Microsoft 365, а Вся электронная почта, отправленная на этот домен, начиналась с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3883-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="d3883-136">Перед изменением записи MX убедитесь, что вы создали почтовые ящики в Microsoft 365 для всех, у кого есть электронная почта в вашем домене.</span><span class="sxs-lookup"><span data-stu-id="d3883-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="d3883-137">Что делать, если вы не хотите перемещать электронную почту для всех в вашем домене в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="d3883-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="d3883-138">Вы можете предпринять действия для [пилотного проекта Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)с несколькими адресами электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d3883-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="d3883-139">Не можете подтвердить состояние некоммерческой или учебной учетной записи?</span><span class="sxs-lookup"><span data-stu-id="d3883-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="d3883-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="d3883-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="d3883-141">Существует несколько сценариев, когда вам нужно просто проверить домен вашей организации и не настроить службы.</span><span class="sxs-lookup"><span data-stu-id="d3883-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="d3883-142">Например, чтобы доказать Microsoft 365, что ваша организация имеет право на подписку на учебное заведения.</span><span class="sxs-lookup"><span data-stu-id="d3883-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="d3883-143">Инструкции по проверке домена [Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) чтобы подтвердить право собственности, статус некоммерческой организации или образования или активировать Yammer, чтобы убедиться, что вы выполнили все необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="d3883-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="d3883-144">Это немного отличается для каждой ситуации.</span><span class="sxs-lookup"><span data-stu-id="d3883-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="d3883-145">Службы не работают с вашим доменом?</span><span class="sxs-lookup"><span data-stu-id="d3883-145">Services not working with your domain?</span></span>
<span data-ttu-id="d3883-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="d3883-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="d3883-147">Мы поможем вам выявить проблемы с настройкой DNS для домена.</span><span class="sxs-lookup"><span data-stu-id="d3883-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="d3883-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span><span class="sxs-lookup"><span data-stu-id="d3883-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="d3883-149">DNS настроена правильно, но почта не работает в Outlook на рабочем столе?</span><span class="sxs-lookup"><span data-stu-id="d3883-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="d3883-150">Ознакомьтесь с различными сценариями потока почты, которые вы можете использовать в [Microsoft 365,](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) чтобы убедиться, что у вас все настроено правильно для вашей компании.</span><span class="sxs-lookup"><span data-stu-id="d3883-150">Check out the [different mail flow scenarios you can have with Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="d3883-151">Дополнительную помощь по устранению неполадок с электронной почтой можно найти здесь: [Устранение неполадок в Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="d3883-151">Or get more troubleshooting help with email here: [Fix Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="d3883-152">Ваш веб-сайт недоступен?</span><span class="sxs-lookup"><span data-stu-id="d3883-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="d3883-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="d3883-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="d3883-154">Если вы устранили все неполадки DNS, но у вас по-прежнему возникают проблемы, попробуйте одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="d3883-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="d3883-155">Пользователи не могут войти на ваш веб-сайт в www.mydomain.com: [Диагностика неполадок веб-сайта](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="d3883-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span></span>
    
- <span data-ttu-id="d3883-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="d3883-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="d3883-157">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="d3883-157">Related content</span></span>

[<span data-ttu-id="d3883-158">Устранение неполадок: аудит данных при изменении проверенного домена</span><span class="sxs-lookup"><span data-stu-id="d3883-158">Troubleshoot: Audit data on verified domain change</span></span>](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
