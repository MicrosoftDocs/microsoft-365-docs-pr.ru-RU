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
description: 'Измените исходный адрес электронной почты на адрес электронной почты, такой как tom@fourthcoffee.com. Для этого необходимо приобрести доменное имя и добавить его в Microsoft 365. '
ms.openlocfilehash: 445b78f759cee79a794f9656afd5b26051534e26
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114025"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="e5188-104">Изменение адреса электронной почты с использованием пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="e5188-104">Change your email address to use your custom domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e5188-105">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="e5188-105">The admin center is changing.</span></span> <span data-ttu-id="e5188-106">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="e5188-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

 <span data-ttu-id="e5188-107">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="e5188-107">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="e5188-108">Исходный адрес электронной почты в Microsoft 365 включает .onmicrosoft.com, например tom@fourthcoffee.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e5188-108">Your initial email address in Microsoft 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com.</span></span> <span data-ttu-id="e5188-109">Вы можете изменить его на более понятный адрес, например ivan@fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="e5188-109">You can change it to a friendlier address like tom@fourthcoffee.com.</span></span> <span data-ttu-id="e5188-110">Сначала вам потребуется получить собственное доменное имя, например fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="e5188-110">You'll need your own domain name, like fourthcoffee.com first.</span></span> <span data-ttu-id="e5188-111">Если оно у вас уже есть, отлично!</span><span class="sxs-lookup"><span data-stu-id="e5188-111">If you already have one, great!</span></span> <span data-ttu-id="e5188-112">Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="e5188-112">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="e5188-113">Исходный адрес электронной почты в Office 365 Germany включает .onmicrosoft.de, например tom@fourthcoffee.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="e5188-113">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="e5188-114">Вы можете изменить его на более дружелюбный адрес, например tom@fourthcoffee.de.</span><span class="sxs-lookup"><span data-stu-id="e5188-114">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="e5188-115">Вам потребуется собственное доменное имя, например fourthcoffee.de.</span><span class="sxs-lookup"><span data-stu-id="e5188-115">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="e5188-116">Если оно у вас уже есть, отлично!</span><span class="sxs-lookup"><span data-stu-id="e5188-116">If you already have one, great!</span></span> <span data-ttu-id="e5188-117">Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="e5188-117">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="e5188-118">Исходный адрес электронной почты в Службе Office 365 под управлением 21Vianet включает partner.onmschina.cn, например tom@fourthcoffee.partner.onmschina.cn.</span><span class="sxs-lookup"><span data-stu-id="e5188-118">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="e5188-119">Вы можете изменить его на более дружелюбный адрес, например tom@fourthcoffee.cn.</span><span class="sxs-lookup"><span data-stu-id="e5188-119">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="e5188-120">Вам потребуется собственное доменное имя, например fourthcoffee.cn.</span><span class="sxs-lookup"><span data-stu-id="e5188-120">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="e5188-121">Если оно у вас уже есть, отлично!</span><span class="sxs-lookup"><span data-stu-id="e5188-121">If you already have one, great!</span></span> <span data-ttu-id="e5188-122">Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="e5188-122">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="e5188-123">При изменении электронной почты домена на Microsoft 365 путем обновления записи MX домена во время настройки все сообщения, от отправленные в этот домен, будут отправляться в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5188-123">When you change your domain's email to come to Microsoft 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="e5188-124">Перед изменением записи MX убедитесь, что вы добавили пользователей и создали почтовые ящики в Microsoft 365 для всех, у кого есть электронная почта в вашем домене.</span><span class="sxs-lookup"><span data-stu-id="e5188-124">Make sure you've added users and created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span> <span data-ttu-id="e5188-125">Не хотите перемещать электронную почту для всех в вашем домене в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e5188-125">Don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="e5188-126">Вы можете предпринять действия для [пилотного проекта Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)с несколькими адресами электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e5188-126">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="e5188-127">Изменение адреса электронной почты для использования настраиваемого домена с помощью Центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5188-127">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="e5188-128">Для выполнения этих действий необходимо иметь учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e5188-128">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e5188-129">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="e5188-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="e5188-130">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="e5188-130">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e5188-131">Перейдите в Центр <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>администрирования по</span><span class="sxs-lookup"><span data-stu-id="e5188-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="e5188-132">Перейдите на **страницу "Домены**  >  **установки".**</span><span class="sxs-lookup"><span data-stu-id="e5188-132">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="e5188-133">На странице **Домены** выберите **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="e5188-133">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="e5188-134">Следуйте указаниям, чтобы подтвердить право собственности на домен и изменить адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e5188-134">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="e5188-135">Вы получите руководство по правильной настройкам домена в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5188-135">You'll be guided to get everything set up correctly with your domain in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="e5188-136">Если вы не используете лицензию Exchange, вы не можете использовать домен для отправки и получения сообщений электронной почты от клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5188-136">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Microsoft 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="e5188-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e5188-137">Related articles</span></span>

[<span data-ttu-id="e5188-138">Покупка пользовательского домена с помощью Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5188-138">Buy a custom domain using Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
