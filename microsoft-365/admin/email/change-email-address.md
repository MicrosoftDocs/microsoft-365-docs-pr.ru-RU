---
title: Изменение адреса электронной почты с использованием пользовательского домена
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
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 'Замените начальный адрес электронной почты на понятный адрес электронной почты, такой как tom@fourthcoffee.com. Для этого необходимо приобрести доменное имя и добавить его в Microsoft 365. '
ms.openlocfilehash: 7b5ab62ea99af52c61ca4ba6a7e9ea37604ddf19
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645543"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="19577-104">Изменение адреса электронной почты с использованием пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="19577-104">Change your email address to use your custom domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="19577-105">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="19577-105">The admin center is changing.</span></span> <span data-ttu-id="19577-106">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="19577-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="19577-107">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="19577-107">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="19577-108">Ваш исходный адрес электронной почты в Microsoft 365 включает. onmicrosoft.com, например tom@fourthcoffee.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="19577-108">Your initial email address in Microsoft 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com.</span></span> <span data-ttu-id="19577-109">Вы можете изменить его на более понятный адрес, например ivan@fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="19577-109">You can change it to a friendlier address like tom@fourthcoffee.com.</span></span> <span data-ttu-id="19577-110">Сначала вам потребуется получить собственное доменное имя, например fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="19577-110">You'll need your own domain name, like fourthcoffee.com first.</span></span> <span data-ttu-id="19577-111">Если оно у вас уже есть, отлично!</span><span class="sxs-lookup"><span data-stu-id="19577-111">If you already have one, great!</span></span> <span data-ttu-id="19577-112">Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="19577-112">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="19577-113">Ваш исходный адрес электронной почты в Office 365 Германия включает. onmicrosoft.de, например tom@fourthcoffee.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="19577-113">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="19577-114">Вы можете изменить его на более понятный адрес, такой как tom@fourthcoffee.de.</span><span class="sxs-lookup"><span data-stu-id="19577-114">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="19577-115">Вам потребуется собственное доменное имя, например fourthcoffee.de.</span><span class="sxs-lookup"><span data-stu-id="19577-115">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="19577-116">Если оно у вас уже есть, отлично!</span><span class="sxs-lookup"><span data-stu-id="19577-116">If you already have one, great!</span></span> <span data-ttu-id="19577-117">Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="19577-117">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="19577-118">Ваш исходный адрес электронной почты в Office 365 под управлением 21Vianet включает partner.onmschina.cn, например tom@fourthcoffee.partner.onmschina.cn.</span><span class="sxs-lookup"><span data-stu-id="19577-118">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="19577-119">Вы можете изменить его на более понятный адрес, такой как tom@fourthcoffee.cn.</span><span class="sxs-lookup"><span data-stu-id="19577-119">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="19577-120">Вам потребуется собственное доменное имя, например fourthcoffee.cn.</span><span class="sxs-lookup"><span data-stu-id="19577-120">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="19577-121">Если оно у вас уже есть, отлично!</span><span class="sxs-lookup"><span data-stu-id="19577-121">If you already have one, great!</span></span> <span data-ttu-id="19577-122">Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="19577-122">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="19577-123">Когда вы изменяете электронную почту вашего домена на поступающий в Microsoft 365, обновляя запись MX вашего домена во время установки, все сообщения, отправленные в этот домен, начнут приходить в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19577-123">When you change your domain's email to come to Microsoft 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="19577-124">Убедитесь, что добавлены пользователи и созданные почтовые ящики в Microsoft 365 для всех пользователей, у которых есть электронная почта в вашем домене, прежде чем изменять запись MX.</span><span class="sxs-lookup"><span data-stu-id="19577-124">Make sure you've added users and created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span> <span data-ttu-id="19577-125">Не хотите перемещать электронную почту для всех пользователей вашего домена в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="19577-125">Don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="19577-126">Вы можете выполнить действия для [пилотного развертывания Microsoft 365 с использованием всего нескольких адресов электронной почты](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="19577-126">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="19577-127">Изменение адреса электронной почты для использования личного домена с помощью центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="19577-127">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="19577-128">Для выполнения этих действий необходимо иметь глобальную учетную запись администратора.</span><span class="sxs-lookup"><span data-stu-id="19577-128">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="19577-129">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="19577-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="19577-130">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="19577-130">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="19577-131">Перейдите в центр администрирования по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>.</span><span class="sxs-lookup"><span data-stu-id="19577-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="19577-132">Перейдите на страницу **Setup**"  >  **домены** установки".</span><span class="sxs-lookup"><span data-stu-id="19577-132">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="19577-133">На странице **Домены** выберите **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="19577-133">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="19577-134">Следуйте указаниям, чтобы подтвердить право собственности на домен и изменить адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="19577-134">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="19577-135">Вы узнаете, как правильно настроить все параметры домена в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19577-135">You'll be guided to get everything set up correctly with your domain in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="19577-136">Если вы не используете лицензию Exchange, вы не можете использовать домен для отправки или получения электронных сообщений от клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="19577-136">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Microsoft 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="19577-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="19577-137">Related articles</span></span>

[<span data-ttu-id="19577-138">Приобретение настраиваемого домена с помощью Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="19577-138">Buy a custom domain using Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
