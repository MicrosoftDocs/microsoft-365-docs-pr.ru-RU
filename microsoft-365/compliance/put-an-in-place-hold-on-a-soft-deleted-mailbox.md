---
title: Назначение удержания на месте для обратимо удаленного почтового ящика в Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как создать запрос удержания на месте для обратимо удаленного почтового ящика, чтобы сделать последний неактивным и сохранить его содержимое.
ms.openlocfilehash: 4dcd6539519675094da9a05c7701b9f8511ce9a1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818868"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Назначение удержания на месте для обратимо удаленного почтового ящика в Exchange Online

Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.

> [!IMPORTANT]
> Так как мы будем хранить содержимое почтового ящика разными способами, мы сообщаем выбытие на месте в центре администрирования Exchange. Начиная с 1 июля, 2020 вы не сможете создавать новые удержания на месте в Exchange Online. Но вы по-прежнему можете управлять удержаниями на месте в центре администрирования Exchange или с помощью командлета **Set-MailboxSearch** в Exchange Online PowerShell. Тем не менее, начиная с 1 октября 2020, вы не сможете управлять удержаниями на месте. Их можно удалить только в центре администрирования Exchange или с помощью командлета **Remove – MailboxSearch** . Для получения дополнительных сведений о прекращении удержания на месте, ознакомьтесь со статьей [выбытие средств прежних версий электронных данных](legacy-ediscovery-retirement.md).
  
You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox. An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. После неактивного почтового ящика можно выполнить поиск в почтовом ящике, используя обнаружение электронных данных на месте в Exchange Online, поиск контента в центре безопасности & соответствия требованиям или в центре обнаружения электронных данных в SharePoint Online. 
  
> [!NOTE]
> In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive. 
  
## <a name="requirements-for-in-place-holds"></a>Требования к удержаниям на месте

- You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online. 

- Сведения о том, как с помощью Оболочка Windows PowerShell подключаться к Exchange Online, см. в статье [Подключение к PowerShell для Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).

- Выполните указанную ниже команду, чтобы отобразить удостоверения обратимо удаленных почтовых ящиков в организации. 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Дополнительные сведения о неактивных почтовых ящиках можно найти [в статье Обзор неактивных почтовых ящиков в Office 365](inactive-mailboxes-in-office-365.md).

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Назначение удержания на месте для обратимо удаленного почтового ящика, чтобы сделать последний неактивным

Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).
  
1. Создайте переменную, содержащую свойства обратимо удаленного почтового ящика.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address. 
  
2. Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Через пару минут запустите одну из указанных ниже команд, чтобы убедиться в неактивности этого обратимо удаленного почтового ящика.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    Еще вариант:
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Дополнительные сведения

After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:
  
- [Изменение срока хранения неактивного почтового ящика](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Возврат неактивного почтового ящика](recover-an-inactive-mailbox.md)

- [Восстановление неактивного почтового ящика](restore-an-inactive-mailbox.md)

- [Удаление неактивного почтового ящика](delete-an-inactive-mailbox.md) (путем удаления удержания)
