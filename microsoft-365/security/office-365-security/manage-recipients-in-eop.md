---
title: Управление получателями в EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
description: Microsoft Exchange Online Protection (EOP) предлагает несколько способов управления получателями электронной почты. Как администратор вы можете выполнять определенные задачи управления в центре администрирования Exchange или с помощью удаленной оболочки Windows PowerShell, а также проверять другие задачи управления, выполняемые в центре администрирования Microsoft 365.
ms.openlocfilehash: b5d1efa0fb54b97f226f25375fb747e5373a36cd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635344"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="f23d0-104">Управление получателями в EOP</span><span class="sxs-lookup"><span data-stu-id="f23d0-104">Manage recipients in EOP</span></span>

<span data-ttu-id="f23d0-105">Microsoft Exchange Online Protection (EOP) предлагает несколько способов управления получателями электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f23d0-105">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="f23d0-106">Как администратор вы можете выполнять определенные задачи управления в центре администрирования Exchange или с помощью удаленной оболочки Windows PowerShell, а также проверять другие задачи управления, выполняемые в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f23d0-106">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="f23d0-107">EOP поддерживает приведенные ниже типы получателей.</span><span class="sxs-lookup"><span data-stu-id="f23d0-107">EOP supports the following types of recipients:</span></span>

- <span data-ttu-id="f23d0-108">**Почтовые пользователи**: почтовые пользователи — это получатели в управляемых доменах EOP.</span><span class="sxs-lookup"><span data-stu-id="f23d0-108">**Mail Users**: Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="f23d0-109">Эти получатели имеют учетные данные для входа в организацию, но у них есть внешние адреса электронной почты, что означает, что их почтовые ящики получателей находятся за пределами облачной организации.</span><span class="sxs-lookup"><span data-stu-id="f23d0-109">These recipients have logon credentials in your organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span>

  <span data-ttu-id="f23d0-110">Вы можете добавлять почтовых пользователей, чтобы они могли получать почту, а также создавать правила для определенных пользователей (также называемые правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="f23d0-110">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="f23d0-111">Вы также можете назначать роли пользователям почты в Организации; Пользователи с правами группы ролей управления могут получать доступ к центру администрирования Exchange и выполнять определенные задачи управления.</span><span class="sxs-lookup"><span data-stu-id="f23d0-111">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="f23d0-112">Чтобы узнать больше о ролях пользователей и о том, как назначать роли пользователей в EOP, обратитесь к разделу [Управление разрешениями группы ролей администраторов в EOP](manage-admin-role-group-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f23d0-112">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>

  <span data-ttu-id="f23d0-113">Дополнительные сведения об управлении почтовыми пользователями в EOP см. в разделе [Управление почтовыми пользователями в EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f23d0-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

- <span data-ttu-id="f23d0-114">**Группы**: почтовые пользователи можно объединять в группы рассылки или группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f23d0-114">**Groups**: Mail users can be grouped together into distribution groups or security groups.</span></span>

<span data-ttu-id="f23d0-115">Дополнительные сведения об управлении группами в EOP см. в разделе [Управление группами в EOP](manage-groups-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f23d0-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
