---
title: Добавление домена в Office 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Добавьте свой домен в Office 365 в центре администрирования Microsoft 365, добавив запись DNS на узел DNS. Мастер установки проводит вас через процесс.
ms.openlocfilehash: a77526efc526073e17b535612213202ad22d5657
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "43800027"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="f852c-104">Добавление домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="f852c-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="f852c-105">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="f852c-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="f852c-106">*Чтобы добавить, изменить или удалить домены, **необходимо** быть **глобальным администратором** [плана бизнеса или предприятия](https://products.office.com/business/office). Эти изменения затрагивают весь клиент, *Администраторы* или *обычные пользователи* не смогут вносить эти изменения.*</span><span class="sxs-lookup"><span data-stu-id="f852c-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="f852c-107">Выполните указанные ниже действия, чтобы добавить, настроить или продолжить настройку домена.</span><span class="sxs-lookup"><span data-stu-id="f852c-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f852c-108">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="f852c-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="f852c-109">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="f852c-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f852c-110">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="f852c-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="f852c-111">Перейдите на страницу "**домены** **установки** > ".</span><span class="sxs-lookup"><span data-stu-id="f852c-111">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="f852c-112">Выберите **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="f852c-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="f852c-113">Введите имя домена, который вы хотите добавить, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f852c-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="f852c-114">Выберите способ проверки того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="f852c-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="f852c-115">Если ваш домен зарегистрирован на&amp;GoDaddy или 1 1, нажмите кнопку **войти** > **Далее** , чтобы Майкрософт[настроила свои записи автоматически](../get-help-with-domains/domain-connect.md).</span><span class="sxs-lookup"><span data-stu-id="f852c-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft[will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="f852c-116">Вы можете отправить контакту, зарегистрированному для домена, сообщение электронной почты с кодом проверки.</span><span class="sxs-lookup"><span data-stu-id="f852c-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="f852c-117">Если вы не узнаете или не можете получить доступ к записи электронной почты, вы можете использовать третий вариант.</span><span class="sxs-lookup"><span data-stu-id="f852c-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="f852c-118">Вы можете подтвердить владение доменом с помощью записи типа TXT.</span><span class="sxs-lookup"><span data-stu-id="f852c-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="f852c-119">Установите этот флажок и нажмите кнопку **Далее** , чтобы просмотреть инструкции по добавлению этой записи DNS на веб-сайт регистратора.</span><span class="sxs-lookup"><span data-stu-id="f852c-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="f852c-120">Проверка после добавления записи может занять до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="f852c-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="f852c-121">Выберите способ внесения изменений DNS, необходимых для использования домена в Office.</span><span class="sxs-lookup"><span data-stu-id="f852c-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="f852c-122">Выберите **добавить записи DNS для меня,** если вы хотите, чтобы Office автоматически настроил DNS.</span><span class="sxs-lookup"><span data-stu-id="f852c-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="f852c-123">Нажмите **я буду добавлять записи DNS самостоятельно** , если вы хотите присоединить к вашему домену только определенные службы Office 365, или если вы хотите пропустить это действие и сделать это позже.</span><span class="sxs-lookup"><span data-stu-id="f852c-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="f852c-124">**Этот пункт предназначен для опытных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="f852c-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="f852c-125">Если вы решили *добавить записи DNS самостоятельно* , нажмите кнопку **Далее** , чтобы увидеть страницу со всеми записями, которые необходимо добавить на веб-сайт регистраторов, чтобы настроить свой домен.</span><span class="sxs-lookup"><span data-stu-id="f852c-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="f852c-126">Если порталу не удается распознать регистратор, [воспользуйтесь общими инструкциями](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="f852c-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="f852c-127">Просмотрите наш список [инструкций для конкретных хостов](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580). Найдите в нем свой хост и следуйте указаниям, чтобы добавить все нужные записи.</span><span class="sxs-lookup"><span data-stu-id="f852c-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="f852c-128">Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    </span><span class="sxs-lookup"><span data-stu-id="f852c-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="f852c-129">Если вы хотите подождать позже, прокрутите страницу вниз и выберите **пропустить этот шаг**.</span><span class="sxs-lookup"><span data-stu-id="f852c-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="f852c-130">Нажмите кнопку Готово, чтобы **завершить работу** .</span><span class="sxs-lookup"><span data-stu-id="f852c-130">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="f852c-131">Добавление и изменение настраиваемых записей DNS</span><span class="sxs-lookup"><span data-stu-id="f852c-131">Add or edit custom DNS records</span></span>

<span data-ttu-id="f852c-132">Выполните указанные ниже действия, чтобы добавить настраиваемую запись для веб-сайта или сторонней службы.</span><span class="sxs-lookup"><span data-stu-id="f852c-132">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="f852c-133">Войдите в центр администрирования Майкрософт по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="f852c-133">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="f852c-134">Перейдите на страницу "**домены** **параметров**  > ".</span><span class="sxs-lookup"><span data-stu-id="f852c-134">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="f852c-135">На странице **Домены** выберите домен.</span><span class="sxs-lookup"><span data-stu-id="f852c-135">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="f852c-136">В разделе **параметры DNS**выберите **Настраиваемые записи**; затем выберите **создать настраиваемую запись**.</span><span class="sxs-lookup"><span data-stu-id="f852c-136">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="f852c-137">Выберите тип записи DNS, которую вы хотите добавить, и введите сведения для новой записи.</span><span class="sxs-lookup"><span data-stu-id="f852c-137">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="f852c-138">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f852c-138">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="f852c-139">Регистраторы с подключением к домену</span><span class="sxs-lookup"><span data-stu-id="f852c-139">Registrars with Domain Connect</span></span>

<span data-ttu-id="f852c-140">Регистраторы с поддержкой [подключения к домену](https://www.domainconnect.org/) позволяют добавить свой домен в Microsoft 365 в процессе, сокоторый в течение трех этапов.</span><span class="sxs-lookup"><span data-stu-id="f852c-140">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="f852c-141">В мастере мы просто подтверждаю, что вы владеете доменом и автоматически настроили записи вашего домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Майкрософт 365, например команды, работающие с доменом.</span><span class="sxs-lookup"><span data-stu-id="f852c-141">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f852c-142">Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.</span><span class="sxs-lookup"><span data-stu-id="f852c-142">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="f852c-143">Служба регистраторов подключений к доменам интеграция с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f852c-143">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="f852c-144">1&amp;1 ионос</span><span class="sxs-lookup"><span data-stu-id="f852c-144">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="f852c-145">123Reg</span><span class="sxs-lookup"><span data-stu-id="f852c-145">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="f852c-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="f852c-146">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="f852c-147">WordPress</span><span class="sxs-lookup"><span data-stu-id="f852c-147">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="f852c-148">плеск</span><span class="sxs-lookup"><span data-stu-id="f852c-148">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="f852c-149">медиатемпле</span><span class="sxs-lookup"><span data-stu-id="f852c-149">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="f852c-150">Секуресервер или Вилдвестдомаинс (GoDaddy торговые посредники, использующие службу хостинга на Секуресервер DNS)</span><span class="sxs-lookup"><span data-stu-id="f852c-150">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="f852c-151">Домены Маддог</span><span class="sxs-lookup"><span data-stu-id="f852c-151">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="f852c-152">чеапнамес</span><span class="sxs-lookup"><span data-stu-id="f852c-152">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="f852c-153">Что происходит с электронной почтой и веб-сайтом?</span><span class="sxs-lookup"><span data-stu-id="f852c-153">What happens to my email and website?</span></span>

<span data-ttu-id="f852c-154">После завершения установки запись MX для вашего домена будет обновлена, чтобы она ссылалась на Microsoft 365, а вся электронная почта для вашего домена будет начинаться с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f852c-154">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="f852c-155">Не забудьте добавить пользователей и создать почтовые ящики в Office 365 для всех, кто получает электронную почту в вашем домене!</span><span class="sxs-lookup"><span data-stu-id="f852c-155">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="f852c-156">Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде.</span><span class="sxs-lookup"><span data-stu-id="f852c-156">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="f852c-157">Действия по настройке подключения к домену не повлияют на ваш веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="f852c-157">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f852c-158">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f852c-158">Related articles</span></span>

[<span data-ttu-id="f852c-159">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="f852c-159">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="f852c-160">Что такое домен?</span><span class="sxs-lookup"><span data-stu-id="f852c-160">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="f852c-161">Приобретение доменного имени в Office 365</span><span class="sxs-lookup"><span data-stu-id="f852c-161">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="f852c-162">Настройка домена (инструкции для конкретных узлов)</span><span class="sxs-lookup"><span data-stu-id="f852c-162">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="f852c-163">Получение справки о доменах</span><span class="sxs-lookup"><span data-stu-id="f852c-163">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
