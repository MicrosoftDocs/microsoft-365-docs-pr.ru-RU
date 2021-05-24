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
description: Узнайте, как настроить политику, позволяющую пользователям сбросить собственные пароли с помощью средства сброса паролей самообслуживки.
ms.openlocfilehash: 81fbe1949b8d5e4a601411703d86165f95cc7b7f
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634272"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="4a24f-103">Предоставление пользователям прав на самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="4a24f-103">Let users reset their own passwords</span></span>

<span data-ttu-id="4a24f-104">Как администратор Microsoft 365, вы можете позволить людям [](https://go.microsoft.com/fwlink/p/?LinkId=522677) использовать средство сброса паролей самообслуживки, чтобы вам не нужно было сбрасывать пароли для них.</span><span class="sxs-lookup"><span data-stu-id="4a24f-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="4a24f-105">Работы станет гораздо меньше!</span><span class="sxs-lookup"><span data-stu-id="4a24f-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="4a24f-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="4a24f-106">Before you begin</span></span>
  
- <span data-ttu-id="4a24f-107">Сброс пароля самообслуживаемых для пользователей облаков будет бесплатным с Microsoft 365 бизнеса, образования или некоммерческой платной программы. </span><span class="sxs-lookup"><span data-stu-id="4a24f-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="4a24f-108">Это не работает с Microsoft 365 пробной.</span><span class="sxs-lookup"><span data-stu-id="4a24f-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="4a24f-p103">Эта функция использует платформу Azure. Она предоставляется в Azure автоматически и **бесплатно** при выполнении описанной ниже процедуры. Если вы не используете другие функции Azure, плата за включение функции самостоятельного сброса пароля не взимается.</span><span class="sxs-lookup"><span data-stu-id="4a24f-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="4a24f-112">**Если вы используете локальное Active Directory,** эти два пункта не применяются.</span><span class="sxs-lookup"><span data-stu-id="4a24f-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="4a24f-113">Это можно настроить, но для этого требуется платная подписка на **Azure AD Premium.**</span><span class="sxs-lookup"><span data-stu-id="4a24f-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="4a24f-114">Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="4a24f-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="4a24f-115">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4a24f-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="4a24f-116">Что такое учетная запись администратора?</span><span class="sxs-lookup"><span data-stu-id="4a24f-116">What's an admin account?</span></span>](../../business-video/admin-center-overview.md)

<span data-ttu-id="4a24f-117">Для выполнения этих [действий](about-admin-roles.md) необходимо быть глобальным администратором или администратором паролей.</span><span class="sxs-lookup"><span data-stu-id="4a24f-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="4a24f-118">Watch: Let users reset their own passwords</span><span class="sxs-lookup"><span data-stu-id="4a24f-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="4a24f-119">Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="4a24f-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="4a24f-120">Действия. Пусть люди сбрасывают собственные пароли</span><span class="sxs-lookup"><span data-stu-id="4a24f-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="4a24f-121">Эта процедура позволяет включить функцию самостоятельного сброса пароля для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="4a24f-121">These steps turn on self-service password reset for everyone in your business.</span></span>

1. <span data-ttu-id="4a24f-122">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">администрирования</a>перейдите на страницу **параметров Параметры**  >  **Org.**</span><span class="sxs-lookup"><span data-stu-id="4a24f-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

2. <span data-ttu-id="4a24f-123">В верхней части страницы **параметров Org** выберите вкладку **Конфиденциальность & безопасности.**</span><span class="sxs-lookup"><span data-stu-id="4a24f-123">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="4a24f-124">Выберите **сброс пароля самообслуживной службы.**</span><span class="sxs-lookup"><span data-stu-id="4a24f-124">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="4a24f-125">При **сбросе пароля самообслуживной** службы выберите Перейдите на портал Azure, чтобы включить сброс **пароля самообслуживки.**</span><span class="sxs-lookup"><span data-stu-id="4a24f-125">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="4a24f-126">В левой области навигации выберите **Пользователи,** а затем на **| Все пользователи страницы,** выберите **сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="4a24f-126">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="4a24f-127">На странице **Свойства выберите** **Все,** чтобы включить его для всех в вашем бизнесе, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4a24f-127">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="4a24f-128">Когда пользователи войдут, им будет предложено ввести дополнительные контактные данные, которые помогут им сбросить пароль в будущем.</span><span class="sxs-lookup"><span data-stu-id="4a24f-128">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="4a24f-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="4a24f-129">Related content</span></span>

<span data-ttu-id="4a24f-130">[Установите политику истечения пароля для организации](../manage/set-password-expiration-policy.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="4a24f-130">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>\
<span data-ttu-id="4a24f-131">[Установите пароль отдельного пользователя, который никогда не истекает](set-password-to-never-expire.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="4a24f-131">[Set an individual user's password to never expire](set-password-to-never-expire.md) (article)</span></span>\
<span data-ttu-id="4a24f-132">[Microsoft 365 бизнес обучающие видео](../../business-video/index.yml) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="4a24f-132">[Microsoft 365 Business training videos](../../business-video/index.yml) (link page)</span></span>
