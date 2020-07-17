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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Узнайте, как можно сбросить пароли с помощью средства самостоятельного сброса пароля.
ms.openlocfilehash: 288613023ee61626bf12f7090ad0ff73139ef06d
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780593"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="28802-103">Предоставление пользователям прав на самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="28802-103">Let users reset their own passwords</span></span>

<span data-ttu-id="28802-104">Голова идет кругом от количества запросов на сброс пароля, поступающих от пользователей?</span><span class="sxs-lookup"><span data-stu-id="28802-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="28802-105">Как администратор Microsoft 365, вы можете позволить пользователям использовать [средство самостоятельного сброса пароля](https://go.microsoft.com/fwlink/p/?LinkId=522677) , чтобы не переустанавливать пароли.</span><span class="sxs-lookup"><span data-stu-id="28802-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="28802-106">Работы станет гораздо меньше!</span><span class="sxs-lookup"><span data-stu-id="28802-106">Less work for you!</span></span> 
  
<span data-ttu-id="28802-107">Обратите внимание на некоторые важные моменты.</span><span class="sxs-lookup"><span data-stu-id="28802-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="28802-108">Вы получаете возможность самостоятельного сброса паролей для облачных пользователей, которые **бесплатно** посвящены любому плану Microsoft 365 для бизнеса, образованию или некоммерческой плате.</span><span class="sxs-lookup"><span data-stu-id="28802-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="28802-109">Она не работает с пробной версией Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28802-109">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="28802-p103">Эта функция использует платформу Azure. Она предоставляется в Azure автоматически и **бесплатно** при выполнении описанной ниже процедуры. Если вы не используете другие функции Azure, плата за включение функции самостоятельного сброса пароля не взимается.</span><span class="sxs-lookup"><span data-stu-id="28802-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="28802-113">**Если вы используете локальную службу Active Directory**, приведенные выше две точки не применяются.</span><span class="sxs-lookup"><span data-stu-id="28802-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="28802-114">Это можно сделать, но **для этого требуется платная подписка на Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="28802-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="28802-115">Посмотрите короткое видео о том, как позволить пользователям сбрасывать собственные пароли.</span><span class="sxs-lookup"><span data-stu-id="28802-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="28802-116">Если этот видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="28802-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="28802-117">Разрешить пользователям сбрасывать собственные пароли</span><span class="sxs-lookup"><span data-stu-id="28802-117">Let people reset their own passwords</span></span>

<span data-ttu-id="28802-118">Эта процедура позволяет включить функцию самостоятельного сброса пароля для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="28802-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="28802-119">В <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центре администрирования</a>перейдите на страницу Параметры организации **параметров** > **Org settings** .</span><span class="sxs-lookup"><span data-stu-id="28802-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="28802-120">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центре администрирования</a>перейдите на страницу **Параметры** \> \*\* &amp; конфиденциальности безопасности\*\* .</span><span class="sxs-lookup"><span data-stu-id="28802-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="28802-121">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центре администрирования</a>перейдите на **Settings** \> страницу **Параметры** \> \*\* &amp; конфиденциальности безопасности параметров безопасности\*\* .</span><span class="sxs-lookup"><span data-stu-id="28802-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="28802-122">В верхней части страницы " **Параметры организации** " выберите вкладку **Безопасность & конфиденциальности** .</span><span class="sxs-lookup"><span data-stu-id="28802-122">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="28802-123">Выберите команду **самостоятельный сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="28802-123">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="28802-124">В разделе **Сброс пароля самостоятельно**выберите перейдите на **портал Azure, чтобы включить функцию самостоятельного сброса пароля**.</span><span class="sxs-lookup"><span data-stu-id="28802-124">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="28802-125">В области навигации слева выберите пункт **Пользователи**, а затем на странице **Пользователи | Все пользователи** » выберите **Сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="28802-125">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="28802-126">На странице " **Свойства** " выберите **все** , чтобы включить его для всех пользователей в вашей организации, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="28802-126">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="28802-127">Когда пользователи входят в систему, им будет предложено ввести дополнительные контактные данные, которые помогут им сбросить пароль в будущем.</span><span class="sxs-lookup"><span data-stu-id="28802-127">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="28802-128">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="28802-128">Related articles</span></span>

[<span data-ttu-id="28802-129">Установка политики срока действия паролей в организации</span><span class="sxs-lookup"><span data-stu-id="28802-129">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="28802-130">Установка бессрочных пользовательских паролей</span><span class="sxs-lookup"><span data-stu-id="28802-130">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="28802-131">учебные видео по Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="28802-131">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
