---
title: Восстановление пользователя
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Узнайте, как восстановить удаленные учетные записи пользователей и все связанные данные.
ms.openlocfilehash: b7d98c1f49f8252ea9fdda2d863b5b77ac5bea9d
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291071"
---
# <a name="restore-a-user"></a><span data-ttu-id="10c27-103">Восстановление пользователя</span><span class="sxs-lookup"><span data-stu-id="10c27-103">Restore a user</span></span>
   
<span data-ttu-id="10c27-p101">Если вы восстановите учетную запись пользователя в течение 30 дней после ее удаления, будут восстановлены сама учетная запись и все связанные с ней данные. Пользователь сможет войти с той же рабочей или учебной учетной записью. Его почтовый ящик будет полностью восстановлен. Если вам нужно узнать, сколько времени осталось до момента, когда определенную учетную запись уже невозможно будет восстановить, [свяжитесь с нами](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="10c27-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../../business-video/get-help-support.md).</span></span>
  
<span data-ttu-id="10c27-108">Вот несколько советов, которые вам помогут.</span><span class="sxs-lookup"><span data-stu-id="10c27-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="10c27-109">Убедитесь, что лицензии доступны для назначения учетной записи.</span><span class="sxs-lookup"><span data-stu-id="10c27-109">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="10c27-110">Если в вашей организации используется служба Active Directory, см. инструкции по восстановлению учетной записи пользователя в статье [Устранение неполадок с удаленными учетными записями пользователей в Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="10c27-110">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="10c27-111">Восстановление одной или нескольких учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="10c27-111">Restore one or more user accounts</span></span>

<span data-ttu-id="10c27-112">Вы должны быть администратором Microsoft 365 или администратором управления пользователями для этих действий.</span><span class="sxs-lookup"><span data-stu-id="10c27-112">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 

1. <span data-ttu-id="10c27-113">В центре администрирования перейдите на страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Удаленные пользователи.</a></span><span class="sxs-lookup"><span data-stu-id="10c27-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="10c27-114">На странице **Удаленные пользователи** выберите имена пользователей, которых необходимо восстановить, а затем выберите **Восстановление.**</span><span class="sxs-lookup"><span data-stu-id="10c27-114">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
3. <span data-ttu-id="10c27-115">Следуйте подсказкам, чтобы установить пароль, а затем выберите **Восстановление**.</span><span class="sxs-lookup"><span data-stu-id="10c27-115">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="10c27-116">Если пользователь успешно восстановлен, выберите **Отправить электронную почту и закрыть**.</span><span class="sxs-lookup"><span data-stu-id="10c27-116">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="10c27-117">Если вы столкнулись с конфликтом имен или конфликтом адресов прокси, см. ниже инструкции по восстановлению этих учетных записей.</span><span class="sxs-lookup"><span data-stu-id="10c27-117">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="10c27-118">После восстановления пользователя убедитесь, что вы уведомите его об изменениях пароля и выполните их действия.</span><span class="sxs-lookup"><span data-stu-id="10c27-118">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="10c27-119">Восстановление пользователя с конфликтующим именем</span><span class="sxs-lookup"><span data-stu-id="10c27-119">Restore a user that has a user name conflict</span></span>

<span data-ttu-id="10c27-120">Конфликт имен пользователей возникает в том случае, если после удаления учетной записи пользователя создается новая учетная запись с таким же именем (для того же самого пользователя или другого пользователя с тем же именем), а затем предпринимается попытка восстановить удаленную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="10c27-120">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="10c27-p103">Чтобы устранить эту проблему, замените активную учетную запись пользователя восстанавливаемой или назначьте восстанавливаемой учетной записи другое имя пользователя, чтобы не было двух учетных записей с одинаковым именем пользователя. Вот как это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="10c27-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>

1. <span data-ttu-id="10c27-124">В центре администрирования перейдите на страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Удаленные пользователи.</a></span><span class="sxs-lookup"><span data-stu-id="10c27-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>
  
2. <span data-ttu-id="10c27-125">На странице **Удаленные пользователи** выберите имена пользователей, которые необходимо восстановить, а затем выберите **Восстановление.**</span><span class="sxs-lookup"><span data-stu-id="10c27-125">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="10c27-p104">Если не удалось восстановить двух или более пользователей, появится соответствующее сообщение об ошибке. Просмотрите журнал, чтобы выяснить, какие пользователи не были восстановлены, а затем восстановите их учетные записи по одной за раз.</span><span class="sxs-lookup"><span data-stu-id="10c27-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="10c27-128">Следуйте подсказкам, чтобы установить пароль и выбрать **Восстановление**.</span><span class="sxs-lookup"><span data-stu-id="10c27-128">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="10c27-p105">Появится всплывающее сообщение о проблеме при восстановлении учетной записи. Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="10c27-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="10c27-p106">Отмените восстановление и переименуйте активного пользователя. После этого попытайтесь выполнить восстановление снова.</span><span class="sxs-lookup"><span data-stu-id="10c27-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="10c27-133">Or, введите новый основной адрес электронной почты для пользователя и выберите **Восстановление**.</span><span class="sxs-lookup"><span data-stu-id="10c27-133">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="10c27-134">Просмотрите результаты и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="10c27-134">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="10c27-135">Восстановление пользователя с конфликтом прокси-адресов</span><span class="sxs-lookup"><span data-stu-id="10c27-135">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="10c27-p107">Конфликт прокси-адресов возникает в том случае, если после удаления учетной записи пользователя, содержащей прокси-адрес, тот же самый прокси-адрес назначается другой учетной записи, а затем предпринимается попытка восстановить удаленную учетную запись. Чтобы устранить эту проблему, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="10c27-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="10c27-138">Для этого [в Microsoft 365](about-admin-roles.md) должны быть разрешения администратора.</span><span class="sxs-lookup"><span data-stu-id="10c27-138">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 

1. <span data-ttu-id="10c27-139">В центре администрирования перейдите на страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Удаленные пользователи.</a></span><span class="sxs-lookup"><span data-stu-id="10c27-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="10c27-140">На странице **Удаленные пользователи** выберите пользователя, которого нужно восстановить, и щелкните ссылку **Восстановить**.</span><span class="sxs-lookup"><span data-stu-id="10c27-140">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="10c27-141">На странице **Восстановление** следуйте инструкциям, чтобы установить пароль и выбрать **Восстановление**.</span><span class="sxs-lookup"><span data-stu-id="10c27-141">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="10c27-142">Для восстанавливаемого пользователя будут автоматически удалены все конфликтующие прокси-адреса.</span><span class="sxs-lookup"><span data-stu-id="10c27-142">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="10c27-143">Просмотрите результаты и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="10c27-143">Review the results, and then select **Close**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="10c27-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="10c27-144">Related articles</span></span>

[<span data-ttu-id="10c27-145">Удаление пользователей</span><span class="sxs-lookup"><span data-stu-id="10c27-145">Delete a user</span></span>](delete-a-user.md)
