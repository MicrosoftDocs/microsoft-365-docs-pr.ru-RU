---
title: Предоставление пользователям прав на самостоятельный сброс пароля
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
ms.openlocfilehash: 7ecadaa42610e0b77dc1727c11140080bd7b1779
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646683"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="61aac-103">Предоставление пользователям прав на самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="61aac-103">Let users reset their own passwords</span></span>

<span data-ttu-id="61aac-104">Как администратор Microsoft 365, вы можете позволить пользователям использовать [средство самостоятельного сброса пароля](https://go.microsoft.com/fwlink/p/?LinkId=522677) , чтобы не переустанавливать пароли.</span><span class="sxs-lookup"><span data-stu-id="61aac-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="61aac-105">Работы станет гораздо меньше!</span><span class="sxs-lookup"><span data-stu-id="61aac-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="61aac-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="61aac-106">Before you begin</span></span>
  
- <span data-ttu-id="61aac-107">Вы получаете возможность самостоятельного сброса паролей для облачных пользователей, которые **бесплатно** посвящены любому плану Microsoft 365 для бизнеса, образованию или некоммерческой плате.</span><span class="sxs-lookup"><span data-stu-id="61aac-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="61aac-108">Она не работает с пробной версией Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61aac-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="61aac-p103">Эта функция использует платформу Azure. Она предоставляется в Azure автоматически и **бесплатно** при выполнении описанной ниже процедуры. Если вы не используете другие функции Azure, плата за включение функции самостоятельного сброса пароля не взимается.</span><span class="sxs-lookup"><span data-stu-id="61aac-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="61aac-112">**Если вы используете локальную службу Active Directory**, приведенные выше две точки не применяются.</span><span class="sxs-lookup"><span data-stu-id="61aac-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="61aac-113">Это можно сделать, но **для этого требуется платная подписка на Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="61aac-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="61aac-114">Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="61aac-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="61aac-115">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61aac-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="61aac-116">Что такое учетная запись администратора?</span><span class="sxs-lookup"><span data-stu-id="61aac-116">What's an admin account?</span></span>](../admin-overview/admin-overview.md)

<span data-ttu-id="61aac-117">Для выполнения этих действий необходимо быть [глобальным администратором или администратором паролей](about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="61aac-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="61aac-118">Контрольное значение: разрешить пользователям сбрасывать собственные пароли</span><span class="sxs-lookup"><span data-stu-id="61aac-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="61aac-119">Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="61aac-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="61aac-120">Действия: Позвольте пользователям сбросить собственные пароли</span><span class="sxs-lookup"><span data-stu-id="61aac-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="61aac-121">Эта процедура позволяет включить функцию самостоятельного сброса пароля для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="61aac-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="61aac-122">В <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">центре администрирования</a>перейдите на страницу Параметры организации **параметров** > **Org settings** .</span><span class="sxs-lookup"><span data-stu-id="61aac-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="61aac-123">В <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">центре администрирования</a>перейдите на страницу **Параметры** \> \*\* &amp; конфиденциальности безопасности\*\* .</span><span class="sxs-lookup"><span data-stu-id="61aac-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="61aac-124">В <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">центре администрирования</a>перейдите на **Settings** \> страницу **Параметры** \> \*\* &amp; конфиденциальности безопасности параметров безопасности\*\* .</span><span class="sxs-lookup"><span data-stu-id="61aac-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="61aac-125">В верхней части страницы " **Параметры организации** " выберите вкладку **Безопасность & конфиденциальности** .</span><span class="sxs-lookup"><span data-stu-id="61aac-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="61aac-126">Выберите команду **самостоятельный сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="61aac-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="61aac-127">В разделе **Сброс пароля самостоятельно**выберите перейдите на **портал Azure, чтобы включить функцию самостоятельного сброса пароля**.</span><span class="sxs-lookup"><span data-stu-id="61aac-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="61aac-128">В области навигации слева выберите пункт **Пользователи**, а затем на странице **Пользователи | Все пользователи** » выберите **Сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="61aac-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="61aac-129">На странице " **Свойства** " выберите **все** , чтобы включить его для всех пользователей в вашей организации, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="61aac-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="61aac-130">Когда пользователи входят в систему, им будет предложено ввести дополнительные контактные данные, которые помогут им сбросить пароль в будущем.</span><span class="sxs-lookup"><span data-stu-id="61aac-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="61aac-131">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="61aac-131">Related content</span></span>

[<span data-ttu-id="61aac-132">Установка политики срока действия паролей в организации</span><span class="sxs-lookup"><span data-stu-id="61aac-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="61aac-133">Установка бессрочных пользовательских паролей</span><span class="sxs-lookup"><span data-stu-id="61aac-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="61aac-134">учебные видео по Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="61aac-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
