---
title: Работать с поставщиками решений
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration <!-- need to figure out what this value should be -->
localization_priority: Normal
ms.collection:
- commerce <!-- probably need to change this -->
ms.custom: ''
search.appverid:
- MET150
description: Вы можете работать с поставщиками решений, сертифицированными корпорацией Майкрософт, для приобретения и управления продуктами и службами в организации или учебном заведении.
keywords: партнер, поставщик решений
ms.openlocfilehash: 341a353247635eab491eb0962273eeed09b31599
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594123"
---
# <a name="working-with-solution-providers-in-microsoft-store-for-business"></a><span data-ttu-id="e1004-104">Работа с поставщиками решений в Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e1004-104">Working with solution providers in Microsoft Store for Business</span></span>

<span data-ttu-id="e1004-105">Вы можете работать с поставщиками решений, сертифицированными корпорацией Майкрософт, для приобретения и управления продуктами и службами в организации или учебном заведении.</span><span class="sxs-lookup"><span data-stu-id="e1004-105">You can work with Microsoft-certified solution providers to purchase and manage products and services for your organization or school.</span></span> <span data-ttu-id="e1004-106">Существует несколько шагов, связанных с настройкой.</span><span class="sxs-lookup"><span data-stu-id="e1004-106">There's a few steps involved in getting the things set up.</span></span> 

<span data-ttu-id="e1004-107">Процесс выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e1004-107">The process goes like this:</span></span>
- <span data-ttu-id="e1004-108">Администраторы находят поставщик решений и подходят к нему, используя **Поиск поставщика решений** в Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e1004-108">Admins find and contact a solution provider using **Find a solution provider** in Microsoft Store for Business.</span></span> 
- <span data-ttu-id="e1004-109">Поставщики решений отправляют клиентам запрос от центра партнерской компании, чтобы стать их поставщиками решений.</span><span class="sxs-lookup"><span data-stu-id="e1004-109">Solution providers send a request from Partner center to customers to become their solution provider.</span></span>
- <span data-ttu-id="e1004-110">Клиенты принимают приглашение в Microsoft Store для бизнеса и начинают работу с поставщиком решений.</span><span class="sxs-lookup"><span data-stu-id="e1004-110">Customers accept the invitation in Microsoft Store for Business and start working with the solution provider.</span></span>
- <span data-ttu-id="e1004-111">Пользователи могут управлять параметрами связи с партнером в Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e1004-111">Customers can manage settings for the relationship with Partner in Microsoft Store for Business.</span></span> 

## <a name="what-can-a-solution-provider-do-for-my-organization-or-school"></a><span data-ttu-id="e1004-112">Что может делать поставщик решений для организации или учебного заведения?</span><span class="sxs-lookup"><span data-stu-id="e1004-112">What can a solution provider do for my organization or school?</span></span>

<span data-ttu-id="e1004-113">Существует несколько способов, с которыми может работать поставщик решений.</span><span class="sxs-lookup"><span data-stu-id="e1004-113">There are several ways that a solution provider can work with you.</span></span> <span data-ttu-id="e1004-114">Поставщики решений будут выбирать один из них при отправке запроса на работу в качестве партнера.</span><span class="sxs-lookup"><span data-stu-id="e1004-114">Solution providers will choose one of these when they send their request to work as a partner with you.</span></span>

| <span data-ttu-id="e1004-115">Функция поставщика решений</span><span class="sxs-lookup"><span data-stu-id="e1004-115">Solution provider function</span></span> | <span data-ttu-id="e1004-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e1004-116">Description</span></span> | 
| ------ | ------------------- | 
| <span data-ttu-id="e1004-117">Торговых посредников</span><span class="sxs-lookup"><span data-stu-id="e1004-117">Reseller</span></span> | <span data-ttu-id="e1004-118">Поставщики решений продают продукты корпорации Майкрософт в организации или учебном заведении.</span><span class="sxs-lookup"><span data-stu-id="e1004-118">Solution providers sell Microsoft products to your organization or school.</span></span> |
| <span data-ttu-id="e1004-119">Полномочный администратор</span><span class="sxs-lookup"><span data-stu-id="e1004-119">Delegated administrator</span></span> | <span data-ttu-id="e1004-120">Поставщик решений служит для управления продуктами и службами в организации или учебном заведении.</span><span class="sxs-lookup"><span data-stu-id="e1004-120">Solution provider manages products and services for your organization or school.</span></span> <span data-ttu-id="e1004-121">В Azure Active Directory партнер будет глобальным администратором для клиента.</span><span class="sxs-lookup"><span data-stu-id="e1004-121">In Azure Active Directory (AD), the Partner will be a Global Administrator for tenant.</span></span> <span data-ttu-id="e1004-122">Это позволяет им управлять службами, такими как создание учетных записей пользователей, назначение и управление лицензиями, а сброс паролей.</span><span class="sxs-lookup"><span data-stu-id="e1004-122">This allows them to manage services like creating user accounts, assigning and managing licenses, and password resets.</span></span> |
| <span data-ttu-id="e1004-123">Торговый посредник & с делегированным администратором</span><span class="sxs-lookup"><span data-stu-id="e1004-123">Reseller & delegated administrator</span></span> | <span data-ttu-id="e1004-124">Поставщики решений, которые продают продукты и службы Майкрософт в организации или учебном заведении и управляют ими.</span><span class="sxs-lookup"><span data-stu-id="e1004-124">Solution providers that sell and manage Microsoft products and services to your organization or school.</span></span> |
| <span data-ttu-id="e1004-125">Партнер</span><span class="sxs-lookup"><span data-stu-id="e1004-125">Partner</span></span> | <span data-ttu-id="e1004-126">Вы можете предоставить поставщику решения учетную запись пользователя в клиенте и работать от вашего имени с другими службами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e1004-126">You can give your solution provider a user account in your tenant, and they work on your behalf with other Microsoft services.</span></span> |
| <span data-ttu-id="e1004-127">Партнер корпорации Майкрософт & соглашений об услугах (МПСА)</span><span class="sxs-lookup"><span data-stu-id="e1004-127">Microsoft Products & Services Agreement (MPSA) partner</span></span> | <span data-ttu-id="e1004-128">Если вы работали с несколькими поставщиками решений с помощью программы МПСА, вы можете позволить партнерам просматривать покупки друг друга.</span><span class="sxs-lookup"><span data-stu-id="e1004-128">If you've worked with multiple solution providers through the MPSA program, you can allow partners to see purchases made by each other.</span></span> |
| <span data-ttu-id="e1004-129">Партнер для OEM-ПК</span><span class="sxs-lookup"><span data-stu-id="e1004-129">OEM PC partner</span></span> | <span data-ttu-id="e1004-130">Поставщики решений могут отправлять идентификаторы устройств для компьютеров, которыми вы [управляете с помощью автопилота](https://docs.microsoft.com/microsoft-store/add-profile-to-devices).</span><span class="sxs-lookup"><span data-stu-id="e1004-130">Solution providers can upload device IDs for PCs that you're [managing with Autopilot](https://docs.microsoft.com/microsoft-store/add-profile-to-devices).</span></span>   |
| <span data-ttu-id="e1004-131">Бизнес-партнер (LOB)</span><span class="sxs-lookup"><span data-stu-id="e1004-131">Line-of-business (LOB) partner</span></span> | <span data-ttu-id="e1004-132">Поставщики решений могут разрабатывать, передавать и управлять бизнес-приложениями, характерными для вашей организации или учебного заведения.</span><span class="sxs-lookup"><span data-stu-id="e1004-132">Solution providers can develop, submit, and manage LOB apps specific for your organization or school.</span></span> |

## <a name="find-a-solution-provider"></a><span data-ttu-id="e1004-133">Поиск поставщика решений</span><span class="sxs-lookup"><span data-stu-id="e1004-133">Find a solution provider</span></span>

<span data-ttu-id="e1004-134">Вы можете найти партнера в Microsoft Store для бизнеса и образовательных учреждений.</span><span class="sxs-lookup"><span data-stu-id="e1004-134">You can find partner in Microsoft Store for Business and Education.</span></span> 

1. <span data-ttu-id="e1004-135">Войдите в [службу Microsoft Store для бизнеса](https://businessstore.microsoft.com/) или [Microsoft Store для образовательных учреждений](https://educationstore.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="e1004-135">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com/) or [Microsoft Store for Education](https://educationstore.microsoft.com/).</span></span>
2. <span data-ttu-id="e1004-136">Выберите пункт **найти поставщика решений**.</span><span class="sxs-lookup"><span data-stu-id="e1004-136">Select **Find a solution provider**.</span></span>
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-find-partner.png)
-->
3. <span data-ttu-id="e1004-137">Уточните список или найдите поставщика решений.</span><span class="sxs-lookup"><span data-stu-id="e1004-137">Refine the list, or search for a solution provider.</span></span> 
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-provider-list.png)
-->
4. <span data-ttu-id="e1004-138">Найдя поставщика решений, с которым вы заинтересованы в работе, щелкните **контакт**.</span><span class="sxs-lookup"><span data-stu-id="e1004-138">When you find a solution provider you're interested in working with, click **Contact**.</span></span>
5. <span data-ttu-id="e1004-139">Заполните и отправьте форму.</span><span class="sxs-lookup"><span data-stu-id="e1004-139">Complete and send the form.</span></span>

<span data-ttu-id="e1004-140">Поставщик решений будет общаться с вами.</span><span class="sxs-lookup"><span data-stu-id="e1004-140">The solution provider will get in touch with you.</span></span> <span data-ttu-id="e1004-141">У вас будет возможность получить дополнительные сведения об этих возможностях.</span><span class="sxs-lookup"><span data-stu-id="e1004-141">You'll have a chance to learn more about them.</span></span> <span data-ttu-id="e1004-142">Если вы решили работать с поставщиком решений, они отправляют вам приглашение по электронной почте от центра партнеров.</span><span class="sxs-lookup"><span data-stu-id="e1004-142">If you decide to work with the solution provider, they will send you an email invitation from Partner Center.</span></span> 

## <a name="work-with-a-solution-provider"></a><span data-ttu-id="e1004-143">Работать с поставщиком решений</span><span class="sxs-lookup"><span data-stu-id="e1004-143">Work with a solution provider</span></span>

<span data-ttu-id="e1004-144">После того как вы нашли поставщика решений и решили работать с ними, он отправит вам приглашение для совместной работы в центре партнеров.</span><span class="sxs-lookup"><span data-stu-id="e1004-144">Once you've found a solution provider and decided to work with them, they'll send you an invitation to work together from Partner Center.</span></span> <span data-ttu-id="e1004-145">В Microsoft Store для бизнеса или образования необходимо принять приглашение.</span><span class="sxs-lookup"><span data-stu-id="e1004-145">In Microsoft Store for Business or Education, you'll need to accept the invitation.</span></span> <span data-ttu-id="e1004-146">После этого вы сможете управлять своими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="e1004-146">After that, you can manage their permissions.</span></span>

<span data-ttu-id="e1004-147">**Прием приглашения поставщика решений**</span><span class="sxs-lookup"><span data-stu-id="e1004-147">**To accept a solution provider invitation**</span></span>
1. <span data-ttu-id="e1004-148">**Подпишитесь на электронную** почту — вы получите электронное письмо со ссылкой, чтобы принять приглашение поставщика решений у поставщика решений.</span><span class="sxs-lookup"><span data-stu-id="e1004-148">**Follow email link** - You'll receive an email with a link to accept the solution provider invitation from your solution provider.</span></span> <span data-ttu-id="e1004-149">По ссылке вы перейдете в Microsoft Store для бизнеса или образовательных учреждений.</span><span class="sxs-lookup"><span data-stu-id="e1004-149">The link will take you to Microsoft Store for Business or Education.</span></span>
2. <span data-ttu-id="e1004-150">**Принять приглашение** — вкл. **примите приглашение партнер**, выберите **авторизовать** для принятия приглашения, примите условия соглашения Microsoft Cloud и начните работу с поставщиком решений.</span><span class="sxs-lookup"><span data-stu-id="e1004-150">**Accept invitation** - On **Accept Partner Invitation**, select **Authorize** to accept the invitation, accept terms of the Microsoft Cloud Agreement, and start working with the solution provider.</span></span> 
<!---
![Image shows accepting an invitation from a solution provider in Microsoft Store for Business.](images/msft-accept-partner.png)
--> 
## <a name="delegate-admin-privileges"></a><span data-ttu-id="e1004-151">Делегирование прав администратора</span><span class="sxs-lookup"><span data-stu-id="e1004-151">Delegate admin privileges</span></span>

<span data-ttu-id="e1004-152">В зависимости от запроса, сделанного поставщиком решения, часть принятия приглашения будет включать в себя согласие на предоставление поставщику решения прав делегированного администратора.</span><span class="sxs-lookup"><span data-stu-id="e1004-152">Depending on the request made by the solution provider, part of accepting the invitation will include agreeing to give delegated admin privileges to the solution provider.</span></span> <span data-ttu-id="e1004-153">Это происходит, когда запрос поставщика решения включает себя в качестве делегированного администратора.</span><span class="sxs-lookup"><span data-stu-id="e1004-153">This will happen when the solution provider request includes acting as a delegated administrator.</span></span> <span data-ttu-id="e1004-154">Для получения дополнительных сведений обратитесь к разделу [делегированные права администратора в Azure AD](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="e1004-154">For more information, see [Delegated admin privileges in Azure AD](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span></span> 

<span data-ttu-id="e1004-155">Если вы не хотите делегировать права администратора поставщику решений, вам потребуется отменить приглашение, а не принимать его.</span><span class="sxs-lookup"><span data-stu-id="e1004-155">If you don't want to delegate admin privileges to the solution provider, you'll need to cancel the invitation instead of accepting it.</span></span> 

<span data-ttu-id="e1004-156">Если вы делегируйте права администратора поставщику решений, вы можете удалить его позже.</span><span class="sxs-lookup"><span data-stu-id="e1004-156">If you delegate admin privileges to a solution provider, you can remove that later.</span></span> 

<span data-ttu-id="e1004-157">**Удаление прав администратора представителя**</span><span class="sxs-lookup"><span data-stu-id="e1004-157">**To remove delegate admin privileges**</span></span>
1. <span data-ttu-id="e1004-158">Войдите в [службу Microsoft Store для бизнеса](https://businessstore.microsoft.com/) или [Microsoft Store для образовательных учреждений](https://educationstore.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="e1004-158">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com/) or [Microsoft Store for Education](https://educationstore.microsoft.com/).</span></span>
2. <span data-ttu-id="e1004-159">Выбор **партнера**</span><span class="sxs-lookup"><span data-stu-id="e1004-159">Select **Partner**</span></span>
3. <span data-ttu-id="e1004-160">Выберите партнера, которого вы хотите управлять.</span><span class="sxs-lookup"><span data-stu-id="e1004-160">Choose the Partner you want to manage.</span></span>
4. <span data-ttu-id="e1004-161">Выберите пункт **Удалить делегированные разрешения**.</span><span class="sxs-lookup"><span data-stu-id="e1004-161">Select **Remove Delegated Permissions**.</span></span> 

<span data-ttu-id="e1004-162">Поставщик решений по-прежнему сможет работать с вами, например, как торговый посредник.</span><span class="sxs-lookup"><span data-stu-id="e1004-162">The solution provider will still be able to work with you, for example, as a Reseller.</span></span> 
