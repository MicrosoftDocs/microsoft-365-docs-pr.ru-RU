---
title: Добавление домена в Microsoft 365
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Добавьте свой домен в Microsoft 365 в центре администрирования Microsoft 365, добавив запись DNS на узел DNS. Мастер установки проводит вас через процесс.
ms.openlocfilehash: 3da99644f339eac2db6f1904e4eb50a7f584bc80
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315721"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="01937-104">Добавление домена в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01937-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="01937-105">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="01937-105">The admin center is changing.</span></span> <span data-ttu-id="01937-106">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="01937-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="01937-107">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="01937-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="01937-108">*Чтобы добавить, изменить или удалить домены, **необходимо** быть **глобальным администратором** [плана бизнеса или предприятия](https://products.office.com/business/office). Эти изменения затрагивают весь клиент, *Администраторы* или *обычные пользователи* не смогут вносить эти изменения.*</span><span class="sxs-lookup"><span data-stu-id="01937-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="01937-109">Выполните указанные ниже действия, чтобы добавить, настроить или продолжить настройку домена.</span><span class="sxs-lookup"><span data-stu-id="01937-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="01937-110">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="01937-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="01937-111">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="01937-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="01937-112">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="01937-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="01937-113">Перейдите на страницу **Settings**"  >  **домены** параметров".</span><span class="sxs-lookup"><span data-stu-id="01937-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="01937-114">Выберите **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="01937-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="01937-115">Введите имя домена, который вы хотите добавить, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="01937-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="01937-116">Выберите способ проверки того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="01937-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="01937-117">Если регистратор домена использует [Подключение к домену](#domain-connect-registrars-integrating-with-microsoft-365), нажмите кнопку **Вход в систему**, а затем Майкрософт настроит  >  **Next** [свои записи автоматически](../get-help-with-domains/domain-connect.md).</span><span class="sxs-lookup"><span data-stu-id="01937-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), select **Sign in** > **Next** and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="01937-118">Вы можете отправить контакту, зарегистрированному для домена, сообщение электронной почты с кодом проверки.</span><span class="sxs-lookup"><span data-stu-id="01937-118">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="01937-119">Если вы не узнаете или не можете получить доступ к записи электронной почты, вы можете использовать третий вариант.</span><span class="sxs-lookup"><span data-stu-id="01937-119">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="01937-120">Вы можете подтвердить владение доменом с помощью записи типа TXT.</span><span class="sxs-lookup"><span data-stu-id="01937-120">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="01937-121">Установите этот флажок и нажмите кнопку **Далее** , чтобы просмотреть инструкции по добавлению этой записи DNS на веб-сайт регистратора.</span><span class="sxs-lookup"><span data-stu-id="01937-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="01937-122">Проверка после добавления записи может занять до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="01937-122">This can take up to 30 minutes to verify after you've added the record.</span></span> 

    4. <span data-ttu-id="01937-123">Вы можете добавить текстовый файл на веб-сайт вашего домена.</span><span class="sxs-lookup"><span data-stu-id="01937-123">You can add a text file to your domain's website.</span></span> <span data-ttu-id="01937-124">Выберите и скачайте txt-файл из мастера установки, а затем отправьте его в папку верхнего уровня своего веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="01937-124">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="01937-125">Путь к файлу должен выглядеть примерно следующим образом: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="01937-125">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="01937-126">Мы подтвердите, что вы являетесь владельцем домена, найдя файл на веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="01937-126">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="01937-127">Выберите способ внесения изменений DNS, необходимых для использования домена в Office.</span><span class="sxs-lookup"><span data-stu-id="01937-127">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="01937-128">Выберите **добавить записи DNS для меня,** если вы хотите, чтобы Office автоматически настроил DNS.</span><span class="sxs-lookup"><span data-stu-id="01937-128">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="01937-129">Нажмите **я буду добавлять записи DNS самостоятельно** , если вы хотите присоединить к домену только определенные службы Microsoft 365, или если вы хотите пропустить эту операцию, и сделать это позже.</span><span class="sxs-lookup"><span data-stu-id="01937-129">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="01937-130">**Этот пункт предназначен для опытных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="01937-130">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="01937-131">Если вы решили  *добавить записи DNS самостоятельно*  , нажмите кнопку **Далее** , чтобы увидеть страницу со всеми записями, которые необходимо добавить на веб-сайт регистраторов, чтобы настроить свой домен.</span><span class="sxs-lookup"><span data-stu-id="01937-131">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="01937-132">Если порталу не удается распознать регистратор, [воспользуйтесь общими инструкциями](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="01937-132">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="01937-133">Просмотрите наш список [инструкций для конкретных хостов](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions). Найдите в нем свой хост и следуйте указаниям, чтобы добавить все нужные записи.</span><span class="sxs-lookup"><span data-stu-id="01937-133">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="01937-134">Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    </span><span class="sxs-lookup"><span data-stu-id="01937-134">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="01937-135">Если вы хотите подождать позже, прокрутите страницу вниз и выберите **пропустить этот шаг**.</span><span class="sxs-lookup"><span data-stu-id="01937-135">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="01937-136">Нажмите кнопку Готово, чтобы **завершить работу** .</span><span class="sxs-lookup"><span data-stu-id="01937-136">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="01937-137">Добавление и изменение настраиваемых записей DNS</span><span class="sxs-lookup"><span data-stu-id="01937-137">Add or edit custom DNS records</span></span>

<span data-ttu-id="01937-138">Выполните указанные ниже действия, чтобы добавить настраиваемую запись для веб-сайта или сторонней службы.</span><span class="sxs-lookup"><span data-stu-id="01937-138">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="01937-139">Войдите в центр администрирования Майкрософт по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="01937-139">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="01937-140">Перейдите на страницу **Settings**"   >  **домены** параметров".</span><span class="sxs-lookup"><span data-stu-id="01937-140">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="01937-141">На странице **Домены** выберите домен.</span><span class="sxs-lookup"><span data-stu-id="01937-141">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="01937-142">В разделе **параметры DNS**выберите **Настраиваемые записи**; затем выберите **создать настраиваемую запись**.</span><span class="sxs-lookup"><span data-stu-id="01937-142">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="01937-143">Выберите тип записи DNS, которую вы хотите добавить, и введите сведения для новой записи.</span><span class="sxs-lookup"><span data-stu-id="01937-143">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="01937-144">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="01937-144">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="01937-145">Регистраторы с подключением к домену</span><span class="sxs-lookup"><span data-stu-id="01937-145">Registrars with Domain Connect</span></span>

<span data-ttu-id="01937-146">Регистраторы с поддержкой [подключения к домену](https://www.domainconnect.org/) позволяют добавить свой домен в Microsoft 365 в процессе, сокоторый в течение трех этапов.</span><span class="sxs-lookup"><span data-stu-id="01937-146">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="01937-147">В мастере мы просто подтверждаю, что вы владеете доменом и автоматически настроили записи вашего домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Майкрософт 365, например команды, работающие с доменом.</span><span class="sxs-lookup"><span data-stu-id="01937-147">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01937-148">Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.</span><span class="sxs-lookup"><span data-stu-id="01937-148">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="01937-149">Служба регистраторов подключений к доменам интеграция с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01937-149">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="01937-150">1 &amp; 1 ионос</span><span class="sxs-lookup"><span data-stu-id="01937-150">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="01937-151">123Reg</span><span class="sxs-lookup"><span data-stu-id="01937-151">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="01937-152">CloudFlare</span><span class="sxs-lookup"><span data-stu-id="01937-152">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="01937-153">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="01937-153">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="01937-154">WordPress</span><span class="sxs-lookup"><span data-stu-id="01937-154">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="01937-155">плеск</span><span class="sxs-lookup"><span data-stu-id="01937-155">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="01937-156">медиатемпле</span><span class="sxs-lookup"><span data-stu-id="01937-156">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="01937-157">Секуресервер или Вилдвестдомаинс (GoDaddy торговые посредники, использующие службу хостинга на Секуресервер DNS)</span><span class="sxs-lookup"><span data-stu-id="01937-157">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="01937-158">Домены Маддог</span><span class="sxs-lookup"><span data-stu-id="01937-158">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="01937-159">чеапнамес</span><span class="sxs-lookup"><span data-stu-id="01937-159">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="01937-160">Что происходит с электронной почтой и веб-сайтом?</span><span class="sxs-lookup"><span data-stu-id="01937-160">What happens to my email and website?</span></span>

<span data-ttu-id="01937-161">После завершения установки запись MX для вашего домена будет обновлена, чтобы она ссылалась на Microsoft 365, а вся электронная почта для вашего домена будет начинаться с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="01937-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="01937-162">Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту в вашем домене.</span><span class="sxs-lookup"><span data-stu-id="01937-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="01937-163">Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде.</span><span class="sxs-lookup"><span data-stu-id="01937-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="01937-164">Действия по настройке подключения к домену не повлияют на ваш веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="01937-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="01937-165">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="01937-165">Related articles</span></span>

[<span data-ttu-id="01937-166">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="01937-166">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="01937-167">Что такое домен?</span><span class="sxs-lookup"><span data-stu-id="01937-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="01937-168">Приобретение доменного имени в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01937-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="01937-169">Настройка домена (инструкции для конкретных узлов)</span><span class="sxs-lookup"><span data-stu-id="01937-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
