---
title: Предоставление пользователям прав на самостоятельный сброс пароля
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Узнайте, как сбросить пароли с помощью средства самостоятельного сброса паролей.
ms.openlocfilehash: c777b9d840e0e9e467c1283fff94eca9a061ee73
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925558"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="f7c53-103">Предоставление пользователям прав на самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="f7c53-103">Let users reset their own passwords</span></span>

<span data-ttu-id="f7c53-104">Как администратор Microsoft 365 вы можете [](https://go.microsoft.com/fwlink/p/?LinkId=522677) позволить людям использовать средство самостоятельного сброса паролей, чтобы вам не нужно было сбрасывать пароли для них.</span><span class="sxs-lookup"><span data-stu-id="f7c53-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="f7c53-105">Работы станет гораздо меньше!</span><span class="sxs-lookup"><span data-stu-id="f7c53-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="f7c53-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="f7c53-106">Before you begin</span></span>
  
- <span data-ttu-id="f7c53-107">Вы получаете самостоятельный сброс паролей для облачных пользователей бесплатно с помощью любого платного плана Microsoft 365 для бизнеса, образования или некоммерческих организаций. </span><span class="sxs-lookup"><span data-stu-id="f7c53-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="f7c53-108">Пробная версия Microsoft 365 не работает.</span><span class="sxs-lookup"><span data-stu-id="f7c53-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="f7c53-p103">Эта функция использует платформу Azure. Она предоставляется в Azure автоматически и **бесплатно** при выполнении описанной ниже процедуры. Если вы не используете другие функции Azure, плата за включение функции самостоятельного сброса пароля не взимается.</span><span class="sxs-lookup"><span data-stu-id="f7c53-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="f7c53-112">**Если вы используете локальное решение Active Directory,** эти два пункта не применяются.</span><span class="sxs-lookup"><span data-stu-id="f7c53-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="f7c53-113">Это можно настроить, но для этого требуется платная подписка **на Azure AD Premium.**</span><span class="sxs-lookup"><span data-stu-id="f7c53-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="f7c53-114">Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="f7c53-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="f7c53-115">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f7c53-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="f7c53-116">Что такое учетная запись администратора?</span><span class="sxs-lookup"><span data-stu-id="f7c53-116">What's an admin account?</span></span>](../admin-overview/admin-overview.md)

<span data-ttu-id="f7c53-117">Для выполнения этих действий [необходимо быть](about-admin-roles.md) глобальным администратором или администратором паролей.</span><span class="sxs-lookup"><span data-stu-id="f7c53-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="f7c53-118">Watch: Let users reset their own passwords</span><span class="sxs-lookup"><span data-stu-id="f7c53-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="f7c53-119">Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="f7c53-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="f7c53-120">Действия: позволить людям сбросить свои пароли</span><span class="sxs-lookup"><span data-stu-id="f7c53-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="f7c53-121">Эта процедура позволяет включить функцию самостоятельного сброса пароля для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="f7c53-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="f7c53-122">В Центре <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">администрирования</a>перейдите на **страницу** параметров организации > **параметров.**</span><span class="sxs-lookup"><span data-stu-id="f7c53-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f7c53-123">В Центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования перейдите</a>на страницу конфиденциальности **"Безопасность** \> **&amp; параметров".**</span><span class="sxs-lookup"><span data-stu-id="f7c53-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f7c53-124">В Центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования перейдите</a>на **страницу** конфиденциальности \> **"Параметры** \> **&amp;** безопасности".</span><span class="sxs-lookup"><span data-stu-id="f7c53-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="f7c53-125">В верхней части **страницы** параметров организации выберите вкладку "Безопасность & **конфиденциальности".**</span><span class="sxs-lookup"><span data-stu-id="f7c53-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="f7c53-126">Выберите **самостоятельный сброс пароля.**</span><span class="sxs-lookup"><span data-stu-id="f7c53-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="f7c53-127">В **области самостоятельного сброса пароля** выберите "Перейти на портал **Azure",** чтобы включить самостоятельный сброс пароля.</span><span class="sxs-lookup"><span data-stu-id="f7c53-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="f7c53-128">В левой области навигации выберите "Пользователи", а затем на | **Страница "Все пользователи"** выберите **"Сброс пароля".**</span><span class="sxs-lookup"><span data-stu-id="f7c53-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="f7c53-129">На странице **"Свойства"** выберите **"Все",** чтобы включить его для всех в вашей компании, а затем выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="f7c53-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="f7c53-130">При входе пользователям будет предложено ввести дополнительные контактные данные, которые помогут им сбросить пароль в будущем.</span><span class="sxs-lookup"><span data-stu-id="f7c53-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="f7c53-131">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="f7c53-131">Related content</span></span>

[<span data-ttu-id="f7c53-132">Установка политики срока действия паролей в организации</span><span class="sxs-lookup"><span data-stu-id="f7c53-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="f7c53-133">Установка бессрочных пользовательских паролей</span><span class="sxs-lookup"><span data-stu-id="f7c53-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="f7c53-134">учебные видео по Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="f7c53-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
