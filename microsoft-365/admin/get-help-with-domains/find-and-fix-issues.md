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
description: Узнайте, как отслеживать любые проблемы, с которыми вы можете возникнуть при настройке настраиваемой области, убедившись, что записи DNS настроены правильно.
ms.openlocfilehash: 5959cae02b87cf481fc06edd941a6da284b71736
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537551"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="de464-103">Поиск и устранение неполадок после добавления домена и записей DNS</span><span class="sxs-lookup"><span data-stu-id="de464-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="de464-104">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="de464-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="de464-105">Настройка домена для работы с Microsoft 365 может быть сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="de464-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="de464-106">Система DNS является придиркой к работе, и установка DNS для вашего домена влияет на важные бизнес-действия, такие как электронная почта!</span><span class="sxs-lookup"><span data-stu-id="de464-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="de464-107">Вы можете проверить проблемы с доменом, проверив его состояние.</span><span class="sxs-lookup"><span data-stu-id="de464-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="de464-108">Перейдите **к**  >  **доменам установки** и просмотреть уведомления в столбце **Состояние.**</span><span class="sxs-lookup"><span data-stu-id="de464-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="de464-109">Если вы видите проблему, выберите три точки (больше действий), а затем выберите **Проверить здоровье**.</span><span class="sxs-lookup"><span data-stu-id="de464-109">If you see an issue, select the three dots (more actions), and then choose **Check health**.</span></span> <span data-ttu-id="de464-110">Открываемая область будет описывать любые проблемы, происходящие с доменом.</span><span class="sxs-lookup"><span data-stu-id="de464-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="de464-111">Почему?</span><span class="sxs-lookup"><span data-stu-id="de464-111">What's going on?</span></span>

- [<span data-ttu-id="de464-112">Не можете проверить домен?</span><span class="sxs-lookup"><span data-stu-id="de464-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="de464-113">Outlook не работает?</span><span class="sxs-lookup"><span data-stu-id="de464-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="de464-114">Все сообщения электронной почты перешли на Microsoft 365 и вы хотели, чтобы ваша электронная почта переключилась?</span><span class="sxs-lookup"><span data-stu-id="de464-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="de464-115">Не можете подтвердить состояние некоммерческой или школьной учетной записи?</span><span class="sxs-lookup"><span data-stu-id="de464-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="de464-116">Службы, не работающие с доменом?</span><span class="sxs-lookup"><span data-stu-id="de464-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="de464-117">Доступ к веб-сайту не работает?</span><span class="sxs-lookup"><span data-stu-id="de464-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="de464-118">Не удается проверить свой домен?</span><span class="sxs-lookup"><span data-stu-id="de464-118">Can't verify your domain?</span></span>
<span data-ttu-id="de464-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="de464-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="de464-120">Вот несколько причин, по которым может не удаваться проверить домен:</span><span class="sxs-lookup"><span data-stu-id="de464-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="de464-p103">**Проверочная запись неправильная.** Убедитесь, что вы скопировали и вставили точное значение в проверочную запись TXT на узле DNS. Часто пользователи забывают указать "MS =". Эта часть тоже нужна!</span><span class="sxs-lookup"><span data-stu-id="de464-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="de464-125">**Запись не была сохранена.**</span><span class="sxs-lookup"><span data-stu-id="de464-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="de464-126">На некоторых узлах DNS необходимо выполнить дополнительное действие для сохранения файла зоны (в котором хранится запись DNS), чтобы он обновился в Интернете.</span><span class="sxs-lookup"><span data-stu-id="de464-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="de464-127">Убедитесь, что вы сохранили изменения, чтобы Microsoft 365 могли видеть и проверять запись.</span><span class="sxs-lookup"><span data-stu-id="de464-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="de464-128">**Запись не обновилась в Интернете.**</span><span class="sxs-lookup"><span data-stu-id="de464-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="de464-129">Обычно новая запись становится доступна через несколько минут, но иногда ее обновление может занять до нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="de464-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="de464-130">Не работает Outlook?</span><span class="sxs-lookup"><span data-stu-id="de464-130">Outlook isn't working?</span></span>
<span data-ttu-id="de464-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="de464-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="de464-132">Если вы настроили свою запись MX и другие записи DNS для домена правильно, но почта не работает, мы поможем [устранить неполадки с Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="de464-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="de464-133">Все сообщения электронной почты перешли на Microsoft 365 и вы хотели, чтобы ваша электронная почта переключилась?</span><span class="sxs-lookup"><span data-stu-id="de464-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="de464-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="de464-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="de464-135">При добавлении домена в Microsoft 365 обычно запись MX вашего домена обновляется (вами или Microsoft 365), чтобы указать на Microsoft 365, и вся электронная почта, отправленная в этот домен, начнет приходить Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de464-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="de464-136">Убедитесь, что вы создали почтовые ящики в Microsoft 365 для всех, у кого есть электронная почта на вашем домене, прежде чем изменить запись MX.</span><span class="sxs-lookup"><span data-stu-id="de464-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="de464-137">Что делать, если вы не хотите переместить электронную почту для всех в вашем домене, чтобы Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="de464-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="de464-138">Вы можете предпринять шаги, чтобы Microsoft 365 [с несколькими адресами электронной почты вместо](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="de464-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](../setup/domains-faq.yml).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="de464-139">Не можете подтвердить состояние некоммерческой или школьной учетной записи?</span><span class="sxs-lookup"><span data-stu-id="de464-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="de464-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="de464-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="de464-141">Существует несколько сценариев, когда просто необходимо проверить домен организации и не настроить какие-либо службы.</span><span class="sxs-lookup"><span data-stu-id="de464-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="de464-142">Например, чтобы доказать, что Microsoft 365 организация имеет право на подписку на школу.</span><span class="sxs-lookup"><span data-stu-id="de464-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="de464-143">Ознакомьтесь с руководством по проверке домена Microsoft 365, чтобы доказать [владение,](../setup/domains-faq.yml) некоммерческое или образовательное состояние или активировать Yammer, чтобы убедиться, что вы выполнили все необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="de464-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](../setup/domains-faq.yml) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="de464-144">Это немного отличается для каждой ситуации.</span><span class="sxs-lookup"><span data-stu-id="de464-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="de464-145">Службы не работают с вашим доменом?</span><span class="sxs-lookup"><span data-stu-id="de464-145">Services not working with your domain?</span></span>
<span data-ttu-id="de464-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="de464-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="de464-147">Мы поможем вам выявить проблемы с настройкой DNS для домена.</span><span class="sxs-lookup"><span data-stu-id="de464-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="de464-148">Устранение неполадок доменов в Microsoft 365 покажет вам все записи, которые необходимо исправить, и точно, какие записи необходимо зафиксировать.</span><span class="sxs-lookup"><span data-stu-id="de464-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="de464-149">DNS настроена правильно, но почта не работает в Outlook на рабочем столе?</span><span class="sxs-lookup"><span data-stu-id="de464-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="de464-150">Ознакомьтесь [с различными](/exchange/mail-flow-best-practices/mail-flow-best-practices) сценариями потока почты, которые можно использовать в Microsoft 365, чтобы убедиться, что у вас все правильно настроено для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="de464-150">Check out the [different mail flow scenarios you can have with Microsoft 365](/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="de464-151">Дополнительную помощь по устранению неполадок с электронной почтой можно найти здесь: [Устранение неполадок в Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="de464-151">Or get more troubleshooting help with email here: [Fix Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="de464-152">Ваш веб-сайт недоступен?</span><span class="sxs-lookup"><span data-stu-id="de464-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="de464-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="de464-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="de464-154">Если вы устранили все неполадки DNS, но у вас по-прежнему возникают проблемы, попробуйте одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="de464-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="de464-155">Пользователи не могут войти на ваш веб-сайт в www.mydomain.com: [Диагностика неполадок веб-сайта](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="de464-155">People can't get to your website at www.mydomain.com: [Track down website issues](../setup/add-domain.md)</span></span>
    
- <span data-ttu-id="de464-156">Вы не можете обновить запись или запись CNAME, чтобы указать на веб-сайт: обновление пользовательских [записей DNS](../setup/add-domain.md) в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="de464-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../setup/add-domain.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="de464-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="de464-157">Related content</span></span>

[<span data-ttu-id="de464-158">Устранение неполадок: аудит данных о проверенном изменении домена</span><span class="sxs-lookup"><span data-stu-id="de464-158">Troubleshoot: Audit data on verified domain change</span></span>](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

