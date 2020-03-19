---
title: Добавление домена в Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.openlocfilehash: 86ca8f986624ad37f780961cb58923ea0a1b2308
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857383"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="7cc7f-104">Добавление домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="7cc7f-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="7cc7f-105">Если вы не нашли то, что вы ищете, обратитесь к разделу **[Вопросы и ответы по доменам](domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="7cc7f-106">*Чтобы добавить, изменить или удалить домены, **необходимо** быть **глобальным администратором** [плана бизнеса или предприятия](https://products.office.com/business/office). Эти изменения затрагивают весь клиент, *Администраторы* или *обычные пользователи* не смогут вносить эти изменения.*</span><span class="sxs-lookup"><span data-stu-id="7cc7f-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="7cc7f-107">Выполните указанные ниже действия, чтобы добавить, настроить или продолжить настройку домена.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7cc7f-108">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="7cc7f-109">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7cc7f-110">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="7cc7f-111">Перейдите на страницу "**домены** **параметров** > ".</span><span class="sxs-lookup"><span data-stu-id="7cc7f-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="7cc7f-112">Выберите **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="7cc7f-113">Введите имя домена, который вы хотите добавить, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="7cc7f-114">Выберите способ проверки того, что вы владеете доменом.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="7cc7f-115">Если ваш домен зарегистрирован на GoDaddy или 1&amp;1, установите флажок **войти** > **Далее, после** чего Office 365 настроит [свои записи автоматически](../get-help-with-domains/domain-connect.md).</span><span class="sxs-lookup"><span data-stu-id="7cc7f-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Office 365 [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="7cc7f-116">Вы можете отправить контакту, зарегистрированному для домена, сообщение электронной почты с кодом проверки.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="7cc7f-117">Если вы не узнаете или не можете получить доступ к записи электронной почты, вы можете использовать третий вариант.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="7cc7f-118">Вы можете подтвердить владение доменом с помощью записи типа TXT.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="7cc7f-119">Установите этот флажок и нажмите кнопку **Далее** , чтобы просмотреть инструкции по добавлению этой записи DNS на веб-сайт регистратора.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="7cc7f-120">Проверка после добавления записи может занять до 30 минут.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="7cc7f-121">Выберите способ внесения изменений DNS, необходимых для использования домена в Office.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="7cc7f-122">Выберите **добавить записи DNS для меня,** если вы хотите, чтобы Office автоматически настроил DNS.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="7cc7f-123">Нажмите **я буду добавлять записи DNS самостоятельно** , если вы хотите присоединить к вашему домену только определенные службы Office 365, или если вы хотите пропустить это действие и сделать это позже.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="7cc7f-124">**Этот пункт предназначен для опытных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="7cc7f-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="7cc7f-125">Если вы решили *добавить записи DNS самостоятельно* , нажмите кнопку **Далее** , чтобы увидеть страницу со всеми записями, которые необходимо добавить на веб-сайт регистраторов, чтобы настроить свой домен.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="7cc7f-126">Если порталу не удается распознать регистратор, [воспользуйтесь общими инструкциями](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="7cc7f-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="7cc7f-127">Просмотрите наш список [инструкций для конкретных хостов](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580). Найдите в нем свой хост и следуйте указаниям, чтобы добавить все нужные записи.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="7cc7f-128">Если вы не знаете, какой поставщик услуг размещения DNS или регистратор используется для домена, см. статью [Определение регистратора домена или поставщика услуг размещения DNS](../get-help-with-domains/find-your-domain-registrar.md).    </span><span class="sxs-lookup"><span data-stu-id="7cc7f-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="7cc7f-129">Если вы хотите подождать позже, прокрутите страницу вниз и выберите **пропустить этот шаг**.</span><span class="sxs-lookup"><span data-stu-id="7cc7f-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="7cc7f-130">Нажмите кнопку Готово, чтобы **завершить работу** .</span><span class="sxs-lookup"><span data-stu-id="7cc7f-130">Select **Finish** - you're done!</span></span> 

## <a name="related-articles"></a><span data-ttu-id="7cc7f-131">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="7cc7f-131">Related articles</span></span>

[<span data-ttu-id="7cc7f-132">Вопросы и ответы о доменах</span><span class="sxs-lookup"><span data-stu-id="7cc7f-132">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="7cc7f-133">Что такое домен?</span><span class="sxs-lookup"><span data-stu-id="7cc7f-133">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="7cc7f-134">Приобретение доменного имени в Office 365</span><span class="sxs-lookup"><span data-stu-id="7cc7f-134">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="7cc7f-135">Настройка домена (инструкции для конкретных узлов)</span><span class="sxs-lookup"><span data-stu-id="7cc7f-135">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="7cc7f-136">Получение справки по доменам Office 365</span><span class="sxs-lookup"><span data-stu-id="7cc7f-136">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.yml)
