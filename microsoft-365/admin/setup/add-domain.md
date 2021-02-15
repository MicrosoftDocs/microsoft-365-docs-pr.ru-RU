---
title: Добавление домена в Microsoft 365
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
description: Добавьте домен в Microsoft 365 в Центре администрирования Microsoft 365, добавив запись DNS на своем сайте DNS. Мастер установки поумека процесса.
ms.openlocfilehash: 5a3c86fb2b2f93e9da844c15a55555c5d0d7b5c1
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114265"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="0b80d-104">Добавление домена в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b80d-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0b80d-105">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="0b80d-105">The admin center is changing.</span></span> <span data-ttu-id="0b80d-106">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="0b80d-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

 <span data-ttu-id="0b80d-107">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="0b80d-107">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="0b80d-108">*Чтобы добавить, изменить или удалить домены, **необходимо** быть глобальным администратором плана предприятия или [предприятия.](https://products.office.com/business/office)  Эти изменения влияют на весь *клиент,* настроенные администраторы или обычные пользователи не смогут вносить эти изменения.*</span><span class="sxs-lookup"><span data-stu-id="0b80d-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="0b80d-109">Выполните следующие действия, чтобы добавить, настроить или продолжить настройку домена.</span><span class="sxs-lookup"><span data-stu-id="0b80d-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0b80d-110">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="0b80d-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="0b80d-111">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="0b80d-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0b80d-112">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="0b80d-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="0b80d-113">Перейдите на **страницу "Домены**  >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="0b80d-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="0b80d-114">Выберите **"Добавить домен".**</span><span class="sxs-lookup"><span data-stu-id="0b80d-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="0b80d-115">Введите имя домена, который нужно добавить, а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="0b80d-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="0b80d-116">Выберите, как вы хотите подтвердить владение доменом.</span><span class="sxs-lookup"><span data-stu-id="0b80d-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="0b80d-117">Если ваш регистратор доменных [](../get-help-with-domains/domain-connect.md) имен использует [Domain Connect,](#domain-connect-registrars-integrating-with-microsoft-365)Корпорация Майкрософт автоматически настроит ваши записи, построив вход в регистратор и подтвердив подключение к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0b80d-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="0b80d-118">Вы будете возвращены в Центр администрирования, и корпорация Майкрософт автоматически проверит ваш домен.</span><span class="sxs-lookup"><span data-stu-id="0b80d-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="0b80d-119">Вы можете подтвердить владение доменом с помощью записи типа TXT.</span><span class="sxs-lookup"><span data-stu-id="0b80d-119">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="0b80d-120">Выберите этот  список и выберите "Далее", чтобы увидеть инструкции по добавлению этой записи DNS на веб-сайт регистратора.</span><span class="sxs-lookup"><span data-stu-id="0b80d-120">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="0b80d-121">Проверка записи может занять до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="0b80d-121">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="0b80d-122">Вы можете добавить текстовый файл на веб-сайт домена.</span><span class="sxs-lookup"><span data-stu-id="0b80d-122">You can add a text file to your domain's website.</span></span> <span data-ttu-id="0b80d-123">Выберите и скачайте TXT-файл из мастера установки, а затем загрузите файл в папку верхнего уровня вашего веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="0b80d-123">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="0b80d-124">Путь к файлу должен выглядеть примерно так: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="0b80d-124">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="0b80d-125">Мы подтвердим, что вы владеете доменом, найдя файл на вашем веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="0b80d-125">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="0b80d-126">Выберите, как вы хотите внести изменения в DNS, необходимые для использования домена корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0b80d-126">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="0b80d-127">Choose **Add the DNS records for me** if your registrar supports Domain [Connect,](#domain-connect-registrars-integrating-with-microsoft-365)and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0b80d-127">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="0b80d-128">Выберите я сам добавлю записи **DNS,** если вы хотите присоединить только определенные службы Microsoft 365 к вашему домену или пропустить это сейчас и сделать это позже.</span><span class="sxs-lookup"><span data-stu-id="0b80d-128">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="0b80d-129">**Этот пункт предназначен для опытных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="0b80d-129">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="0b80d-130">Если вы решили самостоятельно добавить записи  *DNS,* выберите "Далее", и вы увидите страницу со всеми записями, которые необходимо добавить на веб-сайт регистраторов для регистрации домена.</span><span class="sxs-lookup"><span data-stu-id="0b80d-130">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="0b80d-131">Если порталу не удается распознать регистратор, [воспользуйтесь общими инструкциями](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0b80d-131">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="0b80d-132">Просмотрите наш список [инструкций для конкретных хостов](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions). Найдите в нем свой хост и следуйте указаниям, чтобы добавить все нужные записи.</span><span class="sxs-lookup"><span data-stu-id="0b80d-132">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="0b80d-133">Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    </span><span class="sxs-lookup"><span data-stu-id="0b80d-133">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="0b80d-134">Если вы хотите подождать позже, либо отойдите от всех служб и нажмите  кнопку **"Продолжить",** либо на предыдущем шаге подключения к домену выберите "Дополнительные параметры" и выберите "Пропустить **сейчас".**</span><span class="sxs-lookup"><span data-stu-id="0b80d-134">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="0b80d-135">Select **Finish** — you're done!</span><span class="sxs-lookup"><span data-stu-id="0b80d-135">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="0b80d-136">Добавление и изменение настраиваемых записей DNS</span><span class="sxs-lookup"><span data-stu-id="0b80d-136">Add or edit custom DNS records</span></span>

<span data-ttu-id="0b80d-137">Выполните следующие действия, чтобы добавить пользовательскую запись для веб-сайта или стороной службы.</span><span class="sxs-lookup"><span data-stu-id="0b80d-137">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="0b80d-138">Во sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="0b80d-138">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0b80d-139">Перейдите на **страницу "Домены**   >  **параметров".**</span><span class="sxs-lookup"><span data-stu-id="0b80d-139">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="0b80d-140">На странице **Домены** выберите домен.</span><span class="sxs-lookup"><span data-stu-id="0b80d-140">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="0b80d-141">В **параметрах DNS выберите** **настраиваемые записи;** затем выберите **"Новая настраиваемая запись".**</span><span class="sxs-lookup"><span data-stu-id="0b80d-141">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="0b80d-142">Выберите тип записи DNS, которую необходимо добавить, и введите сведения для новой записи.</span><span class="sxs-lookup"><span data-stu-id="0b80d-142">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="0b80d-143">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0b80d-143">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="0b80d-144">Регистраторы с подключением к домену</span><span class="sxs-lookup"><span data-stu-id="0b80d-144">Registrars with Domain Connect</span></span>

<span data-ttu-id="0b80d-145">[Регистраторы](https://www.domainconnect.org/) с включенным подключением к домену позволяют добавлять домен в Microsoft 365 в течение трех этапов, который занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="0b80d-145">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="0b80d-146">В мастере мы просто подтвердим, что вы владеете доменом, а затем автоматически настроим записи домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Microsoft 365, например Teams, работают с вашим доменом.</span><span class="sxs-lookup"><span data-stu-id="0b80d-146">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b80d-147">Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.</span><span class="sxs-lookup"><span data-stu-id="0b80d-147">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="0b80d-148">Интеграция регистраторов Domain Connect с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b80d-148">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="0b80d-149">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="0b80d-149">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="0b80d-150">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="0b80d-150">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="0b80d-151">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="0b80d-151">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="0b80d-152">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="0b80d-152">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="0b80d-153">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="0b80d-153">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="0b80d-154">Plesk</span><span class="sxs-lookup"><span data-stu-id="0b80d-154">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="0b80d-155">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="0b80d-155">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="0b80d-156">SecureServer или WildWestDomains (resellers GoDaddy using SecureServer DNS hosting)</span><span class="sxs-lookup"><span data-stu-id="0b80d-156">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="0b80d-157">Примеры:</span><span class="sxs-lookup"><span data-stu-id="0b80d-157">Examples:</span></span>
        - [<span data-ttu-id="0b80d-158">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="0b80d-158">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="0b80d-159">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="0b80d-159">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="0b80d-160">Что происходит с электронной почтой и веб-сайтом?</span><span class="sxs-lookup"><span data-stu-id="0b80d-160">What happens to my email and website?</span></span>

<span data-ttu-id="0b80d-161">После завершения настройки запись MX для вашего домена будет обновлена так, чтобы она указыировала на Microsoft 365, и вся электронная почта для вашего домена начнет приходить в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0b80d-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="0b80d-162">Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту в вашем домене!</span><span class="sxs-lookup"><span data-stu-id="0b80d-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="0b80d-163">Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде.</span><span class="sxs-lookup"><span data-stu-id="0b80d-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="0b80d-164">Действия по настройке Domain Connect не влияют на ваш веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="0b80d-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0b80d-165">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0b80d-165">Related articles</span></span>

[<span data-ttu-id="0b80d-166">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="0b80d-166">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="0b80d-167">Что такое домен?</span><span class="sxs-lookup"><span data-stu-id="0b80d-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="0b80d-168">Приобретение доменного имени в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b80d-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="0b80d-169">Настройка домена (инструкции для конкретных узлов)</span><span class="sxs-lookup"><span data-stu-id="0b80d-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
