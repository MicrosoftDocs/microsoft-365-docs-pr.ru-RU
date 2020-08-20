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
description: Добавьте домен в Microsoft 365 в Центре администрирования Microsoft 365, добавив запись DNS на узел DNS. Мастер установки поможет вам выполнить все действия.
ms.openlocfilehash: 0adf8b4dcd5d7bd31038b74a574f449f32bfb037
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814436"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="4b970-104">Добавление домена в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b970-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4b970-105">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="4b970-105">The admin center is changing.</span></span> <span data-ttu-id="4b970-106">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="4b970-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="4b970-107">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="4b970-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="4b970-108">*Чтобы добавить, измените или удалите домены, **необходимо быть** **глобальным** администратором [корпоративного или корпоративного плана.](https://products.office.com/business/office) Эти изменения затрагивают весь клиент, *настроенные администраторы* и *обычные* пользователи не смогут внести такие изменения.*</span><span class="sxs-lookup"><span data-stu-id="4b970-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="4b970-109">Выполните следующие действия, чтобы добавить, настроить или продолжить настройку домена.</span><span class="sxs-lookup"><span data-stu-id="4b970-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4b970-110">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="4b970-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="4b970-111">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="4b970-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4b970-112">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="4b970-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="4b970-113">Перейдите на страницу **"Параметры**  >  **домена".**</span><span class="sxs-lookup"><span data-stu-id="4b970-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="4b970-114">Выберите **пункт "Добавить домен".**</span><span class="sxs-lookup"><span data-stu-id="4b970-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="4b970-115">Введите имя домена, который нужно добавить, и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="4b970-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="4b970-116">Выберите способ проверки принадлежности домена.</span><span class="sxs-lookup"><span data-stu-id="4b970-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="4b970-117">Если ваш домен зарегистрирован на сайте GoDaddy или 1 &amp; 1, нажмите кнопку **"Вход в**  >  **систему Next",** и Корпорация Майкрософт [автоматически настроит ваши ваши записи.](../get-help-with-domains/domain-connect.md)</span><span class="sxs-lookup"><span data-stu-id="4b970-117">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="4b970-118">Вы можете отправить контакту, зарегистрированному для домена, сообщение электронной почты с кодом проверки.</span><span class="sxs-lookup"><span data-stu-id="4b970-118">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="4b970-119">Если вам не знаком вашадрес адрес или у вас нет доступа к нему, вы можете использовать третий вариант.</span><span class="sxs-lookup"><span data-stu-id="4b970-119">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="4b970-120">Вы можете подтвердить владение доменом с помощью записи типа TXT.</span><span class="sxs-lookup"><span data-stu-id="4b970-120">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="4b970-121">Установите этот флажок **и** нажмите кнопку "Далее", чтобы просмотреть инструкции о добавлении записи DNS на веб-сайт регистратора.</span><span class="sxs-lookup"><span data-stu-id="4b970-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="4b970-122">Проверка добавленной записи может занять до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="4b970-122">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="4b970-123">Выберите, как вы хотите внести изменения в DNS, необходимые для использования домена системой Office.</span><span class="sxs-lookup"><span data-stu-id="4b970-123">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="4b970-124">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span><span class="sxs-lookup"><span data-stu-id="4b970-124">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="4b970-125">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span><span class="sxs-lookup"><span data-stu-id="4b970-125">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="4b970-126">**Этот пункт предназначен для опытных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="4b970-126">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="4b970-127">Если вы решили  *добавить записи DNS*  самостоятельно, нажмите кнопку **"Далее",** и откроется страница со всеми записями, которые нужно добавить на веб-сайт регистратора для настройки домена.</span><span class="sxs-lookup"><span data-stu-id="4b970-127">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="4b970-128">Если порталу не удается распознать регистратор, [воспользуйтесь общими инструкциями](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4b970-128">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="4b970-129">Просмотрите наш список [инструкций для конкретных хостов](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions). Найдите в нем свой хост и следуйте указаниям, чтобы добавить все нужные записи.</span><span class="sxs-lookup"><span data-stu-id="4b970-129">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="4b970-130">Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    </span><span class="sxs-lookup"><span data-stu-id="4b970-130">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="4b970-131">Если вы хотите подождать, прокрутите экран вниз и выберите этот **шаг пропустить.**</span><span class="sxs-lookup"><span data-stu-id="4b970-131">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="4b970-132">Нажмите **кнопку** "Готово" — все готово!</span><span class="sxs-lookup"><span data-stu-id="4b970-132">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="4b970-133">Добавление и изменение настраиваемых записей DNS</span><span class="sxs-lookup"><span data-stu-id="4b970-133">Add or edit custom DNS records</span></span>

<span data-ttu-id="4b970-134">Выполните указанные ниже действия, чтобы добавить пользовательскую запись для веб-сайта или сторонней службы.</span><span class="sxs-lookup"><span data-stu-id="4b970-134">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="4b970-135">Войдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4b970-135">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="4b970-136">Перейдите на страницу **"Параметры**   >  **домена".**</span><span class="sxs-lookup"><span data-stu-id="4b970-136">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="4b970-137">На странице **Домены** выберите домен.</span><span class="sxs-lookup"><span data-stu-id="4b970-137">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="4b970-138">В разделе **"Параметры DNS"** выберите **"Настраиваемые записи";** затем выберите **"Создать настраиваемую запись".**</span><span class="sxs-lookup"><span data-stu-id="4b970-138">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="4b970-139">Выберите тип записи DNS, которую необходимо добавить, и введите необходимые данные.</span><span class="sxs-lookup"><span data-stu-id="4b970-139">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="4b970-140">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4b970-140">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="4b970-141">Регистраторы с подключением к домену</span><span class="sxs-lookup"><span data-stu-id="4b970-141">Registrars with Domain Connect</span></span>

<span data-ttu-id="4b970-142">[С помощью](https://www.domainconnect.org/) подключаемого домена регистраторы позволяют добавить ваш домен в Microsoft 365 в три этапа, занимаемых минутами.</span><span class="sxs-lookup"><span data-stu-id="4b970-142">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="4b970-143">В мастере мы просто подтвердим, что вы являетесь владельцем домена, а затем настроим записи вашего домена, чтобы электронная почта поступала в Microsoft 365 и другие службы Microsoft 365 (например, Teams) с вами.</span><span class="sxs-lookup"><span data-stu-id="4b970-143">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b970-144">Прежде чем запускать мастер установки, убедитесь, что в браузере отключено блокирование всплывающих окон.</span><span class="sxs-lookup"><span data-stu-id="4b970-144">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="4b970-145">Регистраторы доменных имен, интегрированные с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b970-145">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="4b970-146">1 &amp; 1. ОБЪЕКТЫ СОСТОЯЩИХ ИЗ</span><span class="sxs-lookup"><span data-stu-id="4b970-146">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="4b970-147">123Reg</span><span class="sxs-lookup"><span data-stu-id="4b970-147">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="4b970-148">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="4b970-148">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="4b970-149">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="4b970-149">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="4b970-150">WordPress</span><span class="sxs-lookup"><span data-stu-id="4b970-150">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="4b970-151">Plesk</span><span class="sxs-lookup"><span data-stu-id="4b970-151">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="4b970-152">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="4b970-152">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="4b970-153">SecureServer или WildWestDomains (торговые посредники GoDaddy с использованием размещения DNS SecureServer)</span><span class="sxs-lookup"><span data-stu-id="4b970-153">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="4b970-154">Домены MadDog</span><span class="sxs-lookup"><span data-stu-id="4b970-154">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="4b970-155">CheapNames</span><span class="sxs-lookup"><span data-stu-id="4b970-155">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="4b970-156">Что происходит с моей электронной почтой и веб-сайтом?</span><span class="sxs-lookup"><span data-stu-id="4b970-156">What happens to my email and website?</span></span>

<span data-ttu-id="4b970-157">По окончании настройки выполняется обновление записи MX для вашего домена, в результате чего запись будет указана на Microsoft 365, и все почтовые сообщения для вашего домена будут поступать в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b970-157">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="4b970-158">Убедитесь, что вы добавили пользователей и настроили почтовые ящики в Microsoft 365 для всех, кто получает электронную почту в вашем домене!</span><span class="sxs-lookup"><span data-stu-id="4b970-158">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="4b970-159">Если у вас есть веб-сайт, который вы используете для бизнеса, он будет работать как прежде.</span><span class="sxs-lookup"><span data-stu-id="4b970-159">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="4b970-160">Действия по настройке подключения к домену не влияют на работу вашего веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="4b970-160">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4b970-161">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4b970-161">Related articles</span></span>

[<span data-ttu-id="4b970-162">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="4b970-162">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="4b970-163">Что такое домен?</span><span class="sxs-lookup"><span data-stu-id="4b970-163">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="4b970-164">Приобретение доменного имени в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b970-164">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="4b970-165">Настройка домена (инструкции для конкретных узлов)</span><span class="sxs-lookup"><span data-stu-id="4b970-165">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
