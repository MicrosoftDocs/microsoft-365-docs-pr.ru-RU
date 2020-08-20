---
title: Изменение адреса электронной почты с использованием пользовательского домена
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
description: 'Измените исходный адрес электронной почты на понятный адрес, например tom@fourthcoffee.com smtp. Для этого необходимо купить доменное имя и добавить его в Microsoft 365. '
ms.openlocfilehash: dc6d418961fe29a363aa6a787d8c0bb2d11d7e97
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814484"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="33c9b-104">Изменение адреса электронной почты с использованием пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="33c9b-104">Change your email address to use your custom domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="33c9b-105">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="33c9b-105">The admin center is changing.</span></span> <span data-ttu-id="33c9b-106">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="33c9b-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="33c9b-107">Если вы не нашли то, что вы ищете, см. раздел **[Вопросы и ответы по доменам](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="33c9b-107">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="33c9b-108">Ваш исходный адрес электронной почты в Microsoft 365 включает в себя расширение onmicrosoft.com,tom@fourthcoffee.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="33c9b-108">Your initial email address in Microsoft 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com.</span></span> <span data-ttu-id="33c9b-109">Вы можете изменить его на более понятный адрес, например ivan@fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="33c9b-109">You can change it to a friendlier address like tom@fourthcoffee.com.</span></span> <span data-ttu-id="33c9b-110">Сначала вам потребуется получить собственное доменное имя, например fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="33c9b-110">You'll need your own domain name, like fourthcoffee.com first.</span></span> <span data-ttu-id="33c9b-111">Если оно у вас уже есть, отлично!</span><span class="sxs-lookup"><span data-stu-id="33c9b-111">If you already have one, great!</span></span> <span data-ttu-id="33c9b-112">Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="33c9b-112">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="33c9b-113">Исходный адрес электронной почты в Office 365 Germany включает расширение .onmicrosoft.de, например tom@fourthcoffee.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="33c9b-113">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="33c9b-114">Вы можете изменить его на более понятный адрес, например tom@fourthcoffee.de.</span><span class="sxs-lookup"><span data-stu-id="33c9b-114">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="33c9b-115">Сначала вам понадобится ваше доменное имя, напримерfourthcoffee.de.</span><span class="sxs-lookup"><span data-stu-id="33c9b-115">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="33c9b-116">Если оно у вас уже есть, отлично!</span><span class="sxs-lookup"><span data-stu-id="33c9b-116">If you already have one, great!</span></span> <span data-ttu-id="33c9b-117">Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="33c9b-117">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="33c9b-118">Ваш исходный адрес электронной почты в службе Office 365, предоставляемой 21Vianet, включает partner.onmschina.cn, например tom@fourthcoffee.partner.onmschina.cn.</span><span class="sxs-lookup"><span data-stu-id="33c9b-118">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="33c9b-119">Вы можете изменить его на более понятный адрес, например tom@fourthcoffee.cn.</span><span class="sxs-lookup"><span data-stu-id="33c9b-119">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="33c9b-120">Для начала вам понадобится самостоятельное доменное имя, fourthcoffee.cn.</span><span class="sxs-lookup"><span data-stu-id="33c9b-120">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="33c9b-121">Если оно у вас уже есть, отлично!</span><span class="sxs-lookup"><span data-stu-id="33c9b-121">If you already have one, great!</span></span> <span data-ttu-id="33c9b-122">Если нет, вы можете узнать, как [приобрести имя у регистратора доменных имен](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="33c9b-122">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="33c9b-123">Когда вы меняете электронную почту домена для Microsoft 365, обративая запись MX домена во время установки, все сообщения, отправляемые в этот домен, будут поступать в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33c9b-123">When you change your domain's email to come to Microsoft 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="33c9b-124">Убедитесь, что вы добавили пользователей и создали почтовые ящики в Microsoft 365 для всех пользователей, у которых есть электронная почта в вашем домене, ПРЕЖДЕ Чем изменить запись MX.</span><span class="sxs-lookup"><span data-stu-id="33c9b-124">Make sure you've added users and created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span> <span data-ttu-id="33c9b-125">Не планируете перемещать в Microsoft 365 электронную почту для всех пользователей вашего домена?</span><span class="sxs-lookup"><span data-stu-id="33c9b-125">Don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="33c9b-126">Чтобы выполнить пилотное развертывание [Microsoft 365 с несколькими адресами электронной почты, можно предпринять меры.](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="33c9b-126">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="33c9b-127">Изменение адреса электронной почты на использование личного домена с помощью Центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33c9b-127">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="33c9b-128">Для выполнения этих действий требуются учетные записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="33c9b-128">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="33c9b-129">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="33c9b-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="33c9b-130">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="33c9b-130">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="33c9b-131">Перейдите в Центр <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>администрирования в любой полю.</span><span class="sxs-lookup"><span data-stu-id="33c9b-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="33c9b-132">Перейдите на страницу **"Настройка**  >  **доменов".**</span><span class="sxs-lookup"><span data-stu-id="33c9b-132">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="33c9b-133">На странице **Домены** выберите **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="33c9b-133">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="33c9b-134">Следуйте указаниям, чтобы подтвердить право собственности на домен и изменить адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="33c9b-134">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="33c9b-135">Пошаговые инструкции помогут вам правильно настроить домен в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33c9b-135">You'll be guided to get everything set up correctly with your domain in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="33c9b-136">Если вы не используете лицензию Exchange, вы не сможете использовать домен для отправки и получения сообщений электронной почты из клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33c9b-136">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Microsoft 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="33c9b-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="33c9b-137">Related articles</span></span>

[<span data-ttu-id="33c9b-138">Приобретение личного домена с помощью Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33c9b-138">Buy a custom domain using Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
