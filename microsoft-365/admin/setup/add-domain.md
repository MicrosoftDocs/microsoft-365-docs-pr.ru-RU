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
description: Добавьте домен в Microsoft 365 в центре администрирования Microsoft 365, добавив запись DNS на своем DNS-сайте. Мастер установки проходит через этот процесс.
ms.openlocfilehash: 747de5f61dc9fce53f82f52b65f701572a56f8d4
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470885"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="0a356-104">Добавление домена в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a356-104">Add a domain to Microsoft 365</span></span>

 <span data-ttu-id="0a356-105">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="0a356-105">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="0a356-106">*Чтобы добавить, изменить или  удалить домены, необходимо быть **глобальным** администратором [бизнес-или корпоративного плана.](https://products.office.com/business/office) Эти изменения затрагивают весь клиент, *настраиваемые* администраторы или обычные пользователи не смогут вносить эти изменения.*</span><span class="sxs-lookup"><span data-stu-id="0a356-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="0a356-107">Выполните следующие действия, чтобы добавить, настроить или продолжить настройку домена.</span><span class="sxs-lookup"><span data-stu-id="0a356-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0a356-108">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="0a356-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="0a356-109">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="0a356-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0a356-110">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="0a356-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="0a356-111">Перейдите на **страницу**  >  **Параметры доменов.**</span><span class="sxs-lookup"><span data-stu-id="0a356-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="0a356-112">Выберите **Домен Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0a356-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="0a356-113">Введите имя домена, который вы хотите добавить, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0a356-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="0a356-114">Выберите, как проверить, является ли домен владельцем.</span><span class="sxs-lookup"><span data-stu-id="0a356-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="0a356-115">Если регистратор домена использует [Domain Connect,](#domain-connect-registrars-integrating-with-microsoft-365) [Корпорация](../get-help-with-domains/domain-connect.md) Майкрософт автоматически настроит ваши записи, включив его в регистратор и подтвердив подключение к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0a356-115">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="0a356-116">Вы будете возвращены в центр администрирования, после чего Корпорация Майкрософт автоматически проверит ваш домен.</span><span class="sxs-lookup"><span data-stu-id="0a356-116">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="0a356-117">Вы можете подтвердить владение доменом с помощью записи типа TXT.</span><span class="sxs-lookup"><span data-stu-id="0a356-117">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="0a356-118">Выберите это и выберите **Далее,** чтобы увидеть инструкции по добавлению этой записи DNS на веб-сайт регистратора.</span><span class="sxs-lookup"><span data-stu-id="0a356-118">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="0a356-119">Проверка записи может занять до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="0a356-119">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="0a356-120">Вы можете добавить текстовый файл на веб-сайт вашего домена.</span><span class="sxs-lookup"><span data-stu-id="0a356-120">You can add a text file to your domain's website.</span></span> <span data-ttu-id="0a356-121">Выберите и скачайте файл .txt из мастера установки, а затем загрузите его в папку верхнего уровня вашего сайта.</span><span class="sxs-lookup"><span data-stu-id="0a356-121">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="0a356-122">Путь к файлу должен выглядеть примерно так: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="0a356-122">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="0a356-123">Мы подтвердим, что вы владеете доменом, найдя файл на вашем сайте.</span><span class="sxs-lookup"><span data-stu-id="0a356-123">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="0a356-124">Выберите, как изменить DNS, необходимые корпорации Майкрософт для использования домена.</span><span class="sxs-lookup"><span data-stu-id="0a356-124">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="0a356-125">Выберите Добавить записи **DNS** для меня, если регистратор [](../get-help-with-domains/domain-connect.md) поддерживает Подключение домена, [](#domain-connect-registrars-integrating-with-microsoft-365)и Корпорация Майкрософт автоматически настроит ваши записи, включив его в регистратор и подтвердив подключение к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0a356-125">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="0a356-126">Выберите, чтобы я сам добавил записи **DNS,** если вы хотите прикрепить к домену только определенные службы Microsoft 365 или пропустить это сейчас и сделать это позже.</span><span class="sxs-lookup"><span data-stu-id="0a356-126">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="0a356-127">**Этот пункт предназначен для опытных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="0a356-127">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="0a356-128">Если вы решили самостоятельно добавить записи *DNS,*  выберите **Далее** и увидите страницу со всеми записями, которые необходимо добавить на веб-сайт регистраторов для настройка домена.</span><span class="sxs-lookup"><span data-stu-id="0a356-128">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="0a356-129">Если порталу не удается распознать регистратор, [воспользуйтесь общими инструкциями](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0a356-129">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="0a356-130">Просмотрите наш список [инструкций для конкретных хостов](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md). Найдите в нем свой хост и следуйте указаниям, чтобы добавить все нужные записи.</span><span class="sxs-lookup"><span data-stu-id="0a356-130">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="0a356-131">Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    </span><span class="sxs-lookup"><span data-stu-id="0a356-131">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="0a356-132">Если вы хотите подождать позже, либо отклоните все службы и нажмите кнопку **Продолжить,** или на предыдущем шаге подключения к домену выберите **Дополнительные** параметры и выберите **Пропустить** это на данный момент .</span><span class="sxs-lookup"><span data-stu-id="0a356-132">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="0a356-133">Выберите **Готово** — вы закончили!</span><span class="sxs-lookup"><span data-stu-id="0a356-133">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="0a356-134">Добавление и изменение настраиваемых записей DNS</span><span class="sxs-lookup"><span data-stu-id="0a356-134">Add or edit custom DNS records</span></span>

<span data-ttu-id="0a356-135">Следуйте ниже шагам, чтобы добавить настраиваемую запись для веб-сайта или службы 3-й стороны.</span><span class="sxs-lookup"><span data-stu-id="0a356-135">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="0a356-136">Во входе в центр администрирования Майкрософт по <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> крайней .</span><span class="sxs-lookup"><span data-stu-id="0a356-136">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0a356-137">Перейдите на **страницу**   >  **Параметры доменов.**</span><span class="sxs-lookup"><span data-stu-id="0a356-137">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="0a356-138">На странице **Домены** выберите домен.</span><span class="sxs-lookup"><span data-stu-id="0a356-138">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="0a356-139">В **настройках DNS** выберите **настраиваемые записи;** затем выберите **новую настраиваемую запись**.</span><span class="sxs-lookup"><span data-stu-id="0a356-139">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="0a356-140">Выберите тип записи DNS, которую необходимо добавить и ввести для новой записи.</span><span class="sxs-lookup"><span data-stu-id="0a356-140">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="0a356-141">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0a356-141">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="0a356-142">Регистраторы с подключением к домену</span><span class="sxs-lookup"><span data-stu-id="0a356-142">Registrars with Domain Connect</span></span>

<span data-ttu-id="0a356-143">[Регистраторы](https://www.domainconnect.org/) подключения к домену позволяют добавлять домен в Microsoft 365 в трехшаговом процессе, который занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="0a356-143">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="0a356-144">В мастере мы просто подтвердим, что вы владеете доменом, а затем автоматически настроим записи домена, поэтому электронная почта поступает в Microsoft 365 и другие службы Microsoft 365, такие как Teams, работайте с доменом.</span><span class="sxs-lookup"><span data-stu-id="0a356-144">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a356-145">Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.</span><span class="sxs-lookup"><span data-stu-id="0a356-145">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="0a356-146">Регистраторы Domain Connect, интегрируясь с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a356-146">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="0a356-147">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="0a356-147">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="0a356-148">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="0a356-148">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="0a356-149">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="0a356-149">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="0a356-150">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="0a356-150">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="0a356-151">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="0a356-151">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="0a356-152">Plesk</span><span class="sxs-lookup"><span data-stu-id="0a356-152">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="0a356-153">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="0a356-153">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="0a356-154">SecureServer или WildWestDomains (реселлеры GoDaddy с помощью DNS-хостинга SecureServer)</span><span class="sxs-lookup"><span data-stu-id="0a356-154">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="0a356-155">Примеры:</span><span class="sxs-lookup"><span data-stu-id="0a356-155">Examples:</span></span>
        - [<span data-ttu-id="0a356-156">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="0a356-156">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="0a356-157">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="0a356-157">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="0a356-158">Что происходит с моей электронной почтой и веб-сайтом?</span><span class="sxs-lookup"><span data-stu-id="0a356-158">What happens to my email and website?</span></span>

<span data-ttu-id="0a356-159">После завершения настройки запись MX для вашего домена обновляется, чтобы указать на Microsoft 365, и вся электронная почта для вашего домена начнет приходить в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0a356-159">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="0a356-160">Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту на вашем домене!</span><span class="sxs-lookup"><span data-stu-id="0a356-160">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="0a356-161">Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде.</span><span class="sxs-lookup"><span data-stu-id="0a356-161">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="0a356-162">Действия установки подключения к домену не влияют на веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="0a356-162">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0a356-163">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0a356-163">Related articles</span></span>

[<span data-ttu-id="0a356-164">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="0a356-164">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="0a356-165">Что такое домен?</span><span class="sxs-lookup"><span data-stu-id="0a356-165">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="0a356-166">Приобретение доменного имени в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a356-166">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="0a356-167">Настройка домена (инструкции для конкретных узлов)</span><span class="sxs-lookup"><span data-stu-id="0a356-167">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)