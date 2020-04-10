---
title: Поиск и устранение проблем после добавления домена или записей DNS в Office 365
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Сведения о том, как отслеживать все проблемы, возникающие при настройке настраиваемого домена, убедившись, что DNS-записи настроены правильно.
ms.openlocfilehash: 00330dea6b3401bce02779437dc047ce324dcece
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210408"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a><span data-ttu-id="da3fa-103">Поиск и устранение проблем после добавления домена или записей DNS в Office 365</span><span class="sxs-lookup"><span data-stu-id="da3fa-103">Find and fix issues after adding your domain or DNS records in Office 365</span></span>

 <span data-ttu-id="da3fa-104">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="da3fa-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="da3fa-p101">Настройка домена для работы с Office 365 может оказаться сложной задачей. В работе с системой DNS есть множество мелких нюансов. К тому же, настройка DNS для домена затрагивает важные аспекты бизнес-операций, например электронную почту.</span><span class="sxs-lookup"><span data-stu-id="da3fa-p101">Getting your domain set up to work with Office 365 can be challenging. The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="da3fa-107">Чтобы проверить наличие проблем с доменом, необходимо проверить его состояние.</span><span class="sxs-lookup"><span data-stu-id="da3fa-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="da3fa-108">Перейдите в раздел **Настройка** > **доменов** и просмотрите уведомления в столбце **состояние** .</span><span class="sxs-lookup"><span data-stu-id="da3fa-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="da3fa-109">Если отображается сообщение о неполадке, выберите пункт Дополнительные действия (три точки), а затем нажмите кнопку **проверить работоспособность**.</span><span class="sxs-lookup"><span data-stu-id="da3fa-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="da3fa-110">В открывшейся области будут описаны все проблемы, возникающие при работе с доменом.</span><span class="sxs-lookup"><span data-stu-id="da3fa-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="da3fa-111">Почему?</span><span class="sxs-lookup"><span data-stu-id="da3fa-111">What's going on?</span></span>

- [<span data-ttu-id="da3fa-112">Не удается проверить ваш домен?</span><span class="sxs-lookup"><span data-stu-id="da3fa-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="da3fa-113">Outlook не работает?</span><span class="sxs-lookup"><span data-stu-id="da3fa-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="da3fa-114">Сообщения электронной почты для всех пользователей были переключены на Office 365, и вы хотите, чтобы вы хотели переключить электронную почту?</span><span class="sxs-lookup"><span data-stu-id="da3fa-114">Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="da3fa-115">Не можете подтвердить состояние учетной записи без дохода или учебной учетной записи?</span><span class="sxs-lookup"><span data-stu-id="da3fa-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="da3fa-116">Службы не работают с вашим доменом?</span><span class="sxs-lookup"><span data-stu-id="da3fa-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="da3fa-117">Доступ к веб-сайту не работает?</span><span class="sxs-lookup"><span data-stu-id="da3fa-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="da3fa-118">Не удается проверить свой домен?</span><span class="sxs-lookup"><span data-stu-id="da3fa-118">Can't verify your domain?</span></span>
<span data-ttu-id="da3fa-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="da3fa-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="da3fa-120">Вот несколько причин, по которым может не удаваться проверить домен:</span><span class="sxs-lookup"><span data-stu-id="da3fa-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="da3fa-p103">**Проверочная запись неправильная.** Убедитесь, что вы скопировали и вставили точное значение в проверочную запись TXT на узле DNS. Часто пользователи забывают указать "MS =". Эта часть тоже нужна!</span><span class="sxs-lookup"><span data-stu-id="da3fa-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="da3fa-p104">**Запись не была сохранена.** На некоторых узлах DNS необходимо выполнить дополнительное действие для сохранения файла зоны (в котором хранится запись DNS), чтобы он обновился в Интернете. Убедитесь, что вы сохранили изменения, чтобы у Office 365 появилась возможность увидеть и проверить запись.</span><span class="sxs-lookup"><span data-stu-id="da3fa-p104">**The record hasn't been saved.** At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet. Make sure you've saved your changes so Office 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="da3fa-128">**Запись не обновилась в Интернете.**</span><span class="sxs-lookup"><span data-stu-id="da3fa-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="da3fa-129">Обычно новая запись становится доступна через несколько минут, но иногда ее обновление может занять до нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="da3fa-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="da3fa-130">Не работает Outlook?</span><span class="sxs-lookup"><span data-stu-id="da3fa-130">Outlook isn't working?</span></span>
<span data-ttu-id="da3fa-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="da3fa-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="da3fa-132">Если вы настроили свою запись MX и другие записи DNS для домена правильно, но почта не работает, мы поможем [устранить неполадки с Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span><span class="sxs-lookup"><span data-stu-id="da3fa-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span>
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="da3fa-133">Сообщения электронной почты для всех пользователей были переключены на Office 365, и вы хотите, чтобы вы хотели переключить электронную почту?</span><span class="sxs-lookup"><span data-stu-id="da3fa-133">Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="da3fa-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="da3fa-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="da3fa-135">Когда вы добавляете свой домен в Office 365, обычно запись MX вашего домена обновляется (или Office 365) до Office 365, а вся электронная почта, отправленная в этот домен, будет начинаться с Office 365.</span><span class="sxs-lookup"><span data-stu-id="da3fa-135">When you add your domain to Office 365, typically your domain's MX record is updated (by you or Office 365) to point to Office 365, and ALL email sent to that domain will start coming to Office 365.</span></span> <span data-ttu-id="da3fa-136">Убедитесь, что вы создали почтовые ящики в Office 365 для всех пользователей, имеющих электронную почту в вашем домене, прежде чем изменять запись MX.</span><span class="sxs-lookup"><span data-stu-id="da3fa-136">Make sure you've created mailboxes in Office 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="da3fa-137">Что делать, если вы не хотите перемещать электронную почту для всех пользователей вашего домена в Office 365?</span><span class="sxs-lookup"><span data-stu-id="da3fa-137">What if you don't want to move email for everyone on your domain to Office 365?</span></span> <span data-ttu-id="da3fa-138">Воспользуйтесь [инструкциями по пилотному развертыванию Office 365 с несколькими адресами электронной почты](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span><span class="sxs-lookup"><span data-stu-id="da3fa-138">You can take steps to [pilot Office 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="da3fa-139">Не можете подтвердить состояние учетной записи без дохода или учебной учетной записи?</span><span class="sxs-lookup"><span data-stu-id="da3fa-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="da3fa-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="da3fa-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="da3fa-141">Существует несколько сценариев, когда необходимо только проверить домен организации и не настраивать какие бы то ни было службы.</span><span class="sxs-lookup"><span data-stu-id="da3fa-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="da3fa-142">Например, чтобы доказать, что в Office 365 ваша организация соответствует подписке учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="da3fa-142">For example, to prove to Office 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="da3fa-143">Ознакомьтесь с рекомендациями, приведенными в статье [Проверка домена Office 365 для получения сведений о владении, некоммерческих или образовательных статусах, а также активации Yammer,](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) чтобы убедиться, что все необходимые действия выполнены.</span><span class="sxs-lookup"><span data-stu-id="da3fa-143">Check out the guidance in [Verify your Office 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="da3fa-144">Для каждой ситуации это немного другое.</span><span class="sxs-lookup"><span data-stu-id="da3fa-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="da3fa-145">Службы не работают с вашим доменом?</span><span class="sxs-lookup"><span data-stu-id="da3fa-145">Services not working with your domain?</span></span>
<span data-ttu-id="da3fa-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="da3fa-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="da3fa-147">Мы поможем вам выявить проблемы с настройкой DNS для домена.</span><span class="sxs-lookup"><span data-stu-id="da3fa-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="da3fa-148">Средство устранения неполадок с доменами в Office 365 отобразит все записи, которые нужно исправить, и точно укажет, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="da3fa-148">The domains troubleshooter in Office 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="da3fa-p111">DNS настроена правильно, но почта не работает в Outlook на рабочем столе? Ознакомьтесь с [различными схемами настройки почтового потока в Office 365](https://go.microsoft.com/fwlink/?LinkId=787530), чтобы выбрать оптимальный вариант для своей организации. Дополнительную помощь по устранению неполадок с электронной почтой можно найти здесь: [Устранение неполадок в Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span><span class="sxs-lookup"><span data-stu-id="da3fa-p111">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop? Check out the [different mail flow scenarios you can have with Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) to make sure you've got things set up correctly for your business. Or get more troubleshooting help with email here: [Fix Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="da3fa-152">Ваш веб-сайт недоступен?</span><span class="sxs-lookup"><span data-stu-id="da3fa-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="da3fa-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="da3fa-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="da3fa-154">Если вы устранили все неполадки DNS, но у вас по-прежнему возникают проблемы, попробуйте одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="da3fa-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="da3fa-155">Пользователи не могут войти на ваш веб-сайт в www.mydomain.com: [Диагностика неполадок веб-сайта](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span><span class="sxs-lookup"><span data-stu-id="da3fa-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span></span>
    
- <span data-ttu-id="da3fa-156">Вам не удается обновить запись A или CNAME, чтобы она указывала на веб-сайт: [Обновление пользовательских записей DNS в Office 365](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="da3fa-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Office 365](../dns/add-or-edit-custom-dns-records.md)</span></span>
    
