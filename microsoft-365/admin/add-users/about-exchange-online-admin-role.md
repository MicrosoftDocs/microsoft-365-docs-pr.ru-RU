---
title: Роль администратора Exchange Online
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
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
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: 'Администраторы Exchange online управляют электронной почтой и почтовыми ящиками организации. Например, они восстанавливают удаленные элементы в почтовом ящике пользователя. '
ms.openlocfilehash: 4dc1f435571650ae4a805198782c3c24a92024fb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197653"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="e112c-104">Роль администратора Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e112c-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="e112c-105">Чтобы помочь администрированию Microsoft 365, можно назначить пользователям разрешения на управление электронной почтой и почтовыми ящиками организации из центра [администрирования Exchange.](/exchange/exchange-admin-center) [](assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="e112c-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](/exchange/exchange-admin-center).</span></span> <span data-ttu-id="e112c-106">Для этого нужно назначить им роль администратора Exchange.</span><span class="sxs-lookup"><span data-stu-id="e112c-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="e112c-107">**Совет.** При назначении кого-либо роли администратора Exchange также назначьте их роли администратора службы.</span><span class="sxs-lookup"><span data-stu-id="e112c-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="e112c-108">Таким образом они могут видеть важные сведения в центре администрирования Microsoft 365, такие как состояние службы Exchange Online, а также уведомления об изменении и выпуске.</span><span class="sxs-lookup"><span data-stu-id="e112c-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="e112c-109">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="e112c-109">Before you begin</span></span>

<span data-ttu-id="e112c-110">Ниже описаны некоторые основные задачи, которые пользователи могут выполнять, если им назначена роль администратора Exchange.</span><span class="sxs-lookup"><span data-stu-id="e112c-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="e112c-111">Восстановление элементов, удаленных из почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="e112c-111">Recover deleted items in a user mailbox - Admin Help</span></span>](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- <span data-ttu-id="e112c-112">[Настройка политики архивации и удаления](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)почтовых ящиков в организации.</span><span class="sxs-lookup"><span data-stu-id="e112c-112">[Set up an archive and deletion policy for mailboxes in your organization](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>

- <span data-ttu-id="e112c-113">Настройка функций почтового ящика, например политики общего доступа к нему, которая определяет, как пользователи могут делиться данными календаря и контактов с другими людьми за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e112c-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="e112c-114">Настройка[делегатов "Отправить как"](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)и["Отправить](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)от имени" для чьего-либо почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="e112c-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="e112c-115">Например, руководителю может потребоваться, чтобы его помощник имел возможность отправлять почту от его имени.</span><span class="sxs-lookup"><span data-stu-id="e112c-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="e112c-116">[Создайте общий почтовый ящик,](../email/create-a-shared-mailbox.md) чтобы группа людей могли отслеживать и отправлять сообщения электронной почты с общего адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e112c-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="e112c-117">[Защита от нежелательной почты и](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) фильтры вредоносных программ для организации.</span><span class="sxs-lookup"><span data-stu-id="e112c-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="e112c-118">Управление группами Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e112c-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="e112c-119">Группы ролей Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e112c-119">Exchange Online role groups</span></span>

<span data-ttu-id="e112c-p105">Если вы работаете в крупной организации, администратору Exchange может потребоваться назначить пользователям группы ролей Exchange. Когда администратор добавляет пользователя в группу ролей, этот пользователь получает разрешения на выполнение определенных бизнес-функций, характерных для данной группы.</span><span class="sxs-lookup"><span data-stu-id="e112c-p105">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups. When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="e112c-p106">Например, администратор Exchange может назначить пользователю группу ролей "Управление обнаружением", чтобы он мог искать в почтовых ящиках данные, которые соответствуют определенным критериям. Дополнительные сведения см. в статьях [Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo) и [Управление группами ролей](/exchange/manage-role-groups-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="e112c-p106">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria. To learn more, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="e112c-124">Узнайте о других ролях администратора</span><span class="sxs-lookup"><span data-stu-id="e112c-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="e112c-125">О ролях администратора Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e112c-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="e112c-126">О роли администратора SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e112c-126">About the SharePoint Online admin role</span></span>](/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="e112c-127">Роль администратора Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e112c-127">About the Skype for Business admin role</span></span>](/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="e112c-128">Использование роли администратора Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e112c-128">Use Microsoft Teams admin role</span></span>](/MicrosoftTeams/using-admin-roles)