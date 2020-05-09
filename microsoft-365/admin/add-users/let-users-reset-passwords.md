---
title: Предоставление пользователям прав на самостоятельный сброс пароля
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Узнайте, как можно сбросить пароли с помощью средства самостоятельного сброса пароля.
ms.openlocfilehash: 01099f6f678bbaa3b163ac59e0417614352e0e97
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173534"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="d9038-103">Предоставление пользователям прав на самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="d9038-103">Let users reset their own passwords</span></span>

<span data-ttu-id="d9038-104">Голова идет кругом от количества запросов на сброс пароля, поступающих от пользователей?</span><span class="sxs-lookup"><span data-stu-id="d9038-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="d9038-105">Как администратор Microsoft 365, вы можете позволить пользователям использовать [средство самостоятельного сброса пароля](https://go.microsoft.com/fwlink/p/?LinkId=522677) , чтобы не переустанавливать пароли.</span><span class="sxs-lookup"><span data-stu-id="d9038-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="d9038-106">Работы станет гораздо меньше!</span><span class="sxs-lookup"><span data-stu-id="d9038-106">Less work for you!</span></span> 
  
<span data-ttu-id="d9038-107">Обратите внимание на некоторые важные моменты.</span><span class="sxs-lookup"><span data-stu-id="d9038-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="d9038-108">Вы получаете возможность самостоятельного сброса паролей для облачных пользователей, которые **бесплатно** посвящены любому плану Microsoft 365 для бизнеса, образованию или некоммерческой плате.</span><span class="sxs-lookup"><span data-stu-id="d9038-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="d9038-109">Она не работает с пробной версией Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9038-109">It doesn't work with Microsoft 365 trial.</span></span> 
    
- <span data-ttu-id="d9038-p103">Эта функция использует платформу Azure. Она предоставляется в Azure автоматически и **бесплатно** при выполнении описанной ниже процедуры. Если вы не используете другие функции Azure, плата за включение функции самостоятельного сброса пароля не взимается.</span><span class="sxs-lookup"><span data-stu-id="d9038-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="d9038-113">**Если вы используете локальную службу Active Directory**, приведенные выше две точки не применяются.</span><span class="sxs-lookup"><span data-stu-id="d9038-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="d9038-114">Это можно сделать, но **для этого требуется платная подписка на Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="d9038-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="d9038-115">Посмотрите короткое видео о том, как позволить пользователям сбрасывать собственные пароли.</span><span class="sxs-lookup"><span data-stu-id="d9038-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="d9038-116">Если этот видеоролик помог вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="d9038-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="d9038-117">Разрешить пользователям сбрасывать собственные пароли</span><span class="sxs-lookup"><span data-stu-id="d9038-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="d9038-118">Эта процедура позволяет включить функцию самостоятельного сброса пароля для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="d9038-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1. <span data-ttu-id="d9038-119">В центре администрирования откройте страницу " <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Параметры</a> **настройки** \> ".</span><span class="sxs-lookup"><span data-stu-id="d9038-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d9038-120">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центре администрирования</a>перейдите на страницу **Параметры** \> \*\*конфиденциальности безопасности &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="d9038-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d9038-121">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центре администрирования</a>перейдите на **Settings** \>страницу **Параметры** \> \*\*конфиденциальности безопасности параметров безопасности &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="d9038-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="d9038-122">В верхней части страницы Параметры выберите **безопасность & конфиденциальность**.</span><span class="sxs-lookup"><span data-stu-id="d9038-122">At the top of the Settings page select **Security & Privacy**.</span></span>
  
3. <span data-ttu-id="d9038-123">Выберите **Сброс пароля самообслуживания**.</span><span class="sxs-lookup"><span data-stu-id="d9038-123">Select **Self Service Password Reset**.</span></span>
  
4. <span data-ttu-id="d9038-124">На странице "Свойства" выберите **все** , чтобы включить его для всех пользователей в вашей организации, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d9038-124">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="d9038-125">Когда пользователи входят в систему, им будет предложено ввести дополнительные контактные данные, которые помогут им сбросить пароль в будущем.</span><span class="sxs-lookup"><span data-stu-id="d9038-125">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d9038-126">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="d9038-126">Related articles</span></span>

[<span data-ttu-id="d9038-127">Установка политики срока действия паролей в организации</span><span class="sxs-lookup"><span data-stu-id="d9038-127">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="d9038-128">Установка бессрочных пользовательских паролей</span><span class="sxs-lookup"><span data-stu-id="d9038-128">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="d9038-129">учебные видео по Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="d9038-129">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
