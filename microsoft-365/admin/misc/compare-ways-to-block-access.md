---
title: Сравнение способов блокировки доступа
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: Узнайте, как заблокировать доступ к Microsoft 365, когда сотрудник покидает организацию.
ms.openlocfilehash: b913655065d4c57322aee6dc04e53f7a35cf5760
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399438"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="c38bb-103">Сравнение способов блокировки доступа</span><span class="sxs-lookup"><span data-stu-id="c38bb-103">Compare ways to block access</span></span>

<span data-ttu-id="c38bb-104">Если сотрудник покидает организацию в хороших или плохих условиях, необходимо заблокировать доступ к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c38bb-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365.</span></span> <span data-ttu-id="c38bb-105">Это можно сделать несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="c38bb-105">Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="c38bb-106">**Способ блокировки доступа**</span><span class="sxs-lookup"><span data-stu-id="c38bb-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="c38bb-107">**Определение**</span><span class="sxs-lookup"><span data-stu-id="c38bb-107">**Definition**</span></span> <br/> |<span data-ttu-id="c38bb-108">**Рекомендации**</span><span class="sxs-lookup"><span data-stu-id="c38bb-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="c38bb-109">Блокировка входа</span><span class="sxs-lookup"><span data-stu-id="c38bb-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="c38bb-110">Один из способов заблокировать доступ к Microsoft 365 пользователя — изменить его состояние регистрации на **заблокированный** вход.</span><span class="sxs-lookup"><span data-stu-id="c38bb-110">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="c38bb-111">Это не позволяет им подписываться Microsoft 365 с компьютеров и мобильных устройств, хотя они по-прежнему могут просматривать ранее загруженную или синхронизированную электронную почту и документы.</span><span class="sxs-lookup"><span data-stu-id="c38bb-111">This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="c38bb-112">Если вы используете службу Blackberry Enterprise, вы также можете отключить доступ в ней.</span><span class="sxs-lookup"><span data-stu-id="c38bb-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="c38bb-113">Используйте этот способ, когда сотрудник планирует покинуть организацию или уйти в долгосрочный отпуск.</span><span class="sxs-lookup"><span data-stu-id="c38bb-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="c38bb-114">Сбросить пароль пользователя</span><span class="sxs-lookup"><span data-stu-id="c38bb-114">Reset user password</span></span>  <br/> |<span data-ttu-id="c38bb-115">Еще один способ предотвратить доступ пользователя к Microsoft 365 — сбросить пароль.</span><span class="sxs-lookup"><span data-stu-id="c38bb-115">Another way to prevent a user from accessing Microsoft 365 is to reset their password.</span></span> <span data-ttu-id="c38bb-116">Это не позволит ему входить в Office 365, используя свою учетную запись, хотя он по-прежнему сможет просматривать ранее скачанные или синхронизированные сообщения электронной почты и документы.</span><span class="sxs-lookup"><span data-stu-id="c38bb-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="c38bb-117">Вы сможете войти в учетную запись пользователя и задать пароль, удобный вам.</span><span class="sxs-lookup"><span data-stu-id="c38bb-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="c38bb-118">Используйте этот способ, когда сотрудник внезапно покидает организацию и вы беспокоитесь о безопасности бизнес-данных.</span><span class="sxs-lookup"><span data-stu-id="c38bb-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="c38bb-119">Удаление всех назначенных лицензий</span><span class="sxs-lookup"><span data-stu-id="c38bb-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="c38bb-120">Другим вариантом является удаление Microsoft 365 лицензий, присвоенных пользователю.</span><span class="sxs-lookup"><span data-stu-id="c38bb-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="c38bb-121">Это не позволяет им использовать приложения и службы, такие как набор Office, Office приложений для Веб,Yammer и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c38bb-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="c38bb-122">Пользователь по-прежнему сможет входить в свою учетную запись, но не использовать эти службы.</span><span class="sxs-lookup"><span data-stu-id="c38bb-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="c38bb-123">Используйте, когда вы считаете, что этому пользователю больше не требуется доступ к определенным функциям в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c38bb-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="c38bb-124">**Важно:** При удалении лицензии почтовый ящик пользователя будет удален в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="c38bb-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="c38bb-125">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="c38bb-125">Related articles</span></span>

[<span data-ttu-id="c38bb-126">Отключение пользователя из Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c38bb-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="c38bb-127">Сброс пароля пользователя в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c38bb-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="c38bb-128">Назначение лицензий пользователям в Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c38bb-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="c38bb-129">Удаление лицензий у пользователей в Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c38bb-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

