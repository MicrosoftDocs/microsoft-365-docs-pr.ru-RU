---
title: Назначение удержания на месте для обратимо удаленного почтового ящика в Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: Узнайте, как создать запрос удержания на месте для обратимо удаленного почтового ящика, чтобы сделать последний неактивным и сохранить его содержимое. После этого вы сможете использовать средства обнаружения электронных данных для поиска в неактивном почтовом ящике.
ms.openlocfilehash: 64ee6d2c9887158939a87b9657b607bc9f323cec
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558486"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="1ff26-104">Назначение удержания на месте для обратимо удаленного почтового ящика в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1ff26-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="1ff26-p102">Узнайте, как создать запрос удержания на месте для обратимо удаленного почтового ящика, чтобы сделать последний неактивным и сохранить его содержимое. После этого вы сможете использовать средства обнаружения электронных данных для поиска в неактивном почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="1ff26-p102">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ff26-107">Так как мы будем хранить содержимое почтового ящика разными способами, мы сообщаем выбытие на месте в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="1ff26-107">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="1ff26-108">Начиная с 1 апреля, 2020 вы не сможете создавать новые удержания на месте в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1ff26-108">Starting April 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="1ff26-109">Но вы по-прежнему можете управлять удержаниями на месте в центре администрирования Exchange или с помощью командлета **Set-MailboxSearch** в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ff26-109">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="1ff26-110">Однако, начиная с 1 июля 2020, вы не сможете управлять удержаниями на месте.</span><span class="sxs-lookup"><span data-stu-id="1ff26-110">However, starting July 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="1ff26-111">Их можно удалить только в центре администрирования Exchange или с помощью командлета **Remove – MailboxSearch** .</span><span class="sxs-lookup"><span data-stu-id="1ff26-111">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="1ff26-112">Для получения дополнительных сведений о прекращении удержания на месте, ознакомьтесь со статьей [выбытие средств прежних версий электронных данных](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="1ff26-112">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="1ff26-113">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span><span class="sxs-lookup"><span data-stu-id="1ff26-113">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="1ff26-114">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span><span class="sxs-lookup"><span data-stu-id="1ff26-114">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="1ff26-115">What can you do?</span><span class="sxs-lookup"><span data-stu-id="1ff26-115">What can you do?</span></span> <span data-ttu-id="1ff26-116">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="1ff26-116">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="1ff26-117">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="1ff26-117">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="1ff26-118">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span><span class="sxs-lookup"><span data-stu-id="1ff26-118">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="1ff26-119">После неактивного почтового ящика можно выполнить поиск в почтовом ящике, используя обнаружение электронных данных на месте в Exchange Online, поиск контента в центре безопасности & соответствия требованиям или в центре обнаружения электронных данных в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1ff26-119">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1ff26-p105">В Exchange Online обратимо удаленный почтовый ящик  почтовый ящик, который был удален, но может быть восстановлен в течение определенного срока хранения (в Exchange Online он составляет 30 дней). Это значит, что такой почтовый ящик можно восстановить или сделать неактивным в течение 30 дней после удаления. По истечении этого периода обратимо удаленный почтовый ящик помечается для окончательного удаления, и в этом случае его уже невозможно восстановить или сделать неактивным.</span><span class="sxs-lookup"><span data-stu-id="1ff26-p105">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="1ff26-124">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="1ff26-124">Before you begin</span></span>

- <span data-ttu-id="1ff26-p106">Примените командлет **New-MailboxSearch** в Оболочка Windows PowerShell, чтобы назначить удержание на месте для обратимо удаленного почтового ящика. В SharePoint Online вы не можете использовать Центр администрирования Exchange (EAC) или центр обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="1ff26-p106">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="1ff26-127">Сведения о том, как с помощью Оболочка Windows PowerShell подключаться к Exchange Online, см. в статье [Подключение к PowerShell для Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="1ff26-127">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="1ff26-128">Выполните указанную ниже команду, чтобы отобразить удостоверения обратимо удаленных почтовых ящиков в организации.</span><span class="sxs-lookup"><span data-stu-id="1ff26-128">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="1ff26-129">Дополнительные сведения о неактивных почтовых ящиках можно найти [в статье Обзор неактивных почтовых ящиков в Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1ff26-129">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="1ff26-130">Назначение удержания на месте для обратимо удаленного почтового ящика, чтобы сделать последний неактивным</span><span class="sxs-lookup"><span data-stu-id="1ff26-130">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="1ff26-p107">С помощью командлета **New-MailboxSearch** сделайте обратимо удаленный почтовый ящик неактивным. Дополнительные сведения см. в статье [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ff26-p107">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="1ff26-133">Создайте переменную, содержащую свойства обратимо удаленного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="1ff26-133">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="1ff26-p108">В указанной выше команде используйте значение свойства **DistinguishedName** или **ExchangeGuid** для определения обратимо удаленного почтового ящика. Эти свойства уникальны для каждого почтового ящика в организации, тогда как у активного и обратимо удаленного почтовых ящиков может быть один и тот же основной SMTP-адрес.</span><span class="sxs-lookup"><span data-stu-id="1ff26-p108">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="1ff26-p109">Создайте запрос удержания на месте и назначьте его для обратимо удаленного почтового ящика. В этом примере не указан период удержания. Это означает, что элементы будут храниться в течение неограниченного срока или до тех пор, пока для неактивного почтового ящика не будет отменено удержание.</span><span class="sxs-lookup"><span data-stu-id="1ff26-p109">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="1ff26-p110">Кроме того, вы можете указать длительность удержания при создании запроса удержания на месте. В этом примере элементы в неактивном почтовом ящике удерживаются около 7 лет.</span><span class="sxs-lookup"><span data-stu-id="1ff26-p110">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="1ff26-141">Через пару минут запустите одну из указанных ниже команд, чтобы убедиться в неактивности этого обратимо удаленного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="1ff26-141">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="1ff26-142">Еще вариант:</span><span class="sxs-lookup"><span data-stu-id="1ff26-142">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="1ff26-143">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="1ff26-143">More information</span></span>

<span data-ttu-id="1ff26-p111">Сделав обратимо удаленный почтовый ящик неактивным, вы сможете управлять им несколькими способами. Дополнительные сведения см. в таких статьях:</span><span class="sxs-lookup"><span data-stu-id="1ff26-p111">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="1ff26-146">Изменение срока хранения неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="1ff26-146">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="1ff26-147">Возврат неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="1ff26-147">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="1ff26-148">Восстановление неактивного почтового ящика</span><span class="sxs-lookup"><span data-stu-id="1ff26-148">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="1ff26-149">[Удаление неактивного почтового ящика](delete-an-inactive-mailbox.md) (путем удаления удержания)</span><span class="sxs-lookup"><span data-stu-id="1ff26-149">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
