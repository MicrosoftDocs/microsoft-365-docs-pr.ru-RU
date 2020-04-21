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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: Сведения о том, как заблокировать доступ к Microsoft 365, когда сотрудник покидает организацию.
ms.openlocfilehash: 9383c970ea1c17d9116299d5788c8faf0ed0659f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627936"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="e6a9d-103">Сравнение способов блокировки доступа</span><span class="sxs-lookup"><span data-stu-id="e6a9d-103">Compare ways to block access</span></span>

<span data-ttu-id="e6a9d-104">Когда сотрудник покидает вашу организацию, необходимо заблокировать доступ к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365.</span></span> <span data-ttu-id="e6a9d-105">Это можно сделать несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-105">Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="e6a9d-106">**Способ блокировки доступа**</span><span class="sxs-lookup"><span data-stu-id="e6a9d-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="e6a9d-107">**Определение**</span><span class="sxs-lookup"><span data-stu-id="e6a9d-107">**Definition**</span></span> <br/> |<span data-ttu-id="e6a9d-108">**Рекомендации**</span><span class="sxs-lookup"><span data-stu-id="e6a9d-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="e6a9d-109">Блокировка входа</span><span class="sxs-lookup"><span data-stu-id="e6a9d-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="e6a9d-110">Один из способов заблокировать доступ пользователей к Microsoft 365 — изменить свое состояние входа в систему, чтобы оно было **заблокировано**.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-110">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="e6a9d-111">Это предотвращает вход в Microsoft 365 со своих компьютеров и мобильных устройств, несмотря на то, что они по-прежнему могут просматривать ранее скачанные или синхронизированные сообщения электронной почты и документы.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-111">This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="e6a9d-112">Если вы используете службу Blackberry Enterprise, вы также можете отключить доступ в ней.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="e6a9d-113">Используйте этот способ, когда сотрудник планирует покинуть организацию или уйти в долгосрочный отпуск.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="e6a9d-114">Сбросить пароль пользователя</span><span class="sxs-lookup"><span data-stu-id="e6a9d-114">Reset user password</span></span>  <br/> |<span data-ttu-id="e6a9d-115">Еще один способ предотвратить доступ пользователя к Microsoft 365 — сбросить пароль.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-115">Another way to prevent a user from accessing Microsoft 365 is to reset their password.</span></span> <span data-ttu-id="e6a9d-116">Это не позволит ему входить в Office 365, используя свою учетную запись, хотя он по-прежнему сможет просматривать ранее скачанные или синхронизированные сообщения электронной почты и документы.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="e6a9d-117">Вы сможете войти в учетную запись пользователя и задать пароль, удобный вам.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="e6a9d-118">Используйте этот способ, когда сотрудник внезапно покидает организацию и вы беспокоитесь о безопасности бизнес-данных.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="e6a9d-119">Удаление всех назначенных лицензий</span><span class="sxs-lookup"><span data-stu-id="e6a9d-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="e6a9d-120">Кроме того, можно удалить все лицензии на Microsoft 365, назначенные пользователю.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="e6a9d-121">Это предотвратит использование приложений и служб, таких как набор Office, приложений Office для Интернета, Yammer и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="e6a9d-122">Пользователь по-прежнему сможет входить в свою учетную запись, но не использовать эти службы.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="e6a9d-123">Используйте, когда вам кажется, что этому пользователю больше не требуется доступ к определенным функциям в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="e6a9d-124">**Важно!** При удалении лицензии почтовый ящик пользователя будет удален в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="e6a9d-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="e6a9d-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e6a9d-125">Related articles</span></span>

[<span data-ttu-id="e6a9d-126">Переносе пользователя от Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6a9d-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="e6a9d-127">Сброс пароля пользователя в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6a9d-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="e6a9d-128">Назначение лицензий пользователям в Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e6a9d-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="e6a9d-129">Удаление лицензий пользователей в Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e6a9d-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

