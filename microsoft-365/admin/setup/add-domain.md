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
ms.openlocfilehash: 09a66b9ac4f97a076d71dd7f259678181378ae48
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295026"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="21465-104">Добавление домена в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="21465-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="21465-105">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="21465-105">The admin center is changing.</span></span> <span data-ttu-id="21465-106">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="21465-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="21465-107">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="21465-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="21465-108">*Чтобы добавить, изменить или удалить домены, **необходимо** быть **глобальным администратором** [плана бизнеса или предприятия](https://products.office.com/business/office). Эти изменения затрагивают весь клиент, *Администраторы* или *обычные пользователи* не смогут вносить эти изменения.*</span><span class="sxs-lookup"><span data-stu-id="21465-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="21465-109">Выполните указанные ниже действия, чтобы добавить, настроить или продолжить настройку домена.</span><span class="sxs-lookup"><span data-stu-id="21465-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="21465-110">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="21465-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="21465-111">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="21465-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="21465-112">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="21465-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="21465-113">Перейдите на страницу **Settings**"  >  **домены** параметров".</span><span class="sxs-lookup"><span data-stu-id="21465-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="21465-114">Выберите **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="21465-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="21465-115">Введите имя домена, который вы хотите добавить, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="21465-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="21465-116">Выберите способ проверки того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="21465-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="21465-117">Если ваш регистратор домена использует [Подключение к домену](#domain-connect-registrars-integrating-with-microsoft-365), корпорация Майкрософт настроит [свои записи автоматически](../get-help-with-domains/domain-connect.md) , выполнив вход в регистратор и подтверждая подключение к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21465-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="21465-118">Вы вернетесь в центр администрирования, и Майкрософт затем автоматически проверит ваш домен.</span><span class="sxs-lookup"><span data-stu-id="21465-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="21465-119">Вы можете подтвердить владение доменом с помощью записи типа TXT.</span><span class="sxs-lookup"><span data-stu-id="21465-119">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="21465-120">Установите этот флажок и нажмите кнопку **Далее** , чтобы просмотреть инструкции по добавлению этой записи DNS на веб-сайт регистратора.</span><span class="sxs-lookup"><span data-stu-id="21465-120">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="21465-121">Проверка после добавления записи может занять до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="21465-121">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="21465-122">Вы можете добавить текстовый файл на веб-сайт вашего домена.</span><span class="sxs-lookup"><span data-stu-id="21465-122">You can add a text file to your domain's website.</span></span> <span data-ttu-id="21465-123">Выберите и скачайте txt-файл из мастера установки, а затем отправьте его в папку верхнего уровня своего веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="21465-123">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="21465-124">Путь к файлу должен выглядеть примерно следующим образом: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="21465-124">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="21465-125">Мы подтвердите, что вы являетесь владельцем домена, найдя файл на веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="21465-125">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="21465-126">Выберите способ внесения изменений DNS, необходимых корпорации Майкрософт для использования вашего домена.</span><span class="sxs-lookup"><span data-stu-id="21465-126">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="21465-127">Выберите **добавить записи DNS для меня** , если регистратор поддерживает [Подключение к домену](#domain-connect-registrars-integrating-with-microsoft-365), и Майкрософт настроит [свои записи автоматически](../get-help-with-domains/domain-connect.md) , выполнив вход в регистратор и подтверждаю подключение к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21465-127">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="21465-128">Нажмите **я буду добавлять записи DNS самостоятельно** , если вы хотите присоединить к домену только определенные службы Microsoft 365, или если вы хотите пропустить эту операцию, и сделать это позже.</span><span class="sxs-lookup"><span data-stu-id="21465-128">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="21465-129">**Этот пункт предназначен для опытных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="21465-129">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="21465-130">Если вы решили *добавить записи DNS самостоятельно*  , нажмите кнопку **Далее** , чтобы увидеть страницу со всеми записями, которые необходимо добавить на веб-сайт регистраторов, чтобы настроить свой домен.</span><span class="sxs-lookup"><span data-stu-id="21465-130">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="21465-131">Если порталу не удается распознать регистратор, [воспользуйтесь общими инструкциями](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="21465-131">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="21465-132">Просмотрите наш список [инструкций для конкретных хостов](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions). Найдите в нем свой хост и следуйте указаниям, чтобы добавить все нужные записи.</span><span class="sxs-lookup"><span data-stu-id="21465-132">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="21465-133">Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    </span><span class="sxs-lookup"><span data-stu-id="21465-133">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="21465-134">Если вы хотите подождать позже, отмените выбор всех служб и нажмите **продолжить**, или на предыдущем шаге подключения к домену выберите **Дополнительные параметры** и нажмите кнопку **пропустить**.</span><span class="sxs-lookup"><span data-stu-id="21465-134">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="21465-135">Нажмите кнопку Готово, чтобы **завершить работу** .</span><span class="sxs-lookup"><span data-stu-id="21465-135">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="21465-136">Добавление и изменение настраиваемых записей DNS</span><span class="sxs-lookup"><span data-stu-id="21465-136">Add or edit custom DNS records</span></span>

<span data-ttu-id="21465-137">Выполните указанные ниже действия, чтобы добавить настраиваемую запись для веб-сайта или сторонней службы.</span><span class="sxs-lookup"><span data-stu-id="21465-137">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="21465-138">Войдите в центр администрирования Майкрософт по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="21465-138">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="21465-139">Перейдите на страницу **Settings**"   >  **домены** параметров".</span><span class="sxs-lookup"><span data-stu-id="21465-139">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="21465-140">На странице **Домены** выберите домен.</span><span class="sxs-lookup"><span data-stu-id="21465-140">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="21465-141">В разделе **параметры DNS**выберите **Настраиваемые записи**; затем выберите **создать настраиваемую запись**.</span><span class="sxs-lookup"><span data-stu-id="21465-141">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="21465-142">Выберите тип записи DNS, которую вы хотите добавить, и введите сведения для новой записи.</span><span class="sxs-lookup"><span data-stu-id="21465-142">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="21465-143">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="21465-143">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="21465-144">Регистраторы с подключением к домену</span><span class="sxs-lookup"><span data-stu-id="21465-144">Registrars with Domain Connect</span></span>

<span data-ttu-id="21465-145">Регистраторы с поддержкой [подключения к домену](https://www.domainconnect.org/) позволяют добавить свой домен в Microsoft 365 в процессе, сокоторый в течение трех этапов.</span><span class="sxs-lookup"><span data-stu-id="21465-145">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="21465-146">В мастере мы просто подтверждаю, что вы владеете доменом и автоматически настроили записи вашего домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Майкрософт 365, например команды, работающие с доменом.</span><span class="sxs-lookup"><span data-stu-id="21465-146">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="21465-147">Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.</span><span class="sxs-lookup"><span data-stu-id="21465-147">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="21465-148">Служба регистраторов подключений к доменам интеграция с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="21465-148">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="21465-149">1 &amp; 1 ионос</span><span class="sxs-lookup"><span data-stu-id="21465-149">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="21465-150">еуроднс</span><span class="sxs-lookup"><span data-stu-id="21465-150">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="21465-151">CloudFlare</span><span class="sxs-lookup"><span data-stu-id="21465-151">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="21465-152">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="21465-152">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="21465-153">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="21465-153">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="21465-154">плеск</span><span class="sxs-lookup"><span data-stu-id="21465-154">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="21465-155">медиатемпле</span><span class="sxs-lookup"><span data-stu-id="21465-155">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="21465-156">Секуресервер или Вилдвестдомаинс (GoDaddy торговые посредники, использующие службу хостинга на Секуресервер DNS)</span><span class="sxs-lookup"><span data-stu-id="21465-156">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="21465-157">Примеры:</span><span class="sxs-lookup"><span data-stu-id="21465-157">Examples:</span></span>
        - [<span data-ttu-id="21465-158">домаинсприцедригхт</span><span class="sxs-lookup"><span data-stu-id="21465-158">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="21465-159">домаинригхтнов</span><span class="sxs-lookup"><span data-stu-id="21465-159">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="21465-160">Что происходит с электронной почтой и веб-сайтом?</span><span class="sxs-lookup"><span data-stu-id="21465-160">What happens to my email and website?</span></span>

<span data-ttu-id="21465-161">После завершения установки запись MX для вашего домена будет обновлена, чтобы она ссылалась на Microsoft 365, а вся электронная почта для вашего домена будет начинаться с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21465-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="21465-162">Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту в вашем домене.</span><span class="sxs-lookup"><span data-stu-id="21465-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="21465-163">Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде.</span><span class="sxs-lookup"><span data-stu-id="21465-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="21465-164">Действия по настройке подключения к домену не повлияют на ваш веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="21465-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="21465-165">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="21465-165">Related articles</span></span>

[<span data-ttu-id="21465-166">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="21465-166">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="21465-167">Что такое домен?</span><span class="sxs-lookup"><span data-stu-id="21465-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="21465-168">Приобретение доменного имени в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="21465-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="21465-169">Настройка домена (инструкции для конкретных узлов)</span><span class="sxs-lookup"><span data-stu-id="21465-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
