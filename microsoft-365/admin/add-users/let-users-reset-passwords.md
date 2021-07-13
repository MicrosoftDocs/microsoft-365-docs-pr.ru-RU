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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Узнайте, как настроить политику, позволяющую пользователям сбросить собственные пароли с помощью средства сброса паролей самообслуживки.
ms.openlocfilehash: ac6d7f16cb35cec757340a94c262c3541bea927a
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394319"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="43b89-103">Предоставление пользователям прав на самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="43b89-103">Let users reset their own passwords</span></span>

<span data-ttu-id="43b89-104">Как администратор Microsoft 365, вы можете позволить людям [](https://go.microsoft.com/fwlink/p/?LinkId=522677) использовать средство сброса паролей самообслуживки, чтобы вам не нужно было сбрасывать пароли для них.</span><span class="sxs-lookup"><span data-stu-id="43b89-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="43b89-105">Работы станет гораздо меньше!</span><span class="sxs-lookup"><span data-stu-id="43b89-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="43b89-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="43b89-106">Before you begin</span></span>
  
- <span data-ttu-id="43b89-107">Сброс пароля самообслуживаемых для пользователей облаков будет бесплатным с Microsoft 365 бизнеса, образования или некоммерческой платной программы. </span><span class="sxs-lookup"><span data-stu-id="43b89-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="43b89-108">Это не работает с Microsoft 365 пробной.</span><span class="sxs-lookup"><span data-stu-id="43b89-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="43b89-p103">Эта функция использует платформу Azure. Она предоставляется в Azure автоматически и **бесплатно** при выполнении описанной ниже процедуры. Если вы не используете другие функции Azure, плата за включение функции самостоятельного сброса пароля не взимается.</span><span class="sxs-lookup"><span data-stu-id="43b89-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="43b89-112">**Если вы используете локальное Active Directory,** эти два пункта не применяются.</span><span class="sxs-lookup"><span data-stu-id="43b89-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="43b89-113">Скорее, вы можете настроить это, но для этого требуется **платная** подписка на Azure AD Premium .</span><span class="sxs-lookup"><span data-stu-id="43b89-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="43b89-114">Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="43b89-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="43b89-115">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43b89-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="43b89-116">Что такое учетная запись администратора?</span><span class="sxs-lookup"><span data-stu-id="43b89-116">What's an admin account?</span></span>](../../business-video/admin-center-overview.md)

<span data-ttu-id="43b89-117">Для выполнения этих [действий](about-admin-roles.md) необходимо быть глобальным администратором или администратором паролей.</span><span class="sxs-lookup"><span data-stu-id="43b89-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="43b89-118">Watch: Let users reset their own passwords</span><span class="sxs-lookup"><span data-stu-id="43b89-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="43b89-119">Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="43b89-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="43b89-120">Действия. Пусть люди сбрасывают собственные пароли</span><span class="sxs-lookup"><span data-stu-id="43b89-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="43b89-121">Эта процедура позволяет включить функцию самостоятельного сброса пароля для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="43b89-121">These steps turn on self-service password reset for everyone in your business.</span></span>

1. <span data-ttu-id="43b89-122">В центре <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">администрирования</a>перейдите на страницу **параметров Параметры**  >  **Org.**</span><span class="sxs-lookup"><span data-stu-id="43b89-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

2. <span data-ttu-id="43b89-123">В верхней части страницы **параметров Org** выберите вкладку **Конфиденциальность & безопасности.**</span><span class="sxs-lookup"><span data-stu-id="43b89-123">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="43b89-124">Выберите **сброс пароля самообслуживной службы.**</span><span class="sxs-lookup"><span data-stu-id="43b89-124">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="43b89-125">При **сбросе пароля самообслуживной** службы выберите Перейдите на портал Azure, чтобы включить сброс **пароля самообслуживки.**</span><span class="sxs-lookup"><span data-stu-id="43b89-125">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="43b89-126">В левой области навигации выберите **Пользователи,** а затем на **| Все пользователи страницы,** выберите **сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="43b89-126">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="43b89-127">На странице **Свойства выберите** **Все,** чтобы включить его для всех в вашем бизнесе, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="43b89-127">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="43b89-128">Когда пользователи войдут, им будет предложено ввести дополнительные контактные данные, которые помогут им сбросить пароль в будущем.</span><span class="sxs-lookup"><span data-stu-id="43b89-128">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="43b89-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="43b89-129">Related content</span></span>

<span data-ttu-id="43b89-130">[Установите политику истечения пароля для организации](../manage/set-password-expiration-policy.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="43b89-130">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>\
<span data-ttu-id="43b89-131">[Установка бессрочных пользовательских паролей](set-password-to-never-expire.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="43b89-131">[Set an individual user's password to never expire](set-password-to-never-expire.md) (article)</span></span>\
<span data-ttu-id="43b89-132">[Microsoft 365 бизнес-обучение](../../business-video/index.yml) (страница ссылки)</span><span class="sxs-lookup"><span data-stu-id="43b89-132">[Microsoft 365 Business training videos](../../business-video/index.yml) (link page)</span></span>
