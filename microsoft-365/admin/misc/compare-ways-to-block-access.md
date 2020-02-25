---
title: Сравнение способов блокировки доступа к Office 365
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
description: Сведения о том, как заблокировать доступ к Office 365, когда сотрудник покидает организацию.
ms.openlocfilehash: 3aafef37a43747557ef9a3fcda8ffe0fe3713717
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257399"
---
# <a name="compare-ways-to-block-access-to-office-365"></a><span data-ttu-id="a07d1-103">Сравнение способов блокировки доступа к Office 365</span><span class="sxs-lookup"><span data-stu-id="a07d1-103">Compare ways to block access to Office 365</span></span>

<span data-ttu-id="a07d1-p101">Когда сотрудник покидает организацию (по собственному желанию или нет), необходимо заблокировать его доступ к Office 365. Это можно сделать несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="a07d1-p101">When an employee leaves your organization, on good terms or bad, you need to block their access to Office 365. Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a07d1-106">**Способ блокировки доступа**</span><span class="sxs-lookup"><span data-stu-id="a07d1-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="a07d1-107">**Определение**</span><span class="sxs-lookup"><span data-stu-id="a07d1-107">**Definition**</span></span> <br/> |<span data-ttu-id="a07d1-108">**Рекомендации**</span><span class="sxs-lookup"><span data-stu-id="a07d1-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="a07d1-109">Блокировка входа</span><span class="sxs-lookup"><span data-stu-id="a07d1-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="a07d1-p102">Один из способов блокировки доступа пользователя к Office 365 заключается в изменении его состояния на **Вход заблокирован**. Это не позволит ему входить в Office 365 с компьютеров и мобильных устройств, хотя он по-прежнему сможет просматривать ранее скачанные или синхронизированные сообщения электронной почты и документы. Если вы используете службу Blackberry Enterprise, вы также можете отключить доступ в ней.  </span><span class="sxs-lookup"><span data-stu-id="a07d1-p102">One way to block a user from accessing Office 365 is to change their sign-in status to **Sign-in blocked**. This prevents them from signing into Office 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents. If you're using Blackberry Enterprise Service, you can disable their access there as well.  </span></span><br/> |<span data-ttu-id="a07d1-113">Используйте этот способ, когда сотрудник планирует покинуть организацию или уйти в долгосрочный отпуск.</span><span class="sxs-lookup"><span data-stu-id="a07d1-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="a07d1-114">Сбросить пароль пользователя</span><span class="sxs-lookup"><span data-stu-id="a07d1-114">Reset user password</span></span>  <br/> |<span data-ttu-id="a07d1-p103">Другим способом предотвращения доступа пользователя к Office 365 является сброс его пароля. Это не позволит ему входить в Office 365, используя свою учетную запись, хотя он по-прежнему сможет просматривать ранее скачанные или синхронизированные сообщения электронной почты и документы. Вы сможете войти в учетную запись пользователя и задать пароль, удобный вам.</span><span class="sxs-lookup"><span data-stu-id="a07d1-p103">Another way to prevent a user from accessing Office 365 is to reset their password. This prevents them from using their account though they can still view previously downloaded or synced email and documents. You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="a07d1-118">Используйте этот способ, когда сотрудник внезапно покидает организацию и вы беспокоитесь о безопасности бизнес-данных.</span><span class="sxs-lookup"><span data-stu-id="a07d1-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="a07d1-119">Удаление всех назначенных лицензий</span><span class="sxs-lookup"><span data-stu-id="a07d1-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="a07d1-120">Кроме того, можно удалить все лицензии на Office 365, назначенные пользователю.</span><span class="sxs-lookup"><span data-stu-id="a07d1-120">Another option is to remove any Office 365 licenses assigned to the user.</span></span> <span data-ttu-id="a07d1-121">Это предотвратит использование приложений и служб, таких как набор Office, приложений Office для Интернета, Yammer и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a07d1-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="a07d1-122">Пользователь по-прежнему сможет входить в свою учетную запись, но не использовать эти службы.</span><span class="sxs-lookup"><span data-stu-id="a07d1-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="a07d1-123">Этот способ можно применять, если вы считаете, что пользователю больше не нужен доступ к определенным возможностям Office 365.</span><span class="sxs-lookup"><span data-stu-id="a07d1-123">Use when you feel this user no longer needs access to specific features in Office 365.</span></span>  <br/> <br> <span data-ttu-id="a07d1-124">**Важно!** При удалении лицензии почтовый ящик пользователя будет удален в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="a07d1-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="a07d1-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a07d1-125">Related articles</span></span>

[<span data-ttu-id="a07d1-126">Блокирование доступа сотрудника к данным Office 365</span><span class="sxs-lookup"><span data-stu-id="a07d1-126">Offboard a user from Office 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="a07d1-127">Сброс пароля пользователя в Office 365</span><span class="sxs-lookup"><span data-stu-id="a07d1-127">Reset a user's password in Office 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="a07d1-128">Назначение лицензий пользователям в Office 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a07d1-128">Assign licenses to users in Office 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="a07d1-129">Удаление лицензий пользователей в Office 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a07d1-129">Remove licenses from users in Office 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

