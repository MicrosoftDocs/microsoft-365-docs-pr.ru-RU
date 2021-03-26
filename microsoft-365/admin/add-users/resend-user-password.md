---
title: Повторная отправка пароля пользователя. Справка для администраторов
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b838071-94aa-4b8e-8d84-d17ece1ee951
description: Узнайте, как сбросить пароль и отправить сообщение электронной почты новому пользователю Microsoft 365.
ms.openlocfilehash: 2b2c8657a4bbd4745a3fee34fc259244b83640d3
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222103"
---
# <a name="resend-a-users-password---admin-help"></a><span data-ttu-id="39900-103">Повторная отправка пароля пользователя. Справка для администраторов</span><span class="sxs-lookup"><span data-stu-id="39900-103">Resend a user's password - Admin Help</span></span>

<span data-ttu-id="39900-104">В этой статье рассказывается о том, как повторно отправить сообщение уведомления новому пользователю в Office 365.</span><span class="sxs-lookup"><span data-stu-id="39900-104">This article explains how to resend the notification email to a new user in Office 365.</span></span> <span data-ttu-id="39900-105">Это может произойти при создании нового пользователя, и он не получает электронной почты с новым паролем.</span><span class="sxs-lookup"><span data-stu-id="39900-105">This can happen when you create a new user and they don't get an email with their new password.</span></span> <span data-ttu-id="39900-106">Это необходимо, сбросив пароль пользователя.</span><span class="sxs-lookup"><span data-stu-id="39900-106">You do this by resetting the user's password.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="39900-107">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="39900-107">Before you begin</span></span>

<span data-ttu-id="39900-108">Эта статья адресована тем, кто устанавливает политику срока действия паролей в компании, учебном заведении или некоммерческой организации.</span><span class="sxs-lookup"><span data-stu-id="39900-108">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="39900-109">Чтобы выполнить эти действия, вам нужно войти с помощью своей учетной записи администратора Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39900-109">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="39900-110">[Что такое учетная запись администратора?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)</span><span class="sxs-lookup"><span data-stu-id="39900-110">[What's an admin account?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).</span></span>

<span data-ttu-id="39900-111">Для выполнения этих [действий](about-admin-roles.md) необходимо быть глобальным администратором или администратором паролей.</span><span class="sxs-lookup"><span data-stu-id="39900-111">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="resend-user-password"></a><span data-ttu-id="39900-112">Повторная отправка пароля пользователя</span><span class="sxs-lookup"><span data-stu-id="39900-112">Resend user password</span></span>
  
::: moniker range="o365-worldwide"  
  
1. <span data-ttu-id="39900-113">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="39900-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="39900-114">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="39900-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="39900-115">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="39900-115">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

::: moniker-end

2. <span data-ttu-id="39900-116">На странице **Активные пользователи** выберите пользователя и выберите **пароль Reset**.</span><span class="sxs-lookup"><span data-stu-id="39900-116">On the **Active users** page, select the user and then select **Reset password**.</span></span>

3. <span data-ttu-id="39900-117">Следуйте инструкциям на странице **Сброс** пароля, чтобы автоматически создать новый пароль для пользователя или создать его для них, а затем выберите **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="39900-117">Follow the instructions on the **Reset password** page to auto-generate a new password for the user or create one for them, and then select **Reset**.</span></span>  

4. <span data-ttu-id="39900-118">Введите адрес электронной почты, который пользователь может получить для получения нового пароля, и выполните его, чтобы убедиться, что он получил его.</span><span class="sxs-lookup"><span data-stu-id="39900-118">Enter an email address the user can get to so they receive the new password, and follow up with them to make sure they got it.</span></span>

## <a name="related-content"></a><span data-ttu-id="39900-119">Связанные материалы</span><span class="sxs-lookup"><span data-stu-id="39900-119">Related content</span></span>

[<span data-ttu-id="39900-120">Предоставление пользователям прав на самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="39900-120">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="39900-121">Сброс паролей</span><span class="sxs-lookup"><span data-stu-id="39900-121">Reset passwords</span></span>](../add-users/reset-passwords.md)