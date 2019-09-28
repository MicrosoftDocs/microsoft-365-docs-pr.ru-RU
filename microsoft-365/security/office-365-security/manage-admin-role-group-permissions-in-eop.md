---
title: Управление разрешениями группы ролей администраторов в EOP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Администраторы могут научиться назначать и удалять разрешения в центре администрирования Exchange в Exchange Online Protection.
ms.openlocfilehash: 9b82836b5f9f28c3055e540890771def28382d2b
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "37306133"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="4a868-103">Управление разрешениями группы ролей администраторов в EOP</span><span class="sxs-lookup"><span data-stu-id="4a868-103">Manage admin role group permissions in EOP</span></span>

<span data-ttu-id="4a868-p101">В Microsoft Exchange Online Protection (EOP) с помощью Центра администрирования Exchange можно назначать пользователя членом одной или нескольких групп ролей, чтобы предоставлять ему права на выполнение определенных задач администрирования. С помощью Центра администрирования Exchange можно также удалять пользователя из одной или нескольких групп ролей.</span><span class="sxs-lookup"><span data-stu-id="4a868-p101">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4a868-106">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="4a868-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4a868-107">Предполагаемое время для завершения: 5–10 минут.</span><span class="sxs-lookup"><span data-stu-id="4a868-107">Estimated time to complete: 5-10 minutes</span></span>

- <span data-ttu-id="4a868-108">Чтобы открыть центр администрирования Exchange, ознакомьтесь со статьей [центр администрирования Exchange в Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4a868-108">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="4a868-p102">Для выполнения этих процедур необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в статье Пункт "Пользователи, контакты и группы ролей" в разделе [Разрешения на функции в службе EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4a868-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="4a868-111">Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4a868-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="4a868-112">Возникли проблемы?</span><span class="sxs-lookup"><span data-stu-id="4a868-112">Having problems?</span></span> <span data-ttu-id="4a868-113">Обратитесь за помощью к форуму [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="4a868-113">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="4a868-114">Использование Центра администрирования Exchange для добавления членов в группы ролей администратора</span><span class="sxs-lookup"><span data-stu-id="4a868-114">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="4a868-115">В центре администрирования Exchange откройте раздел \*\*\*\* \> **роли администратора**разрешений, щелкните группу ролей, в которую нужно добавить пользователя, а затем щелкните **изменить** ![значок](../media/ITPro-EAC-EditIcon.gif)редактирования.</span><span class="sxs-lookup"><span data-stu-id="4a868-115">In the EAC, go to **Permissions** \> **Admin roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="4a868-116">В разделе члены щелкните **Добавить** ![значок](../media/ITPro-EAC-AddIcon.gif)добавить.</span><span class="sxs-lookup"><span data-stu-id="4a868-116">Under Members, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="4a868-117">Откроется окно "Выбор членов".</span><span class="sxs-lookup"><span data-stu-id="4a868-117">The Select Members window will appear.</span></span>

3. <span data-ttu-id="4a868-118">Выполните поиск одного или нескольких пользователей, которых нужно добавить, или выберите их из списка.</span><span class="sxs-lookup"><span data-stu-id="4a868-118">Search for the user or users that you wish to add, or select them from the list.</span></span>

4. <span data-ttu-id="4a868-p105">Выбрав одного или нескольких пользователей, которых нужно добавить, нажмите кнопку **Добавить**, а затем  **ОК**. Окно "Выбор членов" закроется.</span><span class="sxs-lookup"><span data-stu-id="4a868-p105">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>

5. <span data-ttu-id="4a868-p106">Вы увидите, что пользователь добавлен в область **Члены**. Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4a868-p106">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4a868-123">После добавления или удаления членов группы ролей данным пользователям необходимо выйти из системы, а затем снова войти в нее, чтобы изменить административные права.</span><span class="sxs-lookup"><span data-stu-id="4a868-123">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="4a868-124">Использование Центра администрирования Exchange для удаления членов из группы ролей администратора</span><span class="sxs-lookup"><span data-stu-id="4a868-124">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="4a868-125">В центре администрирования Exchange откройте раздел \*\*\*\* \> **роли администратора**разрешений, выберите группу ролей, из которой требуется удалить пользователя или пользователей, а затем нажмите кнопку **изменить** ![значок](../media/ITPro-EAC-EditIcon.gif)редактирования.</span><span class="sxs-lookup"><span data-stu-id="4a868-125">In the EAC, go to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="4a868-126">В разделе Члены выберите пользователя или пользователей, которых нужно удалить, и нажмите кнопку **Удалить** ![значок](../media/ITPro-EAC-RemoveIcon.gif)удаления.</span><span class="sxs-lookup"><span data-stu-id="4a868-126">Under Members, select the user or users that you want to remove and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="4a868-p107">Нажмите кнопку **Сохранить**, чтобы сохранить изменение группы ролей и вернуться на страницу **Роли администратора**. Чтобы проверить, удален ли пользователь из группы ролей администратора, убедитесь, что он больше не отображается в разделе "Члены" в области сведений для выбранной группы ролей.</span><span class="sxs-lookup"><span data-stu-id="4a868-p107">Click **Save** to save the change to the role group and return to the **Admin Roles** page. To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4a868-129">После добавления или удаления членов группы ролей данным пользователям необходимо выйти из системы, а затем снова войти в нее, чтобы изменить административные права.</span><span class="sxs-lookup"><span data-stu-id="4a868-129">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="4a868-130">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4a868-130">For more information</span></span>

[<span data-ttu-id="4a868-131">Разрешения на функции в службе EOP</span><span class="sxs-lookup"><span data-stu-id="4a868-131">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
